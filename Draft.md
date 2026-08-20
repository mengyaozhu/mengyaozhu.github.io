prompt DeepSeek and Qwen for paper search, summary and display, disappointed to find the these two LLMs can reliably follow the generation structure requirements such as the number of paragraphs, generating a table with three columns for paper title, paper summary and paper links in each of the table rows, but the suggested paper are not closely relevant to the predefined topic, although with some minor connection with the topic, 







Cumulative Thinking Prompt:
recall your understanding about [{term}] in [{subject}] from essential to abstract in sequential 5 times, then to generate definition of [{term}] in [{subject}] with detailed mathematical explanations in one paragraph of approximately 200 words with used math symbols in LaTeX format, based on all 5 previous sequential thinking before generating the mathematical definition.


Direct Prompt:
definition of [{term}] in [{subject}] with detailed mathematical explanations in one paragraph of approximately 200 words with used math symbols in LaTeX format.


Excellent-Professor-Aware Prompt:
you are an excellent math professor who are good at math teaching, generate definition of [{term}] in [{subject}] with detailed mathematical explanations in one paragraph of approximately 200 words with used math symbols in LaTeX format.


Step-by-Step Prompt:
let's think step by step, definition of [{term}] in [{subject}] with detailed mathematical explanations in one paragraph of approximately 200 words with used math symbols in LaTeX format.


AUDIT Prompt: 
definition of [{term}] in [{subject}] with detailed mathematical explanations in one paragraph of approximately 200 words with used math symbols in LaTeX format in the first paragraph as ``definition\_1'', then suggest math definition refinement suggestions in the second paragraph as ``quality\_audit\_1'', then generate the first refined definition with detailed mathematical explanations in one paragraph of approximately 200 words with used math symbols in LaTeX format in the third paragraph as ``definition\_2'', then suggest math definition refinement suggestions to further refine the ``definition\_2'' in the fourth paragraph as ``quality\_audit\_2'', then generate the second refined definition with detailed mathematical explanations in one paragraph of approximately 200 words with used math symbols in LaTeX format in the fifth paragraph as ``definition\_3:''. Make sure each of the sequential definitions should be optimized to be more strictly aligned with the standard math definitions of college level mathematics lecture notes and textbooks.


Distinguished-Professor-Aware Prompt: 
you are a distinguished professor teaching college level mathematics, generate the definition of [{term}] in [{subject}] with detailed mathematical explanations in one paragraph with used math symbols in LaTeX format, make sure to fully and completely generate the definition, as truncated definition is not acceptable.


Emeritus-Professor-Aware Prompt: 
you are an Emeritus professor teaching college level mathematics, generate the definition of [{term}] in [{subject}] with detailed mathematical explanations in one paragraph with used math symbols in LaTeX format, make sure to fully and completely generate the definition, as truncated definition is not acceptable.


Full-Professor-Aware Prompt: 
you are a full professor teaching college level mathematics, generate the definition of [{term}] in [{subject}] with detailed mathematical explanations in one paragraph with used math symbols in LaTeX format, make sure to fully and completely generate the definition, as truncated definition is not acceptable.


Research-Professor-Aware Prompt: 
you are a research professor teaching college level mathematics, generate the definition of [{term}] in [{subject}] with detailed mathematical explanations in one paragraph with used math symbols in LaTeX format, make sure to fully and completely generate the definition, as truncated definition is not acceptable.

Teaching-Professor-Aware Prompt: 
you are a teaching professor teaching college level mathematics, generate the definition of [{term}] in [{subject}] with detailed mathematical explanations in one paragraph with used math symbols in LaTeX format, make sure to fully and completely generate the definition, as truncated definition is not acceptable.

Associate-Professor-Aware Prompt: 
you are an associate professor teaching college level mathematics, generate the definition of [{term}] in [{subject}] with detailed mathematical explanations in one paragraph with used math symbols in LaTeX format, make sure to fully and completely generate the definition, as truncated definition is not acceptable.

Assistant-Professor-Aware Prompt: 
you are an assistant professor teaching college level mathematics, generate the definition of [{term}] in [{subject}] with detailed mathematical explanations in one paragraph with used math symbols in LaTeX format, make sure to fully and completely generate the definition, as truncated definition is not acceptable.

Lecturer Prompt: 
you are a lecturer teaching college level mathematics, generate the definition of [{term}] in [{subject}] with detailed mathematical explanations in one paragraph with used math symbols in LaTeX format, make sure to fully and completely generate the definition, as truncated definition is not acceptable.




Every Language Model Has a Forgery-Resistant Signature


