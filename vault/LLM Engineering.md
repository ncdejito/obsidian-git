How to build a [[Large Language Model (LLM)]] application

- [Book by Chip Huyen on LLMs](https://huyenchip.com/2023/04/11/llm-engineering.html)

Training & Tuning
- [LLMs Training in 2024 by Hugging Face CEO](https://www.linkedin.com/posts/thom-wolf_ai-openknowledge-openaccess-activity-7173356581361803265-lYWq?utm_source=share&utm_medium=member_android)
- [Tune LLMs to Your Own Data](https://www.linkedin.com/posts/sanyambhutani_terrific-tutorial-on-tuning-llms-on-your-activity-7056445643858358272-ZcMW?utm_source=share&utm_medium=member_android)
- [Lamini: LLM Fine-Tuning Made Easy](https://www.linkedin.com/posts/zhousharon_im-super-excited-to-announce-lamini-the-activity-7057754782249193472-1MKd?utm_source=share&utm_medium=member_desktop)
- [Collecting Data for LLMs](https://github.com/togethercomputer/RedPajama-Data)

[[System Design]]
- [LLM Architecture](https://github.blog/2023-10-30-the-architecture-of-todays-llm-applications/)
- [Emerging Architectures for LLM Applications](https://a16z.com/2023/06/20/emerging-architectures-for-llm-applications/)
- https://barryz-architecture-of-agentic-llm.notion.site/Almost-Everything-I-know-about-LLMs-d117ca25d4624199be07e9b0ab356a77

Components
- 
- [[LLM Memory]]
- **(Lacks Links)** Observability and Safety
- LLM Cache https://github.com/zilliztech/GPTCache
- https://github.com/LMCache/LMCache
- [[Vector databases]]
- [[LLM Unit testing]]
- [Gateway API for Fast LLM Access](https://github.com/Portkey-AI/gateway)
- [Mistral RS: Fast Rust-Based Inference](https://www.linkedin.com/posts/anant-gupta_llms-llms-rust-activity-7191759485839765504-ALI1?utm_source=share&utm_medium=member_desktop) - ideas for optimization
- [LangKit for Observability and Safety](https://www.linkedin.com/posts/whylabsai_whylabs-launches-langkit-to-make-large-language-activity-7074790438624231424-GJY_?utm_source=share&utm_medium=member_desktop)
- [LangChain - Building Applications with LLMs Through Composability](https://github.com/hwchase17/langchain)

Development & Tooling
- [Tools for Building LLM Applications](https://saharh.notion.site/saharh/1e4a35681007464faaa7cc5fe00dbd34?v=0e2f8309375c4f8d885f6221354576f3)
- [Scikit-LLM: Integrate LLMs into Applications Using scikit-learn](https://github.com/iryna-kondr/scikit-llm)
- **(Lacks Links)** Version Control for LLM Applications
- https://github.com/kennethreitz/simplemind - for simple use cases vs using langchain and langgraph
- [LLMs on Your Laptop](https://github.com/nat/openplayground)

Production & Deployment
- [LLMs for Production by Chip Huyen](https://www.linkedin.com/posts/chiphuyen_llms-promptengineering-mlops-activity-7051955337221844992-oG7a?utm_source=share&utm_medium=member_android) - describes challenges in MLOps
- [Hard Stuff No One Talks About in Building LLMs](https://www.honeycomb.io/blog/hard-stuff-nobody-talks-about-llm)
- [LLM Product Field Notes](https://barryz-architecture-of-agentic-llm.notion.site/Barry-s-LLM-Product-Field-Notes-646833d8bd11435b9db22c38edf6f11b)
- Latency - affected by output length, input no because tokens are parallelized
- Cost - affected by input

Models & Implementations
- [LLM Bloom in C++](https://www.linkedin.com/posts/jeremy-pinto_run-language-models-in-pure-c-introducing-activity-7042117323968630784-aOR9?utm_source=share&utm_medium=member_android)
- [LitLLAMA](https://www.linkedin.com/posts/jeremy-pinto_llama-llm-opensource-activity-7046622228049719296-enfr?utm_source=share&utm_medium=member_android)
- [Llama3 in Pure NumPy](https://github.com/likejazz/llama3.np)
- [Falcon LLM](https://huggingface.co/tiiuae/falcon-40b)


Lacking:
"Observability and Safety" and "Version Control for LLM Application"