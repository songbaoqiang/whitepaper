中本聪（Satoshi Nakamoto）的比特币开创了一个全新的领域，点对点的分布式网络架构激发了人们对于去中心化世界的无穷想象。之后，维塔利克·布特林（Vitalik Buterin）通过智能合约将去中心化的应用场景从单一的电子货币扩展到了通用应用领域。从此，人们就开始试图用“去中心化技术”来重构和解决当今时代的生活、商业、社会甚至国家存在的各种问题，人们的想象力扩展到了几乎无所不在的程度。

这些充满颠覆性的概念与项目背后的技术或者思想通常都被人们含糊的称为“区块链”。然而时至今日，区块链技术为我们带来的主要是加密货币的热潮与投机疯狂。除了部分大企业谨慎的试探之外，区块链技术并没有介入我们的生活。目前的区块链项目大多如在沙中筑城，困难重重，人们因此普遍认为区块链技术名过其实，或者任重道远。

据我们纳什团队长时间的研究与试验得出如下结论：区块链类技术能够真正落地并大规模应用的关键是最大范围共通且扎实可靠的信任根基。只有构建在这个信任根基之上的区块链服务才有可能承载类似现有互联网规模的应用场景，眼前行业聚焦的交易量、共识速度等具体指标重要但并不关键。

目前所有区块链项目的根本缺陷都是假设上链数据的可信。但实际上区块链系统最大的不确定性来自人。人们为了利益在数据获取源头甚至计算执行过程中篡改数据是无法监督的。
在工程角度上，目前区块链技术的单一全局共识机制本身约束了系统所能承载的容量天花板。首先是单一的统一共识算法决定了极少数出块节点成了容量的瓶颈，其次是现有的区块链项目依赖算法信任，这种全局信任的成本无法满足大量小成本标的的交易场景。

那么这个最大范围的信任根基是否存在？它究竟是什么？

我们回过头来看比特币，比特币最神奇地方在于只依靠非对称加密、工作量证明、P2P网络以及链式块存储技术解决了点对点之间的信任传递问题。比特币并没有重新发明或者定义某种算法就建立了一个最小化的信任根基，那么在比特币之后涌现的一系列技术是否存在可能将这个信任根放大，大到足以承载整个互联网的可能？也就是说，我们能够在互连网层级的规模上解决去中心化的信任，同时必须适应业务场景的无限复杂性。

目前看来，任何单一的技术都无法达到这个目标。如果要达到这个目标，就需要一系列的技术集合。当代计算机都遵循冯·诺伊曼结构，将整个系统分为输入输出（IO）、计算（运算器与控制器）、存储三个部分。多数区块链技术通过点对点分布式存储、非对称加密以及链式块存储满足存储可信，但IO与计算都只限定了特定类型来解决可信问题。单纯的算法无法解决任意数据类型的IO以及计算也是多数区块链存在的问题。要实现最大范围的信任根，我们需要解决IO、计算以及存储的可信问题。同时，实体（人、组织、甚至AI等）作为最重要的IO源之一，同样需要纳入信任范围。

![John_von_Neumann_arch](assets/John_von_Neumann_zh.jpg)

因此我们提出了信任空间的概念：信任空间被认为是网络空间的一个子集，网络空间当中的信息如果具有确定性，那么我们认为信息是在信任空间当中。信任空间的信息确定性我们定义如下：产生信息的主体(who)和环境（where）可以追溯到确定的信任根，产生信息的时间(when)确定，信息的内容(what)唯一。因此结合冯·诺伊曼结构之后，要实现信任空间至少需要满足以下四个条件：
1. 身份自主可信
2. 计算过程可信
3. 数据存储可信
4. 输入输出可信

身份自主可信是解决数字世界参与者的权利边界问题，计算过程可信是解决协作和交易过程的确定性预期，数据存储可信是解决数据的不可篡改，输入输出可信则是定义信任空间的边界。其中基于1与3可以确保用户对任何类型的数据声明其对数据拥有的权利，并可以将这种权利选择性的分享、出售或让渡给其它人。而2与4则确保用户在使用数据时不侵犯他人的权利。

身份自主可信需要满足以下条件：
1. 用户自主选择信任根
2. 用户自主控制主密钥对的生成与保存
3. 用户使用密钥需要有对应的认证手段，例如密钥、指纹甚至活体识别
4. 用户可以通过匿名与信任根的零知识证明保护自身隐私

