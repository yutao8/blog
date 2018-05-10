# ssh REMOTE HOST IDENTIFICATION HAS CHANGED 解决方法

在mac os 下使用 `ssh root@45.76.51.19` 出现下面的错误:

```bash
~ ssh root@45.76.51.19
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
*********************************
you have requested strict checking.
Host key verification failed.
```

解决方法:

进入此目录，删除45.x.x.19的相关rsa的信息即可.

