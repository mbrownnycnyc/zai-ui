# ZAI-UI

AI-powered web application for image generation, video creation, and chat interactions with persistent storage.

## Quick Start

```bash
# Clone the repository
git clone https://github.com/mbrownnycnyc/zai-ui.git
cd zai-ui

# Clone required API documentation
git clone https://github.com/mbrownnycnyc/zai-api-documentation.git

# Install dependencies
npm install

# Set up environment
cp .env.example .env
# Edit .env with your configuration

# Set up database
npm run db:migrate
npm run db:seed

# Start development server
npm run dev
```

Application available at `http://localhost:3000`.

## Required Documentation

The `zai-api-documentation` repository contains essential z.ai API documentation and must be cloned for development.

## Features

### Image Generation
- Batch processing (5-10 images)
- Quality optimization (Fast <10s, Standard 10-30s, High Quality 30-60s)
- Multiple resolutions (1024x1024 to 4096x4096)
- Color palette customization
- Metadata export (JSON, CSV, PDF)

### Video Generation
- Multi-image sequencing (5-10 images)
- Animation styles (fade, slide, zoom, 3D rotation)
- Flexible specifications (720p to 4K, 30s to 5min)
- Frame rate control (24fps to 120fps)
- Real-time preview with processing estimates

### Chat Features
- Conversation threading (20 concurrent threads)
- Exportable logs (PDF, JSON, CSV, Markdown)
- AI prompt suggestions
- Cross-device synchronization

### Storage System
- Multi-format support (chat, images, videos)
- Search functionality across all content
- 10GB user limit with monitoring
- Annual content rolling with warnings
- User-managed backups

## Technology Stack

- **Frontend**: React, Next.js 14+, TypeScript, Tailwind CSS
- **Backend**: Next.js API Routes, PostgreSQL, Prisma
- **Deployment**: Vercel, GitHub Actions

## Available Scripts

```bash
npm run dev          # Development server
npm run build        # Production build
npm run start        # Production server
npm run test         # Run tests
npm run lint         # ESLint
npm run format       # Prettier formatting
```

## CLI Interface

All functionality accessible via CLI:

```bash
# Image generation
npx zai-ui generate-image --prompt "landscape" --resolution 2048
npx zai-ui batch-generate --input ./images

# Video generation
npx zai-ui create-video --images ./frames --style fade
npx zai-ui preview-video --project ./video-project

# Storage operations
npx zai-ui store --type image --file ./photo.jpg
npx zai-ui search --query "landscape photos"

# Chat operations
npx zai-ui chat --thread "discussion" --export pdf
```

## Performance Targets

- Page load: <3 seconds
- API response: <2 seconds
- Uptime: 99.9%
- Test coverage: 90%

## Environment Variables

Required:
- `DATABASE_URL`: PostgreSQL connection
- `NEXTAUTH_SECRET`: Authentication secret
- `ZAI_API_KEY`: z.ai API authentication
- `STORAGE_ENDPOINT`: File storage endpoint

## License

MIT License - see LICENSE file for details.