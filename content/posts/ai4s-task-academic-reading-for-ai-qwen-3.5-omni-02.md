+++
title = "Academic Reading for AI: Qwen 3.5 Omni Technical Report"
date = 2026-08-20
math = true
tags = ["Academic Reading for AI", "Large Language Model", "Qwen LLM", "Academic Reading"]
author = ["Mengyao Zhu"]
+++

# 1. Qwen 3.5 Omni: Architecture, Training, Evaluation, and Omnimodal Capabilities

## 1.1. Overview of Qwen 3.5 Omni

Qwen3.5-Omni is a new-generation **fully omnimodal large language model** introduced by the Qwen team in 2026. Within a unified framework, it integrates the understanding, reasoning, generation, and action of text, image, audio, and audio-visual content. As a major evolutionary version of the Qwen-Omni model family, Qwen3.5-Omni adopts a **Thinker–Talker architecture**, in which the Thinker is primarily responsible for text generation and multimodal understanding and reasoning, while the Talker generates streaming speech tokens using the high-level representations provided by the Thinker. The model scales to hundreds of billions of parameters and supports a 256k context length. Architecturally, both the Thinker and the Talker employ a **hybrid-attention mixture-of-experts architecture**, or hybrid-attention MoE, to improve the efficiency of long-sequence inference. The model undergoes native omnimodal pretraining using large-scale text data, visual data, and more than 100 million hours of audio-visual data, thereby developing strong omnimodal capabilities. For speech generation, the model introduces **Adaptive Rate Interleave Alignment**, or ARIA, which dynamically coordinates the generation of text units and speech units to improve the stability, naturalness, and prosody of streaming speech synthesis. In addition, the model supports multilingual understanding and speech generation, zero-shot voice customization, controllable audio-visual captioning, and precise audio-visual grounding. Overall, Qwen3.5-Omni is designed as a native omni agent model that can not only perceive and reason across modalities, but also autonomously invoke WebSearch, execute complex FunctionCall operations, generate speech outputs, and conduct real-time streaming interaction, thereby extending omnimodal understanding to tool use and agentic action.


## 1.2. Detailed interpretation of the introduction

The introduction primarily explains the motivation behind Qwen3.5-Omni and its positioning within the Qwen-Omni series. The paper first points out that human interaction with the real world is inherently characterized by omnimodality and an agentic nature: when understanding their environment, humans simultaneously integrate visual information, auditory information, and linguistic information, and respond through text, speech, and goal-directed tool-mediated actions. Although existing large models have made substantial progress in understanding capabilities and reasoning capabilities across text, vision, and audio, many systems still operate mainly within a **passive perception-response paradigm** and remain limited in terms of scalable agentic behavior, real-time interaction, autonomous tool utilization, and cross-modal reasoning. Qwen3.5-Omni is therefore designed as a **native omni agent model** that processes text, vision, audio, and audio-visual information in a unified manner from the stage of native omnimodal pretraining and further acquires action-oriented capabilities such as WebSearch, FunctionCall, speech generation, and real-time streaming interaction. Compared with Qwen3-Omni, the major technical upgrades of Qwen3.5-Omni include a hybrid-attention mixture-of-experts design, **long-context modeling of up to 256k tokens**, a multi-codebook codec representation, ARIA-based dynamic text-speech alignment, and broader multilingual training. These improvements further give rise to three major categories of capability: controllable audio-visual captioning, comprehensive real-time interaction, and **native omnimodal agentic behavior**.

## 1.3. Detailed interpretation of the architecture design

The architecture design of Qwen3.5-Omni is built on the **Thinker–Talker architecture**. The Thinker is responsible for text generation and unified multimodal modeling of information such as text, images, audio, and video. Visual signals are processed by the vision encoder, while audio signals are handled by the Audio Transformer, or AuT. The Talker performs contextual speech generation based on multimodal inputs and the textual outputs produced by the Thinker. The overall backbone adopts a **hybrid mixture-of-experts design**, or hybrid MoE, to improve scalability while balancing model capacity and computational efficiency. To model temporal relationships in audio-visual content, the model uses explicit timestamps and temporal position IDs for temporal modeling. Position indices across different modalities follow a contiguous position numbering scheme, while the corresponding representations are anchored through absolute time, thereby strengthening cross-modal temporal alignment and supporting streaming inputs. For speech generation, the Talker uses a **speech representation based on Residual Vector Quantization**, or RVQ, and employs a Multi-Token Prediction module, or MTP module, to predict a multi-codebook sequence, after which the Code2Wav renderer progressively synthesizes the corresponding waveform. Notably, the full name of ARIA is Adaptive Rate Interleave Alignment rather than Adaptive Resonance Interleave Alignment. ARIA converts the conventional dual-channel generation paradigm into a **unified interleaved single-stream formulation of text tokens and speech tokens** and uses an adaptive rate constraint to coordinate the generation progress of the two token types, thereby reducing problems such as skipped words, incorrect pronunciation, and ambiguity in number rendering caused by mismatched tokenization rates between text and speech.

