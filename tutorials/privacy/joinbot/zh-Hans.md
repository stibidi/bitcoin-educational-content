---
name: JoinBot
description: 理解和使用JoinBot
---

![DALL·E – 红色森林中的武士机器人，3D渲染](assets/cover.webp)

***警告：** 继Samourai Wallet的创始人于4月24日被捕，其服务器被查封后，**JoinBot服务不再可用**。从现在起，无法使用这个工具。然而，您仍然可以执行Stonewall X2，但您需要找到一个合作者并手动交换PSBTs。根据案件的进展，这项服务可能在未来几个月重新启动。*

_我们正在密切关注此案件以及相关工具的发展情况。请放心，一旦有新信息，我们将更新本教程。_

_本教程仅供教育和信息参考之用。我们不支持或鼓励使用这些工具进行犯罪活动。每个用户都有责任遵守其管辖区的法律。_

---

JoinBot是Samourai Wallet套件中的一个新工具，它在著名的比特币钱包软件最新更新0.99.98f中被添加。它允许您轻松进行协作交易以优化您的隐私，无需寻找合作伙伴。

*感谢优秀的Fanis Michalakis提出使用DALL-E为缩略图的想法！*

## 什么是比特币上的协作交易？

比特币基于一个分布式和透明的账本。任何人都能追踪这个电子现金系统用户的交易。为了确保一定程度的隐私，比特币用户可以进行具有特定结构的交易，以增加其解释的合理可疑性。

这个想法不是直接隐藏信息，而是在其他信息中混淆它。这个目标在Coinjoins中得到了应用，Coinjoins是打破比特币上一个硬币的历史并使其追踪变得复杂的交易。为了达到这个结果，交易中必须创建多个相同金额的输入和输出。

输入是比特币交易的输入，输出代表输出。交易消耗其输入以通过改变硬币的支出条件来创建新的输出。这个机制允许比特币在用户之间移动。
我在这篇文章中详细讨论了这个问题：比特币交易机制：UTXO、输入和输出。

在比特币交易中模糊轨迹的一种方式是进行协作交易。顾名思义，它涉及多个用户之间的协议，每个用户在同一交易中作为输入存入一定数量的比特币，并作为输出接收一定数量的比特币。

如前所述，协作交易最著名的结构是Coinjoin。例如，在Coinjoin Whirlpool协议上，交易涉及5个参与者作为输入和输出，每个人都有相同数量的比特币。

![Whirlpool上Coinjoin交易的图解](assets/1.webp)

这笔交易的外部观察者将无法知道哪个输出属于哪个用户作为输入。如果我们以用户#4（紫色）为例，我们可以识别他们的输入UTXO，但我们不会知道5个输出中哪一个实际上是他们的。初始信息没有被隐藏，而是在一组中混淆。
用户能够否认拥有某个特定UTXO作为输出。这种现象被称为“合理可疑性”，它允许在透明的比特币交易中保持机密性。

要了解更多关于Coinjoin的信息，我在这篇长文章中解释了一切：理解和使用比特币上的CoinJoin。
尽管Coinjoin在打破UTXO追踪方面非常有效，但它不适合直接支出。实际上，其结构意味着必须使用预定义金额的输入和相同价值（减去挖矿费）的输出。然而，在比特币上进行的支出交易是隐私的关键时刻，因为它通常会在用户和他们的链上活动之间创建物理链接。因此，使用隐私工具进行支出似乎至关重要。还有其他专为实际支付交易设计的协作交易结构。

## StonewallX2交易

在Samourai Wallet提供的众多支出工具中，有一种是两个用户之间用于支付的协作交易StonewallX2。从外部看，这种交易可能导致几种可能的解释。因此，它为用户提供了合理的否认性，从而保证了隐私。

这种StonewallX2协作交易设置在Samourai Wallet和Sparrow Wallet上都可用。这个工具可以在两个软件之间互操作。

其机制相当简单易懂。以下是它的实际工作方式：

> - 用户想要用比特币进行支付（例如，在商家处）。
> - 他们获取实际支付接收者（商家）的接收地址。
> - 他们构建一个具有多个输入的特定交易：至少有一个属于他们自己，另一个属于外部合作者。
> - 交易将有4个输出，包括2个相同金额的输出：一个用于支付商家的地址，一个作为找零返回给用户，一个与支付金额相同的值返回给合作者，还有一个也返回给合作者。

例如，这里是我进行的一个典型的StonewallX2交易，我支付了50,125 sats。来自我的Samourai钱包的第一个输入是102,588 sats。来自我的合作者钱包的第二个输入是104,255 sats：

![StonewallX2交易图](assets/2.webp)

我们可以观察到4个输出，包括2个用来混淆追踪的相同金额输出：

> - 50,125 sats支付给我支付的实际接收者。
> - 52,306 sats代表我的找零，因此返回到我钱包中的一个地址。
> - 50,125 sats返回给我的合作者。
> - 53,973 sats返回给我的合作者。
>   在操作结束时，合作者将恢复他们的初始余额（减去挖矿费），用户将支付给商家。这给交易增加了大量的熵，打破了支付发送者和接收者之间不可否认的链接。

StonewallX2交易的强大之处在于，它完全反驳了链上分析师使用的一条经验规则：多输入交易中输入的共同所有权。换句话说，在大多数情况下，如果我们观察到一个比特币交易有多个输入，我们可以假设所有这些输入属于同一个人。中本聪在他的白皮书中已经识别出了这个问题对用户隐私的影响：

