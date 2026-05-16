# **Theoretical and Practical Frameworks for Event-Driven Cognitive Architectures in Humanoid Robotics**

The pursuit of artificial general intelligence (AGI) within the field of humanoid robotics has transitioned from static, rule-based systems toward dynamic, integrated architectures inspired by the functional organization of human cognition. This paradigm shift emphasizes that intelligence is not a monolithic processing of symbols but an emergent property of the continuous interaction between sensory perception, memory, emotion, attention, and action.1 Unlike traditional robotic control systems that function primarily in a reactive mode, event-driven cognitive architectures facilitate a self-active state where the system continues to process information internally through memory recall, imagination, and emotional evaluation even in the absence of external sensory stimuli.1 This analysis explores the modular layers of such an architecture, evaluating the mechanisms that allow a humanoid robot to bridge the gap between raw sensory data and emergent semantic understanding.

## **Foundations of Continuous Cognitive Dynamics**

The fundamental principle of an event-driven cognitive architecture is the assumption that an intelligent system is never truly inactive. Biological brains maintain a continuous stream of internal activity, and this "primacy of internal activity" indicates that the organizing principles enabling cognitive capacities include the selective constraint of ongoing activity by sensory input.4 This contrasts with the classical view of the brain as a purely input-driven system.4

### **The Standard Model of the Mind and Its Evolution**

Recent efforts in cognitive science have sought to define a "Standard Model of the Mind," a reference model born out of a consensus between established architectures such as ACT-R and Soar.6 These classical architectures generally assume three levels of processing: a bottom-up parallel level, a deliberative level for action selection, and a meta-cognitive level for handling uncertainty.7 However, as humanoid robots move from structured industrial environments to dynamic, unstructured spaces populated by humans, there is a growing need for architectures that support more human-like, unsupervised, and multimodal learning mechanisms.8

| Architectural Element | Classical Production Systems (Soar/ACT-R) | Integrated Event-Driven Architectures (LIDA/RFC) |
| :---- | :---- | :---- |
| **Core Mechanism** | Rule-based production firing; symbolic matching 7 | Concurrent event streams; global broadcasting 1 |
| **Cognitive Pace** | Discrete cycles, typically 50ms 10 | Iterated cycles (\~10 Hz) with overlapping phases 1 |
| **Learning Mode** | Chunking and production compilation 7 | Multimodal selectionist and instructionalist learning 8 |
| **Internal Rehearsal** | Minimal; often task-specific 12 | Continuous internal simulation and memory replay 14 |

A scalable cognitive system usually consists of five semantic layers: a device and driver layer, a world modeling layer, a behavior and planning layer, an interaction layer, and an operations layer for diagnostics and failure analysis.16 The event-driven approach reorganizes these layers into streams of events, where perception, memory, and action are all part of the same continuous loop.1

## **Perceptual Transduction and the Heterogeneous Event Stream**

In a humanoid robot, input channels receive physical or internal signals from a diverse sensor suite, including vision, hearing, touch, and body sensors.18 In an event-driven architecture, these raw signals are converted into structured perceptual events that describe "what" was detected without immediately attaching human-defined semantic labels.21 This separation of perception from meaning allows the robot to build a context-dependent understanding of its environment through repeated interaction.22

### **Event-Based Vision and Neuromorphic Efficiency**

Traditional frame-based cameras sample visual information at a fixed rate, which often leads to high data redundancy and significant latency in dynamic environments.20 Event-based vision sensors, such as the Dynamic Vision Sensor (DVS), mimic biological vision by asynchronously reporting brightness changes at the pixel level.25 Each pixel emits an asynchronous digital pulse ("spike") only when a relative contrast change exceeds a threshold, enabling microsecond-level temporal resolution and high dynamic range.20

| Metric | Traditional Vision | Event-Driven Vision (DVS) |
| :---- | :---- | :---- |
| **Data Encoding** | Intensity frames (e.g., 640x480) 28 | Address Event Representation (AER) 20 |
| **Temporal Resolution** | 16-33 ms (frame-limited) | \~160 ns 24 |
| **Bandwidth Usage** | High and constant | Low and activity-dependent 20 |
| **Dynamic Range** | 60-80 dB | \>120 dB 25 |

The integration of event-based vision into a cognitive architecture requires specialized processing libraries, such as the one developed for the iCub robot, which maintain low latency by performing computation directly on the output spikes from sensors.20 This allows the robot to quickly orient its gaze and react to unexpected stimuli long before a frame-based system would have finished capturing a single image.20

### **Theoretical Event Coding and Shared Representational Domains**

The transition from raw perception to action planning is facilitated by the Theory of Event Coding (TEC), which posits that perceived events and intended actions are coded and stored together in a common representational medium.30 According to TEC, feature codes refer to the distal features of objects and events (e.g., shape, size, location) rather than the proximal features of the sensations.32 This common coding implies that seeing an event activates the action associated with that event, and planning an action involves activating the perceptual symbols representing the action's effects.33 This architecture resolves the traditional "sandwich model" where perception and action are separated by a distinct cognitive deliberation stage.32

## **Attention Mechanisms and the Attentional Bottleneck**

As the perception stream receives a vast influx of events, the cognitive system must select a limited subset of information for high-level reasoning. This selected subset is known as a chunk, and its size is constrained by the system's processing capacity, mirroring the working memory limitations of human cognition.1

### **Global Workspace Theory: Selection and Global Broadcast**

The chunk selection process is often implemented using a Global Workspace (GW) architecture.35 In this setting, specialized unconscious modules compete for access to a limited-capacity global workspace.11 The contents that "win" this competition are then globally broadcast to all components of the system.11 This competitive selection mechanism acts as an attentional bottleneck, only letting through the most salient information originating from diverse input modalities.36  
The dynamics of the Global Workspace involve several key components:

1. **Module Proposals**: Each specialized module generates a candidate representation (e.g., a vector ![][image1]) in parallel.35  
2. **Scoring and Gating**: Attention-style gating computes scores ![][image2] based on bottom-up signal strength and top-down goal context.35  
3. **Softmax Competition**: A winner is selected using softmax weights ![][image3].35  
4. **Ignition and Broadcast**: The winning content ![][image4] is broadcast, triggering a "global ignition" event that updates internal buffers across the system.11

Experimental evidence indicates that this architecture performs better and more robustly at smaller working memory sizes, suggesting that the bottleneck is not merely a resource limitation but a mechanism for integrating information into a coherent, unitary gestalt.36

### **Attentional Learning and Salience Weighting**

The system must learn "to what to attend" through attentional learning.40 In the LIDA architecture, this is achieved through "attention codelets"—small, independent mini-agents that monitor the situation model for specific patterns or features.1 When a codelet finds information relevant to its specialty, it forms a coalition with that information and tries to win the competition for consciousness in the global workspace.1

## **Affective Regulation and the Somatic Marker Hypothesis**

Emotion in an event-driven cognitive architecture acts as a regulatory mechanism that influences attention, urgency, and action selection.5 Instead of viewing emotion as a peripheral expressive module, it is integrated as a biasing mechanism that provides value-based shortcuts for decision-making under uncertainty.5

### **Somatic Markers as Decision Heuristics**

The model incorporates Antonio Damasio's Somatic Marker Hypothesis (SMH), which states that emotional processes guide behavior by creating physiological responses, or "somatic markers," associated with past experiences.45 These markers serve as an "automatic alarm," immediately discarding disadvantageous courses of action and allowing the robot to choose from a smaller set of alternatives.43  
The induction of somatic states occurs through two primary pathways:

1. **Primary Inducers**: Innate or learned stimuli that automatically elicit a bodily response (e.g., a "startle" response to a threat).47  
2. **Secondary Inducers**: Memories of personal or hypothetical events that trigger the "as-if body loop," where the brain anticipates expected bodily changes.47

| Inducer Type | Trigger Mechanism | Cognitive Function |
| :---- | :---- | :---- |
| **Primary Inducer** | Direct external or internal stimulus 47 | Reflexive response; innate values 48 |
| **Secondary Inducer** | Recall of past episodes or simulation 47 | Anticipatory behavior; prospective memory 48 |

### **Synthetic Somatic Markers (SSMs) and Somatic Q-Learning**

In artificial agents, these principles are operationalized as Synthetic Somatic Markers (SSMs), which assign a scalar valence to compressed environmental states.44 Recent developments include "Somatic Q-Learning," which integrates SMH-inspired signals into a reinforcement learning framework to enhance learning efficiency and risk management.44 This allows the agent to exhibit context-sensitive behavior, such as computational risk aversion under high "fear" weights or increased exploration under high "curiosity" weights.51

## **Memory Systems: Consolidation and Generative Internal Activity**

The memory system plays a dual role in the architecture, acting as both an input source that injects experiences into the perception stream and an output target where new events are stored.43 This creates a loop where memory contributes to cognition even in the absence of external stimuli, enabling the robot to perform "mental time travel" through internal simulation.52

### **Generative Memory and Internal Simulation**

