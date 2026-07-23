# AI-Executive-assistant
I just built an AI Executive Assistant that reads my emails, drafts replies in my voice, and never sends a single word to OpenAI, Google, or any cloud API.

Here's the workflow (built in n8n) 👇
𝗧𝗵𝗲 𝗽𝗿𝗼𝗯𝗹𝗲𝗺: Every founder drowns in the same 3 emails a day — a partnership pitch, a webinar invite, a "quick call?" request. Reading, summarizing, and replying to each one eats focus time that should go into actual work.
𝗧𝗵𝗲 𝗹𝗼𝗴𝗶𝗰 𝗯𝗲𝗵𝗶𝗻𝗱 𝘁𝗵𝗲 𝗯𝘂𝗶𝗹𝗱:
1️⃣ 𝗚𝗺𝗮𝗶𝗹 𝗧𝗿𝗶𝗴𝗴𝗲𝗿 — polls the inbox every 60 seconds. The moment an email lands, the automation wakes up.
2️⃣ 𝗛𝗧𝗠𝗟 𝗘𝘅𝘁𝗿𝗮𝗰𝘁𝗼𝗿 — most emails arrive as messy HTML. This node strips it down to clean, readable body text before it ever touches the AI.
3️⃣ 𝗔𝗜 𝗔𝗴𝗲𝗻𝘁 — this is the brain. I gave it a tightly-scoped system prompt so it acts strictly as my Executive Assistant, not a generic chatbot: → Extracts the sender's name and designation → Summarizes the email into "Sender / Purpose" format → Drafts a reply in my exact tone, with a real signature and a clear call to action → No filler ("hope you're well," "thrilled to," etc.) — just direct, human-sounding output
4️⃣ 𝗢𝗹𝗹𝗮𝗺𝗮 (𝗾𝘄𝗲𝗻𝟮.𝟱:𝟳𝗯) — instead of routing this through a cloud LLM, the Agent is powered by a model running locally via Ollama. Every email, every draft, every bit of context stays on my own machine. Nothing is logged, trained on, or sent to a third party. That's the "Private" in Private AI Assistant.
5️⃣ 𝗦𝗲𝗻𝗱 𝗠𝗲𝘀𝘀𝗮𝗴𝗲 — the drafted reply is sent straight back to the original sender through Gmail. Fully closed loop, zero manual typing.
𝗪𝗵𝘆 𝘁𝗵𝗶𝘀 𝗺𝗮𝘁𝘁𝗲𝗿𝘀: Most "AI email assistant" tutorials plug straight into OpenAI's API. That's fine for a demo — but the second real client emails, NDAs, or sensitive deal terms enter the picture, privacy becomes non-negotiable. Running the LLM locally means you get the automation without shipping your inbox to someone else's servers.
I'm deep in my n8n + AI automation learning journey right now, and this project taught me more about prompt constraints, node chaining, and local-LLM integration than any course could.
Next on my list: adding memory so it can reference past threads before drafting a reply.