> "作为一个额外的防火墙，每次交易都可以使用一对新的密钥对，以防止它们被链接到一个共同的所有者。然而，多输入交易不可避免地揭示了它们的输入是由同一个所有者拥有的。"

这是链上分析中用来构建地址群的许多经验规则之一。要了解更多关于这些启发式规则的信息，我推荐阅读Samourai撰写的这一系列四篇文章，它们精彩地介绍了这个主题。
StonewallX2交易的强大之处在于，外部观察者会认为交易的不同输入属于同一所有者。实际上，它们是两个不同的用户在合作。因此，支付分析会被引向一个假目标，用户隐私得以保护。
从外部看，StonewallX2交易无法与Stonewall交易区分开来。它们之间唯一的实际区别是Stonewall不是协作性的。它只使用单一用户的UTXOs。然而，在账户账簿的结构上，Stonewall和StonewallX2是完全相同的。这允许对这种交易结构有更多可能的解释，因为外部观察者无法判断输入是来自同一个人还是两个合作者。

此外，StonewallX2相比于Stowaway类型的PayJoin的优势在于它可以在任何情况下使用。支付的实际接收者不会对交易贡献任何输入。因此，StonewallX2可以用于向任何接受比特币的商家支付，即使商家不使用Samourai或Sparrow。
另一方面，这种交易结构的主要缺点是它需要一个愿意使用他们的比特币参与你的支付的合作者。如果你有愿意在任何情况下帮助你的比特币朋友，这不是问题。然而，如果你不认识任何其他Samourai Wallet用户，或者没有人可以合作，那么你就卡住了。

为了解决这个问题，Samourai团队最近在他们的应用程序中添加了一个新功能：JoinBot。

# 什么是JoinBot？

JoinBot的原理很简单。如果你找不到任何人来进行StonewallX2交易的合作，你可以与JoinBot合作。实际上，你将直接与Samourai Wallet进行协作交易。

这项服务非常方便，特别是对于新手用户，因为它全天候可用。如果你需要进行紧急支付并想进行StonewallX2，你不再需要联系朋友或寻找在线合作者。JoinBot将协助你。

JoinBot的另一个优点是，它提供作为输入的UTXOs专门来自postmix Whirlpool，这提高了你的支付隐私。此外，由于JoinBot始终在线，你应该与具有大量潜在Anonsets的UTXOs合作。

显然，JoinBot有一些应该注意的妥协：

> 就像经典的StonewallX2一样，你的合作者必然知道使用的UTXOs及其目的地。在JoinBot的情况下，Samourai知道这笔交易的细节。这不一定是坏事，但应该记住。
> 为了避免垃圾邮件，Samourai对实际交易金额收取3.5%的服务费，最高限额为0.01 BTC。例如，如果我通过JoinBot发送100 kilosats的真实支付，服务费金额将是3,500 sats。
> 要使用JoinBot，你的钱包中必须至少有两个无关联且可用的UTXOs。
> 在经典的StonewallX2中，挖矿费用由两个合作者平均分担。使用JoinBot，你显然必须支付全部的挖矿费用。
为了使JoinBot交易与经典的StonewallX2或Stonewall交易完全相同，服务费的支付是在一个完全独立的交易中进行的。Samourai最初支付的一半挖矿费用的退款将在这第二笔交易中完成。为了将您的隐私优化到最后，费用结算使用Stowaway（PayJoin）结构化交易完成。

## 如何使用JoinBot？

要执行JoinBot交易，您必须拥有一个Samourai Wallet。您可以在这里下载它，或者从Google Playstore下载。

与Samourai开发的大多数工具不同，Sparrow Wallet尚未宣布实现JoinBot。因此，这个工具仅在Samourai上可用。

在这个视频中逐步发现如何使用JoinBot执行StonewallX2交易：

![如何使用Joinbot](https://youtu.be/80MoMz2Ne5g)

这是我们刚在视频中执行的交易图：

![我与JoinBot进行的StonewallX2交易的图表。](assets/3.webp)

我们可以看到5个输入：

> - 来自Samourai（JoinBot）的3个输入，每个100 kilosats。
> - 来自我的个人钱包的2个输入，分别为3,524 sats和1.8 megasat。

交易的4个输出如下：

> - 1个212,452 sats到我支付的实际接收者。
> - 另一个相同金额返回给Samourai地址。
> - 1个变更也返回给Samourai，为87,302 sats。这代表了他们输入总额（300,000 sats）与混淆输出（212,452 sats）减去挖矿费用的差额。
> - 1个变更返回到我钱包中的另一个地址。它代表了我的输入总额与实际支付之间的差额，减去挖矿费用。

作为提醒，挖矿费用并不代表交易输出。它们仅代表总输入与总输出之间的差额。

## 结论

JoinBot是一个额外的工具，为Samourai用户增加了更多选择和自由。它允许与Samourai直接合作进行协作性StonewallX2交易。这种类型的交易有助于提高用户隐私。

如果您可以与朋友执行经典的StonewallX2，我仍然推荐使用这个工具。然而，如果您遇到困难，无法找到任何合作者进行支付，您知道JoinBot将全天候可用，与您合作。

**外部资源：**
- https://medium.com/oxt-research/understanding-bitcoin-privacy-with-oxt-part-1-4-8177a40a5923
- https://www.pandul.fr/post/comprendre-et-utiliser-le-coinjoin-sur-bitcoin