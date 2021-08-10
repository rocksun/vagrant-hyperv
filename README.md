# Vagrant 与 Hyper-V 自动配置示例项目

## 安装配置 Hyper-V 和 Vagrant

可以参考[这篇文章](https://github.com/rocksun/cloudlog/blob/main/tools/create-vm-with-hyperv-and-vagrant.md)。

## 运行

安装配置好之后，在根目录执行 ```vagrant up``` 即可。

第一次执行时选择 “1) Default Switch”，然后即可通过 ssh 客户端，使用 ..vagrant\machines\default\hyperv 下的 private_key 访问 192.168.0.2 。

## 参考

* [Enable Hyper-V and Install Vagrant on Windows 10](https://computingforgeeks.com/enable-hyper-v-and-install-vagrant-in-windows/)
* [HyperV - Static Ip with Vagrant](https://superuser.com/questions/1354658/hyperv-static-ip-with-vagrant)