**Built with [Hyperbrowser](https://hyperbrowser.ai)**

# HyperbookLM

A powerful research assistant built with Next.js 15, React 19, and Hyperbrowser. It allows users to aggregate diverse sources (Web URLs, PDFs) and gain deep insights through interactive AI tools.


## Features

- **Multi-Source Ingestion**: 
  - **Scrape Web URLs**: Instantly extract content from any website using **Hyperbrowser**.
  - **PDF Uploads**: Parse and analyze PDF documents client-side.
- **Deep Research Analysis**:
  - **AI Research Summary**: Generates comprehensive summaries with key insights 
  - **Interactive Mindmap**: Visualizes relationships between concepts using React Flow.
  - **Audio Overview**: Generates a podcast-style audio summary (`ElevenLabs`).
  - **Presentation Slides**: Auto-generates slide decks from your sources 
- **Interactive Chat**: Ask questions about your sources with streaming AI responses


## Tech Stack

- **Framework**: Next.js 15 (App Router)
- **UI Library**: React 19, Tailwind CSS, shadcn/ui, Framer Motion
- **Web Scraping**: [Hyperbrowser SDK](https://hyperbrowser.ai)
- **AI Models**: 
  - **OpenAI**: `gpt-5-nano` (Chat), `gpt-4o-mini` (Summary, Mindmap)
  - **Google Gemini**: `gemini-3-pro-image-preview` (Slides)
  - **ElevenLabs**: `eleven_turbo_v2_5` (Audio)
- **Visualization**: React Flow (Mindmaps)
- **PDF Processing**: `unpdf`

## Getting Started

### Prerequisites

You'll need API keys for the following services:

1. **Hyperbrowser** - [Get API Key](https://hyperbrowser.ai) (Required for web scraping)
2. **OpenAI** - [Get API Key](https://platform.openai.com) (Required for Chat, Summary, Mindmap)
3. **Google Gemini** - [Get API Key](https://ai.google.dev) (Required for Slides)
4. **ElevenLabs** - [Get API Key](https://elevenlabs.io) (Optional, for Audio)

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/hyperbrowserai/hyperbooklm.git
   cd hyperbooklm
   ```

2. **Install dependencies**:
   ```bash
   yarn
   # or
   npm install
   ```

3. **Set up environment variables**:
   Create a `.env.local` file in the root directory:
   ```bash
   cp .env.local.example .env.local
   ```

   Add your keys:
   ```env
   # Hyperbrowser API Key
   HYPERBROWSER_API_KEY=your_hyperbrowser_key

   # OpenAI API Key
   OPENAI_API_KEY=your_openai_key

   # Google Gemini API Key
   GEMINI_API_KEY=your_gemini_key

   # ElevenLabs API Key (Optional)
   ELEVENLABS_API_KEY=your_elevenlabs_key
   ```

4. **Run the development server**:
   ```bash
   yarn dev
   ```

5. **Open your browser**:
   Navigate to [http://localhost:3000](http://localhost:3000)

## Growth Use-Cases

This project demonstrates how to build high-value growth tools using Hyperbrowser:

- **Content Repurposing**: Scrape blog posts and auto-generate LinkedIn carousels (Slides) or podcasts (Audio).
- **Competitor Analysis**: Ingest competitor landing pages to generate SWOT analysis mindmaps.
- **Research Automation**: aggregate whitepapers (PDFs) and documentation (URLs) into a single queryable knowledge base.

## Project Structure

```
hyperbooklm/
├── app/
│   ├── api/                # Next.js API Routes (Server-side)
│   │   ├── audio/          # ElevenLabs integration
│   │   ├── chat/           # OpenAI Chat integration
│   │   ├── gemini/slides/  # Google Gemini Slides generation
│   │   ├── gpt/mindmap/    # OpenAI Mindmap generation
│   │   ├── scrape/         # Hyperbrowser Scraping
│   │   ├── summary/        # Research Summary generation
│   │   └── upload/         # PDF/TXT File processing
│   ├── page.tsx            # Main application logic
│   └── globals.css         # Global styles
├── components/
│   ├── ChatInterface.tsx   # Chat UI
│   ├── MindMap.tsx         # React Flow visualization
│   ├── Navbar.tsx          # Navigation & Branding
│   ├── OutputsPanel.tsx    # Right-side results panel
│   └── SourcesPanel.tsx    # Left-side source management
└── lib/
    ├── api/                # API clients
    └── types.ts            # TypeScript interfaces
```

## License

MIT

---

**Follow [@hyperbrowser](https://x.com/hyperbrowser) for updates.**
