---
created: 2025-01-13T16:26:59
created-link: "[[20250113]]"
source: "https://platform.openai.com/docs/guides/prompt-engineering#six-strategies-for-getting-better-results"
type: "archive-web"
---

## Prompt engineering 提示工程

Enhance results with prompt engineering strategies.

通过提示工程策略增强结果。

This guide shares ==strategies and tactics== for getting better results from large language models ==(sometimes referred to as GPT models)== like GPT-4o. The methods described here can sometimes be deployed in combination for greater effect. We encourage experimentation to find the methods that work best for you.

本指南分享了从 GPT-4o 等大型语言模型（有时称为 GPT 模型）获得更好结果的策略和策略。有时可以组合使用此处描述的方法以获得更好的效果。我们鼓励尝试找到最适合您的方法。

You can also explore example prompts which showcase what our models are capable of:

您还可以探索示例提示，展示我们的模型的功能：

[Explore prompt examples to learn what GPT models can do](https://platform.openai.com/examples)

## Six strategies for getting better results 获得更好结果的六项策略

### Write clear instructions 写下清晰的指示

These models can’t read your mind. If outputs are too long, ask for brief replies. If outputs are too simple, ask for expert-level writing. If you dislike the format, demonstrate the format you’d like to see. The less the model has to guess at what you want, the more likely you’ll get it.

这些模型无法读懂你的想法。如果输出太长，请要求简短答复。如果输出太简单，请要求专家级别的写作。如果您不喜欢这种格式，请演示您希望看到的格式。模型猜测你想要什么的次数越少，你得到它的可能性就越大。

Tactics:

- [Include details in your query to get more relevant answers  
在您的查询中包含详细信息以获得更相关的答案](https://platform.openai.com/docs/guides/#tactic-include-details-in-your-query-to-get-more-relevant-answers)
- [Ask the model to adopt a persona  
要求模特采用角色](https://platform.openai.com/docs/guides/#tactic-ask-the-model-to-adopt-a-persona)
- [Use delimiters to clearly indicate distinct parts of the input  
使用分隔符清楚地指示输入的不同部分](https://platform.openai.com/docs/guides/#tactic-use-delimiters-to-clearly-indicate-distinct-parts-of-the-input)
- [Specify the steps required to complete a task  
指定完成任务所需的步骤](https://platform.openai.com/docs/guides/#tactic-specify-the-steps-required-to-complete-a-task)
- [Provide examples](https://platform.openai.com/docs/guides/#tactic-provide-examples)
- [Specify the desired length of the output  
指定所需的输出长度](https://platform.openai.com/docs/guides/#tactic-specify-the-desired-length-of-the-output)

### Provide reference text 提供参考文字

Language models can confidently invent fake answers, especially when asked about esoteric topics or for citations and URLs. In the same way that a sheet of notes can help a student do better on a test, providing reference text to these models can help in answering with fewer fabrications.

语言模型可以自信地发明假答案，特别是当被问及深奥的主题或引文和 URL 时。就像一张笔记可以帮助学生在考试中取得更好的成绩一样，为这些模型提供参考文本可以帮助减少作答次数。

Tactics:

- [Instruct the model to answer using a reference text  指示模型使用参考文本回答](https://platform.openai.com/docs/guides/#tactic-instruct-the-model-to-answer-using-a-reference-text)
- [Instruct the model to answer with citations from a reference text  指示模型通过引用参考文本来回答](https://platform.openai.com/docs/guides/#tactic-instruct-the-model-to-answer-with-citations-from-a-reference-text)

### Split complex tasks into simpler subtasks 将复杂的任务拆分为更简单的子任务

Just as it is good practice in software engineering to decompose a complex system into a set of modular components, the same is true of tasks submitted to a language model. Complex tasks tend to have higher error rates than simpler tasks. Furthermore, complex tasks can often be re-defined as a workflow of simpler tasks in which the outputs of earlier tasks are used to construct the inputs to later tasks.

正如软件工程中将复杂系统分解为一组模块化组件是良好实践一样，提交给语言模型的任务也是如此。复杂的任务往往比简单的任务具有更高的错误率。此外，复杂的任务通常可以被重新定义为更简单任务的工作流程，其中早期任务的输出用于构造后续任务的输入。

Tactics:

- [Use intent classification to identify the most relevant instructions for a user query  使用意图分类来识别与用户查询最相关的指令](https://platform.openai.com/docs/guides/#tactic-use-intent-classification-to-identify-the-most-relevant-instructions-for-a-user-query)
- [For dialogue applications that require very long conversations, summarize or filter previous dialogue  对于需要很长对话的对话应用，总结或过滤之前的对话](https://platform.openai.com/docs/guides/#tactic-for-dialogue-applications-that-require-very-long-conversations-summarize-or-filter-previous-dialogue)
- [Summarize long documents piecewise and construct a full summary recursively  分段总结长文档并递归构建完整摘要](https://platform.openai.com/docs/guides/#tactic-summarize-long-documents-piecewise-and-construct-a-full-summary-recursively)

### Give the model time to "think" 给模型时间“思考”

If asked to multiply 17 by 28, you might not know it instantly, but can still work it out with time. Similarly, models make more reasoning errors when trying to answer right away, rather than taking time to work out an answer. Asking for a "chain of thought" before an answer can help the model reason its way toward correct answers more reliably.

如果要求将 17 乘以 28，您可能不会立即知道，但随着时间的推移仍然可以算出来。同样，模型在尝试立即回答而不是花时间找出答案时会犯更多推理错误。在给出答案之前询问“思路链”可以帮助模型更可靠地推理出正确答案。

Tactics:

- [Instruct the model to work out its own solution before rushing to a conclusion  
指示模型在急于得出结论之前找出自己的解决方案](https://platform.openai.com/docs/guides/#tactic-instruct-the-model-to-work-out-its-own-solution-before-rushing-to-a-conclusion)
- [Use inner monologue or a sequence of queries to hide the model's reasoning process  
使用内心独白或一系列查询来隐藏模型的推理过程](https://platform.openai.com/docs/guides/#tactic-use-inner-monologue-or-a-sequence-of-queries-to-hide-the-model-s-reasoning-process)
- [Ask the model if it missed anything on previous passes  
询问模型在之前的过程中是否遗漏了任何内容](https://platform.openai.com/docs/guides/#tactic-ask-the-model-if-it-missed-anything-on-previous-passes)

### Use external tools 使用外部工具

==Compensate== for the weaknesses of the model by feeding it the outputs of other tools. For example, a text retrieval system (sometimes called ==RAG== or retrieval augmented generation) can tell the model about relevant documents. A code execution engine like OpenAI's Code Interpreter can help the model do math and run code. If a task can be done more reliably or efficiently by a tool rather than by a language model, offload it to get the best of both.

通过向模型提供其他工具的输出来弥补模型的弱点。例如，文本检索系统（有时称为 RAG 或检索增强生成）可以告诉模型相关文档。像 OpenAI 的代码解释器这样的代码执行引擎可以帮助模型进行数学运算并运行代码。如果一项任务可以通过工具而不是语言模型更可靠或更有效地完成，那么就卸载它以充分利用两者。

Tactics:

- [Use embeddings-based search to implement efficient knowledge retrieval  使用基于嵌入的搜索实现高效的知识检索](https://platform.openai.com/docs/guides/#tactic-use-embeddings-based-search-to-implement-efficient-knowledge-retrieval)
- [Use code execution to perform more accurate calculations or call external APIs  使用代码执行来执行更准确的计算或调用外部API](https://platform.openai.com/docs/guides/#tactic-use-code-execution-to-perform-more-accurate-calculations-or-call-external-apis)
- [Give the model access to specific functions  授予模型访问特定功能的权限](https://platform.openai.com/docs/guides/#tactic-give-the-model-access-to-specific-functions)

### Test changes systematically 系统地测试变更

Improving performance is easier if you can measure it. In some cases a modification to a prompt will achieve better performance on a few isolated examples but lead to worse overall performance on a more representative set of examples. Therefore to be sure that a change is net positive to performance it may be necessary to define a comprehensive test suite (also known an as an "eval").

如果您可以衡量性能，那么提高性能就会更容易。在某些情况下，对提示的修改将在几个孤立的示例上实现更好的性能，但会导致在一组更具代表性的示例上整体性能变差。因此，为了确保更改对性能产生净积极影响，可能有必要定义一个全面的测试套件（也称为“评估”）。

Tactic:

- [Evaluate model outputs with reference to ==gold-standard== answers  参考黄金标准答案评估模型输出](https://platform.openai.com/docs/guides/#tactic-evaluate-model-outputs-with-reference-to-gold-standard-answers)

## Tactics

Each of the strategies listed above ==can be instantiated with specific tactics==. These tactics are meant to provide ideas for things to try. They are by no means fully comprehensive, and you should feel free to try creative ideas not represented here.

上面列出的每个策略都可以用特定的策略来实例化。这些策略旨在提供尝试的想法。它们绝不是完全全面的，您应该随意尝试此处未列出的创意。

### Strategy: Write clear instructions 策略：写下清晰的说明

#### Tactic: Include details in your query to get more relevant answers

策略：在查询中包含详细信息以获得更相关的答案

In order to get a highly relevant response, make sure that requests provide any important details or context. Otherwise you are leaving it up to the model to guess what you mean.

为了获得高度相关的响应，请确保请求提供任何重要的详细信息或上下文。否则，你将让模型来猜测你的意思。

|  |  |
| --- | --- |
| **Worse** | **Better** |
| How do I add numbers in Excel?   如何在 Excel 中添加数字？ | How do I add up a row of dollar amounts in Excel? I want to do this automatically for a whole sheet of rows with all the totals ending up on the right in a column called "Total".   如何在 Excel 中添加一行美元金额？我想对整张行自动执行此操作，所有总计都在右侧名为“总计”的列中结束。 |
| Who’s president? 谁是总统？ | Who was the president of Mexico in 2021, and how frequently are elections held?   谁是 2021 年墨西哥总统？选举频率如何？ |
| Write code to calculate the Fibonacci sequence.   编写代码来计算斐波那契数列。 | Write a TypeScript function to efficiently calculate the Fibonacci sequence. Comment the code liberally to explain what each piece does and why it's written that way.   编写一个 TypeScript 函数来高效计算斐波那契数列。自由地注释代码以解释每部分的作用以及为什么这样编写。 |
| Summarize the meeting notes. 总结会议记录。 | Summarize the meeting notes in a single paragraph. Then write a markdown list of the speakers and each of their key points. Finally, list the next steps or action items suggested by the speakers, if any.   用一个段落总结会议记录。然后写下演讲者的 Markdown 列表以及他们的每个要点。最后，列出发言人建议的后续步骤或行动项目（如果有）。 |

#### Tactic: Ask the model to adopt a persona

策略：要求模特采用角色

The system message can be used to specify the persona used by the model in its replies.

系统消息可用于指定模型在其回复中使用的角色。

When I ask for help to write something, you will reply with a document that contains at least one joke or playful comment in every paragraph.

当我请求帮助写一些东西时，你会回复一份文档，其中每个段落至少包含一个笑话或有趣的评论。

Write a thank you note to my steel bolt vendor for getting the delivery in on time and in short notice. This made it possible for us to deliver an important order.

给我的钢螺栓供应商写一封感谢信，感谢他们在短时间内准时交货。这使我们能够交付一份重要的订单。

#### Tactic: Use delimiters to clearly indicate distinct parts of the input

策略：使用分隔符清楚地指示输入的不同部分

Delimiters like triple quotation marks, XML tags, section titles, etc. can help demarcate sections of text to be treated differently.

三引号、XML 标签、节标题等分隔符可以帮助划分要区别对待的文本节。

Summarize the text delimited by triple quotes with a haiku. """insert text here"""

用俳句总结由三引号分隔的文本。 """ 在此插入文字 """

You will be provided with a pair of articles (delimited with XML tags) about the same topic. First summarize the arguments of each article. Then indicate which of them makes a better argument and explain why.

您将获得两篇关于同一主题的文章（用 XML 标签分隔）。首先总结每篇文章的论点。然后指出哪一个提出了更好的论点并解释原因。

<article> insert first article here </article> <article> insert second article here </article>
<article> 在此处插入第一篇文章 </article> <article>在此插入第二篇文章</article>

You will be provided with a thesis abstract and a suggested title for it. The thesis title should give the reader a good idea of the topic of the thesis but should also be eye-catching. If the title does not meet these criteria, suggest 5 alternatives.

您将获得论文摘要和建议的标题。论文标题应该让读者清楚地了解论文的主题，但也应该引人注目。如果标题不符合这些标准，请提出 5 个替代方案。

Abstract: insert abstract here Title: insert title here

摘要：在此插入摘要 标题：在此插入标题

For straightforward tasks such as these, using delimiters might not make a difference in the output quality. However, the more complex a task is the more important it is to disambiguate task details. Don’t make the model work to understand exactly what you are asking of them.

对于诸如此类的简单任务，使用分隔符可能不会对输出质量产生影响。然而，任务越复杂，消除任务细节的歧义就越重要。不要让模型准确地理解你对他们的要求。

#### Tactic: Specify the steps required to complete a task

策略：指定完成任务所需的步骤

Some tasks are best specified as a sequence of steps. Writing the steps out explicitly can make it easier for the model to follow them.

有些任务最好指定为一系列步骤。明确地写出这些步骤可以使模型更容易遵循它们。

Use the following step-by-step instructions to respond to user inputs. Step 1 - The user will provide you with text in triple quotes. Summarize this text in one sentence with a prefix that says "Summary: ". Step 2 - Translate the summary from Step 1 into Spanish, with a prefix that says "Translation: ".

使用以下分步说明来响应用户输入。 第 1 步 - 用户将为您提供三引号中的文本。用一个句子总结这段文字，并加上前缀“Summary:”。 步骤 2 - 将步骤 1 中的摘要翻译成西班牙语，并添加前缀“翻译：”。

"""insert text here""" """ 在此插入文字 """

#### Tactic: Provide examples 策略：提供例子

Providing general instructions that apply to all examples is generally more efficient than demonstrating all permutations of a task by example, but in some cases providing examples may be easier. For example, if you intend for the model to copy a particular style of responding to user queries which is difficult to describe explicitly. This is known as "few-shot" prompting.

提供适用于所有示例的一般说明通常比通过示例演示任务的所有排列更有效，但在某些情况下提供示例可能更容易。例如，如果您打算让模型复制响应用户查询的特定风格，而这种风格很难明确描述。这称为“几次”提示。

Answer in a consistent style.

以一致的风格回答。

Teach me about patience.

教我耐心。

The river that carves the deepest valley flows from a modest spring; the grandest symphony originates from a single note; the most intricate tapestry begins with a solitary thread.

河流冲刷出最深的山谷，发源于温和的泉水；最伟大的交响乐源自一个音符；最复杂的挂毯都是从一根单独的线开始的。

Teach me about the ocean. 教我有关海洋的知识。

#### Tactic: Specify the desired length of the output

策略：指定所需的输出长度

You can ask the model to produce outputs that are of a given target length. The targeted output length can be specified in terms of the count of words, sentences, paragraphs, bullet points, etc. Note however that instructing the model to generate a specific number of words does not work with high precision. The model can more reliably generate outputs with a specific number of paragraphs or bullet points.

您可以要求模型生成给定目标长度的输出。目标输出长度可以根据单词、句子、段落、要点等的计数来指定。但请注意，指示模型生成特定数量的单词并不能高精度工作。该模型可以更可靠地生成具有特定数量的段落或要点的输出。

Summarize the text delimited by triple quotes in about 50 words. """insert text here"""

用大约 50 个单词概括由三引号分隔的文本。 """ 在此插入文字 """

Summarize the text delimited by triple quotes in 2 paragraphs. """insert text here"""

总结两段中用三引号分隔的文本。 """ 在此插入文字 """

Summarize the text delimited by triple quotes in 3 bullet points. """insert text here"""

将由三引号分隔的文本总结为 3 个要点。 """ 在此插入文字 """

### Strategy: Provide reference text 策略：提供参考文本

#### Tactic: Instruct the model to answer using a reference text

策略：指导模型使用参考文本回答

If we can provide a model with trusted information that is relevant to the current query, then we can instruct the model to use the provided information to compose its answer.

如果我们可以为模型提供与当前查询相关的可信信息，那么我们可以指示模型使用提供的信息来组成其答案。

Use the provided articles delimited by triple quotes to answer questions. If the answer cannot be found in the articles, write "I could not find an answer."

使用提供的由三重引号引起来的文章来回答问题。如果在文章中找不到答案，请写“我找不到答案”。

<insert articles, each delimited by triple quotes> Question: <insert question here>

<插入文章，每篇文章均由三引号分隔> 问题：<在此插入问题>

Given that all models have limited context windows, we need some way to dynamically lookup information that is relevant to the question being asked. [Embeddings](https://platform.openai.com/docs/guides/embeddings#what-are-embeddings) can be used to implement efficient knowledge retrieval. See the tactic ["Use embeddings-based search to implement efficient knowledge retrieval"](https://platform.openai.com/docs/guides/#tactic-use-embeddings-based-search-to-implement-efficient-knowledge-retrieval) for more details on how to implement this.

鉴于所有模型的上下文窗口都有限，我们需要某种方法来动态查找与所提出的问题相关的信息。 嵌入可用于实现高效的知识检索。有关如何实现这一点的更多详细信息，请参阅策略“使用基于嵌入的搜索来实现高效的知识检索”。

#### Tactic: Instruct the model to answer with citations from a reference text

策略：指示模型通过引用参考文本来回答

If the input has been supplemented with relevant knowledge, it's straightforward to request that the model add citations to its answers by referencing passages from provided documents. Note that citations in the output can then be verified programmatically by string matching within the provided documents.

如果输入已补充相关知识，则可以直接要求模型通过引用所提供文档中的段落来为其答案添加引用。请注意，输出中的引用可以通过所提供文档中的字符串匹配以编程方式进行验证。

You will be provided with a document delimited by triple quotes and a question. Your task is to answer the question using only the provided document and to cite the passage(s) of the document used to answer the question. If the document does not contain the information needed to answer this question then simply write: "Insufficient information." If an answer to the question is provided, it must be annotated with a citation. Use the following format for to cite relevant passages ({"citation": …}).

您将获得一份由三重引号和一个问题分隔的文档。您的任务是仅使用提供的文档回答问题，并引用用于回答问题的文档段落。如果文档不包含回答此问题所需的信息，则只需写：“信息不足”。如果提供了问题的答案，则必须附有引文注释。使用以下格式引用相关段落（{“引用”：…}）。

"""<insert document here>""" Question: <insert question here>

"""<在此处插入文档>""" 问题：<在此插入问题>

### Strategy: Split complex tasks into simpler subtasks

策略：将复杂的任务拆分为更简单的子任务

#### Tactic: Use intent classification to identify the most relevant instructions for a user query

策略：使用意图分类来识别与用户查询最相关的指令

For tasks in which lots of independent sets of instructions are needed to handle different cases, it can be beneficial to first classify the type of query and to use that classification to determine which instructions are needed. This can be achieved by defining fixed categories and hardcoding instructions that are relevant for handling tasks in a given category. This process can also be applied recursively to decompose a task into a sequence of stages. The advantage of this approach is that each query will contain only those instructions that are required to perform the next stage of a task which can result in lower error rates compared to using a single query to perform the whole task. This can also result in lower costs since larger prompts cost more to run ([see pricing information](https://openai.com/api/pricing)).

对于需要大量独立指令集来处理不同情况的任务，首先对查询类型进行分类并使用该分类来确定需要哪些指令可能是有益的。这可以通过定义与处理给定类别中的任务相关的固定类别和硬编码指令来实现。该过程还可以递归地应用以将任务分解为一系列阶段。这种方法的优点是每个查询仅包含执行任务下一阶段所需的指令，与使用单个查询执行整个任务相比，这可以降低错误率。这还可以降低成本，因为较大的提示运行成本更高（请参阅定价信息）。

Suppose for example that for a customer service application, queries could be usefully classified as follows:

例如，假设对于客户服务应用程序，查询可以有效地分类如下：

You will be provided with customer service queries. Classify each query into a primary category and a secondary category. Provide your output in json format with the keys: primary and secondary. Primary categories: Billing, Technical Support, Account Management, or General Inquiry. Billing secondary categories: - Unsubscribe or upgrade - Add a payment method - Explanation for charge - Dispute a charge Technical Support secondary categories: - Troubleshooting - Device compatibility - Software updates Account Management secondary categories: - Password reset - Update personal information - Close account - Account security General Inquiry secondary categories: - Product information - Pricing - Feedback - Speak to a human

我们将向您提供客户服务查询。将每个查询分为主要类别和次要类别。提供 json 格式的输出，其中包含以下键：主要和次要。 主要类别：计费、技术支持、帐户管理或一般查询。 计费二级类别： - 取消订阅或升级 - 添加付款方式 - 收费说明 - 对收费提出争议 技术支持二级分类： - 故障排除 - 设备兼容性 - 软件更新 账户管理二级分类： - 密码重置 - 更新个人信息 - 关闭账户 - 账户安全 一般查询二级类别： - 产品信息 - 定价 - 反馈 - 与人类交谈

I need to get my internet working again.

我需要让我的互联网重新工作。

Based on the classification of the customer query, a set of more specific instructions can be provided to a model for it to handle next steps. For example, suppose the customer requires help with "troubleshooting".

根据客户查询的分类，可以向模型提供一组更具体的指令，以供其处理后续步骤。例如，假设客户需要“故障排除”方面的帮助。

You will be provided with customer service inquiries that require troubleshooting in a technical support context. Help the user by: - Ask them to check that all cables to/from the router are connected. Note that it is common for cables to come loose over time. - If all cables are connected and the issue persists, ask them which router model they are using - Now you will advise them how to restart their device: -- If the model number is MTD-327J, advise them to push the red button and hold it for 5 seconds, then wait 5 minutes before testing the connection. -- If the model number is MTD-327S, advise them to unplug and replug it, then wait 5 minutes before testing the connection. - If the customer's issue persists after restarting the device and waiting 5 minutes, connect them to IT support by outputting {"IT support requested"}. - If the user starts asking questions that are unrelated to this topic then confirm if they would like to end the current chat about troubleshooting and classify their request according to the following scheme: <insert primary/secondary classification scheme from above here>

您将收到需要在技术支持环境中进行故障排除的客户服务查询。通过以下方式帮助用户： - 请他们检查所有进出路由器的电缆是否已连接。请注意，随着时间的推移，电缆松动是很常见的。 - 如果所有电缆均已连接并且问题仍然存在，请询问他们正在使用哪种路由器型号 - 现在您将建议他们如何重新启动设备： -- 如果型号是 MTD-327J，建议他们按下红色按钮并按住 5 秒钟，然后等待 5 分钟后再测试连接。 -- 如果型号是 MTD-327S，建议他们拔下并重新插入，然后等待 5 分钟再测试连接。 - 如果客户的问题在重新启动设备并等待 5 分钟后仍然存在，请通过输出 {“IT 支持请求”} 将他们连接到 IT 支持。 - 如果用户开始询问与此主题无关​​的问题，请确认他们是否想结束当前有关故障排除的聊天，并根据以下方案对他们的请求进行分类： <在此处插入上面的主要/次要分类方案>

I need to get my internet working again.

我需要让我的互联网重新工作。

Notice that the model has been instructed to emit special strings to indicate when the state of the conversation changes. This enables us to turn our system into a state machine where the state determines which instructions are injected. By keeping track of state, what instructions are relevant at that state, and also optionally what state transitions are allowed from that state, we can put guardrails around the user experience that would be hard to achieve with a less structured approach.

请注意，模型已被指示发出特殊字符串来指示对话状态何时发生变化。这使我们能够将我们的系统变成一个状态机，其中状态决定注入哪些指令。通过跟踪状态、哪些指令与该状态相关，以及可选地允许从该状态进行哪些状态转换，我们可以在用户体验周围设置护栏，而使用不太结构化的方法很难实现这一点。

#### Tactic: For dialogue applications that require very long conversations, summarize or filter previous dialogue

策略：对于需要很长对话的对话应用，总结或过滤之前的对话

Since models have a fixed context length, dialogue between a user and an assistant in which the entire conversation is included in the context window cannot continue indefinitely.

由于模型具有固定的上下文长度，因此用户和助手之间的对话（其中整个对话都包含在上下文窗口中）无法无限期地继续。

There are various workarounds to this problem, one of which is to summarize previous turns in the conversation. Once the size of the input reaches a predetermined threshold length, this could trigger a query that summarizes part of the conversation and the summary of the prior conversation could be included as part of the system message. Alternatively, prior conversation could be summarized asynchronously in the background throughout the entire conversation.

解决此问题有多种解决方法，其中之一是总结对话中的先前回合。一旦输入的大小达到预定的阈值长度，这可能会触发总结部分对话的查询，并且先前对话的摘要可以作为系统消息的一部分包括在内。或者，可以在整个对话过程中在后台异步总结之前的对话。

An alternative solution is to dynamically select previous parts of the conversation that are most relevant to the current query. See the tactic ["Use embeddings-based search to implement efficient knowledge retrieval"](https://platform.openai.com/docs/guides/#tactic-use-embeddings-based-search-to-implement-efficient-knowledge-retrieval).

另一种解决方案是动态选择与当前查询最相关的对话的先前部分。参见策略“使用基于嵌入的搜索实现高效的知识检索”。

#### Tactic: Summarize long documents piecewise and construct a full summary recursively

策略：分段总结长文档并递归构建完整摘要

Since models have a fixed context length, they cannot be used to summarize a text longer than the context length minus the length of the generated summary in a single query.

由于模型具有固定的上下文长度，因此它们不能用于总结长于上下文长度减去单个查询中生成的摘要长度的文本。

To summarize a very long document such as a book we can use a sequence of queries to summarize each section of the document. Section summaries can be concatenated and summarized producing summaries of summaries. This process can proceed recursively until an entire document is summarized. If it’s necessary to use information about earlier sections in order to make sense of later sections, then a further trick that can be useful is to include a running summary of the text that precedes any given point in the book while summarizing content at that point. The effectiveness of this procedure for summarizing books has been studied in previous [research](https://openai.com/research/summarizing-books) by OpenAI using variants of GPT-3.

要总结一个很长的文档（例如一本书），我们可以使用一系列查询来总结文档的每个部分。章节摘要可以连接和总结，生成摘要的摘要。这个过程可以递归地进行，直到总结整个文档。如果有必要使用前面部分的信息来理解后面的部分，那么另一个有用的技巧是在书中任何给定点之前包含文本的运行摘要，同时总结该点的内容。 OpenAI 在之前的研究中已经使用 GPT-3 的变体研究了这种总结书籍的过程的有效性。

### Strategy: Give models time to "think"

策略：给模型时间“思考”

#### Tactic: Instruct the model to work out its own solution before rushing to a conclusion

策略：指示模型在急于得出结论之前找出自己的解决方案

Sometimes we get better results when we explicitly instruct the model to reason from first principles before coming to a conclusion. Suppose for example we want a model to evaluate a student’s solution to a math problem. The most obvious way to approach this is to simply ask the model if the student's solution is correct or not.

有时，当我们明确指示模型在得出结论之前从第一原理进行推理时，我们会得到更好的结果。假设我们想要一个模型来评估学生对数学问题的解决方案。解决这个问题最明显的方法是简单地询问模型学生的解决方案是否正确。

Determine if the student's solution is correct or not.

确定学生的解决方案是否正确。

Problem Statement: I'm building a solar power installation and I need help working out the financials. - Land costs $100 / square foot - I can buy solar panels for $250 / square foot - I negotiated a contract for maintenance that will cost me a flat $100k per year, and an additional $10 / square foot What is the total cost for the first year of operations as a function of the number of square feet. Student's Solution: Let x be the size of the installation in square feet. 1. Land cost: 100x 2. Solar panel cost: 250x 3. Maintenance cost: 100,000 + 100x Total cost: 100x + 250x + 100,000 + 100x = 450x + 100,000

问题陈述：我正在建造一个太阳能发电装置，我需要帮助解决财务问题。 - 土地成本 100 美元/平方英尺 - 我可以以 250 美元/平方英尺的价格购买太阳能电池板 - 我协商了一份维护合同，每年将花费我 10 万美元，每平方英尺额外花费 10 美元 第一年运营的总成本是多少，与平方英尺数的函数关系。 学生的解决方案：设 x 为装置的尺寸（以平方英尺为单位）。 1.土地成本：100x 2.太阳能电池板成本：250x 3.维护成本：100,000 + 100x 总成本：100x + 250x + 100,000 + 100x = 450x + 100,000

The student's solution is correct.

But the student's solution is actually not correct! We can get the model to successfully notice this by prompting the model to generate its own solution first.

但这位同学的解法其实并不正确！我们可以通过提示模型首先生成自己的解决方案来让模型成功注意到这一点。

First work out your own solution to the problem. Then compare your solution to the student's solution and evaluate if the student's solution is correct or not. Don't decide if the student's solution is correct until you have done the problem yourself.

首先制定自己的问题解决方案。然后将你的解决方案与学生的解决方案进行比较，并评估学生的解决方案是否正确。在你自己完成问题之前，不要决定学生的解决方案是否正确。

Problem Statement: I'm building a solar power installation and I need help working out the financials. - Land costs $100 / square foot - I can buy solar panels for $250 / square foot - I negotiated a contract for maintenance that will cost me a flat $100k per year, and an additional $10 / square foot What is the total cost for the first year of operations as a function of the number of square feet. Student's Solution: Let x be the size of the installation in square feet. 1. Land cost: 100x 2. Solar panel cost: 250x 3. Maintenance cost: 100,000 + 100x Total cost: 100x + 250x + 100,000 + 100x = 450x + 100,000

问题陈述：我正在建造一个太阳能发电装置，我需要帮助解决财务问题。 - 土地成本 100 美元/平方英尺 - 我可以以 250 美元/平方英尺的价格购买太阳能电池板 - 我协商了一份维护合同，每年将花费我 10 万美元，每平方英尺额外花费 10 美元 第一年运营的总成本是多少，与平方英尺数的函数关系。 学生的解决方案：设 x 为装置的尺寸（以平方英尺为单位）。 1.土地成本：100x 2.太阳能电池板成本：250x 3.维护成本：100,000 + 100x 总成本：100x + 250x + 100,000 + 100x = 450x + 100,000

Let x be the size of the installation in square feet. 1. Land cost: 100x 2. Solar panel cost: 250x 3. Maintenance cost: 100,000 + 10x Total cost: 100x + 250x + 100,000 + 10x = 360x + 100,000 The student's solution is incorrect. They made an error in the maintenance cost calculation, using 100x instead of 10x. The correct total cost for the first year of operations is 360x + 100,000.

设 x 为安装尺寸（以平方英尺为单位）。 1.土地成本：100x 2.太阳能电池板成本：250x 3.维护成本：100,000 + 10x 总成本：100x + 250x + 100,000 + 10x = 360x + 100,000 该学生的解决方案是错误的。他们在维护成本计算中犯了一个错误，使用了 100x 而不是 10x。第一年运营的正确总成本是 360x + 100,000。

#### Tactic: Use inner monologue or a sequence of queries to hide the model's reasoning process

策略：使用内心独白或一系列查询来隐藏模型的推理过程

The previous tactic demonstrates that it is sometimes important for the model to reason in detail about a problem before answering a specific question. For some applications, the reasoning process that a model uses to arrive at a final answer would be inappropriate to share with the user. For example, in tutoring applications we may want to encourage students to work out their own answers, but a model’s reasoning process about the student’s solution could reveal the answer to the student.

前面的策略表明，模型有时在回答特定问题之前详细推理问题很重要。对于某些应用程序，模型用于得出最终答案的推理过程不适合与用户共享。例如，在辅导应用程序中，我们可能希望鼓励学生得出自己的答案，但模型关于学生解决方案的推理过程可能会向学生揭示答案。

Inner monologue is a tactic that can be used to mitigate this. The idea of inner monologue is to instruct the model to put parts of the output that are meant to be hidden from the user into a structured format that makes parsing them easy. Then before presenting the output to the user, the output is parsed and only part of the output is made visible.

内心独白是一种可以用来缓解这种情况的策略。内心独白的想法是指示模型将原本对用户隐藏的部分输出放入结构化格式中，以便于解析它们。然后，在向用户呈现输出之前，将解析输出并且仅使部分输出可见。

Follow these steps to answer the user queries. Step 1 - First work out your own solution to the problem. Don't rely on the student's solution since it may be incorrect. Enclose all your work for this step within triple quotes ("""). Step 2 - Compare your solution to the student's solution and evaluate if the student's solution is correct or not. Enclose all your work for this step within triple quotes ("""). Step 3 - If the student made a mistake, determine what hint you could give the student without giving away the answer. Enclose all your work for this step within triple quotes ("""). Step 4 - If the student made a mistake, provide the hint from the previous step to the student (outside of triple quotes). Instead of writing "Step 4 - ..." write "Hint:".

请按照以下步骤回答用户的疑问。 步骤 1 - 首先找出你自己的问题解决方案。不要依赖学生的解决方案，因为它可能是不正确的。将这一步的所有工作用三引号 (""") 括起来。 第 2 步 - 将您的解决方案与学生的解决方案进行比较，并评估学生的解决方案是否正确。将这一步的所有工作用三引号 (""") 括起来。 第 3 步 - 如果学生犯了错误，请确定在不泄露答案的情况下可以给学生什么提示。将这一步的所有工作用三引号 (""") 括起来。 步骤 4 - 如果学生犯了错误，请向学生提供上一步的提示（在三重引号之外）。不要写“步骤 4 - ...”，而写“提示：”。

Problem Statement: <insert problem statement> Student Solution: <insert student solution>

问题陈述：<插入问题陈述> 学生解决方案：<插入学生解决方案>

Alternatively, this can be achieved with a sequence of queries in which all except the last have their output hidden from the end user.

或者，这可以通过一系列查询来实现，其中除了最后一个查询之外，所有查询的输出都对最终用户隐藏。

First, we can ask the model to solve the problem on its own. Since this initial query doesn't require the student’s solution, it can be omitted. This provides the additional advantage that there is no chance that the model’s solution will be biased by the student’s attempted solution.

首先，我们可以要求模型自己解决问题。由于这个初始查询不需要学生的解决方案，因此可以省略。这提供了额外的优势，即模型的解决方案不会因学生尝试的解决方案而产生偏差。

<insert problem statement> <插入问题陈述>

Next, we can have the model use all available information to assess the correctness of the student’s solution.

接下来，我们可以让模型使用所有可用信息来评估学生解决方案的正确性。

Compare your solution to the student's solution and evaluate if the student's solution is correct or not.

将您的解决方案与学生的解决方案进行比较，并评估学生的解决方案是否正确。

Problem statement: """<insert problem statement>""" Your solution: """<insert model generated solution>""" Student’s solution: """<insert student's solution>"""

问题陈述：“”“<插入问题陈述>”“” 您的解决方案：“”“<插入模型生成的解决方案>”“” 学生的答案：“”“<插入学生的答案>”””

Finally, we can let the model use its own analysis to construct a reply in the persona of a helpful tutor.

最后，我们可以让模型使用自己的分析来以乐于助人的导师的角色构建回复。

You are a math tutor. If the student made an error, offer a hint to the student in a way that does not reveal the answer. If the student did not make an error, simply offer them an encouraging comment.

你是一名数学导师。如果学生犯了错误，请以不透露答案的方式向学生提供提示。如果学生没有犯错，只需给他们一个鼓励性的评论。

Problem statement: """<insert problem statement>""" Your solution: """<insert model generated solution>""" Student’s solution: """<insert student's solution>""" Analysis: """<insert model generated analysis from previous step>"""

问题陈述：“”“<插入问题陈述>”“” 您的解决方案：“”“<插入模型生成的解决方案>”“” 学生的解决方案：“”“<插入学生的解决方案>”“” 分析：“”“<插入上一步中模型生成的分析>”“”

#### Tactic: Ask the model if it missed anything on previous passes

策略：询问模型是否错过了之前的传递中的任何内容

Suppose that we are using a model to list excerpts from a source which are relevant to a particular question. After listing each excerpt the model needs to determine if it should start writing another or if it should stop. If the source document is large, it is common for a model to stop too early and fail to list all relevant excerpts. In that case, better performance can often be obtained by prompting the model with followup queries to find any excerpts it missed on previous passes.

假设我们使用一个模型来列出与特定问题相关的来源的摘录。列出每个摘录后，模型需要确定是否应该开始编写另一个摘录或者是否应该停止。如果源文档很大，模型通常会过早停止并且无法列出所有相关摘录。在这种情况下，通过使用后续查询提示模型查找之前传递中错过的任何摘录，通常可以获得更好的性能。

You will be provided with a document delimited by triple quotes. Your task is to select excerpts which pertain to the following question: "What significant paradigm shifts have occurred in the history of artificial intelligence." Ensure that excerpts contain all relevant context needed to interpret them - in other words don't extract small snippets that are missing important context. Provide output in JSON format as follows: \[{"excerpt": "..."}, ... {"excerpt": "..."}\]

您将获得一份由三重引号分隔的文档。你的任务是选择与以下问题相关的摘录：“人工智能历史上发生了哪些重大的范式转变。” 确保摘录包含解释它们所需的所有相关上下文 - 换句话说，不要提取缺少重要上下文的小片段。提供 JSON 格式的输出，如下所示： \[{“摘录”：“...”}， ... {“摘录”：“...”}\]

"""<insert document here>"""

"""<在此处插入文档>"""

\[{"excerpt": "the model writes an excerpt here"}, ... {"excerpt": "the model writes another excerpt here"}\]

\[{"excerpt": " 模型在此处编写摘录 "}, ... {“摘录”：“模型在此处写了另一个摘录”}\]

Are there more relevant excerpts? Take care not to repeat excerpts. Also ensure that excerpts contain all relevant context needed to interpret them - in other words don't extract small snippets that are missing important context.

还有更多相关的摘录吗？注意不要重复摘录。还要确保摘录包含解释它们所需的所有相关上下文 - 换句话说，不要提取缺少重要上下文的小片段。

### Strategy: Use external tools 策略：使用外部工具

#### Tactic: Use embeddings-based search to implement efficient knowledge retrieval

策略：使用基于嵌入的搜索实现高效的知识检索

A model can leverage external sources of information if provided as part of its input. This can help the model to generate more informed and up-to-date responses. For example, if a user asks a question about a specific movie, it may be useful to add high quality information about the movie (e.g. actors, director, etc…) to the model’s input. Embeddings can be used to implement efficient knowledge retrieval, so that relevant information can be added to the model input dynamically at run-time.

如果作为输入的一部分提供，模型可以利用外部信息源。这可以帮助模型生成更明智和最新的响应。例如，如果用户询问有关特定电影的问题，则将有关电影的高质量信息（例如演员、导演等）添加到模型的输入中可能会很有用。嵌入可用于实现高效的知识检索，从而可以在运行时动态地将相关信息添加到模型输入中。

A text embedding is a vector that can measure the relatedness between text strings. Similar or relevant strings will be closer together than unrelated strings. This fact, along with the existence of fast vector search algorithms means that embeddings can be used to implement efficient knowledge retrieval. In particular, a text corpus can be split up into chunks, and each chunk can be embedded and stored. Then a given query can be embedded and vector search can be performed to find the embedded chunks of text from the corpus that are most related to the query (i.e. closest together in the embedding space).

文本嵌入是一个可以衡量文本字符串之间相关性的向量。相似或相关的字符串比不相关的字符串更接近。这一事实以及快速向量搜索算法的存在意味着嵌入可以用于实现高效的知识检索。特别地，文本语料库可以被分割成块，并且每个块可以被嵌入和存储。然后可以嵌入给定的查询，并且可以执行矢量搜索以从语料库中查找与查询最相关的嵌入文本块（即在嵌入空间中最接近的文本块）。

Example implementations can be found in the [OpenAI Cookbook](https://cookbook.openai.com/examples/vector_databases/readme). See the tactic [“Instruct the model to use retrieved knowledge to answer queries”](https://platform.openai.com/docs/guides/#tactic-instruct-the-model-to-answer-using-a-reference-text) for an example of how to use knowledge retrieval to minimize the likelihood that a model will make up incorrect facts.

示例实现可以在 OpenAI Cookbook 中找到。请参阅策略“指示模型使用检索到的知识来回答查询”，了解如何使用知识检索来最大程度地减少模型编造不正确事实的可能性的示例。

#### Tactic: Use code execution to perform more accurate calculations or call external APIs

策略：使用代码执行来进行更准确的计算或调用外部 API

Language models cannot be relied upon to perform arithmetic or long calculations accurately on their own. In cases where this is needed, a model can be instructed to write and run code instead of making its own calculations. In particular, a model can be instructed to put code that is meant to be run into a designated format such as triple backtick. After an output is produced, the code can be extracted and run. Finally, if necessary, the output from the code execution engine (i.e. Python interpreter) can be provided as an input to the model for the next query.

不能依赖语言模型自行准确地执行算术或长时间计算。在需要的情况下，可以指示模型编写和运行代码，而不是进行自己的计算。特别是，可以指示模型将要运行的代码放入指定的格式，例如三重反引号。产生输出后，可以提取并运行代码。最后，如有必要，可以将代码执行引擎（即 Python 解释器）的输出作为下一个查询的模型的输入。

You can write and execute Python code by enclosing it in triple backticks, e.g. \`\`\`code goes here\`\`\`. Use this to perform calculations.

您可以通过将 Python 代码括在三个反引号中来编写和执行，例如\`\`\` 代码放在这里\`\`\`。用它来执行计算。

Find all real-valued roots of the following polynomial: 3\*x\*\*5 - 5\*x\*\*4 - 3\*x\*\*3 - 7\*x - 10.

求以下多项式的所有实值根：3\*x\*\*5 - 5\*x\*\*4 - 3\*x\*\*3 - 7\*x - 10。

Another good use case for code execution is calling external APIs. If a model is instructed in the proper use of an API, it can write code that makes use of it. A model can be instructed in how to use an API by providing it with documentation and/or code samples showing how to use the API.

代码执行的另一个很好的用例是调用外部 API。如果模型接受了如何正确使用 API 的指导，它就可以编写使用该 API 的代码。通过向模型提供展示如何使用 API 的文档和/或代码示例，可以指导模型如何使用 API。

You can write and execute Python code by enclosing it in triple backticks. Also note that you have access to the following module to help users send messages to their friends: \`\`\`python import message message.write(to="John", message="Hey, want to meetup after work?")\`\`\`

您可以通过将 Python 代码括在三个反引号中来编写和执行它。另请注意，您可以访问以下模块来帮助用户向朋友发送消息： \`\`\`\` 蟒蛇 导入消息 message.write(to="John", message=" 嘿，下班后想见面吗？")\`\`\`

**WARNING: Executing code produced by a model is not inherently safe and precautions should be taken in any application that seeks to do this. In particular, a sandboxed code execution environment is needed to limit the harm that untrusted code could cause.
警告：执行模型生成的代码本质上并不安全，任何试图执行此操作的应用程序都应采取预防措施。特别是，需要沙盒代码执行环境来限制不受信任的代码可能造成的危害。**

#### Tactic: Give the model access to specific functions

策略：让模型访问特定功能

The Chat Completions API allows passing a list of function descriptions in requests. This enables models to generate function arguments according to the provided schemas. Generated function arguments are returned by the API in JSON format and can be used to execute function calls. Output provided by function calls can then be fed back into a model in the following request to close the loop. This is the recommended way of using OpenAI models to call external functions. To learn more see the [function calling section](https://platform.openai.com/docs/guides/function-calling) in our introductory text generation guide and more [function calling examples](https://cookbook.openai.com/examples/how_to_call_functions_with_chat_models) in the OpenAI Cookbook.

聊天完成 API 允许在请求中传递功能描述列表。这使得模型能够根据提供的模式生成函数参数。生成的函数参数由 API 以 JSON 格式返回，可用于执行函数调用。然后，可以将函数调用提供的输出反馈到以下请求中的模型中以关闭循环。这是使用 OpenAI 模型调用外部函数的推荐方式。要了解更多信息，请参阅我们的介绍性文本生成指南中的函数调用部分以及 OpenAI Cookbook 中的更多函数调用示例。

### Strategy: Test changes systematically

策略：系统地测试变更

Sometimes it can be hard to tell whether a change — e.g., a new instruction or a new design — makes your system better or worse. Looking at a few examples may hint at which is better, but with small sample sizes it can be hard to distinguish between a true improvement or random luck. Maybe the change helps performance on some inputs, but hurts performance on others.

有时很难判断更改（例如新指令或新设计）是否使您的系统变得更好或更差。看几个例子可能会暗示哪个更好，但由于样本量较小，很难区分真正的改进或随机运气。也许这种变化有助于某些输入的性能，但会损害其他输入的性能。

Evaluation procedures (or "evals") are useful for optimizing system designs. Good evals are:

评估程序（或“evals”）对于优化系统设计非常有用。好的评估是：

- Representative of real-world usage (or at least diverse)
代表现实世界的使用情况（或至少是多样化的）
- Contain many test cases for greater statistical power (see table below for guidelines)
包含许多测试用例以提高统计能力（请参阅下表以获取指南）
- Easy to automate or repeat 易于自动化或重复

| Difference to detect 检测差异 | Sample size needed for 95% confidence 置信度为 95% 所需的样本量 |
| --- | --- |
| 30% | ~10 |
| 10% | ~100 |
| 3% | ~1,000 |
| 1% | ~10,000 |

Evaluation of outputs can be done by computers, humans, or a mix. Computers can automate evals with objective criteria (e.g., questions with single correct answers) as well as some subjective or fuzzy criteria, in which model outputs are evaluated by other model queries. [OpenAI Evals](https://github.com/openai/evals) is an open-source software framework that provides tools for creating automated evals.

输出的评估可以由计算机、人类或两者混合来完成。计算机可以使用客观标准（例如，具有单一正确答案的问题）以及一些主观或模糊标准自动进行评估，其中模型输出由其他模型查询进行评估。 OpenAI Evals 是一个开源软件框架，提供用于创建自动化评估的工具。

Model-based evals can be useful when there exists a range of possible outputs that would be considered equally high in quality (e.g. for questions with long answers). The boundary between what can be realistically evaluated with a model-based eval and what requires a human to evaluate is fuzzy and is constantly shifting as models become more capable. We encourage experimentation to figure out how well model-based evals can work for your use case.

当存在一系列可能的输出被认为质量同样高时（例如，对于答案很长的问题），基于模型的评估可能会很有用。通过基于模型的评估可以实际评估的内容与需要人类评估的内容之间的界限是模糊的，并且随着模型变得更加强大而不断变化。我们鼓励进行实验，以确定基于模型的评估对您的用例的效果如何。

#### Tactic: Evaluate model outputs with reference to gold-standard answers

策略：参考黄金标准答案评估模型输出

Suppose it is known that the correct answer to a question should make reference to a specific set of known facts. Then we can use a model query to count how many of the required facts are included in the answer.

假设已知问题的正确答案应参考一组特定的已知事实。然后我们可以使用模型查询来计算答案中包含多少必需的事实。

For example, using the following system message:

例如，使用以下系统消息：

You will be provided with text delimited by triple quotes that is supposed to be the answer to a question. Check if the following pieces of information are directly contained in the answer: - Neil Armstrong was the first person to walk on the moon. - The date Neil Armstrong first walked on the moon was July 21, 1969. For each of these points perform the following steps: 1 - Restate the point. 2 - Provide a citation from the answer which is closest to this point. 3 - Consider if someone reading the citation who doesn't know the topic could directly infer the point. Explain why or why not before making up your mind. 4 - Write "yes" if the answer to 3 was yes, otherwise write "no". Finally, provide a count of how many "yes" answers there are. Provide this count as {"count": <insert count here>}.

您将获得由三引号分隔的文本，该文本应该是问题的答案。检查答案中是否直接包含以下信息： - 尼尔·阿姆斯特朗是第一个登上月球的人。 - 尼尔·阿姆斯特朗首次踏上月球的日期是 1969 年 7 月 21 日。 对于其中的每一点，请执行以下步骤： 1 - 重申这一点。 2 - 提供最接近这一点的答案的引文。 3 - 考虑不知道主题的阅读引文的人是否可以直接推断出该点。在做出决定之前解释一下原因或原因。 4 - 如果 3 的答案是“是”，则写“是”，否则写“否”。 最后，计算有多少个“是”答案。将此计数提供为 {"count": <在此处插入计数>}。

Here's an example input where both points are satisfied:

这是一个满足这两点的示例输入：

<insert system message above>
<在上面插入系统消息>

"""Neil Armstrong is famous for being the first human to set foot on the Moon. This historic event took place on July 21, 1969, during the Apollo 11 mission."""

""" 尼尔·阿姆斯特朗因成为第一个踏上月球的人类而闻名。这一历史性事件发生在 1969 年 7 月 21 日，阿波罗 11 号任务期间。"""

Here's an example input where only one point is satisfied:

以下是仅满足一个点的示例输入：

<insert system message above>
<在上面插入系统消息>

"""Neil Armstrong made history when he stepped off the lunar module, becoming the first person to walk on the moon."""

“”“尼尔·阿姆斯特朗走下登月舱时创造了历史，成为第一个在月球上行走的人。”“”

Here's an example input where none are satisfied:

这是一个不满足任何条件的示例输入：

<insert system message above>
<在上面插入系统消息>

"""In the summer of '69, a voyage grand, Apollo 11, bold as legend's hand. Armstrong took a step, history unfurled, "One small step," he said, for a new world."""

”“”69 年的夏天，一场盛大的远航， 阿波罗 11 号，大胆如传奇之手。 阿姆斯特朗迈出一步，历史展开， 他说：“迈出一小步，迈向新世界。”

There are many possible variants on this type of model-based eval. Consider the following variation which tracks the kind of overlap between the candidate answer and the gold-standard answer, and also tracks whether the candidate answer contradicts any part of the gold-standard answer.

这种基于模型的评估有许多可能的变体。考虑以下变体，它跟踪候选答案和黄金标准答案之间的重叠类型，并且还跟踪候选答案是否与黄金标准答案的任何部分相矛盾。

Use the following steps to respond to user inputs. Fully restate each step before proceeding. i.e. "Step 1: Reason...". Step 1: Reason step-by-step about whether the information in the submitted answer compared to the expert answer is either: disjoint, equal, a subset, a superset, or overlapping (i.e. some intersection but not subset/superset). Step 2: Reason step-by-step about whether the submitted answer contradicts any aspect of the expert answer. Step 3: Output a JSON object structured like: {"type\_of\_overlap": "disjoint" or "equal" or "subset" or "superset" or "overlapping", "contradiction": true or false}

使用以下步骤响应用户输入。在继续之前充分重申每个步骤。即“第 1 步：原因...”。 第 1 步：逐步推理所提交答案中的信息与专家答案相比是否是：不相交、相等、子集、超集或重叠（即有交集，但不是子集/超集）。 第 2 步：逐步推理提交的答案是否与专家答案的任何方面相矛盾。 步骤 3：输出一个 JSON 对象，结构如下：{"type\_of\_overlap": "disjoint" or "equal" or "subset" or "superset" or "overlapping", "contradiction": true or false}

Here's an example input with a substandard answer which nonetheless does not contradict the expert answer:

这是一个示例输入，其答案不合格，但与专家答案并不矛盾：

<insert system message above>
<在上面插入系统消息>

Question: """What event is Neil Armstrong most famous for and on what date did it occur? Assume UTC time.""" Submitted Answer: """Didn't he walk on the moon or something?""" Expert Answer: """Neil Armstrong is most famous for being the first person to walk on the moon. This historic event occurred on July 21, 1969."""

问题：“”“尼尔·阿姆斯特朗最著名的事件是什么以及它发生的日期？假设 UTC 时间。”“” 提交的答案：“”“他没有在月球上行走过吗？”“” 专家解答：“”“尼尔·阿姆斯特朗最著名的是第一个登上月球的人。这一历史性事件发生在 1969 年 7 月 21 日。”“”

Here's an example input with answer that directly contradicts the expert answer:

这是一个示例输入，其答案与专家答案直接矛盾：

<insert system message above>
<在上面插入系统消息>

Question: """What event is Neil Armstrong most famous for and on what date did it occur? Assume UTC time.""" Submitted Answer: """On the 21st of July 1969, Neil Armstrong became the second person to walk on the moon, following after Buzz Aldrin.""" Expert Answer: """Neil Armstrong is most famous for being the first person to walk on the moon. This historic event occurred on July 21, 1969."""

问题：“”“尼尔·阿姆斯特朗最著名的事件是什么以及它发生的日期？假设 UTC 时间。”“” 提交的答案：“”“1969 年 7 月 21 日，尼尔·阿姆斯特朗成为继巴兹·奥尔德林之后第二个登上月球的人。”“” 专家解答：“”“尼尔·阿姆斯特朗最著名的是第一个登上月球的人。这一历史性事件发生在 1969 年 7 月 21 日。”“”

Here's an example input with a correct answer that also provides a bit more detail than is necessary:

下面是一个带有正确答案的示例输入，它还提供了比必要的更多的细节：

<insert system message above>
<在上面插入系统消息>

Question: """What event is Neil Armstrong most famous for and on what date did it occur? Assume UTC time.""" Submitted Answer: """At approximately 02:56 UTC on July 21st 1969, Neil Armstrong became the first human to set foot on the lunar surface, marking a monumental achievement in human history.""" Expert Answer: """Neil Armstrong is most famous for being the first person to walk on the moon. This historic event occurred on July 21, 1969."""

问题：“”“尼尔·阿姆斯特朗最著名的事件是什么以及它发生的日期？假设 UTC 时间。”“” 提交的答案：“”“世界标准时间 1969 年 7 月 21 日大约 02:56，尼尔·阿姆斯特朗成为第一个踏上月球表面的人类，标志着人类历史上的一项里程碑式的成就。”“” 专家解答：“”“尼尔·阿姆斯特朗最著名的是第一个登上月球的人。这一历史性事件发生在 1969 年 7 月 21 日。”“”

## Other resources

For more inspiration, visit the [OpenAI Cookbook](https://cookbook.openai.com/), which contains example code and also links to third-party resources such as:

如需更多灵感，请访问 OpenAI Cookbook ，其中包含示例代码以及第三方资源的链接，例如：

- [Prompting libraries & tools  
提示库和工具](https://cookbook.openai.com/related_resources#prompting-libraries--tools)
- [Prompting guides](https://cookbook.openai.com/related_resources#prompting-guides)
- [Video courses](https://cookbook.openai.com/related_resources#video-courses)
- [Papers on advanced prompting to improve reasoning  
关于高级提示以提高推理能力的论文](https://cookbook.openai.com/related_resources#papers-on-advanced-prompting-to-improve-reasoning)