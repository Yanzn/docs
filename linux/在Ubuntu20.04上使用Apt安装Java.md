`linux`  
`java`  
`Ubuntu`

---

**安装多个版本的jdk**

```bash
# 安装jdk8
$ sudo apt install openjdk-8-jdk

# 安装jdk11
$ sudo apt install openjdk-11-jdk
```

```bash
# 管理Java
$ sudo update-alternatives --config java

```

---

**通过 `update-alternatives` 命令切换系统默认使用的jdk**

```bash
# 列出所有的jre, 选择并按回车确认
$ sudo update-alternatives --config java

# 列出所有的jdk, 选择并按回车确认
$ sudo update-alternatives --config javac

Output
There are 2 choices for the alternative java (providing /usr/bin/java).

  Selection    Path                                         Priority   Status
------------------------------------------------------------
  0            /usr/lib/jvm/java-11-openjdk-amd64/bin/java   1111      auto mode
* 1            /usr/lib/jvm/java-8-openjdk-amd64/bin/java    1091      manual mode

Press <enter> to keep the current choice[*], or type selection number:

```


---

**设置 `JAVA_HOME` 环境变量**  
有部分程序要求使用 `JAVA_HOME` 环境变量来确定Java安装目录  
命令 ```$ sudo update-alternatives --config java``` 列出了jdk的安装目录  
拷贝地址, 添加到 `/etc/environment`  

``` bash
# 打开nano编辑文件
$ sudo nano /etc/environment 
```

将 ` JAVA_HOME="/usr/lib/jvm/java-11-openjdk-amd64" `添加到文件

``` bash
# load 文件
$ source /etc/environment
```

``` bash
# 确认变量添加成功
$ echo $JAVA_HOME

Output
/usr/lib/jvm/java-11-openjdk-amd64
```