Reinforcement Learning (RL) with PPO- like clip objectives has become the standard choice for reward- based fine- tuning of large language models (LLMs). Although recent work has explored improved estimators of advantages and normalization, the clipping mechanism itself has remained untouched. Originally introduced as a proxy for principled KL- based trust regions, clipping is a crude approximation that often causes unstable updates and suboptimal performance. We replace the clip objective with a novel discrete differentiable trust region projection, which provides principled token- level KL constraints. The projection operates on a sparse subset of the model's most important token logits to balance computational cost and projection effectiveness. Our approach, Trust Region Optimization for Large Language models (TROLL), serves as a direct replacement for PPO- like clipping during training and does not alter the model's inference behavior. Across mathematical reasoning and code generation tasks, model families, as well as advantage- estimation methods, TROLL consistently outperforms PPO- like clipping in terms of training speed, stability, and final success rates.

改善你的英文学术写作系列 004：TROLL: Trust Regions Improve Reinforcement Learning for Large Language Models
英语学术写作评估与改进系列 003：Every Language Mo

ai4s-task-general-concept-exploration-prompt-cn
ai4s-task-general-concept-exploration-skill-cn


Prompt-Guided Navigation in the Reasoning Space of Large Language Models
(大規模言語モデルの推論空間におけるプロンプト誘導型ナビゲーション)

Doctoral_Dissertation_Release_Confirmation_Form





Dear Nguyen Sensei

Thank you very much for your kind wisheds to my wife and me. She was very glad to have the opportunity to attend my presentation, and I will certainly pass along your kind regards to her.

And I also want to express my apprepriation for your support during my defense, to help me answer the questions and responses.

I have added the LLM variations Appendix "A.2 Generation Demonstrations for Three Proposed Prompt Methods" (Page 127, type 140 in PDF page navigation box).

I have also attached the Doctoral_Dissertation_Release_Confirmation_Form_Zhu_Mengyao in the this reply.

Please let me know if you have any further questions.

Kind Regards,

Zhu Mengyao

ai4s-task-academic-writing-evaluation-and-refinement
ai4s-task-academic-writing-quality-check


**2.4 Native Vision**

Kimi K3 is natively multimodal: text, images, and videos are processed by a single shared backbone within one context, with no post-hoc modality-alignment stage. This design is the architectural foundation of the long-horizon, vision-in-the-loop behavior described in §1. Rendered outputs and the code that produced them live in the same token stream, the model can write code, inspect screenshots or video frames of the result, and iteratively refine visual artifacts—user interfaces, graphics, video—with no cross-model hand-off.

MoonViT-V2 A key departure from Kimi K2.5 is that we train Kimi K3 vision encoder, MoonViT-V2, entirely from scratch with next-token prediction. Prior practice, including Kimi K2.5 itself, initializes the vision encoder from a contrastively pre-trained model such as SigLIP, under the premise that pre-trained visual knowledge gives the model a head start. We depart from this practice primarily for training stability. When a pre-trained encoder is attached to the LLM, joint optimization becomes unstable: the SigLIP-initialized MoonViT-3D shows persistently higher gradient norms with frequent spikes, while MoonViT-V2 remains stable throughout training (Fig. 6). Training with next-token prediction also allows the encoder's representations to be shaped directly by the language-modeling objective, rather than by a contrastive loss that favors global semantics over fine-grained textual and structural cues. Notably, we find MoonViT-V2 matches the SigLIP-initialized baseline across vision evaluations, indicating that contrastive pre-training is unnecessary as an initialization for multimodal language models at scale.

Architecture This training recipe builds on a vision pathway that follows the overall design of Kimi K2.5 [60,62]: visual inputs are first encoded by MoonViT-V2 and then mapped by a lightweight MLP projector into the LLM. MoonViT-V2 is a 27-layer vision transformer with roughly 0.4B parameters that adopts RMSNorm and removes all bias terms from its linear and attention projections, a design that further stabilizes the from-scratch optimization above. Images and videos are processed with fully shared parameters, as in MoonViT-3D: attention is factorized into intra-frame spatial and inter-frame temporal passes, and temporal pooling further compresses tokens along the time dimension. Before projection, a pixel-shuffle operation with \(2 \times 2\) downsampling reduces the number of visual tokens by a factor of four, keeping inputs of up to \(3584 \times 3584\) pixels affordable within the 1M-token context.






grammatical and structural appropriate
expression selection and word choice appropriate
loggic organization and sequence appropriate
syntactic control appropriate



if "Use each extracted original sentence from the original content as primary evidence for the initial interpretation of the corresponding aspect of lexical and expression appropriateness"

is more appropriate and accurate than 

"Use each extracted original sentence as primary evidence from the original content for the initial interpretation of the corresponding aspect of stylistic appropriateness"?