## 1.4. Detailed interpretation of the pre-training stage

The **pre-training of Qwen3.5-Omni follows a three-stage structure** and uses both unimodal data and cross-modal data from the early stages of training. The training data includes image-text, video-text, audio-text, video-audio, video-audio-text, and pure text corpora. The first stage is the **Encoder Alignment Stage**, or S1. The LLM component initialized with Qwen3.5 parameters is kept fixed, the vision encoder adopted from Qwen3.5 processes visual information, and the audio encoder initialized with AuT processes audio information. The two encoders first train their respective adapters and are then further trained themselves so that visual and audio representations can be better aligned with the fixed large language model. The second stage is the **General Stage**, or S2. All model parameters are unfrozen, and the model is jointly trained on approximately 4 trillion tokens of multimodal data, including about 0.92 trillion text tokens, 1.99 trillion audio tokens, 0.95 trillion image tokens, 0.14 trillion video tokens, and 0.29 trillion video-audio tokens. The sequence length in this stage is 32,768, and the use of more diverse multimodal data and tasks improves the model’s understanding and interaction capabilities across auditory, visual, textual, and audio-visual information. The third stage is the **Long Context Stage**, or S3. The maximum token length is increased from 32,768 to 262,144, while the proportion of long audio and long video in the training data is also increased to strengthen the model’s ability to understand complex long-sequence data. It is important to distinguish this stage from the Talker post-training process: the 64k context length, continual pre-training, or CPT, and Qwen3-Omni-Captioner belong to the Talker’s post-training pipeline rather than to the third stage of Qwen3.5-Omni’s overall pre-training.

## 1.5. Detailed interpretation of the post-training stage

The post-training of Qwen3.5-Omni is not a single unified four-stage process; instead, different training strategies are designed for the Thinker and the Talker. The Thinker undergoes three stages of post-training. The first stage is **Specialist Distillation**. The research team first trains multiple domain-specialized teacher models through supervised fine-tuning, or SFT, and reinforcement learning, or RL, covering text, agentic tasks, coding tasks, foundational reasoning tasks, vision, and audio domains. The domain-specific data generated by these specialist models is then used to distill their capabilities into the unified model. The second stage is **On-Policy Distillation**, or OPD. Because a gap remains between the quality of responses generated under audio queries and text queries, the training process first obtains responses under the corresponding text condition with higher fluency, reasoning quality, and task completion, and then uses them as distillation targets for audio-conditioned queries, thereby promoting modality-consistent generation. The third stage is **Interaction-Aligned Reinforcement Learning**, which targets issues in multi-turn conversations such as language code-switching, persona inconsistency, and degraded instruction-following in long contexts. The Talker, by contrast, follows a four-stage training pipeline. The General Stage uses more than 20 million hours of multilingual speech data. The Long-context Stage improves speech quality through data quality stratification and continual pre-training, or CPT, while extending the maximum context length to 64k tokens. The Reinforcement Learning Stage uses Direct Preference Optimization, or DPO, rule-based rewards, and GSPO to improve model behavior and training stability. Finally, the **Speaker Fine-tuning Stage** strengthens target speaker characteristics, naturalness, expressiveness, and controllability.

## 1.6. Detailed interpretation of the evaluation


