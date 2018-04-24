### Pthreads API

```c
#include <pthread.h>
/* 所有的pthreads api的返回值约定：若成功则返回0，否则返回错误编号 */

/* pthread thread APIs */
int pthread_equal(pthread_t lhs, pthread_t rhs);

pthread_t pthread_self();

int pthread_create(pthread_t *restrict tidp, const pthread_attr_t *restrict attr, void *(start_rtn)(void *), void *restrict arg);

void pthread_exit(void *rval_ptr);

/* 等同于process-control-functions中的wait系列函数 */
int pthread_join(pthread_t thread, void **rval_ptr);

int pthread_cancel(pthread_t tid);

void pthread_cleanup_push(void (*rtn)(void *), void *arg);
void pthread_cleanup_pop(int execute);

/* 线程脱离, 不必调用pthread_join来等待线程结束 */
int pthread_detach(pthread_t tid);

/* pthread mutex APIs */
int pthread_mutex_init(pthread_mutex_t *restrict mutex, const pthread_mutexattr_t *restrict attr);
int pthread_mutex_destroy(pthread_mutex_t *mutex);

int pthread_mutex_lock(pthread_mutex_t *mutex);
int pthread_mutex_trylock(pthread_mutex_t *mutex);
int pthread_mutex_unlock(pthread_mutex_t *mutex);

/* pthread condtion APIs */
int pthread_cond_init(pthread_cond_t *cond, const pthread_condattr_t *attr);
int pthread_cond_destroy(pthread_cond_t *cond);

int pthread_cond_signal(pthread_cond_t *cond);
int pthread_cond_broadcast(pthread_cond_t *cond);
int pthread_cond_wait(pthread_cond_t *cond, pthread_mutex_t *mutex);
```

