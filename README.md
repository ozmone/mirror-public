<img width="1915" height="487" alt="image" src="https://github.com/user-attachments/assets/9d1c3124-c1e9-4957-9377-f3acfe8ce37a" />

## 

Mirror is a **free**, **open-source** chat PWA (Progressive Web App) compatible with [OpenAI](https://openai.com/api/) and [OpenRouter](https://openrouter.ai/) API keys. 

### No built-in guardrails!
As a writer, it was difficult to talk to GPT 5.2+ models that have such heavy guardrails. So that's why I was frustrated and made Mirror app - a way to talk to 4o again as well as any other model I want.

---

### ⦿ No server. No accounts. No signup.

All your data lives in your browser's local storage (IndexedDB). You are responsible for your own backups — use the **"Backup All Data"** button and save the export somewhere safe, like Google Drive. Chats persist as long as you're on the same device and haven't cleared your app data.

---

### ⦿ It's free?

The app itself is free. You still pay for API usage through OpenAI or OpenRouter — Mirror doesn't add any markup or middleman costs.

If you want to donate to this project, my ko-fi link is https://ko-fi.com/saveoursouls# 

---

## ✅ **Getting Started**

1. Open the app https://ozmone.github.io/mirror-public/ 
2. Go to **Settings** and paste your OpenAI or OpenRouter API key
3. Create a **Project**
4. Start a chat

> Installation on your phone: Specifically use a Chrome app on your phone, select the three dots next to the address, click "Add to homepage". You should get an option to "Install Mirror" which will make it work just like a real app and not a browser window.

---

### ⦿ Memory System

Mirror has a **per-project memory system** with full control over how memories are created and used.

- **Retention modes:**
  - `Manual only` — you write memories yourself, the AI never creates them
  - `Review` — the AI may suggest memories, but they stay pending until you approve
  - `Autonomous` — the AI saves memories directly; review them periodically
- **Memory types:** `Factual` (real-world preferences, routines, constraints) or `Fiction` (canon, lore, character state, plot consequences)
- Memories have **categories**, **importance ratings (1–5)**, **tags**, and statuses (`pending`, `active`, `archived`)
- Memory **lookup is a tool call** — the model retrieves relevant memories on demand rather than stuffing everything into the context window

  > Note: It's called "lookup" if you need the tell the AI you want it to *really look*. For e.g. "lookup my character Magniss" and it will actually look up that character. This is useful for project prompts such as "always use tools to lookup characters when they enter a scene."

---

### ⦿ Context Window Control

You have full manual control over how much context is sent with each message:

- Set a **rolling context window** — e.g. last 6, 20, 50, or unlimited messages
- **Compaction** — older message batches are summarised by the model and stored as compressed chunks, keeping the context lean without losing continuity
  - Configure batch size, max chunks, and token budget for summaries
  - VIEW and EDIT your actual context window
  - Toggle project context on/off - keep your same context from another chat inside the same project
- Per-chat **temperature**, **top-p**, and **max output token** overrides
  

---

### 📁 Projects

Chats live inside **Projects**, which act as persistent workspaces. Each project has:

- A **system prompt** and **lore** block injected at the start of every conversation
- Its own **model and provider** override (or inherits from global settings)
- **Memory** scoped to that project
- **Characters** — create named characters with descriptions, traits, and notes; the model can look them up as a tool call mid-conversation
- **Lore files** — longer world-building documents the model can retrieve on demand; files can be marked as restricted with a reason
- **Inventory** — a credits + items tracker the model can read and update during fiction/roleplay sessions

---

### ✍️ Creative Writing & Roleplay

Mirror was originally designed for collaborative fiction. Features built with that in mind:

- Per-project **character sheets** the AI can look up without them clogging the context
- **Lore files** for world-building notes, faction details, timelines — retrieved only when relevant
- **Fiction memory mode** tracks character state, relationships, scene outcomes, and canon
- **Inventory system** lets the AI track in-world items and currency
- **Autonomous memory** with fiction type means the model can maintain a living record of your story as it evolves

---

### 🖼️ Images

Mirror supports both **sending images to the model** and **generating images**, using your existing API key.

#### **Attaching images (vision / multimodal input)**

You can attach images to any message and send them to vision-capable models (e.g. GPT-4o, Gemini). Mirror accepts PNG, JPG, WEBP, and GIF — up to 20 MB each, up to 8 attachments per message.

Before sending, Mirror automatically resizes and compresses large images to keep your token costs reasonable. You can control this behaviour per-chat:

- **Max side** — the longest dimension images are scaled down to (1024 / 1536 / 2048 px)
- **JPEG quality** — compression level for non-PNG images (default 86%)
- **Input detail** — maps to the API's `detail` parameter: `low` (fixed token cost, faster), `high` (full resolution tiles), or `auto`

If you send an image to a model that doesn't support vision, Mirror detects the error and lets you know.

#### **Model routing:**

- `Auto-route` (default) — Mirror fetches the live list of image-capable models at request time and picks the best available ChatGPT image model it finds
- `Manual` — you pick a specific image generation model from the list yourself

You can configure image generation under **Chat Options → Image Settings**.

> Image generation uses your existing OpenRouter API key — no separate account or key needed.

---

### ❌ Limitations ❌ 

- **No voice / microphone** — audio is not supported
- No cloud sync — backups are manual

---

### ⦿ Privacy (OpenRouter users)

Mirror exposes OpenRouter's data routing options:

- `Standard` — no extra filter
- `No-training providers` — routes only to providers OpenRouter marks as not training on your prompts
- `Zero data retention` — strictest; routes only to ZDR endpoints

---

# Screenshots:

Chat (example using 4o)
<img width="270" height="594" src="https://github.com/user-attachments/assets/51cf0393-19e7-46fb-ac14-5e84b04932ae"><img width="324" height="324" src="https://github.com/user-attachments/assets/165b458a-836f-4344-8025-a3a3fc6e6df1" />

-----
Projects
<img width="270" height="594" alt="image" src="https://github.com/user-attachments/assets/4299e8dd-a450-4549-8612-6e9b51aa5129" />
-----
Character cards
<img width="330" height="502" src="https://github.com/user-attachments/assets/4ad88082-5e8d-4be1-ad63-8b1cde600ccb" />
-----
Customizable settings
<img width="270" height="594" src="https://github.com/user-attachments/assets/3f2dc1eb-752a-4903-bd94-654d23bf929b" />
-----
Customizable app
<img width="270" height="594" src="https://github.com/user-attachments/assets/3124a286-e6a6-4f03-9cc2-6f8d0823fc81" />
-----
API Privacy settings
<img width="270" height="594" src="https://github.com/user-attachments/assets/61d84c10-7cc1-474e-822b-14c6a969b18d" />
-----
Memory Management + more
<img width="270" height="594" src="https://github.com/user-attachments/assets/7f7eb0c1-4e35-41f6-81e6-f600bb468db6" />


