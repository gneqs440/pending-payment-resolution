# 搬瓦工付款后多久开通：即时开通的真实等待时间，Pending 卡单的原因与处理步骤，附全套餐价格对比

先给结论：绝大多数情况下，搬瓦工（BandwagonHost）付款成功后几分钟内就会自动开通，官方对外的说法就是 Instant setup（即时开通）。你在付款后泡杯茶回来，大概率已经能在邮箱和 KiwiVM 面板里看到服务器信息了。真正会让人等上几个小时甚至一天的，主要是风控人工审核和 PayPal 放款延迟这两种情况，后面会分别说清楚怎么判断、怎么处理。

## 正常流程：付款后会发生什么

搬瓦工的开通是系统自动完成的，不需要人工介入。付款成功后，系统会做三件事：生成订单的 Paid 状态、自动部署 VPS 实例、发送开通邮件。整套流程通常在 1 到 5 分钟内走完，多数中文教程站的观察也一致：最慢一般不超过半小时。

开通邮件里会包含 IP 地址、SSH 端口和 root 密码这些关键信息。如果邮件没到，还有两个地方可以查：

- 登录搬瓦工客户后台，进入 Services → My Services，能看到已开通的 VPS 和对应的 KiwiVM Control Panel 按钮；
- 后台有 Email History 功能，保存了系统发出的所有邮件记录，邮件被邮箱拦截时可以直接在这里找回内容。

顺便提醒一句，KiwiVM 面板密码和账号登录密码、SSH 密码是三回事，别搞混。

## 付款后显示 Pending 或 Unpaid，一般是这几种情况

搬瓦工在绝大多数情况下即时开通，但确实存在付款后订单一直显示 Unpaid、服务状态停在 Pending 的案例。把这些案例放在一起看，原因基本可以归为三类。

### 触发风控的常用操作

搬瓦工有一套风控系统，某些操作会触发人工审核，开通就会被挂起。中文交流群里流传的几个真实案例都挺典型：有人在 PayPal 上用争议（dispute）方式退过款，之后再用同一个 PayPal 付款就被风控了；有人付款时挂着代理、注册 IP 和常用 IP 对不上，直接被判为可疑订单；还有人填了生成的假美国地址，后来尝试修改账户信息时触发风控，连名下已有的 VPS 都被一并暂停。

共同点很明显：不是搬瓦工系统慢，而是账户或订单触发了审核机制。

### PayPal 新账户的放款延迟

用新注册的 PayPal 账户付款时，PayPal 端显示扣款了，但钱实际还没到搬瓦工手里。这是 PayPal 对新账户的风控放款机制，一般 24 小时内自动完成，之后服务随之开通。这种情况联系搬瓦工客服也没用，只能等。

### 首次购买的人工审核

部分用户首次购买时会遇到人工审核，时间会比自动开通长一些，但一般也在 24 小时内处理完。

## 卡单了怎么处理：按这个顺序来

1. **确认钱真的扣了。** 打开支付宝或 PayPal 账单，确认扣款成功、金额正确。这一步能排除“付款其实没成功”的乌龙情况。
2. **等。** 如果扣款正常，订单显示 Unpaid，先等几个小时。PayPal 放款延迟和一般性人工审核大多在 24 小时内自行解决。
3. **超过 24 小时再开工单。** 登录后台，进 Support → Tickets → Open New Ticket，说明情况并附上支付宝或 PayPal 的订单号（银联付款就提供对应扣款凭证）。搬瓦工客服工作时间是工作日，因为时差，北京时间早上七点左右处理较多，通常 24 小时内会有回复。
4. **检查邮箱和账户信息。** 如果当初注册时用了代理或填了明显虚假的地址，建议之后别再反复改动账户信息，这类操作本身就容易再次触发风控。

还有一种情况要单独说：如果订单最终被判定为欺诈（fraud），搬瓦工会直接退款，钱会原路退回，这种情况下不用纠结开通问题，换个干净的支付环境和真实信息重新下单即可。

## 顺带把优惠码用了

