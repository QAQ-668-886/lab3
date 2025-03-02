# Lab3 操作指南

## 一、下载安装文件

1. &zwnj;**下载VirtualBox安装文件**&zwnj;
   - 从官方网站或可信源下载VirtualBox的安装文件。
<div align="center">
  <img src="image/1.png" width="80%" />
  <img src="image/2.png" width="80%" />
</div>

2. &zwnj;**下载Ubuntu 18.04安装文件**&zwnj;
   - 访问清华镜像源：[https://mirrors.tuna.tsinghua.edu.cn/ubuntu-releases/18.04/](https://mirrors.tuna.tsinghua.edu.cn/ubuntu-releases/18.04/)
   - 下载Ubuntu 18.04的安装文件。
<div align="center">
  <img src="image/3.png" width="80%" />
</div>
## 二、安装VirtualBox

- 按照常规软件安装步骤安装VirtualBox。
<div align="center">
  <img src="image/4.png" width="80%" />
  <img src="image/5.png" width="80%" />
</div>
## 三、虚拟机安装

1. &zwnj;**创建虚拟机**&zwnj;
   - 在VirtualBox中创建一个新的虚拟机。
<div align="center">
  <img src="image/6.png" width="80%" />
  <img src="image/7.png" width="80%" />
  <img src="image/8.png" width="80%" />
  <img src="image/9.png" width="80%" />
  <img src="image/10.png" width="80%" />
  <img src="image/11.png" width="80%" />
</div>
2. &zwnj;**配置虚拟机**&zwnj;
   - 点击“设置”->“存储”->“选择虚拟盘”。
   - 选择之前下载的Ubuntu 18.04安装文件。
<div align="center">
  <img src="image/12.png" width="80%" />
</div>
3. &zwnj;**设置加载镜像**&zwnj;
   - 确保虚拟机配置中加载了Ubuntu 18.04的安装镜像。
<div align="center">
  <img src="image/13.png" width="80%" />
</div>
4. &zwnj;**设置网络为NAT模式**&zwnj;
   - 在虚拟机网络设置中，选择NAT模式以确保虚拟机能够访问外部网络。
<div align="center">
  <img src="image/14.png" width="80%" />
</div>
5. &zwnj;**启动虚拟机**&zwnj;
   - 启动创建的虚拟机，开始安装Ubuntu 18.04。
<div align="center">
  <img src="image/15.png" width="80%" />
</div>
## 四、安装Ubuntu 18.04

- 按照以下提示完成Ubuntu 18.04的安装过程。
<div align="center">
  <img src="image/16.png" width="80%" />
  <img src="image/17.png" width="80%" />
</div>
## 五、安装Ubuntu虚拟机A、B、C

- 重复上述虚拟机创建和安装步骤，分别创建并安装三个Ubuntu虚拟机（A、B、C）。
<div align="center">
  <img src="image/18.png" width="80%" />
  <img src="image/19.png" width="80%" />
  <img src="image/20.png" width="80%" />
</div>
## 六、环境配置与网络测试

1. &zwnj;**安装net-tools工具**&zwnj;
   - 在每个虚拟机中运行以下命令安装net-tools工具：
     ```bash
     sudo apt update
     sudo apt install net-tools
     ```
<div align="center">
  <img src="image/21.png" width="80%" />
</div>
2. &zwnj;**查看虚拟机IP地址**&zwnj;
   - 使用`ifconfig`命令查看虚拟机的IP地址。
     - 虚拟机A的IP地址为：10.0.2.5
     - 虚拟机B的IP地址为：10.0.2.4
     - 虚拟机C的IP地址为：10.0.2.6
<div align="center">
  <img src="image/22.png" width="80%" />
  <img src="image/23.png" width="80%" />
  <img src="image/24.png" width="80%" />
</div>
3. &zwnj;**虚拟机A ping 虚拟机B**&zwnj;
   - 在虚拟机A中运行以下命令测试与虚拟机B的连通性：
     ```bash
     ping 10.0.2.4
     ```
   - 确认能够ping通虚拟机B。
<div align="center">
  <img src="image/25.png" width="80%" />
</div>
4. &zwnj;**限制虚拟机B对虚拟机C的访问**&zwnj;
   - 在虚拟机B中运行以下命令使用iptables限制对虚拟机C的访问：
     ```bash
     sudo iptables -A OUTPUT -d 10.0.2.6 -j DROP
     ```
   - 此命令将阻止虚拟机B向虚拟机C发送任何数据包。
<div align="center">
  <img src="image/26.png" width="80%" />
</div>
