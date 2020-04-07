对应四篇博文：

- [k8s 监控（一）安装 Prometheus](https://juejin.im/post/5d4ac8e9f265da03e921b463)
- [k8s 监控（二）监控集群组件和 pod](https://juejin.im/post/5d5d32a2f265da03f77e6e22)
- [k8s 监控（三）prometheus-adapter](https://juejin.im/post/5da5c0b7f265da5b894a18d3)
- [k8s 监控（四）监控宿主机](https://juejin.im/post/5e3a52866fb9a07c8b5ba0bf)

目前已经在 k8s 1.17.4 上面运行正常，随着 k8s 和 prometheus 版本的迭代，可能需要调整一些小的参数，但是大方向是不会变的。当然，用到的镜像的版本可能需要修改到最新。

注意，node_exporter 和 telegraf 需要二选一，个人推荐 telegraf。

`prometheus-secret.yml` 用到的三个证书是监控 etcd 用的，这三个文件位于 `/etc/kubernetes/pki/etcd/`，你需要用你的覆盖它，不会操作的看第二篇博文。当然如果你不打算监控 etcd 的话，就无所谓了。