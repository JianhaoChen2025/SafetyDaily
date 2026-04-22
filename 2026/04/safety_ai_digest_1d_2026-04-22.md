# AI 日报 [AI 安全] - 2026-04-22


# AI 安全与治理日报：2026-04-22

## Highlights

今日学术与产业动态聚焦于**对抗攻击的新范式**、**具身智能的安全评估**以及**隐私计算的理论突破**。在安全领域，**[Involuntary In-Context Learning: Exploiting Few-Shot Pattern Completion to Bypass Safety Alignment in GPT-5.4]** 揭示了基于少样本模式完成的新型越狱攻击，证明了语义算子命名可达成 100% 的防御绕过率，这对现有的基于指令微调的安全对齐构成了严峻挑战。在评估方面，**[SafetyALFRED: Evaluating Safety-Conscious Planning of Multimodal Large Language Models]** 发布了首个针对多模态大模型主动风险缓解的具身安全基准，填补了从“识别危害”到“主动规避”的评估空白。此外，**[An AI Agent Execution Environment to Safeguard User Data]** 提出的 GAAP 执行环境为 AI Agent 访问私有数据提供了可信沙箱方案。产业层面，SpaceX 与 Cursor 的潜在收购案及 Anthropic Mythos 模型在欧洲银行的开放计划，标志着 AI 安全能力正加速向高价值商业场景渗透，同时也引发了关于数据主权与模型泄露的新一轮关注。

## 对抗攻击与鲁棒性新范式

随着大模型从静态生成向动态 Agent 演进，对抗攻击的边界正从单纯的 Prompt Injection 向更深层的上下文逻辑操纵扩展。 **[Involuntary In-Context Learning: Exploiting Few-Shot Pattern Completion to Bypass Safety Alignment in GPT-5.4]** 与 **[HarDBench: A Benchmark for Draft-Based Co-Authoring Jailbreak Attacks for Safe Human-LLM Collaborative Writing]** 共同揭示了一个关键趋势：攻击者正利用模型对“上下文模式”的依赖来绕过安全对齐。前者通过抽象算子命名诱导模型在少样本学习中覆盖安全训练，后者则针对人机协作写作场景，利用未完成的草稿注入危险内容。这两项工作互补地表明，现有的安全防御多基于输入过滤，而忽视了模型内部推理链的“模式完成”机制。相比之下，**[Do Agents Dream of Root Shells? Partial-Credit Evaluation of LLM Agents in Capture The Flag Challenges]** 则从防御视角出发，通过 DeepRed 基准在隔离环境中评估 Agent 的 CTF 能力，指出当前 Agent 在真实攻防场景下的表现仍停留在二元“解决/未解决”的粗糙评估，缺乏对攻击路径的细粒度归因。

在视觉与基础模型层面，**[Benign Overfitting in Adversarial Training for Vision Transformers]** 提供了理论层面的新视角，首次分析了 ViT 在对抗训练下的良性过拟合现象，指出在特定信噪比条件下，ViT 的鲁棒性可能优于 CNN。这与传统认为 Transformer 架构更易受攻击的观点形成对比，暗示了架构选择对安全性的潜在影响。然而，这些理论进展与工业界面临的现实风险形成张力，如 **[EvoPatch-IoT: Evolution-Aware Cross-Architecture Vulnerability Retrieval and Patch-State Profiling for BusyBox-Based IoT Firmware]** 所示，物联网固件的跨架构漏洞检索仍面临严重挑战，表明基础模型的安全理论尚未完全覆盖边缘计算与嵌入式系统的复杂环境。

## 对齐理论与推理安全性

模型对齐的研究正从简单的“指令遵循”转向更深层的“认知一致性”与“推理边界”管理。 **[Taming Actor-Observer Asymmetry in Agents via Dialectical Alignment]** 指出多 Agent 框架中存在的“行动者 - 观察者不对称”认知偏差，即 Agent 在自我反思时倾向于将失败归因于外部因素，这可能导致多 Agent 系统中的责任推诿与风险累积。这一发现与 **[Pause or Fabricate? Training Language Models for Grounded Reasoning]** 中提出的“无根推理”问题相呼应，后者强调模型在缺乏前提时仍会自信地编造信息，缺乏推理边界意识。两者共同指向了当前对齐技术的核心缺陷：模型在追求流畅性的同时，牺牲了事实的严谨性与归因的诚实性。