The evaluation of Qwen3.5-Omni covers two model variants, Qwen3.5-Omni-Flash and Qwen3.5-Omni-Plus, and is primarily divided into two categories: **understanding with textual output, or X→Text**, and **speech generation, or X→Speech**. X→Text includes Text→Text, Audio→Text, Vision→Text, and Audio-Visual Video→Text. Text→Text evaluates general knowledge, instruction following, long-context understanding, STEM, reasoning, and general agent ability. Audio→Text evaluates audio understanding, end-to-end speech dialogue, speech-to-text translation, or S2TT, and automatic speech recognition, or ASR. Vision→Text covers visual question answering, or VQA, document understanding, spatial intelligence, and video understanding. Audio-Visual Video→Text evaluates audio-visual understanding, audio-visual interaction, captioning, and tool use. The paper reports that, across multiple dimensions, the **text capabilities of Qwen3.5-Omni-Plus are comparable to those of the same-scale text-only counterpart, Qwen3.5-Plus-Instruct**, while the model also achieves competitive results across a broad range of audio and audio-visual benchmarks. The speech-generation evaluation further covers zero-shot speech generation, multilingual speech generation, cross-lingual speech generation, and custom-voice speech generation, using metrics such as Word Error Rate, or WER, Character Error Rate, or CER, and speaker similarity. For example, Qwen3.5-Omni-Plus achieves a WER of 1.26 on the English split of SEED-TTS; among the 29 languages evaluated in the paper, it obtains the lowest WER in 22; and in cross-lingual speech generation, it achieves the best result in 10 of the 12 evaluated language directions.

## 1.7. Detailed interpretation of the conclusion

The conclusion characterizes Qwen3.5-Omni as a **fully omnimodal large language model** that unifies understanding, reasoning, generation, and action across text, image, audio, and audio-visual inputs. The model is built on the Thinker–Talker framework and further strengthens real-time multimodal interaction through a hybrid-attention MoE architecture, 256k long-context modeling, multi-codebook codec prediction, ARIA, and broader multilingual speech support. The paper summarizes these technical advances into three core capabilities: **controllable audio-visual captioning**, **comprehensive real-time interaction**, and **native omnimodal agentic behavior** enabled through autonomous tool use and audio-visual code generation. Experimental results show that Qwen3.5-Omni achieves state-of-the-art, or SOTA, or otherwise highly competitive performance across a broad range of audio and audio-visual benchmarks, while largely maintaining the text and vision capabilities of same-scale Qwen models. The paper therefore argues that scaling native omnimodal training may lead to unified systems capable of perception, reasoning, real-time interaction, and action across different modalities, thereby providing a foundation for future research on general-purpose omnimodal agents.

# 2. Qwen 3.5 Omni: Explore the Concepts

**Fully omnimodal large language model**

A large language model designed to work with several forms of information, such as text, images, audio, and video, within one integrated system. In the context of Qwen3.5-Omni, the concept additionally emphasizes that these modalities are incorporated into a unified model for understanding, reasoning, generation, and interaction rather than being handled only by separate external components.

**Thinker–Talker architecture**

A model architecture that separates higher-level understanding and text generation from speech generation into two closely connected components. In Qwen3.5-Omni, the Thinker processes multimodal information and generates textual representations, while the Talker uses contextual information and representations from the Thinker to generate streaming speech tokens.

**Hybrid-attention mixture-of-experts architecture**

A model design that combines different attention mechanisms with a mixture-of-experts structure so that only selected computational components need to participate in particular processing steps. In Qwen3.5-Omni, this architecture is used for both the Thinker and Talker and is intended to improve scalability and the efficiency of long-sequence inference.

**Adaptive Rate Interleave Alignment**

A speech-generation technique that dynamically coordinates the relative progress of text-token and speech-token generation instead of requiring them to proceed according to a fixed relationship. In Qwen3.5-Omni, ARIA is specifically introduced to reduce instability caused by differences between text and speech tokenization rates and to improve the naturalness and robustness of streaming speech generation.

**Passive perception-response paradigm**

A model interaction pattern in which a system mainly receives information and produces a response rather than independently carrying out actions toward a broader goal. The paper contrasts this paradigm with systems capable of scalable agentic behavior, autonomous tool use, real-time interaction, and cross-modal reasoning.

**Native omni agent model**

A model designed from its underlying training and architecture to combine multimodal perception and reasoning with the ability to perform actions. For Qwen3.5-Omni, this includes processing multiple modalities while also invoking WebSearch, executing FunctionCall operations, generating speech, and participating in real-time streaming interaction.

**Long-context modeling of up to 256k tokens**

The ability of a model to process and relate information across an input sequence containing as many as approximately 256,000 tokens. For Qwen3.5-Omni, this extended context capacity is intended to support substantially longer textual and multimodal inputs, including long audio and audio-visual sequences.

**Native omnimodal agentic behavior**

The ability of an omnimodal model to move beyond understanding information and independently perform goal-oriented actions involving multiple modalities and tools. In Qwen3.5-Omni, this capability includes autonomous WebSearch, complex FunctionCall invocation, and Audio-Visual Vibe Coding.

**Hybrid mixture-of-experts design**

