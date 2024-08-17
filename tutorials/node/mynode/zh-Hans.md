---
name: 我的节点
description: 设置您的比特币MyNode
---

![image](assets/0.webp)

https://mynodebtc.com/

运行比特币和闪电网络节点最简单、最强大的方式！我们结合了最佳的开源软件与我们的界面、管理和支持，使您可以轻松、私密且安全地使用比特币和闪电网络。

## 节点设置类型

有各种节点设置。MyNode非常出色。它附带许多应用程序，如果您支付高级版本费用，可以获得更多应用程序。否则，自己下载所有这些应用程序将非常繁琐。正如您将看到的，MyNode使其变得相当容易。

另一个类似的选择是RaspiBlitz。GUI界面不那么友好，且应用程序与MyNode附带的应用程序大量重叠，但RaspiBlitz是免费的开源软件（FOSS），而MyNode则不完全是。另一个区别是MyNode在Docker容器中运行。我发现Docker令人生畏且难以排错。只有在遇到错误或bug时，这才是问题。开发者为高级用户提供帮助，也有Telegram聊天群组。

RaspiBlitz只是在Linux上安装了多个程序，没有使用Docker。如果需要，可以轻松将外置硬盘连接到另一台安装了比特币核心的Linux机器上，然后继续使用。

另一个选项是仅在操作系统上安装比特币核心和一个Electrum服务器版本（有几种）。我有Linux（树莓派）、Mac和Windows的指南。

## 购物清单

- 树莓派4，4Gb内存或8Gb（4Gb已足够）

- 官方树莓派电源（非常重要！不要购买通用品，认真）

- 树莓派的外壳。FLIRC外壳非常棒。整个外壳是散热器，不需要风扇，风扇可能会产生噪音

- 16 Gb microSD卡（你需要一张，但几张会更方便）

- 一个内存卡读卡器（大多数电脑没有microSD卡槽）。

- 外置SSD 1Tb硬盘。
  注意：SSD至关重要。即使便宜，也不要使用便携式外置硬盘

- 以太网线（连接到您的家用路由器）

- 你不需要显示器

## 下载MyNode镜像

导航至MyNode网站链接

![image](assets/1.webp)

点击<立即下载>

下载树莓派4版本：

![image](assets/2.webp)

这是一个大文件：

![image](assets/3.webp)

下载SHA 256哈希值

![image](assets/4.webp)

在Mac或Linux上打开终端，或者在Windows上打开命令提示符。输入：

```bash
shasum -a 256 DOWNLOADEDFILENAME # <--- Mac/Linux
certUtil -hashfile DOWNLOADEDFILENAME SHA256 # <--- Windows
```

计算机思考大约20秒。然后，检查输出的哈希文件是否与上一步从网站下载的文件匹配。如果完全相同，您可以继续。
刷写SD卡

## 下载并安装Balena Etcher。链接

我无法找到这个的数字签名。如果您知道如何操作，请告诉我，我将更新这篇文章。

Etcher的使用非常直观。插入您的micro SD卡并将树莓派软件（.img文件）刷写到SD卡上。

![image](assets/5.webp)
![image](assets/6.webp)
一旦完成，驱动器将不再可读。您可能会从操作系统收到一个错误，驱动器应该会从桌面上消失。拔出卡片。

## 设置树莓派并插入SD卡

部件（未显示外壳）：

![image](assets/12.webp)
![image](assets/13.webp)

连接以太网线和硬盘USB连接器（暂时不要连接电源）。避免连接到中间的蓝色USB端口。它们是USB 3。MyNode建议您使用USB 2端口，即使驱动器可能支持USB 3。

![image](assets/14.webp)

微型SD卡放在这里：

![image](assets/15.webp)

最后，连接电源：

![image](assets/16.webp)

## 找到树莓派的IP地址

使用MyNode，您永远不需要显示器。然而，您确实需要在家庭网络上的另一台计算机。如果您的树莓派没有通过以太网连接，并且您想依赖WiFi，找到IP需要高级计算机技能。对不起，无法帮助您。您需要一个以太网连接。（问题来自于需要访问显示器和操作系统以连接到WiFi并输入密码）。

