# RFP: PB-scale Miner Testing

**Name of Project:** `Large Miner Testing`

**Proposal Category:** `mining`

**Proposers:**  @keren117

**Deadline:**  April 15th, 2020 23:59 PDT

## Project Description(项目描述)

As the Filecoin testnet has reached PB-scale and node implementations are nearing protocol-completeness, we are interested in understanding how Filecoin mining software performs on large scale configurations.

由于Filecoin testnet已经达到PB规模，节点实现接近协议完整性，我们有兴趣了解Filecoin挖掘软件如何在大规模配置上执行。

We are seeking proposals for designing, implementing and running tests of mining and storage hardware at scale if you are running a mining operation in the 5 PB or more range.

如果您正在5 PB或更大范围内运行挖掘操作，我们正在寻求设计、实现和运行大规模挖掘和存储硬件测试的建议。

  <sub>*Proposals can be emailed directly to devgrants@filecoin.org and your operation's details will be kept confidential.*</sub>
  <sub>*建议可以直接发送到devgrants@filecoin.org，您的操作细节将保密。*</sub>

**The main goal is to understand(主要目的是了解):**

- Sealing rates for Phase II v23 or v24 proof params PoRep
- 第二阶段v23或v24验证参数的复制证明的密封效率
- Performance of ePoSt on 5 PB+ of sealed data
- 时空证明在5PB+密封数据上的性能
- What other performance bottlenecks exist
- 存在的其他性能瓶颈
- Critical events in the mining process
- 采矿过程中的严重的不稳定事件
- How mining software could be improved for large scale environments
- 如何改进大型规模环境中的挖掘软件
- Seal speed per US Dollar (GB / h)
- 每美元的密封速度(GB/h)

We are especially interested in measuring the cost and performance of sealing per gigabyte-hour, so proposals that help us understand that metric are encouraged. We also invite additional proposals for more optimal configurations and other useful test plans.

我们对测量GB-小时的密封成本和性能特别感兴趣，因此鼓励提出有助于我们理解这一指标的建议。我们还邀请更多的建议，为更优化的配置和其他有用的测试计划。

<sub>We are only seeking test plan _proposals_ for April 15th along with verification of any current capacity in the latest testnet storage power table, **not** verification of 5 PB capacity. Please do not purchase hardware at this time as there are upcoming changes to the proofs (PoSt and Actors) in progress before the final draft is ready. Also this proposal is unrelated to testnet phase 2.</sub>
<sub>我们只寻求4月15日的测试计划 _提案_，并在最新的testnet存力表中验证任何当前容量，**而不是** 验证5 PB容量。请不要在这个时候购买硬件，因为在最终草案准备好之前，正在对校样（PoSt和Actors）进行更改。此外，这个提案与testnet第2阶段无关。</sub>

#### Application Requirements(应用需求) 

