## Linux下C语言获取毫秒级时间

Linux获取毫秒级的时间，使用的方法是`gettimeofday()`
 
gettimeofday原型: 
```c 
int gettimeofday(struct timeval* tv, struct timezone& tz);
```
```c
struct timeval {
    long tv_sec;           // 秒
    long   tv_usec;        //  微秒 
};
```
```c
struct timezone {
    int tz_minuteswest;    //和greenwich时间差多少分钟
    int  tz_dsttime;
};
```
函数执行成功返回0， 执行失败返回-1.
使用该函数时需要包含头文件: `<sys/time.h>`