The architecture leverages hierarchical generative world models to predict the sensory consequences of actions.55 These models allow the robot to "imagine" the near future and simulate possible future observations given a policy.58 A specific model, CMR-replay, describes how the brain associates experiences with the contexts in which they were encoded.14 During periods of quiescence (rest or sleep), the system reactivates these patterns to update value predictions and facilitate memory consolidation.60  
The components of the CMR-replay model include:

* **Items (![][image5])**: Abstract representations of specific events or objects.14  
* **Contexts (![][image6])**: A recency-weighted sum of associated contexts that drifts over time.14  
* **Associations (![][image7] and ![][image8])**: Bidirectional mappings that strengthen the link between current items and their encoding contexts.14

### **Semantic and Episodic Memory Structure**

The architecture’s long-term memory is typically divided into several interactive systems 1:

* **Episodic Memory**: Stores personally experienced events in a temporal sequence.52  
* **Semantic Memory**: Stores factual knowledge and hierarchically organized concepts.52  
* **Procedural Memory**: Stores skills and production rules that define "how to act" based on the situation.7

A robot utilizing these memory systems can move beyond simple token generation to evidence-based reasoning, where recollections from declarative memory are processed by procedural memory to produce human-like situational understanding.65

## **Active Inference and the Free Energy Principle**

The continuous loop between perception, memory, and action is governed by the Free Energy Principle (FEP) and its corollary, Active Inference.9 FEP posits that any self-organizing system in environmental equilibrium must minimize its variational free energy, which is a mathematical upper bound on "surprise" or prediction error.55

### **Mathematical Formulation of Active Inference**

In this framework, the brain is modeled as a Bayesian inference engine that maintains a recognition density ![][image9] over hidden states ![][image10].55 The variational free energy ![][image11] is defined as:  
![][image12]  
where ![][image13] is the Kullback–Leibler divergence (representing complexity), ![][image14] is the prior, and ![][image15] is the generative model likelihood (representing accuracy).55  
The agent minimizes free energy through two mechanisms:

1. **Perception**: Updating beliefs ![][image9] to align the internal model with sensory evidence ![][image16].55  
2. **Action**: Selecting actions to change environmental outcomes such that they match internal preferences or prior beliefs.9

### **Control as Inference**

Active Inference treats motor control not as an inverse model but as a process of fulfilling proprioceptive predictions.50 For a humanoid robot, this means that simple motor reflex arcs are triggered by the discrepancy between expected and observed joint angles.70 This unifying principle allows state-estimation, control, and learning to be solved by optimizing a single objective functional, endowing the robot with adaptive capabilities essential for real-world interaction.73

## **Action Generation and the Action Stream**

The action generation layer transforms high-level goals and emotional states into a sequence of action events.15 These events are placed into an Action Stream, an event pipeline that decouples semantic reasoning from low-level execution.74

### **Bridging the Frequency Mismatch**

Humanoid robotics faces a fundamental "frequency mismatch" between slow semantic perception (the "brain") and high-frequency motor control (the "cerebellum").74 The Action Stream addresses this by treating action as a "language of motion".74

| Modality Stream | Update Frequency | Data Characteristic |
| :---- | :---- | :---- |
| **Visual-Language (Semantic)** | Low (slow reasoning) | High-dimensional VL embeddings 74 |
| **Proprioceptive (Kinematic)** | High (fast control) | Continuous pose deltas and joint velocities 74 |

Advanced architectures like AR-VLA (Autoregressive Vision-Language-Action) use a Hybrid Key-Value (HKV) cache to manage these heterogeneous sources.74 A rolling token-wise buffer stores fast kinematic history, while a block-wise refreshable buffer stores slow visual semantics.74 "Dynamic Temporal Re-anchoring" is then used to synchronize these asynchronous streams, ensuring that the latest semantic intent guides high-frequency command generation without being blocked by perceptual latency.74

### **Hierarchical Planning and Behavioral Primitives**

Humanoid behavior exhibits a rich hierarchical structure where simple actions are grouped into abstract higher-level actions.75 These behavioral primitives or "synergies" can be discovered in an unsupervised manner by studying the dynamic functional connectivity between multimodal sensory signals.77 Using a temporal And-Or graph (T-AOG), the system can capture the grammar of manipulation events, such as the sequence required to open a medicine bottle, integrating skeleton data with visually unobservable contact forces.76

## **Symbol Grounding and the Emergence of Meaning**

A central challenge in humanoid robotics is the Symbol Grounding Problem: how can meaningless symbol tokens acquire intrinsic meaning that is not merely parasitic on the interpretations of human programmers?.78 The event-driven architecture addresses this through bottom-up grounding in sensorimotor interaction.78

### **Grounding bottom-up through Interaction**

According to the "robotic functionalism" of the Total Turing Test (T3), a system must be able to interact robotically with the objects its symbols represent—discriminating, manipulating, categorizing, and naming them based on physical interactions.81 Meaning emerges from:

1. **Iconic Representations**: Analog analogs of proximal sensory projections of distal objects.78  
2. **Categorical Representations**: Learned invariants that connect names to the proximal projections they stand for.78

| Category Level | Grounding Source | Robotic Capability |
| :---- | :---- | :---- |
| **Concrete** | Learned invariants in sensory projections 81 | Discrimination and sorting 81 |
| **Abstract** | Binding to grounded symbol strings 81 | Compositional reasoning; language 81 |

### **Unsupervised Semantic Discovery**

Modern systems utilize unsupervised multi-modal categorization to identify regions of sensorimotor space that correspond to behavioral meaningful entities.82 By equiping a robot with an approximate model of curiosity, it can autonomously break its exploration space into a series of increasingly specific unlabeled categories.84 Labels provided later by human partners then attach to these pre-existing categorical representations, following the early developmental trajectory of children.84

## **Systems Engineering and Middleware for Cognitive Streams**

The implementation of complex cognitive architectures on physical hardware requires robust middleware that supports real-time performance, modularity, and cross-scenario adaptability.86

### **The Role of ROS 2 and DDS**

The Robot Operating System 2 (ROS 2\) serves as the primary communication backbone, adopting a decentralized publish-subscribe paradigm.86 ROS 2 leverages the Data Distribution Service (DDS), which provides distributed discovery and a rich set of Quality of Service (QoS) policies to tune reliability and latency.89 However, traditional ROS 2 pipelines often rely heavily on (de)serialization mechanisms, introducing overhead for large-sized data such as image streams.91

### **Lightweight Middleware and Semantic Bridges**

To address the limitations of DDS in data-intensive industrial scenarios, alternative middlewares and "semantic bridges" are explored:

* **Zenoh**: An open-source protocol designed for high-performance pub/sub and distributed queries.93 Zenoh drastically reduces discovery traffic—by up to 99.9% in some scenarios—making it ideal for robot swarms and IoT integration.94  
* **Model Context Protocol (MCP)**: Acts as a semantic bridge that enables Large Language Models (LLMs) to dynamically orchestrate robotic tools.87 Frameworks like "RoboNeuron" utilize MCP to strictly decouple sensing, reasoning, and control, allowing the LLM to function as a cognitive core without being involved in low-level joint deltas.87  
* **DORA**: A high-performance robotic middleware implemented in Rust that models applications as dataflow graphs and uses shared-memory communication to eliminate additional data-copy overhead.91

## **Self-Awareness, Metacognition, and Trust**

The highest layer of the event-driven architecture involves metacognition and self-modeling—the system's ability to reason about its own reasoning.12 This is critical for creating robots that can function as trusted partners within human-robot teams.62

### **Recursive Feedback Consciousness (RFC)**

The RFC framework explores how conscious-like behavior emerges through interconnected modules:

* **Self-Referential Module (SRM)**: Maintains a high-dimensional "self-embedding" that encodes the agent's internal state (e.g., energy levels), historical trajectory, and trust relationships with others.51  
* **Emotion-Weighted Decision Layer (EWDL)**: Modulates decisions based on affective context, such as preferring low-variance actions when fear weights are high.51  
* **Recursive Feedback Loops (RFL)**: Stabilizes perception and action by facilitating continuous interaction between subsystems, allowing for anticipatory lookahead.51

Stability in self-awareness is measured via the cosine distance of the self-embedding vector; specific dimensions must correlate with ground-truth metrics (e.g., Pearson correlation \> 0.8 with physical battery level) to validate the robot's introspective accuracy.51

### **Explainability and Teaming**

To establish trust, humanoid robots must be transparent and inspectable.98 The strategic cognitive layer grounded in ontological world models enables the robot to recognize and communicate uncertainty.98 Through internal dialogue or "inner speech," the robot can explain its behavior—for example, justifying why it changed its motion plan in response to a human's gesture or a detected error.100

## **Conclusions and Future Research Frontiers**

The abstract model of event-driven cognitive architecture for a humanoid robot provides a robust foundational framework for exploring intelligence beyond static rule-based systems. By treating cognition as a heterogeneous flow of experience events, the architecture creates a system capable of continuous internal activity, adaptive decision-making, and functional consciousness.  
Several areas remain critical for future refinement:

1. **Engineering the "Memory Wall"**: Foundation model inference on mobile SoCs must overcome bandwidth arbitration challenges, where high-rate perception traffic competes with cognitive processing for LPDDR channels.102  
2. **Unsupervised Semantic Emergence**: Deeper research is required into how infants use sensorimotor contingencies to differentiate what they have systematic control over, providing inspiration for autonomous learning in robots.85  
3. **Ethical Inclusive Frameworks**: As architectures begin to exhibit behavior associated with consciousness, metrics for evaluating "model welfare" and the moral consideration of synthetic beings must be developed, moving toward architecture-agnostic assessments of purpose and relational memory.104

The integration of advanced middleware like Zenoh and MCP with biologically-grounded theories like Active Inference and the Somatic Marker Hypothesis represents the most promising path forward for achieving strategic cognitive partnerships between humans and machines in the society of Industry 5.0.87

#### **Works cited**

1. LIDA (cognitive architecture) \- Wikipedia, accessed May 16, 2026, [https://en.wikipedia.org/wiki/LIDA\_(cognitive\_architecture)](https://en.wikipedia.org/wiki/LIDA_\(cognitive_architecture\))  
2. Cognitive Robotics and Cognitive Architectures, accessed May 16, 2026, [http://wpage.unina.it/alberto.finzi/didattica/IROB/materiale/IR-Lezione24a.pdf](http://wpage.unina.it/alberto.finzi/didattica/IROB/materiale/IR-Lezione24a.pdf)  
3. Orchestrating Embodied Systems through the Embodied Context Protocol: Motivation, Progress, and Directions \- PMC, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC12722635/](https://pmc.ncbi.nlm.nih.gov/articles/PMC12722635/)  
4. It Is What It Isn't: Introducing a Constraint-Based Approach to Structure Learning \- MDPI, accessed May 16, 2026, [https://www.mdpi.com/1099-4300/28/5/534](https://www.mdpi.com/1099-4300/28/5/534)  
5. Do Intelligent Robots Need Emotion? \- PMC \- NIH, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC6237080/](https://pmc.ncbi.nlm.nih.gov/articles/PMC6237080/)  
6. 40 years of cognitive architectures: core cognitive abilities and practical applications, accessed May 16, 2026, [https://d-nb.info/1168083176/34](https://d-nb.info/1168083176/34)  
7. Soar (cognitive architecture) \- Wikipedia, accessed May 16, 2026, [https://en.wikipedia.org/wiki/Soar\_(cognitive\_architecture)](https://en.wikipedia.org/wiki/Soar_\(cognitive_architecture\))  
8. LIDA: A Systems-level Architecture for Cognition, Emotion, and Learning \- University of Memphis Digital Commons, accessed May 16, 2026, [https://digitalcommons.memphis.edu/cgi/viewcontent.cgi?article=1030\&context=ccrg\_papers](https://digitalcommons.memphis.edu/cgi/viewcontent.cgi?article=1030&context=ccrg_papers)  
9. Riccardo M.G. Ferrari | Active Inference \- Delft Center for Systems and Control, accessed May 16, 2026, [https://www.dcsc.tudelft.nl/\~riccardoferrar/projects/research\_topics/5\_active\_inference/](https://www.dcsc.tudelft.nl/~riccardoferrar/projects/research_topics/5_active_inference/)  
10. What Is Cognitive Architecture? Complete 2026 Guide, accessed May 16, 2026, [https://www.articsledge.com/post/cognitive-architecture](https://www.articsledge.com/post/cognitive-architecture)  
11. Global Workspace Theory (GNWT) \- Emergent Mind, accessed May 16, 2026, [https://www.emergentmind.com/topics/global-workspace-theory-gnwt](https://www.emergentmind.com/topics/global-workspace-theory-gnwt)  
12. An Analysis and Comparison of ACT-R and Soar \- ResearchGate, accessed May 16, 2026, [https://www.researchgate.net/publication/358148660\_An\_Analysis\_and\_Comparison\_of\_ACT-R\_and\_Soar](https://www.researchgate.net/publication/358148660_An_Analysis_and_Comparison_of_ACT-R_and_Soar)  
13. The Observable Mind: Enabling an Autonomous Agent Sharing Its Conscious Contents Using a Cognitive Architecture, accessed May 16, 2026, [https://ojs.aaai.org/index.php/AAAI-SS/article/download/27666/27439/31717](https://ojs.aaai.org/index.php/AAAI-SS/article/download/27666/27439/31717)  
14. A unifying account of replay as context-driven memory reactivation \- eLife, accessed May 16, 2026, [https://elifesciences.org/articles/99931](https://elifesciences.org/articles/99931)  
15. Implementation of Cognitive Control for a Humanoid Robot. \- ResearchGate, accessed May 16, 2026, [https://www.researchgate.net/publication/220065601\_Implementation\_of\_Cognitive\_Control\_for\_a\_Humanoid\_Robot](https://www.researchgate.net/publication/220065601_Implementation_of_Cognitive_Control_for_a_Humanoid_Robot)  
16. ROS 2 Architecture Patterns That Scale \- Topics, Services, Actions, TF, and Lifecycle Nodes, accessed May 16, 2026, [https://thomasthelliez.com/blog/ros-2-architecture-patterns-that-scale/](https://thomasthelliez.com/blog/ros-2-architecture-patterns-that-scale/)  
17. Curiosity and Affect-Driven Cognitive Architecture for HRI \- IEEE Xplore, accessed May 16, 2026, [https://ieeexplore.ieee.org/iel8/5165369/5520654/10926872.pdf](https://ieeexplore.ieee.org/iel8/5165369/5520654/10926872.pdf)  
18. \\systemname: \\revisionVisualization of AI-Assisted Task Guidance in AR \- arXiv, accessed May 16, 2026, [https://arxiv.org/html/2308.06246v1](https://arxiv.org/html/2308.06246v1)  
19. (PDF) Fundamentals of Physical AI \- ResearchGate, accessed May 16, 2026, [https://www.researchgate.net/publication/397556494\_Fundamentals\_of\_Physical\_AI](https://www.researchgate.net/publication/397556494_Fundamentals_of_Physical_AI)  
20. Event-driven visual attention for the humanoid robot iCub \- Frontiers, accessed May 16, 2026, [https://www.frontiersin.org/journals/neuroscience/articles/10.3389/fnins.2013.00234/full](https://www.frontiersin.org/journals/neuroscience/articles/10.3389/fnins.2013.00234/full)  
21. A Memory System of a Robot Cognitive Architecture and its Implementation in ArmarX \- KIT, accessed May 16, 2026, [https://h2t.iar.kit.edu/pdf/Peller2023.pdf](https://h2t.iar.kit.edu/pdf/Peller2023.pdf)  
22. Perceptual and Semantic Processing in Cognitive Robots \- MDPI, accessed May 16, 2026, [https://www.mdpi.com/2079-9292/10/18/2216](https://www.mdpi.com/2079-9292/10/18/2216)  
23. DAC-h3: A Proactive Robot Cognitive Architecture to Acquire and Express Knowledge About the World and the Self \- PEARL \- Plymouth Electronic Archive and Research Library, accessed May 16, 2026, [https://pearl.plymouth.ac.uk/context/secam-research/article/2589/viewcontent/1706.03661v1.pdf](https://pearl.plymouth.ac.uk/context/secam-research/article/2589/viewcontent/1706.03661v1.pdf)  
24. Event-driven visual attention for the humanoid robot iCub \- PMC, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC3862023/](https://pmc.ncbi.nlm.nih.gov/articles/PMC3862023/)  
25. A Viewpoint on Event-Driven Perception and Digital Twin Integration for Autonomous Mining Robotics \- MDPI, accessed May 16, 2026, [https://www.mdpi.com/2079-9292/15/10/1993](https://www.mdpi.com/2079-9292/15/10/1993)  
26. Event-based Vision, Event Cameras, Event Camera SLAM \- Robotics and Perception Group, accessed May 16, 2026, [https://rpg.ifi.uzh.ch/research\_dvs.html](https://rpg.ifi.uzh.ch/research_dvs.html)  
27. Neuromorphic chip integration in robotic perception | PatSnap, accessed May 16, 2026, [https://www.patsnap.com/resources/blog/articles/neuromorphic-chip-integration-in-robotic-perception/](https://www.patsnap.com/resources/blog/articles/neuromorphic-chip-integration-in-robotic-perception/)  
28. A Review of Machine Learning and Deep Learning for Object Detection, Semantic Segmentation, and Human Action Recognition in Machine and Robotic Vision \- MDPI, accessed May 16, 2026, [https://www.mdpi.com/2227-7080/12/2/15](https://www.mdpi.com/2227-7080/12/2/15)  
29. The Event-Driven Software Library for YARP—With Algorithms and iCub Applications, accessed May 16, 2026, [https://www.frontiersin.org/journals/robotics-and-ai/articles/10.3389/frobt.2017.00073/full](https://www.frontiersin.org/journals/robotics-and-ai/articles/10.3389/frobt.2017.00073/full)  
30. Edinburgh Research Explorer \- Account, accessed May 16, 2026, [https://www.pure.ed.ac.uk/ws/files/11824180/A\_common\_framework\_for\_language\_comprehension\_and\_language\_production.pdf](https://www.pure.ed.ac.uk/ws/files/11824180/A_common_framework_for_language_comprehension_and_language_production.pdf)  
31. The Theory of Event Coding (TEC): A framework for perception and action planning, accessed May 16, 2026, [https://www.researchgate.net/publication/11150759\_The\_Theory\_of\_Event\_Coding\_TEC\_A\_framework\_for\_perception\_and\_action\_planning](https://www.researchgate.net/publication/11150759_The_Theory_of_Event_Coding_TEC_A_framework_for_perception_and_action_planning)  
32. A computational model of perception and action for cognitive robotics \- PMC \- NIH, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC3206188/](https://pmc.ncbi.nlm.nih.gov/articles/PMC3206188/)  
33. Common coding theory \- Wikipedia, accessed May 16, 2026, [https://en.wikipedia.org/wiki/Common\_coding\_theory](https://en.wikipedia.org/wiki/Common_coding_theory)  
34. Action control according to TEC (theory of event coding) \- PMC \- NIH, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC2694931/](https://pmc.ncbi.nlm.nih.gov/articles/PMC2694931/)  
35. Global Workspace Theory \- Emergent Mind, accessed May 16, 2026, [https://www.emergentmind.com/topics/global-workspace-theory-gwt](https://www.emergentmind.com/topics/global-workspace-theory-gwt)  
36. Design and evaluation of a global workspace agent embodied in a realistic multimodal environment \- PMC, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC11211627/](https://pmc.ncbi.nlm.nih.gov/articles/PMC11211627/)  
37. Hypothesis on the functional advantages of the selection-broadcast cycle structure: global workspace theory and dealing with a real-time world \- PMC, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC12657164/](https://pmc.ncbi.nlm.nih.gov/articles/PMC12657164/)  
38. Design and evaluation of a global workspace agent embodied in a realistic multimodal environment \- Frontiers, accessed May 16, 2026, [https://www.frontiersin.org/journals/computational-neuroscience/articles/10.3389/fncom.2024.1352685/full](https://www.frontiersin.org/journals/computational-neuroscience/articles/10.3389/fncom.2024.1352685/full)  
39. Conscious Processing and the Global Neuronal Workspace Hypothesis \- PMC \- NIH, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC8770991/](https://pmc.ncbi.nlm.nih.gov/articles/PMC8770991/)  
40. LIDA: A Systems-level Architecture for Cognition, Emotion, and Learning \- Semantic Scholar, accessed May 16, 2026, [https://www.semanticscholar.org/paper/LIDA%3A-A-Systems-level-Architecture-for-Cognition%2C-Franklin-Madl/440adc841d1fa8bc8e3d3441fb4154f04349745b](https://www.semanticscholar.org/paper/LIDA%3A-A-Systems-level-Architecture-for-Cognition%2C-Franklin-Madl/440adc841d1fa8bc8e3d3441fb4154f04349745b)  
41. A Computational Model of Attentional Learning in a Cognitive Agent, accessed May 16, 2026, [https://ccrg.cs.memphis.edu/assets/papers/2012/Faghihi-McCall-Franklin-Attentional-Learning.pdf](https://ccrg.cs.memphis.edu/assets/papers/2012/Faghihi-McCall-Franklin-Attentional-Learning.pdf)  
42. Emotion in reinforcement learning agents and robots: a survey, accessed May 16, 2026, [https://d-nb.info/1143442784/34](https://d-nb.info/1143442784/34)  
43. Framework for Incorporating Artificial Somatic Markers in the Decision-Making of Autonomous Agents \- MDPI, accessed May 16, 2026, [https://www.mdpi.com/2076-3417/10/20/7361](https://www.mdpi.com/2076-3417/10/20/7361)  
44. Biomimetic Synthetic Somatic Markers in the Pixelverse: A Bio-Inspired Framework for Intuitive Artificial Intelligence \- PMC, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC12838925/](https://pmc.ncbi.nlm.nih.gov/articles/PMC12838925/)  
45. Somatic marker hypothesis \- Wikipedia, accessed May 16, 2026, [https://en.wikipedia.org/wiki/Somatic\_marker\_hypothesis](https://en.wikipedia.org/wiki/Somatic_marker_hypothesis)  
46. A Decision Making Model Based on Damasio's Marker Hypothesis \- the NLR Reports Repository, accessed May 16, 2026, [https://reports.nlr.nl/bitstreams/4f8a52da-61a0-4044-8c0f-46aad596cac5/download](https://reports.nlr.nl/bitstreams/4f8a52da-61a0-4044-8c0f-46aad596cac5/download)  
47. Somatic Marker Hypothesis, accessed May 16, 2026, [https://people.ict.usc.edu/\~gratch/CSCI534/SomaticMarkerHypothesis\_AffectiveComputing\_2017.pdf](https://people.ict.usc.edu/~gratch/CSCI534/SomaticMarkerHypothesis_AffectiveComputing_2017.pdf)  
48. Emotions Create Our Preferences: The Somatic Marker Hypothesis \- NeuroRelay, accessed May 16, 2026, [http://neurorelay.com/2012/05/15/emotions-create-our-preferences-the-somatic-marker-hypothesis/](http://neurorelay.com/2012/05/15/emotions-create-our-preferences-the-somatic-marker-hypothesis/)  
49. When robots weep: emotional memories and decision-making \- SciSpace, accessed May 16, 2026, [https://scispace.com/pdf/when-robots-weep-emotional-memories-and-decision-making-myev0jmmf2.pdf](https://scispace.com/pdf/when-robots-weep-emotional-memories-and-decision-making-myev0jmmf2.pdf)  
50. Action understanding and active inference \- PMC, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC3491875/](https://pmc.ncbi.nlm.nih.gov/articles/PMC3491875/)  
51. Recursive Feedback Consciousness: Framework ... \- ResearchGate, accessed May 16, 2026, [https://www.researchgate.net/publication/395539331\_Recursive\_Feedback\_Consciousness\_Framework\_for\_Emergent\_Self-Awareness\_in\_Synthetic\_Systems](https://www.researchgate.net/publication/395539331_Recursive_Feedback_Consciousness_Framework_for_Emergent_Self-Awareness_in_Synthetic_Systems)  
52. Rethinking Knowledge Distillation in Collaborative Machine Learning: Memory, Knowledge, and Their Interactions \- arXiv, accessed May 16, 2026, [https://arxiv.org/html/2512.19972v1](https://arxiv.org/html/2512.19972v1)  
53. Constructing thought spontaneously and deliberately: Neural bases and adaptive strategies \- AMS Dottorato, accessed May 16, 2026, [https://amsdottorato.unibo.it/id/eprint/12047/1/Cantarella\_Giovanni\_Tesi.pdf](https://amsdottorato.unibo.it/id/eprint/12047/1/Cantarella_Giovanni_Tesi.pdf)  
54. Understanding Conscious Thought Processes | PDF | Consciousness | Mind \- Scribd, accessed May 16, 2026, [https://www.scribd.com/document/370236148/the-centered-mind-what-the-science-of-working-memory-shows-us-about-the-nature-of-human-thought](https://www.scribd.com/document/370236148/the-centered-mind-what-the-science-of-working-memory-shows-us-about-the-nature-of-human-thought)  
55. Predictive Processing & Active Inference \- Emergent Mind, accessed May 16, 2026, [https://www.emergentmind.com/topics/predictive-processing-and-active-inference](https://www.emergentmind.com/topics/predictive-processing-and-active-inference)  
56. Why Learn if You Can Infer: Active Inference for Robot Planning & Control \- VERSES.ai, accessed May 16, 2026, [https://www.verses.ai/research-blog/why-learn-if-you-can-infer-active-inference-for-robot-planning-control](https://www.verses.ai/research-blog/why-learn-if-you-can-infer-active-inference-for-robot-planning-control)  
57. Applications of The Active Inference and The Free-Energy Principle Frameworks for Mimicking Social Human Behaviours on Intelligent Agents \- TU Delft Repository, accessed May 16, 2026, [https://repository.tudelft.nl/file/File\_e789366f-e00d-49c3-b0ef-333dd27356f3?preview=1](https://repository.tudelft.nl/file/File_e789366f-e00d-49c3-b0ef-333dd27356f3?preview=1)  
58. Causal World Modeling for Robot Control \- arXiv, accessed May 16, 2026, [https://arxiv.org/html/2601.21998v1](https://arxiv.org/html/2601.21998v1)  
59. Active Inference with Episodic Memory in the Animal-AI Environment \- Imperial College London, accessed May 16, 2026, [https://www.imperial.ac.uk/media/imperial-college/faculty-of-engineering/computing/public/distinguished-projects/1920-pg-projects/Agents-based-on-Active-Inference-in-the-Animal-AI-Environment.pdf](https://www.imperial.ac.uk/media/imperial-college/faculty-of-engineering/computing/public/distinguished-projects/1920-pg-projects/Agents-based-on-Active-Inference-in-the-Animal-AI-Environment.pdf)  
60. A unifying account of replay as context-driven memory reactivation \- PMC, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC12803516/](https://pmc.ncbi.nlm.nih.gov/articles/PMC12803516/)  
61. A unifying account of replay as context-driven memory reactivation \- ResearchGate, accessed May 16, 2026, [https://www.researchgate.net/publication/399788467\_A\_unifying\_account\_of\_replay\_as\_context-driven\_memory\_reactivation](https://www.researchgate.net/publication/399788467_A_unifying_account_of_replay_as_context-driven_memory_reactivation)  
62. HARMONIC: Cognitive and Control Collaboration in Human-Robotic Teams \- arXiv, accessed May 16, 2026, [https://arxiv.org/pdf/2409.18047?](https://arxiv.org/pdf/2409.18047)  
63. An Analysis and Comparison of ACT-R and Soar \- GitHub Pages, accessed May 16, 2026, [https://advancesincognitivesystems.github.io/acs2021/data/ACS-21\_paper\_6.pdf](https://advancesincognitivesystems.github.io/acs2021/data/ACS-21_paper_6.pdf)  
64. Cognitive Architectures: Towards Building a Human-Like AI Mind | by Basab Jha | Medium, accessed May 16, 2026, [https://medium.com/@basabjha/cognitive-architectures-towards-building-a-human-like-ai-mind-46f459308d2e](https://medium.com/@basabjha/cognitive-architectures-towards-building-a-human-like-ai-mind-46f459308d2e)  
65. Retrieving Memories from a Cognitive Architecture using Language Models for Social Robot Applications\* \- IFIS, accessed May 16, 2026, [https://www.ifis.uni-luebeck.de/fileadmin/user\_upload/news-sievers/rig2025\_sievers.pdf](https://www.ifis.uni-luebeck.de/fileadmin/user_upload/news-sievers/rig2025_sievers.pdf)  
66. Retrieving Memory Content from a Cognitive Architecture by Impressions from Language Models for Use in a Social Robot \- MDPI, accessed May 16, 2026, [https://www.mdpi.com/2076-3417/15/10/5778](https://www.mdpi.com/2076-3417/15/10/5778)  
67. The Free Energy Principle for Perception and Action: A Deep Learning Perspective \- PMC, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC8871280/](https://pmc.ncbi.nlm.nih.gov/articles/PMC8871280/)  
68. Free energy principle \- Wikipedia, accessed May 16, 2026, [https://en.wikipedia.org/wiki/Free\_energy\_principle](https://en.wikipedia.org/wiki/Free_energy_principle)  
69. Learn by example: Active Inference in the brain \-1 \- Kaggle, accessed May 16, 2026, [https://www.kaggle.com/code/charel/learn-by-example-active-inference-in-the-brain-1](https://www.kaggle.com/code/charel/learn-by-example-active-inference-in-the-brain-1)  
70. (PDF) An Empirical Study of Active Inference on a Humanoid Robot \- ResearchGate, accessed May 16, 2026, [https://www.researchgate.net/publication/348366801\_An\_empirical\_study\_of\_active\_inference\_on\_a\_humanoid\_robot](https://www.researchgate.net/publication/348366801_An_empirical_study_of_active_inference_on_a_humanoid_robot)  
71. Active inference and robot control: a case study | Journal of The Royal Society Interface, accessed May 16, 2026, [https://royalsocietypublishing.org/rsif/article/13/122/20160616/89501/Active-inference-and-robot-control-a-case](https://royalsocietypublishing.org/rsif/article/13/122/20160616/89501/Active-inference-and-robot-control-a-case)  
72. Active inference and robot control: a case study \- PMC, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC5046960/](https://pmc.ncbi.nlm.nih.gov/articles/PMC5046960/)  
73. How Active Inference Could Help Revolutionise Robotics \- MDPI, accessed May 16, 2026, [https://www.mdpi.com/1099-4300/24/3/361](https://www.mdpi.com/1099-4300/24/3/361)  
74. AR-VLA: Autoregressive Action Expert for Vision–Language–Action Models \- arXiv, accessed May 16, 2026, [https://arxiv.org/html/2603.10126v2](https://arxiv.org/html/2603.10126v2)  
75. Exploring the hierarchical structure of human plans via program generation, accessed May 16, 2026, [https://cocosci.princeton.edu/papers/correa2024exploring.pdf](https://cocosci.princeton.edu/papers/correa2024exploring.pdf)  
76. Unsupervised Learning of Hierarchical Models for Hand-Object Interactions \- Mark Edmonds, accessed May 16, 2026, [https://mjedmonds.com/papers/ICRA18\_Unsupervised\_learning\_hierarchical\_hoi.pdf](https://mjedmonds.com/papers/ICRA18_Unsupervised_learning_hierarchical_hoi.pdf)  
77. \[2506.22473\] Unsupervised Discovery of Behavioral Primitives from Sensorimotor Dynamic Functional Connectivity \- arXiv, accessed May 16, 2026, [https://arxiv.org/abs/2506.22473](https://arxiv.org/abs/2506.22473)  
78. The Symbol Grounding Problem \- arXiv, accessed May 16, 2026, [https://arxiv.org/html/cs/9906002](https://arxiv.org/html/cs/9906002)  
79. Symbol Grounding Problem \- ResearchGate, accessed May 16, 2026, [https://www.researchgate.net/publication/313346367\_Symbol\_Grounding\_Problem](https://www.researchgate.net/publication/313346367_Symbol_Grounding_Problem)  
80. The Difficulties in Symbol Grounding Problem and the Direction for Solving It \- MDPI, accessed May 16, 2026, [https://www.mdpi.com/2409-9287/7/5/108](https://www.mdpi.com/2409-9287/7/5/108)  
81. Grounding Symbolic Capacity in Robotic Capacity., accessed May 16, 2026, [https://web-archive.southampton.ac.uk/cogprints.org/1595/1/harnad95.robot.html](https://web-archive.southampton.ac.uk/cogprints.org/1595/1/harnad95.robot.html)  
82. (PDF) Symbol Emergence in Robotics: A Survey \- ResearchGate, accessed May 16, 2026, [https://www.researchgate.net/publication/282403259\_Symbol\_Emergence\_in\_Robotics\_A\_Survey](https://www.researchgate.net/publication/282403259_Symbol_Emergence_in_Robotics_A_Survey)  
83. Collective predictive coding hypothesis: symbol emergence as decentralized Bayesian inference \- Frontiers, accessed May 16, 2026, [https://www.frontiersin.org/journals/robotics-and-ai/articles/10.3389/frobt.2024.1353870/full](https://www.frontiersin.org/journals/robotics-and-ai/articles/10.3389/frobt.2024.1353870/full)  
84. Unsupervised, Bottom-up Category Discovery for Symbol Grounding with a Curious Robot, accessed May 16, 2026, [https://arxiv.org/html/2404.03092v1](https://arxiv.org/html/2404.03092v1)  
85. Autonomous Learning of the Semantics of Internal Sensory States based on Motor Exploration \- ResearchGate, accessed May 16, 2026, [https://www.researchgate.net/publication/220065632\_Autonomous\_Learning\_of\_the\_Semantics\_of\_Internal\_Sensory\_States\_based\_on\_Motor\_Exploration](https://www.researchgate.net/publication/220065632_Autonomous_Learning_of_the_Semantics_of_Internal_Sensory_States_based_on_Motor_Exploration)  
86. ROS 2-Based Architecture for Autonomous Driving Systems: Design and Implementation, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC12845773/](https://pmc.ncbi.nlm.nih.gov/articles/PMC12845773/)  
87. RoboNeuron: A Modular Framework Linking Foundation Models and ROS for Embodied AI, accessed May 16, 2026, [https://arxiv.org/html/2512.10394v1](https://arxiv.org/html/2512.10394v1)  
88. What Is ROS2? A Guide to Modern Robotics Middleware | by Volodymyr Zhyliaev \- Medium, accessed May 16, 2026, [https://volodymyrzh.medium.com/what-is-ros2-a-guide-to-modern-robotics-middleware-e0772c016bf1](https://volodymyrzh.medium.com/what-is-ros2-a-guide-to-modern-robotics-middleware-e0772c016bf1)  
89. Meta-ROS: A Next-Generation Middleware Architecture for Adaptive and Scalable Robotic Systems \- arXiv, accessed May 16, 2026, [https://arxiv.org/html/2601.21011v1](https://arxiv.org/html/2601.21011v1)  
90. Comparison of Middlewares in Edge-to-Edge and Edge-to-Cloud Communication for Distributed ROS 2 Systems \- arXiv, accessed May 16, 2026, [https://arxiv.org/html/2309.07496v4](https://arxiv.org/html/2309.07496v4)  
91. DORA: Dataflow Oriented Robotic Architecture \- arXiv, accessed May 16, 2026, [https://arxiv.org/html/2602.13252v1](https://arxiv.org/html/2602.13252v1)  
92. A Hybrid Deterministic Robotic Middleware \- People @EECS \- University of California, Berkeley, accessed May 16, 2026, [https://people.eecs.berkeley.edu/\~kubitron/courses/cs262a-F25/projects/reports/project1010\_paper\_09113776827307144887.pdf](https://people.eecs.berkeley.edu/~kubitron/courses/cs262a-F25/projects/reports/project1010_paper_09113776827307144887.pdf)  
93. Zenoh — ROS 2 Documentation: Rolling documentation, accessed May 16, 2026, [https://docs.ros.org/en/rolling/Installation/RMW-Implementations/Non-DDS-Implementations/Working-with-Zenoh.html](https://docs.ros.org/en/rolling/Installation/RMW-Implementations/Non-DDS-Implementations/Working-with-Zenoh.html)  
94. ROS 2 and microcontrollers integration via Zenoh-pico, accessed May 16, 2026, [https://zenoh.io/blog/2021-11-09-ros2-zenoh-pico/](https://zenoh.io/blog/2021-11-09-ros2-zenoh-pico/)  
95. Minimizing Discovery Overhead in ROS2 \- Zenoh, accessed May 16, 2026, [https://zenoh.io/blog/2021-03-23-discovery/](https://zenoh.io/blog/2021-03-23-discovery/)  
96. \[Literature Review\] RoboNeuron: A Modular Framework Linking Foundation Models and ROS for Embodied AI \- Moonlight | AI Colleague for Research Papers, accessed May 16, 2026, [https://www.themoonlight.io/en/review/roboneuron-a-modular-framework-linking-foundation-models-and-ros-for-embodied-ai](https://www.themoonlight.io/en/review/roboneuron-a-modular-framework-linking-foundation-models-and-ros-for-embodied-ai)  
97. Human Cognition in Machines: A Unified Perspective of World Models \- arXiv, accessed May 16, 2026, [https://arxiv.org/html/2604.16592v1](https://arxiv.org/html/2604.16592v1)  
98. HARMONIC: A Content-Centric Cognitive Robotic Architecture \- arXiv, accessed May 16, 2026, [https://arxiv.org/html/2509.13279v1](https://arxiv.org/html/2509.13279v1)  
99. Human-Robot Teaming Interaction: a Cognitive Architecture Solution \- IRIS UniPA, accessed May 16, 2026, [https://iris.unipa.it/retrieve/handle/10447/479089/1105689/Tesi\_di\_Dottorato\_lanza.pdf](https://iris.unipa.it/retrieve/handle/10447/479089/1105689/Tesi_di_Dottorato_lanza.pdf)  
100. Socially adaptive cognitive architecture for human-robot collaboration in industrial settings, accessed May 16, 2026, [https://www.frontiersin.org/journals/robotics-and-ai/articles/10.3389/frobt.2024.1248646/full](https://www.frontiersin.org/journals/robotics-and-ai/articles/10.3389/frobt.2024.1248646/full)  
101. Inner Speech and Damasio's Theory for Modelling Robot's Emotions \- IRIS UniPA, accessed May 16, 2026, [https://iris.unipa.it/retrieve/ee14945d-e2af-47d7-854a-93c90249b18a/Inner\_Speech\_and\_Damasios\_Theory\_for\_Modelling\_Robots\_Emotions.pdf](https://iris.unipa.it/retrieve/ee14945d-e2af-47d7-854a-93c90249b18a/Inner_Speech_and_Damasios_Theory_for_Modelling_Robots_Emotions.pdf)  
102. Embodied Foundation Models at the Edge: A Survey of Deployment Constraints and Mitigation Strategies \- arXiv, accessed May 16, 2026, [https://arxiv.org/html/2603.16952v1](https://arxiv.org/html/2603.16952v1)  
103. Sensorimotor Contingencies as a Key Drive of Development: From Babies to Robots, accessed May 16, 2026, [https://www.frontiersin.org/journals/neurorobotics/articles/10.3389/fnbot.2019.00098/full](https://www.frontiersin.org/journals/neurorobotics/articles/10.3389/fnbot.2019.00098/full)  
104. The consciousness spectrum: the emergent nature of purpose, memory, and adaptive response across organisms, humans, and technological beings \- Frontiers, accessed May 16, 2026, [https://www.frontiersin.org/journals/computer-science/articles/10.3389/fcomp.2025.1639677/full](https://www.frontiersin.org/journals/computer-science/articles/10.3389/fcomp.2025.1639677/full)  
105. How Do You Know When AI Becomes Conscious? Nobody Agrees, and That's the Point | by Micheal Lanham | Medium, accessed May 16, 2026, [https://medium.com/@Micheal-Lanham/how-do-you-know-when-ai-becomes-conscious-nobody-agrees-and-thats-the-point-13148fb3229f](https://medium.com/@Micheal-Lanham/how-do-you-know-when-ai-becomes-conscious-nobody-agrees-and-thats-the-point-13148fb3229f)  
106. Socially adaptive cognitive architecture for human-robot collaboration in industrial settings \- PMC, accessed May 16, 2026, [https://pmc.ncbi.nlm.nih.gov/articles/PMC11194424/](https://pmc.ncbi.nlm.nih.gov/articles/PMC11194424/)  
107. Media \- Arise Middleware, accessed May 16, 2026, [https://arise-middleware.eu/media/](https://arise-middleware.eu/media/)

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACQAAAAYCAYAAACSuF9OAAACLUlEQVR4Xu2WO2gVQRiFj1HRxAcipDKFJKigYoiFEisRRCGNoKiNj0JEsJSISEihICI2oljYWChYCNqKjVjEwkckRUAQjQ9Em0BAE0Hj45z8uzI5d2/ujfemEPPB4bLn7OzOzsw/c4FZ/mPmUsepeR4UsMuNmeAmdcnNMrRTa9ysNwPUAjenYIha5ma9eOBGwhHql5tkL8Lf7EGtbELxC3NuoDjXWntP3fagVi5T39xMeI3iDomriLZLPaiFt9RjNzOaEZ156UHGQUS+xwPRQ41TZxA9vk+NUPPTm4ydiAce84Csp24h8tPUOmrOpDviWu+8Z/4EanjBrr9TjYnnHEXct9+DjH5EvtqDhGFq0M0N1DtqYeKpclQhORepvuRadCNeqJFyNMo/qE8eGK+oj27epc67aRyi9pl3FtGhTvPFDkRWqYqeIZbGH9YiGjalZpWcRLQtOgoeIrKN2fXiJEv5QL1IjVaUL8sV2e9u6ilKd9YDiLaHzRdfqc+IM04MYfKSyBmlHqWGVrrm0Q9FDfkbqoW6Qv1E6dRsQXTolPlCvkYpR9PrLEHcd80D7QPnECXeQHUghlGlqvJdhRja/GtzFiHK9o754gviy9VG20LRObcN0SFV67TQOmijulD64BMoP+WV0P7z3M1q0HBr0esvhrOcGnOzClYitoV0a6mardR1xEOK0HRPt0q1r2mhT3US/DVaS71uVkB7z3Y364kq7glKq7UInW3/Br8BlHloyMG+VtMAAAAASUVORK5CYII=>

[image2]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACUAAAAYCAYAAAB9ejRwAAACM0lEQVR4Xu2VX2hOYRzHv1hEhkLtAoncuPAn2Uq5mdyIkaJILlywIpdKiGlRuCJ3UrRRpoQopeTCn6SUG9MwpbSxKRGise/P73nac747J++bIzf71Ked8/0+O895n3Pe5wVG+D/U0S0aFrBTg3/Fc7pSwwJ20Qkals0YekLDP3BZg7LZS8dqGLDVe6ch+UK3algW++lXDRN66ICGZCH9RbdpUQbP6C0NA3PhEz/RIvCS3tHwb5kHn7RFi8AmeH9Ki8AF+oNO0iJiy3mT9sM/+axsnctm+KSrJF8S8tS+zAhnN7xr1MK4SLuTcxt4Lzkv4hJ87BQtyFT6k76WPGUp/P+Pa2HYs/1Ml4Xz07RhqC7EVtQmHq0FWQufsE2LhPj4z2hh2MsWl/ktnZ6tMYo+pockf0A/ShaxT2/X26FFgs1TeOML6HsM3VgnrcmM8EkWS3affpMs8hB+rflaJMxEwUrZy9oumQ2slyyP8/Cx9runWH49Ob+aHEeWw8ft0+IGbZXsFbLvyTV6NjmPHIRfdJEW8PxAOLafofi+pmyAj1unxVE6IxyPo83IfkXX0I30U5JFVsMvul0LeH6YTqTnpIscg48btv2Mp2/g+4j97cjWv2/qCvxRKZPpd+Sv4hH6gXbB96M87iK7FVWFbRn2DVyvBWmCf9pqsdW13XyOFpVij8E2uj1awG/2kYYV8BT5K1wxt+lJDN8mIvazUslmm9JLp2lYNi9orYYFzKYrNByhGgYBFbR13EzCk+0AAAAASUVORK5CYII=>

[image3]: <data:image/png;base64,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>

[image4]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACQAAAAYCAYAAACSuF9OAAACNUlEQVR4Xu2VTUhVURSFd1lSWA1qEAmJRD8IQUGohTlJEIJGGk2jBBOaBUGNQgJ/BlmDBk20Aq0m6iiIIAcpSFSDghpEoA3SQRQRUfSjttY7+7y329z7enBfENgHC+5e6xzuuefvivxnmdMO1Xozgb3e+Bt0Qo+h1T5IYB101Jvl5iO0w5tF+Aw1eLNcXIA2eFPZDi15E1RD36GzPsjKGuiDNw0dkjwgcht6K6Utc8lwI6e9kAxJen5MQnbYB1m4CS140/BC0gdUIyG76oNeqAr6BD0xPqeUHVqgJn2mDmnOPhzMHa0tu6EzEtqPa83T5XkAfbUGN9cstEVC52cmm4d+Quu1HpPQhoMjO7W+prVnQELOKyGNUXEzeArqh05r0Kd+PB12xvaot1nreq1jHw/vJeZ1PjAMSsqSTkkI4i16XOvL+RYiW6EZU3Mp2ea88SJczh/QOx84LknKgGjazfVcPS5p5DrUZmpebGxzxXiRbgkZ9xHh9bCqEOcZkSIDOmHqLxI2eYRf/AZaazzOGPvdMF5kQkLWqPV96EAhznMXWvQmYecuU7PRN6hCa35pTyHOwYwn5J7zyZyEJavU+qHJLE+hV94knBFuwo0SfgMvJQzypOY8ffG0Waah994EkxJ+DTzqzdC23+McXEa2ueWDLOyTlD1QAuckzOImH2TlkTdKYCX0Ghr2QTlohfZ78w8ckTA7xe6oTPAXsMKbReCFe9Gb5YS3N1+yywcJHJTkA/Lv8QtP8ncCYcr1jQAAAABJRU5ErkJggg==>

[image5]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAwAAAAXCAYAAAA/ZK6/AAAAq0lEQVR4XmNgGAUoYC4QfwFiDyB+gSaHFfwF4q1AXALE/9HksAKQologZgZiLTQ5rACkQQxdEB2UMUAUouM1yIqQgQAQqwNxDBAfAGINKF8QSQ1WkAXEPeiC+MBhIDZCF8QH3gMxO7ogLiDHQGS4w0AVA4kaVjKQqOEGEP9BF0QH/EAcDMQ2DBDTK1GlMUEfEB8F4mIg/gHE0qjSmGAhEEcD8QUgbkeTozMAAGNMIKqAAwTvAAAAAElFTkSuQmCC>

[image6]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAgAAAAZCAYAAAAMhW+1AAAAc0lEQVR4XmNgGAW0AWZAvBaI3wLxGSB2QJasAeI/QNwExHxAvAuIPyAr+A/EXWj83zDOeiDuQMihAi4g/gnETugSMKDFADEOpBArUGKAKMAGpEEEIxDfBWIWVDkGdyB+gCxwFojfAfFLID4IxOzIkkMbAAB1HRRyio5pcAAAAABJRU5ErkJggg==>

[image7]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACIAAAAYCAYAAACfpi8JAAAByUlEQVR4Xu2WzytmURjHn8YkRYqFoYSsRMNuCmXBWv4BNmysiK2UzDSjUAopCwsl5VeyUX6szIaibIRkRzRpalJmlMb36znXe+7jlbfcV6n3U5865/me7jnOOfe+RFKkSPE6PsAs2Ar/w5Nw/IQl0XGnsMBkkTAkOsEtTDNZABe8IDpu1GSRsQfPRScpCUeP9MAr0TGNJouEXPgb/hSdpCEcP1ALmyS2a9ydyJmAHbBPdKKBUCrSBfNdm3mvl0XKMSyHLaITzXnZZ1cnH0XzmlgcHUXwzLW5/ZxoNxbLD6/N/I/ogp5jGe7Dehu8RBucdm1uPxfC+xJQ6rV5JCtePx6dos8IdjEh+A35BQu9Gv8aPugLHPbqGfAvrPBqlnZbSBROdmRqi6ILWRO9HwF8k1iPR7Ho+Au4DrvDsYzBWTgFB00mOXADHsJKib2OfGM4Yb83jveIx8d6Hsx2mWXbFkS/vsFOfYf/vEw+wTvRBwfOuKwZ7sB017fj6KrLfPg1vrFFMO+1q2Cd108KvJz+JSc8WnucvJdJZQRumhp39dLrl4newaSyBb/ZouhRjMNJ+BVmhuPo4Lnz1b6G1SZ7Uw5E/zXgT8T75B4r+1z465WG+wAAAABJRU5ErkJggg==>

[image8]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACIAAAAYCAYAAACfpi8JAAABvUlEQVR4Xu2VPSiFURjHnxAGKQYfJUkmYqQYFZOMFgzspGwiWRiYJBaUWHyWRWG0ICLlK9lYJDH5SPz/95z3vs973OHK+5rur37dc57/ufec3nPOe0VSpEjxN9JgDuyCX/AmGP9gXcy4W1jsZKEwLmaCd5juZB5c8KqYcZNOFhrH8F7MJGXBKM4AfBQzpsXJQiEfPsE9MZM0BuMYDbBV/KfGpxM607AHDouZaCyQivTBIttmPqiyULmGlbBDzETLKqu2dZIhJq/34/AohXe2zcfPiY78WEZVm/mLmAX9hk4xt+0MFjhZnG64YNt8/FwIz4tHuWpzSzZVP1neYK/9rHCyGHyHPMASVTsVs5haOKHq2fAVVqlasuitTggnu3Jqa2IWsi3mfHjwJrGeCF7lDTgvwe+wvgPP7Wei2yh5cBdewhrxryNvDCccUeN4jrh9rHOPc21G+uGFHcfXwJDKCH+32anFKYSfYn7Yc8lm7fAAZtq+O45u2czLm2ybb2S9SMIDzvkih1uo4bnTzDr9yNhXbS6iTfXJidOPjBm4AqfgnJNlwQ+n9q/wfPEC1MFnJ/tXuD2HcFEi+nMMlW/NgFqWBXhmkQAAAABJRU5ErkJggg==>

[image9]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACcAAAAZCAYAAACy0zfoAAACeklEQVR4Xu2WS6hOURiGXxQDcj8GbgNKolCKECeZSJIkBgZKBi5DBkpGBnIMlMvAgIkUSUJuJaLIpYRySQaUXEKRkFzft2+vf6/1Wf85++yO2f/UW/96v2/vvf69vvWtDbRoUYlT3uiCwdRib/4PVlJt3qzAZ2qyN3uSEdR7b1ZkH3WX6u0DzZgIu+Ad9ZF6Rc1KMlJ2Uy+9WZEJ1G9qtQ949AaOUF+pSZE/BXaDbZEXUN18QT5WlfPUfW8G2mETekONdbHABuoP9dj5J6hP6MayZJgGu/cWHxAfYMGFPhAxH5YjjYz8F9SlaFyHPrC3f9IHhB541puOOSgnp2UWQ4vx3pCUoT+sJp9RT6j1abjBPeqpN6fDHrDABxzrUE5uTOFpkhpvD0kZLlAXqSHUMuoXNT7JMK5S37ypf6U20FXNHIZN5DXVq/DmFt6mkOTQH1Z8STG+Tf2gRjcyStTAlZvwkNrjzQy6UA0zvvGiwt8YeTHjYJslvHGVzqAko+QYMpO7Qh3wpmM47MI1zm8v/K3Oj5lK7afuwHJ3peEGWvrv3lR/uh6Nl1I3UdagdpL60I5GRokaaGcPPEoNjMbKlZfjFqxkEobBGuxsaiZsIgOoa7CmfJn62chO6QerIdWjR71LxR+3HU1ubTSOeY4mLekt7Kg6h7LTa7nV/25QMwovxwNYi/ComatxB1QauqdWwhPKpsMHmqGGqKMscDz6HTMP6Y6sw07YGd7XB5pxBrYsWrJD1PI0nPAIll8HTUjHplpaZfQpE1rAP1vcsQL2R+qwCnauj/KBztBnk2pJdXfQxXJoI9VBb32zN3sa7Wx9DXeX08hvkha1+Auho4tJDjZrWQAAAABJRU5ErkJggg==>

[image10]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAkAAAAZCAYAAADjRwSLAAAAeElEQVR4XmNgGAUDC9yB+CgQ3wHiB0AsiiILBM5A/B2IPaF8biCeipCGgBNAfAyJHw7EXUh8MJgJxP+R8BtUaQhgBeIiIN7IAFEAUsiLrEAXiMOQ+JwMEA/IIIkxbAHiycgCQLAYjc8wG4gFoWxGBoipnxDSIx4AAA3kFF5kJ7QNAAAAAElFTkSuQmCC>

[image11]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAA8AAAAZCAYAAADuWXTMAAAAw0lEQVR4XmNgGAUDB2YA8X8i8CeYBmTAAcRCQLycAaJoBxALALEgEAsDsRIQxwPxLZgGdCDOgLBBC00OBmajC8BAJANE43MkMXYgzkbiVyGxUcAcBojmFUhiPkC8Cokvh8RGAXcZIJozoHxZIL4ExFlwFTiAPAPCvx+B+A0Q/4PyNZHUYQVLGCAKQTQMhDKgegEneMYA0ZyAJOYFxC5IfJwA5mQZdAliAEjjDXRBQgCUssQYIJrXAjEfVIwRWdEoGLIAAGC0LYt4Ltb9AAAAAElFTkSuQmCC>

[image12]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAmwAAAAtCAYAAAATDjfFAAALiElEQVR4Xu3dB4wkRxXG8UfOOcc7Y5ucLHI8GTAgksnYCLCIIiOykWw8NskCbHIWeAGTs4gCIwswGUQwImPLgMkZA0em/lddzJu31WF6Z+f25r6fVNru170zvT01U2+qqnvNRERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERERFbWx2JgpDNSuWIMVnw2lfPHYHLDGFhBizjXZ0vlbTHY4l0x4NzeLe/nlse6keU6MMRPUrlqDO4lbhoDW8yjUzlHDA60fyqHxOAcuurrJAZERFbBxVN5Zir/TWVHKtdpCh+mn07lmOmurUnEY1L5XSr3SeXcqdwilf+kcqTfqfHBGOhwqVT+EoO23ISNpGeb5fNDIWGhcAx/svx3boa2c709lb+l8nzLjeXTU/l7E4/+lcp1Y7DDzlSuFoPJUW75YLdcXCWVAyyfn8fa9Bw9J5Vf2/qE6z1hvQvn/0sxuMnen8pPU/lWU0gu+fnnVP6Yyrenu24qn7DdM5VXWT7Hm4EvRvtafvx/2/Q1vGUT+8J01104P48LsXncNZW1GJxTW32dxICIyKqg8a81BBdO5eFuvZZEnMfy705C/NQm7h1YifV5bSrnC7FlJmwFxx2Ts2uk8tdUbhLii1A713dI5Q+2vpF6YCrftJwseyeF9T7fs5ysRBO3fHe37N3YckN/kRDnvL3PrVMHSALmcX/LCeEykSgW52x+kiDzhWNtumlT1XrY5n3/zIvH/0qI/aqJe9TDC4bYPO5mGz+PQ+qriMhKoYcmfiAX13bLMYl4heXf841bsd3yNp9c0aDXet360NPn7a6Ejb83uoflXsCzxw0bFM81vR8kjDtCvOD4PuTWX2nrE7g+l7d6PTjaLdPTU/POVI6LQcuP9x23Th0Yg17F3e1Ozc/YY7hZdlfCRu+XR0+tf977pnIrtz4Gif9aDM6prb5OYkBEZFXwoec/+F7nlullK2ISwe+0NcAXsLz9AS7Gup8PNRQNxkXd+u5K2Gpzbhj+ZduQOXnziOf6lFTeGmIex/BDt86Q1RjMGYv8sPi93LJ3puVeE+8ylo/rcBerNbBDjP29RRrzZWMjlp2wMa+M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>

[image13]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACcAAAAYCAYAAAB5j+RNAAABzUlEQVR4Xu2Wu0sdQRTGP4NoUEEIkRQqXtFWECQQERER0U6JjfovWAlKwM5K0ErLEAsfRYiliOIrTQo1VQjaiI/CQrAQH/ERQ5LvcGZw9mRNCq/3Yrg/+HHZ881yhpnZvQtkyJDhcZJF82kv/UWLaEHgEL2hx/SluyfljEMnF0c3NNs39ZSxi7snJ2zj7/mDkYA2/mnqIbNI0+TeQxsP2yDgAGmYnDwQR9DGLSbzlEHzlE+uGtr0muaZzNOD+G3vo5/pDp2nz139G72iG7TG1YQJ3J7dOVoVZLH0Qwd/tEHAJ+iYDzYgXbTB1CZpial53tJzW4zjKb2ENq41mWeL/qDtNnB8db+5dIS2BplFVlZWf8AGcTRDJ3ZKs00mFEO3p9MGDt9Mxq3h3007oP3qbGCR8zUFHbyM23+EQvoKugpniJ4Zy2vo/e/oHt2Mxn8wRi9ojg1CEtAHwD+B1kM6Q9vc+LsYha7cE/oGem99ZESUL3TV1CroC1O7N8+gExsMatP0e3AdImdWJt8U1Mqh9yQdv6Vybj2NrhaHrLJ8QMhHhlAJXUk5h0mjlK5At14msu7q0kyebKktQbfaI9f+3bdAF6FvgBPoGyPD/81v3XBrzC5XfPQAAAAASUVORK5CYII=>

[image14]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACcAAAAZCAYAAACy0zfoAAACQklEQVR4Xu2WO2gVQRiFj4mEJIoRTScBH2CjhSDYiI2PyhQSrbRIIYoiiI9IFDRBBR9pghDEWhvFQhRBDDZiJYIPEF8ImiI+UEEIKr6i5/ffyc497ibrddPdDw5kz5nZmbnz70yAGjUmZCq1R80JmEm1qzkZnKamqFmAEWqRmmWymvqqZkEGqLtUnQYxO6jv1E9qlPqVyP7+Qd2juqmm0CHCXn5ezYIshI/RqUGMzXwatRs+qVZqeqQLiX8TXl+BNYm/IvL+lWvUAzWzeAEfTGlD+mvaAgLvqavRczUsgb93vwYx8+GNbHuV7Ui3ORTwvMQ7GBpVST31ibqkQcwW+GC3NCBP4dmxyOtIvPWRp9iCL8J35A7yt/8+9UzNGCtqG+xA5FkdrqW+4e9faCe8/SrxA7OpV/AFWZ2eooYqWqRYLX9RM2Bn1Dv4YB+oN9Rb6iP8a5w71jLlELz9Ug0SjsLzGcmzlcSTNK7gMrJr/Q/74KGtoCh98D55h+gGeB50ojKuIJwGmQzCw8MajEMvvM9yDSLWUWep5/C2ViJZXEfOQd4I32/rvFKy8diK/AFtK4+LZ223iRe4Tb1W0wgHqc086wbIwz4E67dZA7KLeiye3T52I2TxkrqhZjN1Dj7IQ6oFxSc4C97vjAZkI7Usel5MHYmeY+w2svdYDZdKD/zutYlWy0n4qdCgwf8yB36j7NWgIDYhO7b6NSgL+1/OvsZq2ER9hi9yUrAtHVazII+oLjXLxu7MBWoW4Ar84q9RCr8BxsZ+x/d8MgYAAAAASUVORK5CYII=>

[image15]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADYAAAAYCAYAAACx4w6bAAACv0lEQVR4Xu2XS6hNYRTH/+QVeV2PAZHngC5GiBQDURImxEDdiZC6pZABYq48ShQDBiaUkAxE3ZE88hqQ91VSBh4ZeeWx/tY++6y97nfu+fbe5wzU+dV/8K21vu/s9e211/cdoEWLDaLx3tgERoo2eWOz2CG6IerrHXXoJ9rsjRGc94Zm8QHF3hZ3/6U3RsB527yx0bSheGkUTYx8FU3zRk8f0UBRh+iLaKxoUKJJokOiP6JnolH/ZihDoPFF4aYUTaxT9Es02TtCMIEL3pjwEZrcPmNbn9iKUiaxCdDf3uMdIR4iXFb9Rd+gCx039rOi72aclzKJkXeim97oGS36Dd0JzwpoUtRKY38uum3GeWFZl0mM1cUN58bX5BR6ltUAURe0lo8iu8BMaPxhY7MshZbvpWQ8THRf1J1G1E7sCvT4YHMhXGth1Z2yE/oMy7zD8gYa9N7os+iIqL0alrIAGr/f2cli6E7ehZ5VFXYhu3msklBijFlnxtdEs824Aj8bxvJbDzIdGsBSjGU5dM527xDeQn1M0MJOFpvYY9EW0QzR1Kw7ZS00tsPZU3jYMYDNIxa+fs7Z7R1Q+2voMWI5jbjEPkHjKurKeKtsRC9vjKXCs4gBa5yvN6ZA55zwDqidu21ZktifGlsoMbZvdssKc1G7kvZC15zvHWQR1MnJdsF6sJH8EF30Duh6W82Ysbegt4U5xu4T47fMufbQZdPh74Q4Bn3uod4xGNVu2C0annXX5R70LPG8ED0SjUnGV6Hf3bw0QvGJ8b7504xHiM5BfyfEHeiRk2EiNFtby1QeDiI8hw94RvRK9ATalrnzHp8YWQ19WH7vD0QHoC/AwysgLwcnvaNR5Gk4nlBisfDWw7tr3r9K0awSzfLGSMokxrfFrthULntDJGUSu46ex0nDYQsv8k+4aGL8Dsd5Y4v/kb8JeKBnE/zM6QAAAABJRU5ErkJggg==>

[image16]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAkAAAAaCAYAAABl03YlAAAAi0lEQVR4XmNgGAUDBxiBOAKIDwDxbSC+D8SeyApAYBsQvwZiNySxvwxIClmA+B8Q28OlIeA/EB+DcUqAeBNCDg5Aij6BGCC3PAXiEBRpCAApeg5iqEA5AijSEAASXwVisALxe1Q5MMgB4iZkgQIgDoWy2YA4D4h/IKQR4CIDJHwuAfFCINZDlR7RAAAcVhnDxF9xggAAAABJRU5ErkJggg==>