1. Verification of your current capacity and throughput in the testnet storage power table (e.g. a signed message using the method described in [lotus PR #1292](https://github.com/filecoin-project/lotus/pull/1292))
1. 在testnet存储能力表中验证您当前的容量和吞吐量（例如，使用[lotus PR#1292](https://github.com/filecoin project/lotus/pull/1292)中描述的方法的签名消息）
2. A general test plan description involving lotus or go-filecoin 
2. 包含lotus或go-filecoin的通用测试计划描述
3. A description of your 5 PB+ mining operation topology under test (including geographic location)
3. 正在测试的5 PB+挖掘操作拓扑的描述（包括地理位置）


#### Additional Test Criteria that may be considered(可考虑的附加试验标准)

Test plans can optionally also include ways to benchmark your operation with respect to some of the topics listed below:

测试计划还可以选择性地包括一些方法，以根据下面列出的一些主题对您的操作进行基准测试：

- Benchmarking tools
- 基准测试工具
  - (open sourcing any custom tools you use would be greatly appreciated and may make your proposal more competitive)
  - (开源任何你使用的自制工具将被非常欢迎，并可能使您的提案更具竞争力)
- Hardware configurations
- 硬件配置
	- CPU, GPU, RAM, SSD and HDDs, Switches if any
	- CPU、GPU、内存、固态硬盘和硬盘、交换机（如果有）
	- Performance-based BIOS changes if any
	- 基于BIOS的性能更改（如果有）
	- Sample metrics: 
	- 样本指标：
      - performance and usage over time
      - 随时间变化的性能和使用情况
      - any cooling requirements and failure rates
      - 任何(停机)冷却要求和故障率
- Networking topology, bandwidth and throughput metrics
- 网络拓扑、带宽和吞吐量指标
	- Description of the network topology
	- 网络拓扑的描述
	- libp2p metrics, any relays, etc.
	- libp2p指标、任何中继等。
	- Number of peers seen over time
	- 一段时间内看到的对等点数量
- Filecoin software configurations
- Filecoin软件配置
  - Sector builder and sizes under test (we are especially interested in 32GB sectors)
  - 在测试中使用的扇区构建器及大小（我们对32GB扇区特别感兴趣）
  - Sector loss monitoring
  - 扇区丢失监视
  - Daemon - Miner - Seal Worker configurations
  - 链程序 - 矿工程序 - 密封程序 的配置
	  - Including any shared storage
	  - 包括任何共享存储
  - Chain checkpointing and backups
  - 链检查点和备份点
  - Sealing and Proofs metrics
  - 密封和证明指标
	  - Election PoSt at scale e.g. 1-5+ PB
      - 在大规模上时空证明选举，比如：1-5+ PB
  - Deal state metrics
  - 交易状态指标
  - Blockchain metrics
  - 区块链指标
    - e.g. block production, block propagation times, chain storage, etc.
    - 比如区块生产、区块传播时间，链存储，等等
  - Fork detection and related information
  - 分叉检测及相关信息
  - Automation or Integration testing
  - 自动化或集成测试
  - Bootstrapping and data ingestion optimizations
  - (链)启动引导和数据接收优化
  - Queuing strategies if any
  - 排队策略（如有）
  - Caching strategies if any
  - 缓存策略（如有)
  - Any software modifications made or additional logging tools
  - 任何软件修改或附加日志工具
- Supporting software configurations 
- 支持软件配置
	- Storage layer management (we are especially interested in this)
    - 存储层管理（我们对此特别感兴趣）
  - e.g. RAIDs, filesystems, any software-defined storage, NAS, SAN 
  - 比如RAID，文件系统，任何软件定义的存储、NAS、SAN
  - including metrics for I/O per second and use of HDDs vs SSDs
  - 包括使用HDD盘和SSD盘每秒I/O指标
  - your storage growth strategies
  - 您的存储增长战略
	- redundancy strategies if any
    - 冗余策略（如有）
	- workflow orchestration tools if any
    - 工作流编排工具（如果有）
	- networking configurations and tools
    - 网络配置和工具
   - (e.g. DDOS sentry, multi-node to multiaddr reverse proxy, etc.)
   - (比如DDOS哨兵，多节点到多地址反向代理等等)
  - Any additional tools used
  - 任何额外使用的工具
- Any other relevant metrics that may be useful
- 可能有用的任何其他相关指标
	- e.g. data center, location, comparisons to any other networks you may run
    - 数据中心、位置、与您可能运行的任何其他网络的比较
- Finally, we are also interested in financial models such as:
- 最后，我们还对金融模型感兴趣，如
  - cost of mining, broken down by capital expenditure, power costs, datacenter costs, etc
  - 采矿的成本，按资本支出细分, 电力成本、数据中心成本等
  - profitability assuming fixed FIL price
  - 假设固定市价的盈利能力
  - slashing
  - 削减(这里因指金融的模型，或不是指技术上的存力削减机制)
  - proportion of successful blocks on the main chain
  - 在主链成功出块的比例
  - any other information that may help us understand financial concerns
  - 任何其他有助于我们理解财务问题的信息

 *Based on initial results we may ask for additional tests.*
 *根据初步结果，我们可能要求进行额外的测试。*


#### Grant Amounts(补助金)

The goal of this grant is to incentivize sharing testing knowledge and test results to benefit the mining community and understanding how the protocol works at scale. We will keep any proprietary or personal information confidential but will aim to share general knowledge and results with the wider community.

这项拨款的目的是激励共享测试知识和测试结果，以造福采矿社区，并了解协议如何在大规模上工作。我们将对任何专有或个人信息保密，但我们的目标是与更广泛的社区共享一般知识和结果。

We are not sure how many miners will apply and have a capped budget for this grant so will decide how to dispense funds fairly once all proposals have been submitted and reviewed.

我们不确定有多少矿工会申请这笔补助金，并且有一个上限预算，因此在提交和审查所有提案后，我们将决定如何公平分配资金。

Multiple teams may be accepted based on the quality of your proposal and verification of your storage capacity. Please also include the geographic location of your operation in the proposal.

可能会有多个团队被邀请验证您的提案质量和存储容量。请在提案书中包含您的经营地理位置。

Grants can be in fiat or a future grant of FIL or a combination.

补助金可以是法币或未来的FIL或一个组合。

## Deliverables(可交付成果)

Once your proposal is accepted, below are the planned deliverables:

一旦您的提案被接受，以下是计划的可交付成果：

- A specific and detailed test plan involving lotus or go-filecoin.
- 一个包含lotus或go-filecoin的具体而详细的测试计划。
- A description of your mining operation topology under test.
- 正在测试的挖掘操作拓扑的描述。
- A summary of your testing results including any monitoring and metrics screenshots.
- 测试结果的摘要，包括任何监视和度量屏幕截图。
- A write-up of your learnings and recommendations.
- 写下你的学习和建议。

Deliverables can be emailed to devgrants@filecoin.org or published in a Github repo.

可交付成果可通过电子邮件发送至devgrants@filecoin.org或在Github仓库中发布。


#### Deliverable Requirements(可交付成果要求):

- A well-documented, human-readable test plan and summary of results and recommendations.
- 一份文件齐全、可读的测试计划以及结果和建议摘要。
- A listing of all tools and configurations used with documentation and links to any custom tools
- 与文档一起使用的所有工具和配置的列表，以及指向任何自定义工具的链接
- Large-scale hardware environment tests with a current Filecoin node (lotus and/or go-filecoin if feasible)
- 使用当前Filecoin节点（lotus和/或go-filecoin，如果可行）进行大规模硬件环境测试


## Milestones & Funding (里程碑和资金)

| Milestone No.(里程编号) | Milestone Description(里程描述) | Funding(资金) | Estimated Timeframe(预计时间范围) |
| --- | --- | --- | --- |
| 1 | Test plan finalization and a detailed mining operation topology description | 0% | 1-2 weeks |
| 1 | 测试计划定稿和详细的挖掘操作拓扑描述 | 0% | 1-2 周 |
| 2 | Initial benchmarks and iteration on testplans | 25% | 1-2 weeks |
| 2 | 测试计划的初始化基准(测试)和迭代 | 25% | 1-2 周 |
| 3 | Potential iteration and discussion of results with the Filecoin team | 25% | 2 weeks |
| 3 | 潜在迭代和与Filecoin团队的结果讨论 | 25% | 2 周 |
| 4 | Final results, all deliverables and any additional requests for testing based on learnings | 50% | 2-3 weeks |
| 4 | 最终结果、所有可交付成果和基于所学知识的任何额外测试要求 | 50% | 2-3 周 |

If a milestone is not satisfactorily met, we may not continue to fund your team for this project.

如果里程碑未能令人满意地实现，我们可能不会继续为您的团队提供此项目的资金。

**Questions about this RFP?(对本提案的有疑问？)**

Email devgrants@filecoin.org

发送邮件至 devgrants@filecoin.org
