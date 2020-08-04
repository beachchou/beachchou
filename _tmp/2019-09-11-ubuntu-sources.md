---
---

1. 备份原始文件

        sudo cp /etc/apt/sources.list /etc/apt/sources.list.backup

2. 修改文件并添加国内源

        vi /etc/apt/sources.list

3. 注释原文件内的源并添加如下地址

        #Ubuntu 官方源 
        deb http://archive.ubuntu.com/ubuntu/ gutsy main restricted universe multiverse
        deb http://archive.ubuntu.com/ubuntu/ gutsy-security main restricted universe multiverse
        deb http://archive.ubuntu.com/ubuntu/ gutsy-updates main restricted universe multiverse
        deb http://archive.ubuntu.com/ubuntu/ gutsy-proposed main restricted universe multiverse
        deb http://archive.ubuntu.com/ubuntu/ gutsy-backports main restricted universe multiverse
        deb-src http://archive.ubuntu.com/ubuntu/ gutsy main restricted universe multiverse
        deb-src http://archive.ubuntu.com/ubuntu/ gutsy-security main restricted universe multiverse
        deb-src http://archive.ubuntu.com/ubuntu/ gutsy-updates main restricted universe multiverse
        deb-src http://archive.ubuntu.com/ubuntu/ gutsy-proposed main restricted universe multiverse
        deb-src http://archive.ubuntu.com/ubuntu/ gutsy-backports main restricted universe multiverse

        #或者这些源

        #阿里云
        deb http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse
        deb http://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse
        deb http://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse
        deb http://mirrors.aliyun.com/ubuntu/ trusty-proposed main restricted universe multiverse
        deb http://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse
        deb-src http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse
        deb-src http://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse
        deb-src http://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse
        deb-src http://mirrors.aliyun.com/ubuntu/ trusty-proposed main restricted universe multiverse
        deb-src http://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse

        #网易163
        deb http://mirrors.163.com/ubuntu/ trusty main restricted universe multiverse
        deb http://mirrors.163.com/ubuntu/ trusty-security main restricted universe multiverse
        deb http://mirrors.163.com/ubuntu/ trusty-updates main restricted universe multiverse
        deb http://mirrors.163.com/ubuntu/ trusty-proposed main restricted universe multiverse
        deb http://mirrors.163.com/ubuntu/ trusty-backports main restricted universe multiverse
        deb-src http://mirrors.163.com/ubuntu/ trusty main restricted universe multiverse
        deb-src http://mirrors.163.com/ubuntu/ trusty-security main restricted universe multiverse
        deb-src http://mirrors.163.com/ubuntu/ trusty-updates main restricted universe multiverse
        deb-src http://mirrors.163.com/ubuntu/ trusty-proposed main restricted universe multiverse
        deb-src http://mirrors.163.com/ubuntu/ trusty-backports main restricted universe multiverse

4. 放置非官方源的包不完整，可在为不添加官方源

        deb http://archive.ubuntu.org.cn/ubuntu-cn/ feisty main restricted universe multiverse

5. 更新源

        sudo apt-get update

6. 更新软件

        sudo apt-get dist-upgrade
        sudo apt-get upgrade

    由于包与包之间存在各种依赖关系。upgrade只是简单的更新包，不管这些依赖，它不和添加包，或是删除包。而dist-upgrade可以根据依赖关系的变化，添加包，删除包。upgrade:系统将现有的Package升级,如果有相依性的问题,而此相依性需要安装其它新的Package或影响到其它Package的相依性时,此Package就不会被升级,会保留下来. dist-upgrade:可以聪明的解决相依性的问题,如果有相依性问题,需要安装/移除新的Package,就会试着去安装/移除它. (所以通常这个会被认为是有点风险的升级) 

7. 常见的修复安装命令

        sudo apt-get -f install