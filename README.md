# iplcforward
iplc 转发教程 iptables 脚本版


脚本来自逗比根据地，本教程较为简洁(jian lou)只有关键步骤，可以到原帖阅读更详细的教程。转发应部署在入口设备上，出口设备正常部署入 shadowsocks/v2ray 等代理工具。
准备工作

脚本使用 iptables 进行转发，可能会与其他使用 iptables 的软件冲突，其中最常见的是防火墙 firewalld 和 ufw。建议在使用脚本前卸载它们并重启 vps。

    卸载 firewalld 和 ufw

    debian/ubuntu

        sudo apt remove firewalld ufw

    centos

        sudo yum remove firewalld ufw

    重启

        sudo reboot

    下载和运行脚本
    下载脚本

        wget -N --no-check-certificate https://www.qexw.cf/tutorial/iptables-pf.sh

    运行脚本，必须以 root 权限运行

        sudo bash iptables-pf.sh

    按照脚本提示操作即可，脚本包含开机自动生效。

踩坑指南

在 qexw 的深圳端，添加转发时填写的第二个 ip（脚本要求填写公网网卡 ip），经测试必须填 10.10 开头的 ip 才能正常工作。