A model structure that distributes computation across multiple specialized components while selectively using relevant components during processing. In Qwen3.5-Omni, the hybrid MoE backbone is intended to improve scalability while balancing model capacity with computational efficiency across multimodal understanding and generation.

**Speech representation based on Residual Vector Quantization**

A method of representing speech using multiple levels of discrete codes that progressively capture information about an audio signal. In Qwen3.5-Omni, this RVQ-based representation allows the Talker to predict speech information through multiple codebooks and supports efficient speech generation.

**Unified interleaved single-stream formulation of text tokens and speech tokens**

A generation arrangement in which text and speech tokens are organized within one coordinated sequence rather than being generated through two separate tracks. In Qwen3.5-Omni, ARIA uses this formulation to reduce synchronization overhead and better coordinate incremental text and speech generation during streaming interaction.

**Pre-training of Qwen3.5-Omni follows a three-stage structure**

A training arrangement in which the model's initial large-scale learning is divided into three successive phases with different training objectives and context settings. In Qwen3.5-Omni, these are the Encoder Alignment Stage, General Stage, and Long Context Stage.

**Encoder Alignment Stage**

The first pre-training stage in which multimodal encoders are trained to produce representations that can work effectively with an existing large language model. In Qwen3.5-Omni, the LLM is kept fixed while the vision and audio encoders first train their adapters and are subsequently trained themselves.

**General Stage**

The second pre-training stage in which all model parameters are made trainable and the model learns from a large and diverse collection of multimodal data. In Qwen3.5-Omni, this stage uses approximately four trillion tokens spanning text, audio, images, video, and video-audio data.

**Long Context Stage**

The final overall pre-training stage in which training emphasizes substantially longer input sequences. For Qwen3.5-Omni, the maximum token length is increased from 32,768 to 262,144 and the amount of long audio and long video data is increased to strengthen long-sequence understanding.

**Specialist Distillation**

A training method in which knowledge and capabilities developed by models specialized for particular domains are transferred into a more general unified model. In Qwen3.5-Omni, specialized teacher models are trained for areas including text, reasoning, coding, agentic tasks, vision, and audio, and their generated domain-specific data is used for distillation.

**On-Policy Distillation**

A distillation method that uses responses produced under the model's own relevant operating conditions as training targets for improving another form of model behavior. In Qwen3.5-Omni, higher-quality responses generated from text-conditioned versions of paired queries are used as targets for corresponding audio-conditioned queries to improve response quality and consistency across modalities.

**Interaction-Aligned Reinforcement Learning**

A reinforcement-learning stage specifically designed to improve behavior during extended interaction with users. In Qwen3.5-Omni, it addresses problems such as unintended language switching, inconsistent personas, and weaker instruction following during long multi-turn conversations.

**Speaker Fine-tuning Stage**

A final Talker training stage that adjusts the model toward desired speaker characteristics. In Qwen3.5-Omni, this lightweight fine-tuning is used to strengthen the model's ability to reproduce target speaker characteristics while improving the naturalness, expressiveness, and controllability of generated speech.

**Understanding with textual output, or X→Text**

An evaluation category in which a model receives information in one or more modalities and produces text as its response. For Qwen3.5-Omni, this category covers text, audio, vision, and audio-visual inputs and evaluates abilities ranging from general reasoning and instruction following to speech recognition, visual understanding, and multimodal tool use.

**Speech generation, or X→Speech**

An evaluation category that examines the model's ability to generate spoken output from relevant input and contextual information. In Qwen3.5-Omni, evaluation includes zero-shot, multilingual, cross-lingual, and custom-voice speech generation, with measures covering content accuracy and speaker similarity.

**Text capabilities of Qwen3.5-Omni-Plus are comparable to those of the same-scale text-only counterpart, Qwen3.5-Plus-Instruct**

An evaluation finding indicating that incorporating broad multimodal capabilities does not necessarily require a substantial loss of text performance. The paper reports comparable performance across areas including knowledge, instruction following, long-context understanding, STEM, reasoning, and general agent tasks.

**Controllable audio-visual captioning**

The ability to generate structured and adjustable descriptions of content that jointly involves visual and auditory information. In Qwen3.5-Omni, this capability can include detailed descriptions, automatic segmentation, timestamp annotation, and descriptions of relationships between characters and audio.

**Comprehensive real-time interaction**

The ability of a model to participate in ongoing multimodal communication with sufficiently immediate processing and generation for interactive use. In Qwen3.5-Omni, this includes capabilities such as semantic interruption, turn-taking intent recognition, and end-to-end control over properties of generated speech.

