# ⚠️ This Repository Has Moved

**This codebase has been migrated to [claraverse-space/ClaraVerse](https://github.com/claraverse-space/ClaraVerse).**

Please visit the new repository for the latest updates, issues, and contributions.

---

*Looking for the Desktop Electron app? It has moved to [claraverse-space/ClaraVerse-Desktop](https://github.com/claraverse-space/ClaraVerse-Desktop).*

---

<div align="center">

<img src="docs/images/image-banner.png" alt="Claraverse - Your Private AI Workspace" width="800" />

### **Your Private AI Workspace**

*One app replaces ChatGPT, Midjourney, and N8N. Local or cloud - your data stays yours.*

<p>

[![License](https://img.shields.io/badge/license-AGPL--3.0-blue.svg)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/claraverse-space/ClaraVerseAI?style=social)](https://github.com/claraverse-space/ClaraVerseAI/stargazers)
[![Docker Pulls](https://img.shields.io/docker/pulls/claraverseoss/claraverse?color=blue)](https://hub.docker.com/r/claraverseoss/claraverse)
[![Discord](https://img.shields.io/badge/Discord-Join%20Us-7289da?logo=discord&logoColor=white)](https://discord.com/invite/j633fsrAne)

[Website](https://claraverse.space) · [Documentation](#-documentation) · [Quick Start](#-quick-start) · [Community](#-community) · [Contributing](#-contributing)

</div>

---

## 🚀 Quick Start

**Install CLI:**
```bash
curl -fsSL https://get.claraverse.app | bash
```

**Start ClaraVerse:**
```bash
claraverse init
```

Open **http://localhost** → Register → Add AI provider → Start chatting!

<details>
<summary><b>Other options</b></summary>

**Docker (no CLI):**
```bash
docker run -d -p 80:80 -p 3001:3001 -v claraverse-data:/data claraverseoss/claraverse:latest
```

**Clone & Run:**
```bash
git clone https://github.com/claraverse-space/ClaraVerseAI.git && cd ClaraVerseAI && ./quickstart.sh
```

</details>

---

## ✨ What's Included

Everything runs locally - no external APIs needed:

| Service | Purpose |
|---------|---------|
| **Frontend** | React app on port 80 |
| **Backend** | Go API on port 3001 |
| **MongoDB** | Conversations & workflows |
| **MySQL** | Providers & models |
| **Redis** | Job scheduling |
| **SearXNG** | Web search (no API key!) |
| **E2B** | Code execution (no API key!) |

---

## <img src="https://cdn.simpleicons.org/starship/DD0B78" width="24" height="24" alt="Star"/> Why ClaraVerse?

**Self-hosting isn't enough.** Most "privacy-focused" chat UIs still store your conversations in MongoDB or PostgreSQL. ClaraVerse goes further with **browser-local storage**—even the server admin can't read your chats.

| Feature | ClaraVerse | ChatGPT/Claude | Open WebUI | LibreChat |
|---------|------------|----------------|------------|-----------|
| **Browser-Local Storage** | ✅ Never touches server | ❌ Cloud-only | ❌ Stored in MongoDB | ❌ Stored in MongoDB |
| **Server Can't Read Chats** | ✅ Zero-knowledge architecture | ❌ Full access | ❌ Admin has full access | ❌ Admin has full access |
| **Self-Hosting** | ✅ Optional | ❌ Cloud-only | ✅ Required | ✅ Required |
| **Works Offline** | ✅ Full offline mode | ❌ Internet required | ⚠️ Server required | ⚠️ Server required |
| **Multi-Provider** | ✅ OpenAI, Claude, Gemini, local | ❌ Single provider | ✅ Multi-provider | ✅ Multi-provider |
| **Visual Workflow Builder** | ✅ Chat + n8n combined | ❌ | ❌ | ❌ |
| **Interactive Prompts** | ✅ AI asks questions mid-chat | ❌ | ⚠️ Pre-defined only | ❌ |

> **50,000+ downloads** | The only AI platform where conversations never touch the server—even when self-hosted

<details>
<summary><b>📋 Advanced Setup & Troubleshooting</b></summary>

### Prerequisites
- Docker & Docker Compose installed
- 4GB RAM minimum (8GB recommended)

### Manual Installation

```bash
# 1. Clone
git clone https://github.com/claraverse-space/ClaraVerseAI.git
cd ClaraVerseAI

# 2. Configure
cp .env.default .env

# 3. Start
docker compose up -d

# 4. Verify
docker compose ps
```

### Troubleshooting

```bash
# Run diagnostics
./diagnose.sh     # Linux/Mac
diagnose.bat      # Windows

# View logs
docker compose logs -f backend

# Restart
docker compose restart

# Fresh start
docker compose down -v && docker compose up -d
```

</details>

---

## <img src="https://cdn.simpleicons.org/shieldsdotio/4CAF50" width="24" height="24" alt="Shield"/> Browser-Local Storage: True Zero-Knowledge Privacy

**The Problem with Traditional Self-Hosted Chat UIs:**

When you self-host Open WebUI or LibreChat, conversations are stored in your MongoDB database. You control the server, but the data still exists in a queryable database.

```python
# Traditional self-hosted architecture
User → Server → MongoDB
                   ↓
        db.conversations.find({user_id: "123"})  # Admin can read everything
```

**ClaraVerse's Zero-Knowledge Architecture:**

Conversations stay in your browser's IndexedDB and **never touch the server or database**. The server only proxies API calls to LLM providers—it never sees or stores message content.

```python
# ClaraVerse browser-local mode
User → IndexedDB (browser only, never leaves device)
     → Server (API proxy only, doesn't log or store)
```

### Why This Matters

✅ **Host for Teams Without Liability**: Even as server admin, you **cannot** access user conversations
✅ **True Compliance**: No server-side message retention = simplified GDPR/HIPAA compliance
✅ **No Database Bloat**: Messages aren't stored in MongoDB—database only holds accounts and settings
✅ **Air-Gap Capable**: Browser caches conversations; works completely offline after initial load
✅ **Zero Backup Exposure**: Database backups don't contain sensitive chat content

### Per-Conversation Privacy Control

Unlike competitors that force you into one mode, ClaraVerse lets you choose **per conversation**:

- **Work Projects**: Browser-local mode (100% offline, zero server access)
- **Personal Chats**: Cloud-sync mode (encrypted backup for mobile access)
- **Switch Anytime**: Toggle privacy mode without losing conversation history

**This is privacy-first architecture done right.**

---

## <img src="https://cdn.simpleicons.org/spring_creators/4285F4" width="24" height="24" alt="Images"/> Feature Showcase in a Nutshell

<div align="center">

### Natural Chat Interface
<img src="docs/images/image-1.png" alt="Natural Chat with Multiple AI Models" width="700" />

*Chat naturally with GPT-4, Claude, Gemini, and more - all in one unified interface*

<br/>

### Clara Memory - Context-Aware Conversations
<img src="docs/images/image-2.png" alt="Clara Memory Feature" width="700" />

*Clara remembers your preferences and conversation context across sessions*
<p><b>Clara's memory system: She can remember which is needed in Short Term Memory and <br>Archive rest of the Memories that's not used very often</b></p>

<br/>

### Smart Multi-Agent Orchestration, Chat with Clara to Create your crew of agents
<img src="docs/images/image-3.png" alt="Smart Agents Collaboration" width="700" />

*Coordinate multiple specialized AI agents for complex workflows*
<p><b>Clara's Integrated Architecture allows Chat and Agents to use and <br>share Integration and Automate the chat workflow automatically</b></p>


<br/>

### Private AI Processing - Nothing needs to be stored on the server
<img src="docs/images/image-4.png" alt="Privacy-First Architecture" width="700" />

*Browser-local storage ensures your data stays private - even server admins can't access your conversations* 

</div>

---

## <img src="https://cdn.simpleicons.org/sparkfun/E53525" width="24" height="24" alt="Features"/> Key Features

### <img src="https://cdn.simpleicons.org/letsencrypt/4CAF50" width="20" height="20" alt="Lock"/> **Privacy & Security First**
- **Browser-Local Storage**: Conversations stored in IndexedDB, never touch server—even admins can't read your chats
- **Zero-Knowledge Architecture**: Server only proxies LLM API calls, doesn't log or store message content
- **Per-Conversation Privacy**: Choose browser-local (100% offline) or cloud-sync (encrypted backup) per chat
- **Local JWT Authentication**: Secure authentication with Argon2id password hashing
- **True Offline Mode**: Works completely air-gapped after initial load—no server dependency

### <img src="https://cdn.simpleicons.org/openaccess/412991" width="20" height="20" alt="AI"/> **Universal AI Access**
- **Multi-Provider Support**: OpenAI, Anthropic Claude, Google Gemini, and any OpenAI-compatible endpoint
- **Bring Your Own Key (BYOK)**: Use existing API accounts or free local models
- **400+ Models Available**: From GPT-4o to Llama, Mistral, and specialized models
- **Unified Interface**: One workspace for all your AI needs

### <img src="https://cdn.simpleicons.org/rocketdotchat/FF6B6B" width="20" height="20" alt="Rocket"/> **Advanced Capabilities**
- **Visual Workflow Builder**: Drag-and-drop workflow designer with auto-layout—chat to create, visual editor to refine
- **Hybrid Block Architecture**: Variable blocks, LLM blocks, and Code blocks (execute tools without LLM overhead)
- **Interactive Prompts**: AI asks clarifying questions mid-conversation with typed forms (text, select, checkbox)
- **Real-Time Streaming**: WebSocket-based chat with automatic reconnection and conversation resume
- **Tool Execution**: Code generation, image creation, web search, file analysis with real-time status tracking
- **Response Versioning**: Generate, compare, and track multiple versions (add details, make concise, no search)

### <img src="https://cdn.simpleicons.org/google/4285F4" width="20" height="20" alt="Globe"/> **Cross-Platform & Flexible**
- **Desktop Apps**: Native Windows, macOS, and Linux applications
- **Web Interface**: Browser-based access via React frontend
- **Mobile Ready**: Responsive design for tablets and phones
- **P2P Sync**: Device-to-device synchronization without cloud storage
- **Enterprise Deployment**: Self-host for complete organizational control

### <img src="https://cdn.simpleicons.org/vscodium/007ACC" width="20" height="20" alt="Tools"/> **Developer-Friendly**
- **MCP Bridge**: Native Model Context Protocol support—connect any MCP-compatible tool seamlessly
- **Open API**: RESTful + WebSocket APIs for custom integrations
- **Plugin System**: Extend functionality with custom tools and connectors
- **Docker Support**: One-command deployment with `docker compose`
- **GitHub, Slack, Notion Integration**: Pre-built connectors for your workflow
- **Database Connections**: Query and analyze data with AI assistance

---

## <img src="https://cdn.simpleicons.org/target/CC0000" width="24" height="24" alt="Target"/> Our Mission

**Building the best AI interface experience—without compromising your privacy.**

While other AI tools force you to choose between features and privacy, ClaraVerse refuses that trade-off. We believe you deserve both: a powerful, intuitive interface AND complete data sovereignty.

### Why ClaraVerse is Different

Most "privacy-focused" AI tools sacrifice usability for security. Open WebUI and others offer self-hosting, but you're still limited to basic chat interfaces. ClaraVerse goes further:

<img src="https://cdn.simpleicons.org/figma/00C4CC" width="18" height="18" alt="Design"/> **Best-in-Class Interface**
- Intuitive, polished UI that rivals ChatGPT and Claude
- Real-time streaming with automatic reconnection
- Smart context management across sessions
- Multi-modal support (text, images, code, files)
- Clara Memory: Remembers what matters, archives what doesn't

<img src="https://cdn.simpleicons.org/letsencrypt/4CAF50" width="18" height="18" alt="Lock"/> **Privacy WITHOUT Compromise**
- **Browser-local storage**: Conversations in IndexedDB, never touch server/database
- **Zero-knowledge architecture**: Server admins cannot read user chats—even in self-hosted deployments
- **Per-conversation privacy**: Toggle browser-local (offline) vs cloud-sync (encrypted) per chat
- **Air-gap capable**: Works 100% offline after initial load, no server dependency
- **Local authentication**: JWT with Argon2id password hashing, no external auth services
- **Open source (AGPL-3.0)**: Verify and audit security yourself

<img src="https://cdn.simpleicons.org/probot/00B0D8" width="18" height="18" alt="Plugin"/> **Extensibility That Matters**
- **MCP Bridge**: Native Model Context Protocol integration for seamless tool connections
- Multi-agent orchestration: Coordinate specialized AI agents for complex workflows
- 400+ models: OpenAI, Anthropic, Google, Gemini, and any OpenAI-compatible endpoint
- BYOK: Use your own API keys or completely free local models
- Plugin ecosystem: GitHub, Slack, Notion, databases, and custom integrations

<img src="https://cdn.simpleicons.org/rocketdotchat/FF6B6B" width="18" height="18" alt="Platform"/> **All-in-One Platform**
- Replaces ChatGPT (conversations), Midjourney (image generation), n8n (workflows)
- **Visual workflow builder + chat** in one interface—chat to design, visual editor to execute
- **Interactive prompts**: AI asks clarifying questions mid-conversation with typed forms
- **Memory auto-archival**: Active memory management—keeps context focused without manual cleanup
- Cross-platform: Desktop apps, web interface, mobile-ready
- P2P sync: Device-to-device synchronization without cloud dependencies

### Our Promise

**Privacy-first doesn't mean features-last.** Every interface decision, every feature, every line of code is designed with this dual commitment:

1. **Security by Default**: Your data, your keys, your control
2. **Excellence by Design**: Experience that makes privacy feel effortless

### Built For

- **Individuals**: Super-powered AI workspace without surveillance
- **Developers**: Open API, MCP bridge, plugin system, complete source access
- **Teams**: Collaborate with AI while keeping confidential data on-premises
- **Enterprises**: Deploy infrastructure that complies with strictest data sovereignty requirements (GDPR, HIPAA, SOC2)

> **50,000+ downloads worldwide** | Join developers and privacy advocates who refuse to compromise

---

## <img src="https://cdn.simpleicons.org/bookstack/0288D1" width="24" height="24" alt="Book"/> Documentation

| Resource | Description |
|----------|-------------|
| [<img src="https://cdn.simpleicons.org/apachenetbeanside/1B6AC6" width="14"/> Architecture Guide](backend/docs/ARCHITECTURE.md) | System design and component overview |
| [<img src="https://cdn.simpleicons.org/fastapi/009688" width="14"/> API Reference](backend/docs/API_REFERENCE.md) | REST and WebSocket API documentation |
| [<img src="https://cdn.simpleicons.org/docker/2496ED" width="14"/> Docker Guide](docs/DOCKER.md) | Comprehensive Docker deployment |
| [<img src="https://cdn.simpleicons.org/letsencrypt/4CAF50" width="14"/> Security Guide](backend/docs/FINAL_SECURITY_INSPECTION.md) | Security features and best practices |
| [<img src="https://cdn.simpleicons.org/serverfault/E7282D" width="14"/> Admin Guide](backend/docs/ADMIN_GUIDE.md) | System administration and configuration |
| [<img src="https://cdn.simpleicons.org/accenture/007ACC" width="14"/> Developer Guide](backend/docs/DEVELOPER_GUIDE.md) | Contributing and local development |
| [<img src="https://cdn.simpleicons.org/lightning/FFCC00" width="14"/> Quick Reference](backend/docs/QUICK_REFERENCE.md) | Common commands and workflows |

---

## <img src="https://cdn.simpleicons.org/apachenetbeanside/1B6AC6" width="24" height="24" alt="Architecture"/> Architecture

ClaraVerse is built with modern, production-ready technologies:

```
┌─────────────────────────────────────────────────────────────┐
│                      Frontend Layer                          │
│         React 19 + TypeScript + Tailwind CSS 4              │
│              Zustand State + React Router 7                  │
└────────────────────┬────────────────────────────────────────┘
                     │ WebSocket + REST API
┌────────────────────▼────────────────────────────────────────┐
│                      Backend Layer                           │
│              Go 1.24 + Fiber Framework                       │
│         Real-time Streaming + Tool Execution                 │
└────────────────────┬────────────────────────────────────────┘
                     │
        ┌────────────┼────────────┐
        │            │            │
   ┌────▼───┐   ┌───▼────┐  ┌───▼────┐
   │MongoDB │   │ Redis  │  │SearXNG │
   │Storage │   │  Jobs  │  │ Search │
   └────────┘   └────────┘  └────────┘
```

**Technology Stack:**
- **Frontend**: <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" width="16"/> React 19, <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" width="16"/> TypeScript, <img src="https://cdn.simpleicons.org/vite/646CFF" width="16"/> Vite 7, <img src="https://cdn.simpleicons.org/tailwindcss/06B6D4" width="16"/> Tailwind CSS 4, <img src="https://cdn.simpleicons.org/redux/764ABC" width="16"/> Zustand 5
- **Backend**: <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/go/go-original.svg" width="16"/> Go 1.24, <img src="https://cdn.simpleicons.org/go/00ADD8" width="16"/> Fiber (web framework), WebSocket streaming
- **Database**: <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg" width="16"/> MongoDB for persistence, <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" width="16"/> MySQL for models/providers, <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/redis/redis-original.svg" width="16"/> Redis for caching/jobs
- **Services**: <img src="https://cdn.simpleicons.org/searxng/3050FF" width="16"/> SearXNG (search), E2B Local Docker (code execution - no API key!)
- **Deployment**: <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" width="16"/> Docker Compose, <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nginx/nginx-original.svg" width="16"/> Nginx reverse proxy
- **Auth**: <img src="https://cdn.simpleicons.org/jsonwebtokens/000000" width="16"/> Local JWT with Argon2id password hashing (v2.0 - fully local, no Supabase)

---

## <img src="https://cdn.simpleicons.org/modelscope/00C4CC" width="24" height="24" alt="Palette"/> Features in Detail

### Real-Time Streaming Chat

Experience instant AI responses with our WebSocket-based architecture:

- **Chunked Streaming**: See responses as they're generated
- **Connection Recovery**: Automatic reconnection with conversation resume
- **Heartbeat System**: Maintains stable connections through proxies
- **Multi-User Support**: Concurrent conversations without interference

### Tool Execution Engine

Extend AI capabilities beyond text:

| Tool | Description | Example |
|------|-------------|---------|
| **Code Generation** | Execute Python, JavaScript, Go code in sandboxed E2B environment | "Write and run a script to analyze this CSV" |
| **Image Generation** | Create images with DALL-E, Stable Diffusion, or local models | "Generate a logo for my startup" |
| **Web Search** | Real-time internet search via SearXNG | "What are the latest AI developments?" |
| **File Analysis** | Process PDFs, images, documents with vision models | "Summarize this 50-page report" |
| **Data Query** | Connect to databases and run SQL queries | "Show sales trends from our PostgreSQL" |

### Bring Your Own Key (BYOK)

Use your existing AI subscriptions:

1. Add your API keys in `backend/providers.json`
2. Configure model preferences and rate limits
3. Switch between providers seamlessly
4. Or use completely free local models (Ollama, LM Studio)

```json
{
  "providers": [
    {
      "name": "OpenAI",
      "api_key": "sk-your-key",
      "models": ["gpt-4o", "gpt-4o-mini"]
    },
    {
      "name": "Anthropic",
      "api_key": "your-key",
      "models": ["claude-3-5-sonnet", "claude-3-opus"]
    }
  ]
}
```

### Multi-Agent Orchestration

Coordinate multiple AI agents for complex workflows:

- **Specialized Agents**: Create agents with specific roles (researcher, coder, analyst)
- **Agent Collaboration**: Agents can communicate and share context
- **Workflow Automation**: Chain agent tasks for multi-step processes
- **Custom Instructions**: Define agent behavior with natural language

---

## <img src="https://cdn.simpleicons.org/chartdotjs/FF6384" width="24" height="24" alt="Chart"/> Use Cases

### For Developers
- **Code Review & Debugging**: Get instant feedback on code quality
- **Documentation Generation**: Auto-generate docs from codebases
- **API Integration**: Connect ClaraVerse to your development workflow
- **Database Analysis**: Query and visualize data with AI assistance

### For Businesses
- **Zero-Liability Hosting**: Host for teams without server-side chat storage—admins can't access conversations
- **True Data Sovereignty**: Browser-local mode means data never leaves employee devices, even when self-hosted
- **Simplified Compliance**: No message retention in database = easier GDPR/HIPAA compliance
- **Team Collaboration**: Shared AI workspace with access control and privacy guarantees
- **Custom Integrations**: Connect to Slack, Notion, GitHub, CRMs via visual workflow builder
- **Cost Control**: BYOK means you control AI spending with your own API keys

### For Privacy Advocates
- **Browser-Local Storage**: Conversations never touch server—even when self-hosted, admins can't read chats
- **Zero-Knowledge Architecture**: Server only proxies API calls, doesn't log or store message content
- **Per-Conversation Privacy**: Choose offline browser-local or encrypted cloud-sync per conversation
- **Air-Gapped Operation**: Works 100% offline after initial load—no server dependency
- **Open Source**: Verify zero-knowledge claims yourself or hire security auditors
- **No Database Retention**: Messages not stored in MongoDB—simplified compliance for GDPR/HIPAA

### For Researchers
- **Experiment with Models**: Test 400+ models in one interface
- **Dataset Analysis**: Process large datasets with AI assistance
- **Literature Review**: Search and summarize academic papers
- **Reproducible Workflows**: Save and share AI-assisted research processes

---

## <img src="https://cdn.simpleicons.org/openstreetmap/7EBC6F" width="24" height="24" alt="Map"/> Roadmap

### ✅ Completed (v2.0 - Current Version)
- [x] **Browser-local storage** (IndexedDB) with zero-knowledge architecture
- [x] **Visual workflow builder** with drag-and-drop interface and auto-layout
- [x] **Interactive prompts** (AI asks questions mid-conversation with typed forms)
- [x] **Per-conversation privacy toggle** (browser-local vs cloud-sync)
- [x] Multi-provider LLM support (OpenAI, Anthropic, Google, OpenAI-compatible)
- [x] Real-time WebSocket streaming with automatic reconnection
- [x] Tool execution (code, image generation, web search)
- [x] Response versioning (regenerate, add details, make concise, etc.)
- [x] Memory system with auto-archival and scoring
- [x] Hybrid block architecture (Variable, LLM, Code blocks)
- [x] Docker-based deployment
- [x] BYOK (Bring Your Own Key) functionality
- [x] MongoDB + MySQL + Redis infrastructure
- [x] **Local JWT authentication** (v2.0 - replaced Supabase, fully offline)
- [x] **E2B Local Docker mode** (v2.0 - code execution without API key)
- [x] **Removed payment processing** (v2.0 - all users Pro tier by default)
- [x] **Removed CAPTCHA** (v2.0 - rate limiting only)
- [x] **100% offline core functionality** (v2.0 - no external service dependencies)
- [x] File upload support with previews (images, PDFs, documents, CSV, audio)
- [x] Markdown rendering with reasoning extraction

### 🚧 In Progress (v1.1)
- [ ] Desktop applications (Windows, macOS, Linux)
- [ ] Mobile apps (iOS, Android)
- [ ] P2P device synchronization
- [ ] Enhanced multi-agent orchestration
- [ ] Plugin marketplace

### 🔮 Planned (v2.0 and beyond)
- [ ] Local LLM integration (Ollama, LM Studio native support)
- [ ] Voice input/output
- [ ] Advanced RAG (Retrieval-Augmented Generation)
- [ ] Workspace collaboration features
- [ ] Browser extension
- [ ] Kubernetes deployment templates
- [ ] Enterprise SSO integration

[View full roadmap →](https://github.com/claraverse-space/ClaraVerseAI/projects)

---

## <img src="https://cdn.simpleicons.org/handshake/F7931E" width="24" height="24" alt="Handshake"/> Contributing

We welcome contributions from developers of all skill levels! ClaraVerse is built by the community, for the community.

### How to Contribute

1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feature/amazing-feature`
3. **Make** your changes and add tests
4. **Run** linting: `npm run lint && go vet ./...`
5. **Commit** with clear messages: `git commit -m 'Add amazing feature'`
6. **Push** to your fork: `git push origin feature/amazing-feature`
7. **Open** a Pull Request with a detailed description

### Contribution Areas

We especially welcome help in these areas:

- <img src="https://cdn.simpleicons.org/databricks/FF3621" width="16" height="16" alt="Bug"/> **Bug Fixes**: Check [open issues](https://github.com/claraverse-space/ClaraVerseAI/issues)
- <img src="https://cdn.simpleicons.org/readthedocs/8CA1AF" width="16" height="16" alt="Docs"/> **Documentation**: Improve guides, add examples, fix typos
- <img src="https://cdn.simpleicons.org/googletranslate/4285F4" width="16" height="16" alt="Language"/> **Translations**: Help us reach non-English speakers
- <img src="https://cdn.simpleicons.org/figma/F24E1E" width="16" height="16" alt="Design"/> **UI/UX**: Design improvements and accessibility
- <img src="https://cdn.simpleicons.org/pytest/0A9EDC" width="16" height="16" alt="Testing"/> **Testing**: Add unit tests, integration tests, E2E tests
- <img src="https://cdn.simpleicons.org/probot/00B0D8" width="16" height="16" alt="Plugin"/> **Integrations**: Build connectors for new tools and services
- <img src="https://cdn.simpleicons.org/codersrank/412991" width="16" height="16" alt="AI"/> **Models**: Add support for new LLM providers

### Development Setup

See [DEVELOPER_GUIDE.md](backend/docs/DEVELOPER_GUIDE.md) for detailed instructions.

Quick start for contributors:

```bash
# Install dependencies
make install

# Start development environment with hot reload
./dev.sh

# Run tests
cd frontend && npm run test
cd backend && go test ./...

# Check code quality
npm run lint && npm run format
go vet ./... && go fmt ./...
```

### Code of Conduct

We are committed to providing a welcoming and inclusive environment. Please read our [Code of Conduct](CODE_OF_CONDUCT.md) before participating.

---

## <img src="https://cdn.simpleicons.org/element/0DBD8B" width="24" height="24" alt="Community"/> Community

Join thousands of privacy-conscious developers and AI enthusiasts:

- <img src="https://cdn.simpleicons.org/discord/5865F2" width="16" height="16" alt="Discord"/> **[Discord](https://discord.com/invite/j633fsrAne)**: Real-time chat and support
- <img src="https://cdn.simpleicons.org/x/1DA1F2" width="16" height="16" alt="X"/> **[Twitter/X](https://x.com/clara_verse_)**: Updates and announcements
- <img src="https://cdn.simpleicons.org/tiktok/000000" width="16" height="16" alt="TikTok"/> **[TikTok](https://www.tiktok.com/@claraversehq)**: Short-form content and demos
- <img src="https://cdn.simpleicons.org/substack/FF6719" width="16" height="16" alt="Newsletter"/> **[Newsletter](https://claraverse.space/newsletter)**: Monthly updates and tips
- <img src="https://cdn.simpleicons.org/youtube/FF0000" width="16" height="16" alt="YouTube"/> **[YouTube](https://www.youtube.com/@ClaraVerseAI)**: Tutorials and demos
- <img src="https://cdn.simpleicons.org/imessage/0077B5" width="16" height="16" alt="LinkedIn"/> **[LinkedIn](https://linkedin.com/company/claraverse)**: Professional updates

### Show Your Support

If ClaraVerse has helped you, consider:

- <img src="https://cdn.simpleicons.org/starship/DD0B78" width="16" height="16" alt="Star"/> **Star** this repository
- <img src="https://cdn.simpleicons.org/databricks/FF3621" width="16" height="16" alt="Bug"/> **Report bugs** and suggest features
- <img src="https://cdn.simpleicons.org/sharex/5D50C6" width="16" height="16" alt="Share"/> **Share** with colleagues and on social media
- <img src="https://cdn.simpleicons.org/githubsponsors/EA4AAA" width="16" height="16" alt="Sponsor"/> **Sponsor** development ([GitHub Sponsors](https://github.com/sponsors/claraverse-space))
- <img src="https://cdn.simpleicons.org/githubsponsors/007ACC" width="16" height="16" alt="Code"/> **Contribute** code, docs, or designs

---


## <img src="https://cdn.simpleicons.org/libreofficewriter/18A303" width="24" height="24" alt="License"/> License

ClaraVerse is licensed under the **GNU Affero General Public License v3.0 (AGPL-3.0)** - see the [LICENSE](LICENSE) file for details.

### What This Means:

**You ARE free to:**
- ✅ **Use commercially** - Host ClaraVerse as a service, even for profit
- ✅ **Modify** - Customize and improve the software
- ✅ **Distribute** - Share with others
- ✅ **Private use** - Use internally in your organization

**BUT you MUST:**
- 📤 **Share modifications** - Any changes must be open-sourced under AGPL-3.0
- 🌐 **Network copyleft** - If you host ClaraVerse as a service, users must have access to your source code
- 📝 **Credit developers** - Preserve copyright and license notices
- 🔓 **Give back to the community** - Improvements benefit everyone

### Why AGPL-3.0?

We chose AGPL-3.0 to ensure that:
1. **ClaraVerse remains free forever** - No one can take it private
2. **The community benefits from all improvements** - Even from hosted/SaaS deployments
3. **Developers get credit** - Your contributions are always attributed
4. **Big tech gives back** - Companies using ClaraVerse must contribute improvements

**ClaraVerse is and will remain free and open-source forever.**

---

## <img src="https://cdn.simpleicons.org/githubsponsors/EA4AAA" width="24" height="24" alt="Thanks"/> Acknowledgments

ClaraVerse is built on the shoulders of giants. Special thanks to:

- <img src="https://cdn.simpleicons.org/go/00ADD8" width="16"/> **[Go Fiber](https://gofiber.io/)** - Lightning-fast web framework
- <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" width="16"/> **[React](https://react.dev/)** - UI library
- <img src="https://cdn.simpleicons.org/anthropic/D4A574" width="16"/> **[Anthropic](https://anthropic.com/)**, <img src="https://cdn.simpleicons.org/openai/412991" width="16"/> **[OpenAI](https://openai.com/)**, <img src="https://cdn.simpleicons.org/google/4285F4" width="16"/> **[Google](https://ai.google.dev/)** - AI model providers
- <img src="https://cdn.simpleicons.org/searxng/3050FF" width="16"/> **[SearXNG](https://github.com/searxng/searxng)** - Privacy-respecting search
- **[E2B](https://e2b.dev/)** - Code execution sandboxes (now running in local Docker mode!)
- **[Argon2](https://github.com/P-H-C/phc-winner-argon2)** - Password hashing library
- All our [contributors](https://github.com/claraverse-space/ClaraVerseAI/graphs/contributors) and community members

**Note**: v2.0 moved from Supabase to local JWT authentication for complete offline capability

---

## <img src="https://cdn.simpleicons.org/helpscout/1292EE" width="24" height="24" alt="Help"/> Troubleshooting

### Common Issues

<details>
<summary><b>WebSocket connection drops frequently</b></summary>

**Solution**: Check nginx/proxy timeout settings. Ensure `proxy_read_timeout` is at least 300s:

```nginx
location /ws/ {
    proxy_pass http://localhost:3001;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "upgrade";
    proxy_read_timeout 300s;
}
```
</details>

<details>
<summary><b>Docker containers won't start</b></summary>

**Solution**: Check for port conflicts and validate compose file:

```bash
# Check logs
docker compose logs backend

# Validate configuration
docker compose config

# Check port usage
lsof -i :3001
```
</details>

<details>
<summary><b>Models not appearing in UI</b></summary>

**Solution**: Verify `backend/providers.json` configuration:

1. Ensure file exists (copy from `providers.example.json`)
2. Check API keys are valid
3. Verify `enabled: true` for each provider
4. Restart backend: `docker compose restart backend`
</details>

<details>
<summary><b>Build failures</b></summary>

**Solution**: Ensure you have the correct versions:

```bash
go version  # Should be 1.24+
node --version  # Should be 20+
python --version  # Should be 3.11+
```

Clear caches and reinstall:
```bash
make clean
make install
```
</details>

For more help:
- <img src="https://cdn.simpleicons.org/bookstack/0288D1" width="16" height="16" alt="Guide"/> [Full troubleshooting guide](backend/docs/TROUBLESHOOTING.md)
- <img src="https://cdn.simpleicons.org/discord/5865F2" width="16" height="16" alt="Discord"/> [Discord support channel](https://discord.com/invite/j633fsrAne)
- <img src="https://cdn.simpleicons.org/databricks/FF3621" width="16" height="16" alt="Bug"/> [Report an issue](https://github.com/claraverse-space/ClaraVerseAI/issues)

---

## <img src="https://cdn.simpleicons.org/telegram/26A5E4" width="24" height="24" alt="Contact"/> Contact

- <img src="https://cdn.simpleicons.org/googlechrome/4285F4" width="16" height="16" alt="Website"/> **Website**: [claraverse.space](https://claraverse.space)
- <img src="https://cdn.simpleicons.org/gmail/EA4335" width="16" height="16" alt="Email"/> **Email**: [hello@claraverse.space](mailto:hello@claraverse.space)
- <img src="https://cdn.simpleicons.org/databricks/FF3621" width="16" height="16" alt="Enterprise"/> **Enterprise**: [enterprise@claraverse.space](mailto:enterprise@claraverse.space)
- <img src="https://cdn.simpleicons.org/github/181717" width="16" height="16" alt="Bug"/> **Bug Reports**: [GitHub Issues](https://github.com/claraverse-space/ClaraVerseAI/issues)
- <img src="https://cdn.simpleicons.org/gitbook/3884FF" width="16" height="16" alt="Ideas"/> **Feature Requests**: [GitHub Discussions](https://github.com/claraverse-space/ClaraVerseAI/discussions)

---

<div align="center">

**Built with ❤️ by the ClaraVerse Community**

*Pioneering the new age of private, powerful AI for the Super Individual*

[⬆ Back to Top](#️-claraverse)

</div>