下单时在结算页面可以填优惠码。2026 年多个中文站整理的信息显示，目前可尝试的循环折扣码是 NODESEEK2026 和 BWHCGLUKKB，都是全场通用、新购续费都能用的 6.77% 循环折扣。搬瓦工的优惠码时效变化比较快，大促（双十一、黑五）期间折扣力度更大，付款前不妨先搜一下最新可用码再结账。如果准备下单，可以👉 [前往搬瓦工查看套餐并完成付款](https://bit.ly/BandwagonHost)，开通后记得第一时间去后台确认订单状态。

## 下单前顺便把套餐选好

既然在等开通，不如先把套餐选对。搬瓦工目前常规在售的产品线分几个系列：入门的 KVM 常规套餐、主力的 CN2 GIA-E、企业级的 E-Commerce SLA PLAN，以及日本大阪、日本东京、中国香港三条 CN2 GIA 高端线路，另有面向中东的迪拜方案。下面是当前官网及各中文站汇总的在售套餐全表。

> 价格均为美元，库存和结算金额以购买页实时显示为准。限量版套餐（THE PLAN、HK85、MINICHICKEN 等）只在补货时短暂上架，不列入常规表格。

| 系列 | 配置（CPU/内存/SSD/月流量/带宽） | 价格 | 计费周期 | 购买链接 |
| --- | --- | --- | --- | --- |
| KVM/CN2 入门 | 1核/1GB/20GB/1TB/1Gbps | $49.99 | 年付 | [ 查看此套餐并购买](https://bandwagonhost.com/aff.php?aff=79616&pid=57) |
| KVM/CN2 入门 | 1核/2GB/40GB/2TB/1Gbps | $99.99 | 年付 | [ 查看此套餐并购买](https://bandwagonhost.com/aff.php?aff=79616&pid=58) |
| KVM 常规 | 3核/2GB/40GB/2TB/1Gbps | $52.99 | 半年付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| KVM 常规 | 4核/4GB/80GB/3TB/1Gbps | $19.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| KVM 常规 | 5核/8GB/160GB/4TB/1Gbps | $39.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| KVM 常规 | 6核/16GB/320GB/5TB/1Gbps | $79.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| KVM 常规 | 7核/24GB/480GB/6TB/1Gbps | $119.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| CN2 GIA-E | 2核/1GB/20GB/1TB/2.5Gbps | $49.99（年付$169.99） | 季付/年付 | [ 前往购买页](https://bandwagonhost.com/aff.php?aff=79616&pid=87) |
| CN2 GIA-E | 3核/2GB/40GB/2TB/2.5Gbps | $89.99（年付$299.99） | 季付/年付 | [ 前往购买页](https://bandwagonhost.com/aff.php?aff=79616&pid=88) |
| CN2 GIA-E | 4核/4GB/80GB/3TB/2.5Gbps | $56.99 | 月付 | [ 前往购买页](https://bit.ly/BandwagonHost) |
| CN2 GIA-E | 6核/8GB/160GB/5TB/5Gbps | $86.99 | 月付 | [ 前往购买页](https://bit.ly/BandwagonHost) |
| CN2 GIA-E | 8核/16GB/320GB/8TB/5Gbps | $159.99 | 月付 | [ 前往购买页](https://bit.ly/BandwagonHost) |
| CN2 GIA-E | 10核/32GB/640GB/10TB/10Gbps | $289.99 | 月付 | [ 前往购买页](https://bit.ly/BandwagonHost) |
| CN2 GIA-E | 12核/64GB/1280GB/12TB/10Gbps | $549.99 | 月付 | [ 前往购买页](https://bit.ly/BandwagonHost) |
| CN2 GIA-E | 12核/64GB/1280GB/15TB/10Gbps | $679.00 | 月付 | [ 前往购买页](https://bit.ly/BandwagonHost) |
| CN2 GIA-E | 12核/64GB/1280GB/20TB/10Gbps | $899.00 | 月付 | [ 前往购买页](https://bit.ly/BandwagonHost) |
| CN2 GIA-E | 24核/64GB/1280GB/12TB/10Gbps | $749.99 | 月付 | [ 前往购买页](https://bit.ly/BandwagonHost) |
| E-Commerce SLA | 2核独享/1GB/20GB/1TB/2.5Gbps | $65.89 | 季付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| E-Commerce SLA | 3核独享/2GB/40GB/2TB/2.5Gbps | $116.99 | 季付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| E-Commerce SLA | 4核独享/4GB/80GB/3TB/2.5Gbps | $69.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| E-Commerce SLA | 6核独享/8GB/160GB/5TB/5Gbps | $109.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| E-Commerce SLA | 8核独享/16GB/320GB/8TB/5Gbps | $199.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| E-Commerce SLA | 10核独享/32GB/640GB/10TB/10Gbps | $369.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| E-Commerce SLA | 12核独享/64GB/1280GB/12TB/10Gbps | $699.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| E-Commerce SLA | 12核独享/64GB/1280GB/15TB/10Gbps | $879.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| E-Commerce SLA | 12核独享/64GB/1280GB/20TB/10Gbps | $1159.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 日本大阪 CN2 GIA | 2核/2GB/40GB/0.5TB/1.5Gbps | $49.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 日本大阪 CN2 GIA | 4核/4GB/80GB/1TB/1.5Gbps | $86.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 日本大阪 CN2 GIA | 6核/8GB/160GB/2TB/1.5Gbps | $165.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 日本大阪 CN2 GIA | 8核/16GB/320GB/4TB/1.5Gbps | $329.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 日本大阪 CN2 GIA | 10核/32GB/640GB/6TB/1.5Gbps | $549.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 日本大阪 CN2 GIA | 12核/64GB/1280GB/8TB/1.5Gbps | $1059.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 日本东京 CN2 GIA | 2核/2GB/40GB/0.5TB/1.2Gbps | $89.99（年付$899.99） | 月付/年付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 日本东京 CN2 GIA | 4核/4GB/80GB/1TB/1.2Gbps | $155.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 日本东京 CN2 GIA | 6核/8GB/160GB/2TB/1.2Gbps | $299.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 日本东京 CN2 GIA | 8核/16GB/320GB/4TB/1.2Gbps | $589.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 日本东京 CN2 GIA | 10核/32GB/640GB/6TB/1.2Gbps | $989.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 日本东京 CN2 GIA | 12核/64GB/1280GB/8TB/1.2Gbps | $1889.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 香港 CN2 GIA | 2核/2GB/40GB/0.5TB/1Gbps | $89.99（年付$899.99） | 月付/年付 | [ 前往购买页](https://bandwagonhost.com/aff.php?aff=79616&pid=95) |
| 香港 CN2 GIA | 4核/4GB/80GB/1TB/1Gbps | $155.99 | 月付 | [ 前往购买页](https://bandwagonhost.com/aff.php?aff=79616&pid=96) |
| 香港 CN2 GIA | 6核/8GB/160GB/2TB/1Gbps | $299.99 | 月付 | [ 前往购买页](https://bit.ly/BandwagonHost) |
| 香港 CN2 GIA | 8核/16GB/320GB/4TB/1Gbps | $589.99 | 月付 | [ 前往购买页](https://bit.ly/BandwagonHost) |
| 香港 CN2 GIA | 10核/32GB/640GB/6TB/1Gbps | $989.99 | 月付 | [ 前往购买页](https://bit.ly/BandwagonHost) |
| 香港 CN2 GIA | 12核/64GB/1280GB/8TB/1Gbps | $1889.99 | 月付 | [ 前往购买页](https://bit.ly/BandwagonHost) |
| 迪拜 | 2核/1GB/20GB/0.5TB/1Gbps | $19.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 迪拜 | 3核/2GB/40GB/1TB/1Gbps | $32.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 迪拜 | 4核/4GB/80GB/2TB/1Gbps | $56.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 迪拜 | 6核/8GB/160GB/3TB/1Gbps | $86.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 迪拜 | 8核/16GB/320GB/4TB/1Gbps | $159.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 迪拜 | 10核/32GB/640GB/5TB/1Gbps | $289.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |
| 迪拜 | 12核/64GB/1280GB/6TB/1Gbps | $549.99 | 月付 | [ 查看当前价格](https://bit.ly/BandwagonHost) |

几个简单的选择逻辑：预算有限、主要跑海外业务或练手，KVM 常规套餐 $49.99/年 就够用；主力建站、对国内访问速度有要求，CN2 GIA-E 是多数人的选择，季付 $49.99 起步，试错成本不高；预算充足、对延迟有硬需求，再考虑香港和东京，这两个系列月付 $89.99 起步，价格不便宜，但线路确实顶级。拿不准的话，可以先👉 [对比各套餐的当前价格和库存](https://bit.ly/BandwagonHost) 再决定。

付款方式方面，目前下单支持支付宝、PayPal、信用卡等（银联和微信的状态有过反复，以结账页面实际显示为准）。注意一点：账户余额充值（Add Funds）只支持 PayPal 和信用卡，不走支付宝渠道。

## 续费和退款的时间点

和开通时间同样值得记住的还有两个时间节点。一是续费：系统会在到期前 7 天自动生成续费账单，你有 7 天时间付款，逾期未付服务会被暂停。二是退款：搬瓦工官方政策提供 30 天退款保障，如果机器用下来不符合预期，在 30 天内可以申请退款，这对第一次买的人来说相当于一个低成本的试用窗口。

最后补一句实用建议：付款时用真实信息、稳定的网络环境，别挂代理注册，也别填生成的假地址——这不仅能避免开头说的 Pending 卡单，也能省掉后续跟客服解释的时间。正常情况下，从付款到登录上自己的 VPS，就是几分钟的事。