作为身份自主可信的实现方案之一，分布式身份（Decentralized ID）目前已经作为草案提交了W3C（参见[这里](https://w3c-ccg.github.io/did-spec/)）同时基于DID也已经有了大量实现，例如　Indy、Sidetree等。作为分布式身份的主流标准之一，用户可以选择自主选择身份信任根（例如身份证、护照、学校提供的在读证明、公司提供的工作证明等），可以选择匿名模式，从而避免个人数据完全被厂商控制或者隐私泄漏的风险。当用户使用匿名模式，而应用场景要求用户证明自己的某个属性时（例如年龄、工作单位、所在地等），DID规范可以帮助人们通过身份信任根实现零知识属性证明。

我们允许用户通过DID实名或者匿名的声明他对数据的所有权、商用权、二次加工权等一系列权利，同时将内容与权利声明加密存储在点对点的分布式文件系统当中，例如IPFS。文件加密确保只有拥有密钥的用户可以读取对应内容，点对点分布式文件系统则保证内容能够以安全且快速的方式在网络上传播，提供给更多用户使用。点对点的分布式存储缺乏时间属性，这在更为严肃一些的场合会造成不可预知的问题，因此对于重要数据（例如对全网公开的数据、声明以及合约等）需要保存一份存证在一个由全局投票选拔出来的若干节点组成的联盟链当中。对于非重要数据（例如私有的数据、声明及合约等），我们认为无需进行全局共识。因此，数据存储可信需要满足以下条件：
1. 数据归属权明确不可篡改
2. 数据内容不可泄漏
3. 存储自身具备鲁棒性
4. 私有内容传播受限
5. 公开内容的声明需要全局存证

如果只是权利声明而没有实质性的保护，那么和现有互联网对于权利保护只能走法律途径没有不同，无法把维权成本大幅降低。要做到实质性的保护，我们需要将硬件级的信任根植入到操作系统当中，实现计算过程可信。信任空间当中的可信执行环境应当满足以下条件：
1. 应用运行在独立且尽可能隔离的环境当中
2. 操作系统限制应用程序对文件与网络的访问和修改，保护所有者对于内容的权利声明边界
3. 操作系统应当假设自身所处的环境是不可信的，防止修改、窥探、侧信道等攻击行为
4. 操作系统以及应用软件的来源只有两种：一是信任空间内私人共享，二是通过安全检测及审核之后的公开镜像库
5. 硬件应能够提供关键软件（包括但不限于密钥计算、权限控制、智能合约等）运行在保护范围当中的证明，并能够进行远程验证

幸运的是，现代CPU普遍提供了可信执行环境，例如[Intel SGX](https://software.intel.com/en-us/sgx)、[AMD SEV](https://developer.amd.com/sev/)、[ARM Trustzone](https://developer.arm.com/ip-products/security-ip/trustzone)等，并提供了高度隔离的虚拟化容器，例如[Kata-containers](https://katacontainers.io)，可以让应用同时享受容器化的便利以及虚拟化的安全。在可信执行环境中，我们可以安全的存储和计算用户的私钥，并执行用户的内容、声明与合约。通过将操作系统的文件及网络接口逻辑处理放在可信环境中执行，可以让用户对于内容的使用限制在所有者声明范围之内，最大化的保护内容所有者的权益。而操作系统级的接口管理带来一个额外的好处，就是运行在操作系统上的应用几乎无需任何修改及适配就能运行在区块链的环境之中，也就是说，由应用创建的任何数据天生就是链上数据，通过可信DID身份以及可信软硬件环境，链上数据天生就具有可信属性。

这也就意味着现有PC生产力环境输出的任何类型的数字内容，包括代码、程序、照片、CG、音乐、视频等，天生就在信任空间当中。这些多种类的数字内容在输入输出的环节同样应当确保在信任空间当中。信任空间的IO同样需要满足以下条件：
1. 输入终端设备自身需要对产生的内容记录可验证的签名
2. 输入输出过程需要确保内容不被泄漏或者篡改
3. 所有输入输出的具体行为都绑定实体的具体身份（DID）

网络传输环节的解决方案已经非常成熟（TLS/SSL等）。输入输出终端可信的解决方案目前并不多，例如数字版权管理(DRM，Digital rights management)等。但我们将这个视为产业升级的机会，能够通过IoT等更低成本的方式将内容保护真正普惠到每一个创作者。

信任空间中的多样化数字内容，在结合合适的智能合约形式之后，有可能激发新的生产力。现有的智能合约形式都是基于代码的形式，对于开发人员来说学习成本并不高，但是对于其它职业的创作者，如作者、记者、摄像师、导演、绘画师、音乐家、艺术家等如果要参与到合作当中来，重新学习智能合约的开发语言则会导致整个系统门槛太高。为了能让大多数人都能参与进来，智能合约需要以自然语言的形式表达，同时能够无歧义的翻译成多种语言。通过智能合约之间相互引用的特性，用户可以很容易的形成针对特定内容二次开发、代理销售等协作方式。同时数字内容的边际成本为零的特性，有可能让有限的利润进行几乎无限的分配，从而让生产过程中所有的人都能够从中获益。同时，信任空间提供的可追溯属性，让工作量按件、按量、按时等计费方式得以可靠实现，使实时动态的按劳分配有可能成为智能合约的重要属性之一。

为了实现以上的目标，我们将项目的主干部分分为7块：
1. 容器化安全操作系统 Stem Cell OS
2. 安全操作系统权限统一控制程序 Plasma Membrane
3. 灵犀合约语言 Telepathy
5. 用户客户端 Trust Passport
6. 分布式文件系统 DFS
7. 联盟存证链

* 容器化安全操作系统 Stem Cell OS

Stem Cell OS（简称SCOS）是虚拟化容器操作系统的框架，通过X Window窗口系统、QT框架、.Net框架等支持各种窗口类应用，文件、网络与IO系统通过 Plasma Membrane(简称PM) 程序对接到DFS、RamDisk、网络以及外设设备。根据应用程序或者内容方的声明，PM决定那些文件存在用户域，哪些是临时数据无需保存，哪些是用户设置需要下次启动时自动加载；同时规定了可以访问哪些类型的设备、使用什么协议访问什么网站等。SCOS可以运行在运营方提供的服务器，或者满足硬件条件需求的用户本地。从安全角度考虑，SCOS同时只能运行一个应用程序。多个应用程序之间的交互，例如剪贴板，需要由操作系统的容器间通讯来解决；考虑到多开应用程序导致操作系统资源耗用太大的问题，SCOS应当支持最小化裁剪，只保留应用程序需要的功能。同时SCOS出于对硬件环境安全的考虑，要求运行在内存加密（Total Memory Encryption）环境下，以防止通过非易失性内存泄漏，并要求硬件提供已对内存进行硬件级加密的证明以及远程验证方式。因为SCOS运行在容器环境中，而容器默认的rootfs会映射到宿主操作系统的磁盘当中，这样也会造成容器中的内容泄漏，为了避免这种情况，SCOS应当将容器文件操作系统映射在加密后的易失性内存的Ramdisk当中，避免中间过程文件持久化。作为SCOS所在的容器，需要禁止用户通过容器接口将容器内文件拷贝到宿主机之上。在用户退出应用程序时，SCOS应当保证释放容器，清除掉容器文件及对应内存。对于用户状态的保持，应当通过保存用户状态到用户域文件的方式处理。SCOS的启动应当置于TPM的管理之下，通过TPM模块度量容器与操作系统加载的正确性。

* 安全操作系统权限统一控制程序 Plasma Membrane

PM的功能程序的功能就如同它的名称“细胞膜”一般，选择性的与外界交换物质。PM程序的文件读写部分将会替代VFS当中的ACL，网络控制部分嵌入到内核的network层中，在操作系统的提供的接口之下对内容访问进行管理。为了实现这些功能，PM不可避免的需要保存用户的私钥以便进行加密解密操作，因此PM获取私钥与保存私钥的流程尤为关键。从用户处获取私钥的流程首先要避免单一通道被中间人攻击的可能性，在用户与PM程序建立连接时通常建议首先以二维码之类的方式传递Nonce以及SCOS的公网地址，然后用户客户端根据这些内容开始进行安全密钥交换建立加密通道。在加密通道之后才能开始安全传递密钥。PM与用户通信的私钥，以及用户自身的私钥，都应该加密保存在内存之中，仅当需要计算时解密。同时应当避免直接调用CPU提供的加密指令，以防止Hypervisor通过特殊指令的线索抓取到关键信息。PM需要保证在用户使用应用期间一直运行，如果因为任何原因导致的崩溃，应当触发SCOS立即退出容器。PM将文件存储到IPFS时，应当将文件通过用户的私钥（或者私钥管理下的对称密钥）进行加密，并使用用户私钥、程序私钥、硬件私钥等对内容、应用版本、TPM记录等信息生成数字签名后一起保存。需要注意的是，应用如果需要用户使用记录，应当在用户授权的前提下进行多方签名，同时使用记录应当遵循一定的规范，不允许在记录中泄露用户隐私、内容等记录。同理，应用的网络访问记录也需要被记录，默认情况下只能访问信任空间内的web页面与服务，同时不允许上传用户隐私或者内容信息。对于非信任空间的网络，一般情况下禁止访问。需要特别注意的是，PM在运行时不应当假定本地或者网络时间时可信的，唯一的可信时间应当来自于联盟存证链的区块高度。

* 合约语言 灵犀 Telepathy

Telepathy 作为一种类自然语言的编程语言，可以视为信任空间内一种法律的DSL（Domain-Specific Language），无需实现图灵完备，同时可以自动执行。Telepathy 的组成要素与一般合同并无二致，包括引用、定义、条款三要素。引用包含两种，一种是合约引用，一种是条款引用；合约引用将会直接链接到其它合约，并执行其中的指定条款；而条款引用则是引用合约内部条款，通过条款的共同作用达到目的。定义一般是指定签约方以及合约的操作对象，签约方可以指定（双方或者多方合约）也可以不指定（使用声明）；操作对象包含加密货币、文件、文件内容甚至计数、统计等任何可以通过扩展手段采集的结构化数据。条款则是定义条件判断以及执行内容。Telepathy 应当有专用的编辑器以及运行环境；专用编辑器不但方便用户编写，同时方便用户对合约条款进行演算，判断己方利益以及检查条款冲突；而运行环境则会安全执行合约，同时将所有操作打包为一个交易，只有交易整体成功提交才能最终执行。Telepathy运行在PM当中，通过功能插件与支付插件的接口对外操作，合约一旦生成，外部除了触发合约执行和展示合约内容以外不能改变合约运行内容或条件；功能插件主要是执行采集、计数、统计等功能的外部实现，通常建议以动态链接库的方式与合约集成，功能对于插件的入参与出参类型有严格的限制，同时应当对于任何类型的参数输入都能正常处理，不能轻易终止处理或者崩溃；对于支付插件来说，主要用于对接各种支持点对点支付的电子货币，并负责各类电子货币之间的实时兑换，确保用户购买时支付的资金能够正确的转入到卖方账户中。

* 用户客户端 Trust Passport

Trust Passport （简称TP）主要承担用户私钥存储以及使用验证，控制了用户身份的验证过程，因此是系统中最为关键的环节。TP一般运行在手机或者专用存储设备（冷钱包）当中；用户私钥应当被加密存储在安全区域，同时按照安全等级提供密码、指纹、活体等多种访问密钥时的验证方式。TP除了通过TLS/SSL方式与PM程序进行网络通信以外，同时需要通过网络之外的方式，例如二维码、NFC等方式与PM程序进行验证或者交换信息，以避免单一网络通信方式造成的中间人攻击。用户私钥应当允许用户通过分片导出、手抄等方式将私钥或者助记词通过不可拦截的方式备份到系统外的安全区域中，但应当禁止用户通过拷贝、截屏等易于被窃取的方式保存私钥或助记词。TP同时负责用户身份（DID）的管理，允许用户生成、绑定、切换匿名或者实名的DID，同时设置DID的隐私级别，包括可验证声明是否公开、是否允许第三方验证等内容，当用户在使用特定内容或应用时，PM在请求这些信息的同时，TP必须提供给用户进行明确此类选择的界面以及对应的可选项。

* 分布式文件系统 Decentralized Filesystem

DFS主要承担内容保存及分发的功能，DFS分布在整个平台所有参与者之中，DFS之中分为两种角色，一种是用户节点，用户可以在本地保存自己的内容，以及自己经常访问或希望收藏的内容；另一种是备份/分发节点，负责数字内容的备份与分发；默认情况下若干备份/分发节点组建一个集群，而整个平台当中有若干集群存在，每一个集群都由一个运营方维护，每个用户可以选择至少一个运营方作为自己的备份/分发节点；而备份/分发节点通过为用户内容的服务，根据容量或者流量从用户的内容收入当中收取一定的费用。DFS存储的内容主要包括：用户私有数据、用户公开数据、应用程序日志、公开应用程序镜像库、私有应用程序镜像库、存证数据、合约交易等。运营方可以选择拒绝为某位或者某类用户服务，但是不能在服务期间删除或者丢失用户数据。

* 联盟存证链 Consortium Blockchain of Evidence

CBE主要承担身份、声明、合约与交易的存证以及查询；CBE当中具有写入权限的成员是由社区投票选举出来进行记账，同时也是平台规则的讨论与制定者，代表社区成员发表意见；联盟的最终决议将以全局合约的形式存储在平台当中；考虑到联盟链负载较高，联盟链的共识算法将会采用允许高并发的共识算法，例如PBFT或改进型BFT进行全局共识；共识记账接受全局监督，记账结果记录在DFS当中以便随时查阅。