检查您的路由器，列出所有已连接设备的所有IP。

我在浏览器中输入了192.168.0.1（我的路由器附带的说明），登录后，能够看到一个设备“MyNode”和IP 192.168.0.18。请注意，这些IP地址在互联网上不是公开可见的（它们首先通过路由器），它们只是家庭网络上设备的标识符。

找到IP至关重要。

> 更新：您可以在Mac或Linux机器上使用终端，通过命令“arp -a”找到家庭网络上所有通过以太网连接的设备的IP地址。输出的格式可能不如路由器显示的那么美观，但所有您需要的信息都在那里。如果不明显哪个是树莓派，进行尝试和错误。

## 通过SSH登录树莓派

您有选项通过SSH命令远程登录设备，但这不是必需的（如果是RaspiBlitz Node则需要）。无论如何，我会向您展示如何操作，因为这非常方便。

打开Mac或Linux计算机（对于Windows，下载putty，一个SSH工具）并输入：

```bash
ssh admin@192.168.0.18
```

使用您自己的IP地址。MyNode设备的用户名默认为“admin”。密码默认为“bolt”。

如果您之前使用过您的树莓派并更换了微型SD卡，您将收到此错误：

![image](assets/17.webp)

您需要做的是导航到“known_hosts”文件所在的位置并删除它。这样做是安全的。错误消息会向您显示路径。对我来说，它是/Users/MyUserName/.ssh/

不要忘记ssh前的“.”，这表示它是一个隐藏目录。

然后再次尝试ssh命令。

这次您会看到此输出：

![image](assets/18.webp)

您删除的文件已被删除，您正在添加一个新的指纹。输入yes并按<enter>。

您将被要求输入密码。密码是“bolt”。
您现在已经获得了对MyNode Pi的终端访问权限，无需显示器，可以确认一切都顺利加载。
![image](assets/19.webp)

## 通过网络浏览器访问

打开浏览器。这需要是您家庭网络中的一台电脑，您不能从外部做这个操作。有方法，但很难。我还没有测试过。

在浏览器地址窗口中输入IP地址。会发生这样的情况：

![image](assets/20.webp)

输入密码“bolt” - 稍后更改它。

然后会发生这样的情况：

![image](assets/21.webp)

选择格式化驱动器

![image](assets/22.webp)

现在我们等待。

在某个时刻，系统会询问您是否想输入您的产品密钥，或者使用免费的“社区版” — 我将展示高级版。如果您负担得起，我确实推荐购买高级版本，它非常值得。

![image](assets/23.webp)

然后您会看到下载的区块进度。这需要几天时间：

![image](assets/24.webp)

如果您需要关闭机器，这是安全的。进入设置，找到关闭机器的按钮。不要直接拔掉电源线，这可能会损坏安装或硬盘。

确保，早期，进入“设置”并禁用quicksync。它将从头开始初始区块下载。

![image](assets/25.webp)

我想继续创建指南，所以这里是我之前准备的另一个MyNode。当区块链同步，且几个“应用”已被启用并同步时，页面看起来是这样的：

![image](assets/26.webp)

请注意，Electrum服务器也需要同步，因此一旦比特币区块链同步，点击按钮开始该过程 - 需要一两天。一旦您选择启用，其他所有东西在几分钟内就能启用。您可以点击东西并探索。您不会破坏任何东西。如果出现故障（这发生在我身上，但我认为是因为我用了便宜的部件），您将不得不重新刷写并重新开始下载。我对MyNode的问题是，如果您需要“重新刷写”，您最终需要从头开始区块链同步。有技术方法可以解决这个问题，但不容易。

如果您还想尝试另一个节点，比如RaspiBlitz，您需要一个额外的SSD外置硬盘，以及另一张micro SD卡来刷写。否则，设备相同，您只是不能同时运行MyNode和RaspiBlitz，显然。如果您想这样做，是时候购买另一个树莓派了。

现在您已经有了一个运行中的节点，使用它，不要让它闲置着对您无用。跟随我的文章（和视频）了解如何将您的Electrum桌面钱包连接到Electrum服务器和比特币核心这里。