```c
struct pollfd pfd;
pfd.fd = sockfd;
pfd.events = POLLIN | POLLPRI | POLLRDHUP;
pfd.revents = 0;

int nready = poll(&pfd, 1, -1);

/*
 * 当poll()返回时，在Linux下:
 * * 如果对端发送RST, pfd.revents返回为 (POLLIN | POLLRDHUP | POLLERR | POLLHUP)
 * * 如果对端调用shutdown(sockfd, SHUT_WR)或者close(sockfd), 则pfd.revents返回为 (POLLIN | POLLRDHUP)
 */

struct epoll_event event;
event.events = EPOLLIN | EPOLLPRI | EPOLLRDHUP;
event.data.fd = sockfd;

int epfd = epoll_create(0);
epoll_ctl(epfd, EPOLL_CTL_ADD, sockfd, &event);

struct epoll_event revent;
int nready = epoll_wait(epfd, &revent, 1, -1);


close(sockfd)
EPOLLERR

RST
EPOLLRDHUP
EPOLLERR

shutdown(sockfd, SHUT_WR)
EPOLLRDHUP
EPOLLERR


/* 发送RST的方法 */
struct linger lingo;
lingo.l_onoff = 1;
lingo.l_linger = 0;
setsockopt(sockfd, SOL_SOCKET, SO_LINGER, &lingo, sizeof(struct linger));
close(sockfd); /* TCP协议栈代码丢弃套接字发送缓冲区的数据并发送一个RST分节到对端, 然后进入CLOSED状态 */
```

