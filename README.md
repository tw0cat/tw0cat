- 👋 Hi, I’m @tw0cat

Hello World!
# 渗透中POC、EXP、Payload与Shellcode的区别

**1. POC、EXP、Payload与Shellcode**

> POC：全称 ' Proof of Concept '，中文 ' 概念验证 ' ，常指一段漏洞证明的代码。
>
> EXP：全称 ' Exploit '，中文 ' 利用 '，指利用系统漏洞进行攻击的动作。
>
> Payload：中文 ' 有效载荷 '，指成功exploit之后，真正在目标系统执行的代码或指令。
>
> Shellcode：简单翻译 ' shell代码 '，是Payload的一种，由于其建立正向/反向shell而得名。

**2. 几点注意**

> POC是用来证明漏洞存在的，EXP是用来利用漏洞的，两者通常不是一类，或者说，PoC通常是无害的，Exp通常是有害的，有了POC，才有EXP。
>
> Payload有很多种，它可以是Shellcode，也可以直接是一段系统命令。同一个Payload可以用于多个漏洞，但每个漏洞都有其自己的EXP，也就是说不存在通用的EXP。
>
> Shellcode也有很多种，包括正向的，反向的，甚至meterpreter。
>
> Shellcode与Shellshcok不是一个，Shellshock特指14年发现的Shellshock漏洞。

**3. Payload模块**

> 在Metasploit Framework 6大模块中有一个Payload模块，在该模块下有Single、Stager、Stages这三种类型，Single是一个all-in-one的Payload，不依赖其他的文件，所以它的体积会比较大，Stager主要用于当目标计算机的内存有限时，可以先传输一个较小的Stager用于建立连接，Stages指利用Stager建立的连接下载后续的Payload。Stager和Stages都有多种类型，适用于不同场景。

**4. 总结**

> 想象自己是一个特工，你的目标是监控一个重要的人，有一天你怀疑目标家里的窗子可能没有关，于是你上前推了推，结果推开了，这是一个POC。之后你回去了，开始准备第二天的渗透计划，第二天你通过同样的漏洞渗透进了它家，仔细查看了所有的重要文件，离开时还安装了一个隐蔽的窃听器，这一天你所做的就是一个EXP，你在他家所做的就是不同的Payload，就把窃听器当作Shellcode吧！





### 3、MSF专业术语讲解

#### 3.1、渗透攻击（exploit）

 渗透攻击是指由攻击者或者渗透测试者利用系统、应用或服务中的安全漏洞，所进行的攻击行为。
​ 流行的攻击技术包括：缓冲区溢出、Web应用程序漏洞攻击，以及利用配置错误等。

#### 3.2、攻击载荷（payload）

 payload字面意思是有效攻击载荷，包含需要在远程主机上运行的恶意代码。

 payload和exploit的区别：

- exploit是传送系统（运载火箭），payload是用来实际做什么事的代码（弹头）

#### 3.3、溢出代码（Shellcode）

 shellcode是在渗透攻击时作为攻击载荷运行的一组机器指令。shellcode通常用汇编语言编写。在大多数情况下，目标系统执行了shellcode这一组指令后，才会提供一个命令行shell或者meterpreter shell，这也是shellcode名称的由来。

#### 3.4、模块（module）

 在MSF中，一个模块是指MSF框架中所使用的一段软件代码组件。例：渗透攻击模块（exploit module），用来发起渗透攻击的软件组件。扫描模块（auxiliary module），用来扫描可以使用的攻击工具或扫描工具。

#### 3.5、监听器（listener）

 监听器是MSF中用来等待网络连接的组件。例：在目标主机被渗透攻击之后，它可能会通过互联网回连到攻击者主机上，而监听器组件在攻击者主机上等待被渗透攻击的主机主动连接，并负责处理这些网络连接。
