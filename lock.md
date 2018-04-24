#### How to implement a lock?

##### goals

* basic task: provide mutual exclusion
* fairness
* performance



```c++
int TestAndSet(int* old_ptr, int new) {
  int old = *old_ptr;
  *old_ptr = new;
  return old;
}

int CompareAndSwap(int* ptr, int expected, int new) {
  int actual = *ptr;
  if (actual == expected)
    *ptr = new;
  return actual;
}

char CompareAndSwap(int* ptr, int old, int new) {
  unsigned char ret;
  
  // Note that sete sets a 'byte' not the word
  __asm__ __volatile__ (
    "	lock\n"
    "	cmpxchgl %2,%1\n"
    "	sete %0\n"
    : "=q" (ret), "=m" (*ptr)
    : "=r" (new), "m" (*ptr), "a" (old)
    : "memory"
  );
  return ret;
}
```



```c
/* Lock with queues, test-and-set, yield, and wakeup */

/*
 * park() to put a calling thread to sleep
 * unpark(threadID) to wake a particular thread as designated by threadID
 */
typedef struct __lock_t {
  int flag;
  int guard;
  queue_t *q;
} lock_t;

void lock_init(lock_t* m) {
  m->flag = 0;
  m->guard = 0;
  queue_init(m->q);
}

void lock(lock_t* m) {
  while (TestAndSet(&m->guard, 1) == 1)
    ; /* acquire guard lock by spinning */
  if (m->flag == 0) {
    m->flag = 1; /* lock is acquired */
    m->guard = 0;
  } else {
    queue_add(m->q, gettid()); /* linux-specific api?? */
    m->guard = 0;
    park();
  }
}

void unlock(lock_t* m) {
  while (TestAndSet(&m->guard, 1) == 1)
    ; /* acquire guard lock by spinning */
  if (queue_empty(m->q))
    m->flag = 0; /* let go of lock; no one wants it */
  else
    unpark(queue_remove(m->q)); /* hold lock (for next thread!) */
  
  m->guard = 0;
}
```