为了解决推理的可解释性与逻辑一致性，**[Discovering a Shared Logical Subspace: Steering LLM Logical Reasoning via Alignment of Natural-Language and Symbolic Views]** 提出了自然语言与符号视角共享逻辑子空间的假设，试图在模型内部建立跨视图的逻辑一致性。这与 **[Four-Axis Decision Alignment for Long-Horizon Enterprise AI Agents]** 提出的四轴对齐框架（事实精度、推理连贯性、合规性、意图对齐）形成理论互补。前者关注微观的推理机制，后者关注宏观的决策行为。然而，**[Counting Worlds Branching Time Semantics for post-hoc Bias Mitigation in generative AI]** 指出，现有的推理时间缓解策略缺乏形式化保证，提出的 CTLF 分支时间逻辑试图为生成过程中的偏差提供可验证的数学框架，这为未来的对齐理论提供了新的形式化路径。

## 隐私计算与联邦学习

在数据隐私保护日益严格的背景下，联邦学习（FL）与合成数据生成成为平衡数据效用与隐私的关键。 **[A Dual Perspective on Synthetic Trajectory Generators: Utility Framework and Privacy Vulnerabilities]** 深入探讨了基于生成模型的人体移动数据合成，指出虽然生成模型提升了数据效用，但其隐私漏洞（如成员推断攻击）尚未得到充分评估。这与 **[Sherpa.ai Privacy-Preserving Multi-Party Entity Alignment without Intersection Disclosure for Noisy Identifiers]** 中提出的隐私保护实体对齐技术形成呼应，后者针对垂直联邦学习中的样本对齐问题，利用混淆电路实现了在不泄露交集信息下的实体匹配。

然而，联邦学习的实际部署仍面临数据质量与异构性的挑战。 **[FB-NLL: A Feature-Based Approach to Tackle Noisy Labels in Personalized Federated Learning]** 与 **[Heterogeneity-Aware Personalized Federated Learning for Industrial Predictive Analytics]** 分别针对噪声标签与异构退化过程提出了个性化解决方案。前者通过特征解耦避免聚类决策受低质量数据干扰，后者则允许不同客户端构建定制化的预测模型。值得注意的是，**[FedSEA: Achieving Benefit of Parallelization in Federated Online Learning]** 扩展了在线联邦学习范式，通过随机扩展对手模型实现了并行化收益，这在理论上突破了传统 OFL 对并行计算的假设限制。这些工作共同表明，隐私保护技术正从单纯的“加密传输”向“计算过程中的隐私保持”与“数据质量治理”深化。

## 评估基准与治理框架

随着 AI 系统应用场景的复杂化，单一的性能指标已无法全面反映模型的安全性与社会影响。 **[SafetyALFRED: Evaluating Safety-Conscious Planning of Multimodal Large Language Models]** 与 **[FairTree: Subgroup Fairness Auditing of Machine Learning Models with Bias-Variance Decomposition]** 分别从具身安全与子群公平性两个维度拓展了评估边界。前者在厨房场景中评估模型对物理危害的主动规避能力，后者则利用心理测量不变性测试直接处理连续协变量，解决了传统切片工具无法处理连续特征的痛点。

在评估方法论上，**[Beyond Rating: A Comprehensive Evaluation and Benchmark for AI Reviews]** 批判了当前将评审任务简化为评分预测的倾向，提出了包含内容忠实度、论证一致性等五个维度的 holistic 评估框架。这与 **[The signal is the ceiling: Measurement limits of LLM-predicted experience ratings from open-ended survey text]** 中关于 LLM 预测体验评分的测量极限研究形成对话，后者指出提示词设计与模型选择对预测精度的影响有限，暗示了自动化评估本身存在理论天花板。此外，**[Detecting Data Contamination in Large Language Models]** 通过统一数据集对比了黑盒成员推断攻击（MIA），为评估模型训练数据的合规性提供了基准。这些工作共同指向一个趋势：评估体系正从“结果导向”转向“过程与影响导向”，强调可解释性、公平性与数据溯源。

## 开源工具与基础设施

开源社区正在构建一系列支持安全开发与隐私保护的工具链，以填补理论研究与工程落地之间的鸿沟。 **[An AI Agent Execution Environment to Safeguard User Data]** 提出的 GAAP 环境为 Agent 访问私有数据提供了可信沙箱，通过会计机制保障用户数据不被泄露。在代码与 Agent 开发领域， **[agents-md]** 通过标准化 Agent 行为（如强制验证循环、抑制谄媚），试图解决 Agent 在代码生成中的不可控风险。 **[Vela]** 与 **[ovo-local-llm]** 则分别针对隐私优先的写作 IDE 与 Apple Silicon 本地 Agent 提供了开源实现，强调本地化推理以减少云端数据泄露风险。

