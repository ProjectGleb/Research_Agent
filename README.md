**GPT Researcher is an autonomous agent designed for comprehensive online research on a variety of tasks.** 

Demo: https://drive.google.com/file/d/1CG_AdDGKyXO6c1AIuytDsV0fj_Ry2ShR/view?usp=sharing

The agent can produce detailed, factual and unbiased research reports, with customization options for focusing on relevant resources, outlines, and lessons. Inspired by the recent [Plan-and-Solve](https://arxiv.org/abs/2305.04091) and [RAG](https://arxiv.org/abs/2005.11401) papers, GPT Researcher addresses issues of speed, determinism and reliability, offering a more stable performance and increased speed through parallelized agent work, as opposed to synchronous operations.


## Why GPT Researcher?

- To form objective conclusions for manual research tasks can take time, sometimes weeks to find the right resources and information.
- Current LLMs are trained on past and outdated information, with heavy risks of hallucinations, making them almost irrelevant for research tasks.
- Current LLMs are limited to short token outputs which are not sufficient for long detailed research reports (2k+ words).
- Services that enable web search (such as ChatGPT + Web Plugin), only consider limited sources and content that in some cases result in superficial and biased answers.
- Using only a selection of web sources can create bias in determining the right conclusions for research tasks.

## Architecture
The main idea is to run "planner" and "execution" agents, whereas the planner generates questions to research, and the execution agents seek the most related information based on each generated research question. Finally, the planner filters and aggregates all related information and creates a research report.

The agents leverage both `gpt3.5-turbo` and `gpt-4o` (128K context) to complete a research task. I optimize for costs using each only when necessary. **The average research task takes around 3 minutes to complete, and costs ~$0.005.**


More specifically:
* Create a domain specific agent based on research query or task.
* Generate a set of research questions that together form an objective opinion on any given task. 
* For each research question, trigger a crawler agent that scrapes online resources for information relevant to the given task.
* For each scraped resources, summarize based on relevant information and keep track of its sources.
* Finally, filter and aggregate all summarized sources and generate a final research report.

## Features
- 📝 Generate research, outlines, resources and lessons reports with local documents and web sources
- 📜 Can generate long and detailed research reports (over 2K words)
- 🌐 Aggregates over 20 web sources per research to form objective and factual conclusions
- 🖥️ Includes an easy-to-use web interface (HTML/CSS/JS)
- 🔍 Scrapes web sources with javascript support
- 📂 Keeps track and context of visited and used web sources
- 📄 Export research reports to PDF, Word and more.

