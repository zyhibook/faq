# 以后台服务形式启动Akaxin

对于Linux系统，在退出终端后，系统会杀掉前台进程。如果你希望服务一直运行，需要用以下命令启动服务。

```
$ nohup java -jar openzaly-server.jar &
```

然后通过输入 `exit` 退出终端。如此，服务便会在系统中一直运行下去了。