此外，**[AutoProber]** 为硬件黑客提供了自动化探针栈，支持安全监控的 CNC 运动与探针审查，体现了 AI 安全在物理硬件层面的延伸。这些工具不仅降低了安全测试的门槛，也通过“安全即代码”的理念，将安全机制内嵌到开发流程中。

## Looking Forward

尽管今日的研究在对抗攻击、隐私计算与评估基准上取得了显著进展，但仍有若干核心理论问题亟待解决。首先，**Agent 的长程安全对齐** 仍缺乏形式化保证，特别是当 Agent 具备自主工具调用与记忆能力时，如何防止其通过多步推理绕过安全约束（如 IICL 攻击所示）是一个开放问题。其次，**隐私与效用的理论边界** 在生成式模型中尚未明确，合成数据在提升效用同时带来的隐私泄露风险（如轨迹生成器）需要更严格的数学界定。最后，**多模态评估的标准化** 仍面临挑战，如何统一不同语言、不同模态下的安全与公平性指标（如 MM-JudgeBench 与 FairTree 的差异），是构建全球 AI 治理框架的关键。未来研究需进一步探索基于形式化验证的对齐方法，以及跨模态、跨语言的隐私保护计算架构。

---


## 参考来源

- **A Dual Perspective on Synthetic Trajectory Generators: Utility Framework and Privacy Vulnerabilities** — [arxiv_ai](https://arxiv.org/abs/2604.19653v1)
- **Taming Actor-Observer Asymmetry in Agents via Dialectical Alignment** — [arxiv_ai](https://arxiv.org/abs/2604.19548v1)
- **Evaluating LLM-Driven Summarisation of Parliamentary Debates with Computational Argumentation** — [arxiv_cl](https://arxiv.org/abs/2604.19331v1)
- **HarDBench: A Benchmark for Draft-Based Co-Authoring Jailbreak Attacks for Safe Human-LLM Collaborative Writing** — [arxiv_cl](https://arxiv.org/abs/2604.19274v1)
- **Sherpa.ai Privacy-Preserving Multi-Party Entity Alignment without Intersection Disclosure for Noisy Identifiers** — [arxiv_cr](https://arxiv.org/abs/2604.19219v1)
- **UniT: Toward a Unified Physical Language for Human-to-Humanoid Policy Learning and World Modeling** — [arxiv_ai](https://arxiv.org/abs/2604.19734v1)
- **Benign Overfitting in Adversarial Training for Vision Transformers** — [arxiv_ai](https://arxiv.org/abs/2604.19724v1)
- **An AI Agent Execution Environment to Safeguard User Data** — [arxiv_ai](https://arxiv.org/abs/2604.19657v1)
- **SafetyALFRED: Evaluating Safety-Conscious Planning of Multimodal Large Language Models** — [arxiv_ai](https://arxiv.org/abs/2604.19638v1)
- **Counting Worlds Branching Time Semantics for post-hoc Bias Mitigation in generative AI** — [arxiv_ai](https://arxiv.org/abs/2604.19431v1)
- **Diagnosable ColBERT: Debugging Late-Interaction Retrieval Models Using a Learned Latent Space as Reference** — [arxiv_cl](https://arxiv.org/abs/2604.19566v1)
- **VCE: A zero-cost hallucination mitigation method of LVLMs via visual contrastive editing** — [arxiv_cl](https://arxiv.org/abs/2604.19412v1)
- **Lost in Translation: Do LVLM Judges Generalize Across Languages?** — [arxiv_cl](https://arxiv.org/abs/2604.19405v1)
- **FB-NLL: A Feature-Based Approach to Tackle Noisy Labels in Personalized Federated Learning** — [arxiv_lg](https://arxiv.org/abs/2604.19729v1)
- **PREF-XAI: Preference-Based Personalized Rule Explanations of Black-Box Machine Learning Models** — [arxiv_lg](https://arxiv.org/abs/2604.19684v1)
- **ZC-Swish: Stabilizing Deep BN-Free Networks for Edge and Micro-Batch Applications** — [arxiv_lg](https://arxiv.org/abs/2604.19453v1)
- **Heterogeneity-Aware Personalized Federated Learning for Industrial Predictive Analytics** — [arxiv_lg](https://arxiv.org/abs/2604.19451v1)
- **FairTree: Subgroup Fairness Auditing of Machine Learning Models with Bias-Variance Decomposition** — [arxiv_lg](https://arxiv.org/abs/2604.19357v1)
- **FedSEA: Achieving Benefit of Parallelization in Federated Online Learning** — [arxiv_lg](https://arxiv.org/abs/2604.19336v1)
- **FASTER: Value-Guided Sampling for Fast RL** — [arxiv_ai](https://arxiv.org/abs/2604.19730v1)
- **VLA Foundry: A Unified Framework for Training Vision-Language-Action Models** — [arxiv_ai](https://arxiv.org/abs/2604.19728v1)
- **A-MAR: Agent-based Multimodal Art Retrieval for Fine-Grained Artwork Understanding** — [arxiv_ai](https://arxiv.org/abs/2604.19689v1)
- **Learning Hybrid-Control Policies for High-Precision In-Contact Manipulation Under Uncertainty** — [arxiv_ai](https://arxiv.org/abs/2604.19677v1)
- **Lyapunov-Certified Direct Switching Theory for Q-Learning** — [arxiv_ai](https://arxiv.org/abs/2604.19569v1)
- **Multi-modal Reasoning with LLMs for Visual Semantic Arithmetic** — [arxiv_ai](https://arxiv.org/abs/2604.19567v1)
- **Detecting Data Contamination in Large Language Models** — [arxiv_ai](https://arxiv.org/abs/2604.19561v1)
- **DT2IT-MRM: Debiased Preference Construction and Iterative Training for Multimodal Reward Modeling** — [arxiv_ai](https://arxiv.org/abs/2604.19544v1)
- **EVPO: Explained Variance Policy Optimization for Adaptive Critic Utilization in LLM Post-Training** — [arxiv_ai](https://arxiv.org/abs/2604.19485v1)
- **Fairness Audits of Institutional Risk Models in Deployed ML Pipelines** — [arxiv_ai](https://arxiv.org/abs/2604.19468v1)
- **LePREC: Reasoning as Classification over Structured Factors for Assessing Relevance of Legal Issues** — [arxiv_ai](https://arxiv.org/abs/2604.19464v1)
- **Four-Axis Decision Alignment for Long-Horizon Enterprise AI Agents** — [arxiv_ai](https://arxiv.org/abs/2604.19457v1)
- **GOLD-BEV: GrOund and aeriaL Data for Dense Semantic BEV Mapping of Dynamic Scenes** — [arxiv_ai](https://arxiv.org/abs/2604.19411v1)
- **Discovering a Shared Logical Subspace: Steering LLM Logical Reasoning via Alignment of Natural-Language and Symbolic Views** — [arxiv_cl](https://arxiv.org/abs/2604.19716v1)
- **Epistemic orientation in parliamentary discourse is associated with deliberative democracy** — [arxiv_cl](https://arxiv.org/abs/2604.19699v1)
- **Pause or Fabricate? Training Language Models for Grounded Reasoning** — [arxiv_cl](https://arxiv.org/abs/2604.19656v1)
- **The signal is the ceiling: Measurement limits of LLM-predicted experience ratings from open-ended survey text** — [arxiv_cl](https://arxiv.org/abs/2604.19645v1)
- **Emotion-Cause Pair Extraction in Conversations via Semantic Decoupling and Graph Alignment** — [arxiv_cl](https://arxiv.org/abs/2604.19547v1)
- **Beyond Rating: A Comprehensive Evaluation and Benchmark for AI Reviews** — [arxiv_cl](https://arxiv.org/abs/2604.19502v1)
- **Rethinking Scale: Deployment Trade-offs of Small Language Models under Agent Paradigms** — [arxiv_cl](https://arxiv.org/abs/2604.19299v1)
- **Location Not Found: Exposing Implicit Local and Global Biases in Multilingual LLMs** — [arxiv_cl](https://arxiv.org/abs/2604.19292v1)
- **Beyond Semantic Similarity: A Component-Wise Evaluation Framework for Medical Question Answering Systems with Health Equity Implications** — [arxiv_cl](https://arxiv.org/abs/2604.19281v1)
- **Involuntary In-Context Learning: Exploiting Few-Shot Pattern Completion to Bypass Safety Alignment in GPT-5.4** — [arxiv_cr](https://arxiv.org/abs/2604.19461v1)
- **Secure Storage and Privacy-Preserving Scanpath Comparison via Garbled Circuits in Eye Tracking** — [arxiv_cr](https://arxiv.org/abs/2604.19422v1)
- **On two ways to use determinantal point processes for Monte Carlo integration** — [arxiv_lg](https://arxiv.org/abs/2604.19698v1)
- **From Top-1 to Top-K: A Reproducibility Study and Benchmarking of Counterfactual Explanations for Recommender Systems** — [arxiv_lg](https://arxiv.org/abs/2604.19663v1)
- **Disentangling Damage from Operational Variability: A Label-Free Self-Supervised Representation Learning Framework for Output-Only Structural Damage Identification** — [arxiv_lg](https://arxiv.org/abs/2604.19658v1)
- **Evaluating LLM-Generated Obfuscated XSS Payloads for Machine Learning-Based Detection** — [arxiv_lg](https://arxiv.org/abs/2604.19526v1)
- **Accelerating Optimization and Machine Learning through Decentralization** — [arxiv_lg](https://arxiv.org/abs/2604.19518v1)
- **CAST: Modeling Semantic-Level Transitions for Complementary-Aware Sequential Recommendation** — [arxiv_lg](https://arxiv.org/abs/2604.19414v1)
- **Optimal Routing for Federated Learning over Dynamic Satellite Networks: Tractable or Not?** — [arxiv_lg](https://arxiv.org/abs/2604.19399v1)
- **TACENR: Task-Agnostic Contrastive Explanations for Node Representations** — [arxiv_lg](https://arxiv.org/abs/2604.19372v1)
- **LASER: Learning Active Sensing for Continuum Field Reconstruction** — [arxiv_lg](https://arxiv.org/abs/2604.19355v1)
- **Concept Inconsistency in Dermoscopic Concept Bottleneck Models: A Rough-Set Analysis of the Derm7pt Dataset** — [arxiv_lg](https://arxiv.org/abs/2604.19323v1)
- **An Answer is just the Start: Related Insight Generation for Open-Ended Document-Grounded QA** — [arxiv_cl](https://arxiv.org/abs/2604.19685v1)
- **Exploring Language-Agnosticity in Function Vectors: A Case Study in Machine Translation** — [arxiv_cl](https://arxiv.org/abs/2604.19678v1)
- **Micro Language Models Enable Instant Responses** — [arxiv_cl](https://arxiv.org/abs/2604.19642v1)
- **The "Small World of Words" German Free-Association Norms** — [arxiv_cl](https://arxiv.org/abs/2604.19620v1)
- **A Bolu: A Structured Dataset for the Computational Analysis of Sardinian Improvisational Poetry** — [arxiv_cl](https://arxiv.org/abs/2604.19584v1)
- **A Self-Evolving Framework for Efficient Terminal Agents via Observational Context Compression** — [arxiv_cl](https://arxiv.org/abs/2604.19572v1)
- **"We are currently clean on OPSEC": Why JD Can't Encrypt** — [arxiv_cr](https://arxiv.org/abs/2604.19711v1)
- **Adding Compilation Metadata To Binaries To Make Disassembly Decidable** — [arxiv_cr](https://arxiv.org/abs/2604.19628v1)
- **Cyclic Equalizability Characterized by Parikh Vectors** — [arxiv_cr](https://arxiv.org/abs/2604.19504v1)
- **EvoPatch-IoT: Evolution-Aware Cross-Architecture Vulnerability Retrieval and Patch-State Profiling for BusyBox-Based IoT Firmware** — [arxiv_cr](https://arxiv.org/abs/2604.19496v1)
- **API Security Based on Automatic OpenAPI Mapping** — [arxiv_cr](https://arxiv.org/abs/2604.19471v1)
- **Malicious ML Model Detection by Learning Dynamic Behaviors** — [arxiv_cr](https://arxiv.org/abs/2604.19438v1)
- **Do Agents Dream of Root Shells? Partial-Credit Evaluation of LLM Agents in Capture The Flag Challenges** — [arxiv_cr](https://arxiv.org/abs/2604.19354v1)
- **Phase Transitions in the Fluctuations of Functionals of Random Neural Networks** — [arxiv_lg](https://arxiv.org/abs/2604.19738v1)
- **Safe Continual Reinforcement Learning in Non-stationary Environments** — [arxiv_lg](https://arxiv.org/abs/2604.19737v1)
- **Ultrametric OGP - parametric RDT \emph{symmetric} binary perceptron connection** — [arxiv_lg](https://arxiv.org/abs/2604.19712v1)
- **Planning in entropy-regularized Markov decision processes and games** — [arxiv_lg](https://arxiv.org/abs/2604.19695v1)
- **SpaceX is working with Cursor and has an option to buy the startup for $60B** — [techcrunch_ai](https://techcrunch.com/2026/04/21/spacex-is-working-with-cursor-and-has-an-option-to-buy-the-startup-for-60-billion/)
- **SpaceX cuts a deal to maybe buy Cursor for $60 billion** — [theverge_ai](https://www.theverge.com/science/916427/spacex-cursor-potential-deal-acquisition)
- **Roundtables: Unveiling The 10 Things That Matter in AI Right Now** — [mit_tech_review](https://www.technologyreview.com/2026/04/21/1135486/roundtables-unveiling-the-10-things-that-matter-in-ai-right-now/)
- **The new word in home construction could be “plastics”** — [mit_tech_review](https://www.technologyreview.com/2026/04/21/1134856/the-new-word-in-home-construction-could-be-plastics/)
- **A natural protein may protect the GI tract from infection** — [mit_tech_review](https://www.technologyreview.com/2026/04/21/1134858/a-natural-protein-may-protect-the-gi-tract-from-infection/)
- **This tool could show how consciousness works** — [mit_tech_review](https://www.technologyreview.com/2026/04/21/1134862/this-tool-could-show-how-consciousness-works/)
- **Early life may have breathed oxygen earlier than believed** — [mit_tech_review](https://www.technologyreview.com/2026/04/21/1134867/early-life-may-have-breathed-oxygen-earlier-than-believed/)
- **Analog computing from waste heat** — [mit_tech_review](https://www.technologyreview.com/2026/04/21/1134870/analog-computing-from-waste-heat/)
- **Get ready for hotter, muggier, stormier summers** — [mit_tech_review](https://www.technologyreview.com/2026/04/21/1134873/get-ready-for-hotter-muggier-stormier-summers/)
- **Recent books from the MIT community** — [mit_tech_review](https://www.technologyreview.com/2026/04/21/1134879/recent-books-from-the-mit-community-28/)
- **AI at MIT** — [mit_tech_review](https://www.technologyreview.com/2026/04/21/1134938/ai-at-mit/)
- **Inventor recalls eye imaging breakthrough** — [mit_tech_review](https://www.technologyreview.com/2026/04/21/1134945/inventor-recalls-eye-imaging-breakthrough/)
- **Sam Altman throws shade at Anthropic’s cyber model, Mythos: ‘fear-based marketing’** — [techcrunch_ai](https://techcrunch.com/2026/04/21/sam-altman-throws-shade-at-anthropics-cyber-model-mythos-fear-based-marketing/)
- **Clarifai deletes 3 million photos that OkCupid provided to train facial recognition AI, report says** — [techcrunch_ai](https://techcrunch.com/2026/04/21/clarifai-okcupid-facial-recognition-ai-ftc-settlement/)
- **AI backlash is coming for elections** — [theverge_ai](https://www.theverge.com/policy/916210/ai-midterm-elections-data-centers-jobs)
- **OpenAI’s updated image generator can now pull information from the web** — [theverge_ai](https://www.theverge.com/ai-artificial-intelligence/916166/openai-chatgpt-images-2)
- **Framework’s first eGPUs turn its laptop into a desktop PC** — [theverge_ai](https://www.theverge.com/gadgets/915328/framework-oculink-egpu-dev-kit-laptop-16)
- **Celebrities will be able to find and request removal of AI deepfakes on YouTube** — [theverge_ai](https://www.theverge.com/ai-artificial-intelligence/915872/celebrities-will-be-able-to-find-and-request-removal-of-ai-deepfakes-on-youtube)
- **Ordering with the Starbucks ChatGPT app was a true coffee nightmare** — [theverge_ai](https://www.theverge.com/ai-artificial-intelligence/915821/starbucks-chatgpt-app-testing)
- **Bond, a new social media platform, wants to use AI to help you kick your doomscrolling habit** — [techcrunch_ai](https://techcrunch.com/2026/04/21/bond-social-media-platform-ai-memories-kick-doomscrolling-habit/)
- **John Ternus’ first big problem is AI** — [theverge_ai](https://www.theverge.com/ai-artificial-intelligence/915662/john-ternus-apple-ceo-tim-cook-ai-problem-siri)
- **Yelp is making its AI chatbot way more useful** — [theverge_ai](https://www.theverge.com/ai-artificial-intelligence/915626/yelp-ai-assistant-chatbot-major-upgrade)
- **Meta will record employees’ keystrokes and use it to train its AI models** — [techcrunch_ai](https://techcrunch.com/2026/04/21/meta-will-record-employees-keystrokes-and-use-it-to-train-its-ai-models/)
- **Unauthorized group has gained access to Anthropic’s exclusive cyber tool Mythos, report claims** — [techcrunch_ai](https://techcrunch.com/2026/04/21/unauthorized-group-has-gained-access-to-anthropics-exclusive-cyber-tool-mythos-report-claims/)
- **Apple’s John Ternus will run one of the world’s most powerful companies; the job is a minefield** — [techcrunch_ai](https://techcrunch.com/2026/04/21/apples-john-ternus-will-run-one-of-the-worlds-most-powerful-companies-the-job-is-a-minefield/)
- **AI research lab NeoCognition lands $40M seed to build agents that learn like humans** — [techcrunch_ai](https://techcrunch.com/2026/04/21/ai-research-lab-neocognition-lands-40m-seed-to-build-agents-that-learn-like-humans/)
- **ChatGPT’s new Images 2.0 model is surprisingly good at generating text** — [techcrunch_ai](https://techcrunch.com/2026/04/21/chatgpts-new-images-2-0-model-is-surprisingly-good-at-generating-text/)
- **AI Dungeon maker Latitude unveils Voyage, a platform for creating AI-powered RPGs** — [techcrunch_ai](https://techcrunch.com/2026/04/21/voyage-is-an-ai-rpg-platform-for-creating-custom-gaming-worlds-with-ai-generated-npc-interactions/)
- **YouTube expands its AI likeness detection technology to celebrities** — [techcrunch_ai](https://techcrunch.com/2026/04/21/youtube-expands-its-ai-likeness-detection-technology-to-celebrities/)
- **3 new ways Ads Advisor is making Google Ads safer and faster** — [google_ai](https://blog.google/products/ads-commerce/ads-advisor-google-ads/)
- **GRAI believes AI can make music more social, not replace artists** — [techcrunch_ai](https://techcrunch.com/2026/04/21/grai-believes-ai-can-make-music-more-social-not-replace-artists/)
- **heider-x/vela** — [github](https://github.com/heider-x/vela)
- **AMAP-ML/DCW** — [github](https://github.com/AMAP-ML/DCW)
- **Tencent-Hunyuan/HY-SOAR** — [github](https://github.com/Tencent-Hunyuan/HY-SOAR)
- **atomgit-atomcode/atomcode** — [github](https://github.com/atomgit-atomcode/atomcode)
- **dsd2077/CyberVerse** — [github](https://github.com/dsd2077/CyberVerse)
- **ovoment/ovo-local-llm** — [github](https://github.com/ovoment/ovo-local-llm)
- **yzhao062/anywhere-agents** — [github](https://github.com/yzhao062/anywhere-agents)
- **intertwine/dspy-agent-skills** — [github](https://github.com/intertwine/dspy-agent-skills)
- **GainSec/AutoProber** — [github](https://github.com/GainSec/AutoProber)
- **TheRealSeanDonahoe/agents-md** — [github](https://github.com/TheRealSeanDonahoe/agents-md)
- **alchaincyf/huashu-design** — [github](https://github.com/alchaincyf/huashu-design)
- **宝洁公司已成功注册WHITELOCK商标** — [36kr](https://36kr.com/newsflashes/3777608395592704?f=rss)
- **具微科技两个月狂揽4轮数亿元融资，产业资本“天团”强势入局 | 36氪首发** — [36kr](https://36kr.com/p/3777491215913736?f=rss)
- **“清听声学”完成B+轮数亿元融资** — [36kr](https://36kr.com/newsflashes/3777574458316034?f=rss)
- **快手618商家大会于杭州启动** — [36kr](https://36kr.com/newsflashes/3777543279137794?f=rss)
- **车企在给电池厂打工？宁德时代罗坚：只需问输出的价值够不够，其他的交给市场** — [36kr](https://36kr.com/newsflashes/3777534945072133?f=rss)
- **萤石发布搭“星辰世界模型”的蒸汽洗地机** — [36kr](https://36kr.com/newsflashes/3777526407713797?f=rss)
- **消息人士：Anthropic计划很快向欧洲的银行开放Mythos使用权限** — [36kr](https://36kr.com/newsflashes/3777518954566656?f=rss)
- **汇丰新加坡寿险业务的竞购者名单据悉缩减至安联、第一生命和住友生命** — [36kr](https://36kr.com/newsflashes/3777501470954754?f=rss)
- **押注AAV体内CAR-T，「西湖云谷智药」即将启动IIT研究** — [36kr](https://36kr.com/p/3774632804057607?f=rss)
- **8点1氪丨MCN机构回应女孩挪用上千万打赏主播；苹果更换CEO原因曝光；国内油价2026年首次下调** — [36kr](https://36kr.com/p/3777227930224900?f=rss)
- **智界要打翻盘仗：V9给了年均12万辆指引｜36氪独家** — [36kr](https://36kr.com/p/3776741071571200?f=rss)
- **氪星晚报｜星巴克中国回应开放加盟传闻：不实信息；苹果公司宣布特纳斯将接替库克担任CEO** — [36kr](https://36kr.com/p/3776458805904129?f=rss)
- **PettiChat获百万美元种子投资，造出宠物穿戴AI翻译器** — [36kr](https://36kr.com/p/3769659305427459?f=rss)
- **g2i-ai/agents** — [github](https://github.com/g2i-ai/agents)
- **dezgit2025/auto-memory** — [github](https://github.com/dezgit2025/auto-memory)
- **kernullist/windbg-decompile-ext** — [github](https://github.com/kernullist/windbg-decompile-ext)
- **ConardLi/web-design-skill** — [github](https://github.com/ConardLi/web-design-skill)
- **tobyilee/book-writer** — [github](https://github.com/tobyilee/book-writer)
- **geekjourneyx/travel-guidebook** — [github](https://github.com/geekjourneyx/travel-guidebook)
- **catoncat/notion-local-ops-mcp** — [github](https://github.com/catoncat/notion-local-ops-mcp)
- **TheRealSeanDonahoe/ijfw** — [github](https://github.com/TheRealSeanDonahoe/ijfw)
- **KarryViber/Orb** — [github](https://github.com/KarryViber/Orb)
- **机构：千问AI眼镜线上市场份额达53%，持续位居市场第一** — [36kr](https://36kr.com/newsflashes/3777626884805634?f=rss)
- **农业农村部：今日全国农产品批发市场猪肉平均价格为14.68元/公斤，比昨天下降0.7%** — [36kr](https://36kr.com/newsflashes/3777619190551808?f=rss)
- **韩国预计到2040年用电量将增长近30%** — [36kr](https://36kr.com/newsflashes/3777596020003844?f=rss)
- **沪指午后站上4100点** — [36kr](https://36kr.com/newsflashes/3777563699107075?f=rss)
- **新易盛午后涨逾4%，总市值突破6000亿** — [36kr](https://36kr.com/newsflashes/3777545382204681?f=rss)
- **一季度长三角区域进出口总值创历史同期新高** — [36kr](https://36kr.com/newsflashes/3777539903132673?f=rss)
- **秀强股份：目前不涉及玻璃基板业务** — [36kr](https://36kr.com/newsflashes/3777462494515972?f=rss)
- **前小鹏汽车自动驾驶一号位李力耘出任众擎CTO，加速打造具身大脑** — [qbitai](https://www.qbitai.com/2026/04/404124.html)
- **从GPU到Token：AI基础设施竞争逻辑重构** — [qbitai](https://www.qbitai.com/2026/04/404440.html)
- **2026萤石品牌新品发布会：驭智向前锚定长期主义，AI驱动多点开花** — [qbitai](https://www.qbitai.com/2026/04/404420.html)
- **6分钟满电续航1500公里！宁王一夜终结加油时代** — [qbitai](https://www.qbitai.com/2026/04/404167.html)
- **单Agent时代结束，AI们开始组团上班** — [qbitai](https://www.qbitai.com/2026/04/404130.html)
- **5月20日，马上AI起来！中国AIGC产业峰会报名已启动｜首波嘉宾官宣** — [qbitai](https://www.qbitai.com/2026/04/404096.html)
- **物理优先+VLA闭环进化：高德ABot-World世界模型，破解具身智能零样本泛化难题** — [qbitai](https://www.qbitai.com/2026/04/404086.html)
- **ISC.AI 2026创新独角兽沙盒大赛在京启动 聚焦智能体 共筑AI创新生态** — [qbitai](https://www.qbitai.com/2026/04/404082.html)