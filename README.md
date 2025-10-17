# ZAI-UI

A modern web application for AI-powered image generation, video creation, and chat interactions with persistent storage capabilities.

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- PostgreSQL 14+
- Vercel CLI (for deployment)

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd zai-ui

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env
# Edit .env with your configuration

# Set up the database
npm run db:migrate
npm run db:seed

# Start development server
npm run dev
```

The application will be available at `http://localhost:3000`.

## 🏗️ Architecture

### Technology Stack

**Frontend & Framework**
- **React** - UI components with modern hooks and patterns
- **Next.js 14+** - Full-stack framework with App Router
- **TypeScript** - Type safety with strict mode enabled
- **Tailwind CSS** - Utility-first styling framework

**Backend & Database**
- **PostgreSQL** - Primary database with relational schema
- **Next.js API Routes** - Backend API endpoints
- **Prisma** - Database ORM and migrations

**Deployment & Infrastructure**
- **Vercel** - Primary deployment platform
- **GitHub Actions** - CI/CD pipeline

## 🎯 Core Features

### 1. Image Generation Suite
- **Batch Processing**: Generate 5-10 images simultaneously with consistent parameters
- **Quality Optimization**: Variable processing modes (Fast: <10s, Standard: 10-30s, High Quality: 30-60s)
- **Resolution Options**: Multiple resolutions (1024x1024, 2048x2048, 4096x4096, custom)
- **Color Palette Customization**: Preset and custom color schemes with real-time preview
- **Metadata Export**: Comprehensive metadata in JSON, CSV, and PDF formats

### 2. Video Generation Suite
- **Multi-Image Sequencing**: Upload and arrange 5-10 images for video creation
- **Animation Styles**: Multiple transitions (fade, slide, zoom, 3D rotation, cross dissolve)
- **Flexible Specifications**: Multiple video options (Basic: 720p/30s, Standard: 1080p/2min, High: 4K/5min)
- **Frame Rate Control**: Support for 24fps, 30fps, 60fps, and custom rates (15-120fps)
- **Real-time Preview**: Preview functionality with processing time estimates
- **Complexity-Based Timing**: Processing scales with video complexity (simple <60s, standard 1-3min, complex 3-5min)

### 3. Chat Enhancement Suite
- **Conversation Threading**: Support for 20 concurrent threads with independent context
- **Exportable Logs**: Export conversations in PDF, JSON, CSV, and Markdown formats
- **AI Prompt Suggestions**: Context-aware prompt recommendations
- **Cross-Device Sync**: Conversation synchronization across devices

### 4. Persistent Storage System
- **Multi-Format Support**: Store chat conversations, images, and videos
- **Search Functionality**: Text-based search across all content types
- **Storage Management**: 10GB user limit with capacity monitoring
- **Annual Content Rolling**: 30-day advance warnings for content cleanup
- **User-Managed Backups**: Manual backup and restore operations

## 🔧 Development

### Project Structure

```
zai-ui/
├── src/
│   ├── app/                    # Next.js App Router
│   ├── components/             # Reusable React components
│   ├── lib/                    # Utility functions and configurations
│   ├── types/                  # TypeScript type definitions
│   └── hooks/                  # Custom React hooks
├── prisma/                     # Database schema and migrations
├── public/                     # Static assets
├── docs/                       # Documentation
└── specs/                      # Feature specifications
```

### Available Scripts

```bash
# Development
npm run dev          # Start development server
npm run build        # Build for production
npm run start        # Start production server

# Database
npm run db:migrate   # Run database migrations
npm run db:seed      # Seed database with sample data
npm run db:studio    # Open Prisma Studio

# Testing
npm run test         # Run tests
npm run test:watch   # Run tests in watch mode
npm run test:coverage # Generate coverage report

# Code Quality
npm run lint         # Run ESLint
npm run lint:fix     # Fix ESLint issues
npm run type-check   # Run TypeScript type checking
npm run format       # Format code with Prettier
```

### CLI Interface

All functionality is accessible via command-line interface per constitutional requirements:

```bash
# Image Generation
npx zai-ui generate-image --prompt "landscape" --resolution 2048 --quality high
npx zai-ui batch-generate --input ./images --quality standard

# Video Generation
npx zai-ui create-video --images ./frames --style fade --framerate 30
npx zai-ui preview-video --project ./video-project

# Storage Operations
npx zai-ui store --type image --file ./photo.jpg
npx zai-ui search --query "landscape photos" --format json
npx zai-ui backup --all --output ./backup.zip

# Chat Operations
npx zai-ui chat --thread "project-discussion" --export pdf
npx zai-ui suggest-prompts --context "web development"
```

## 📊 Performance Targets

### Core Web Vitals
- **First Contentful Paint**: <3 seconds
- **Time to Interactive**: <1 second
- **Lighthouse Score**: 90+
- **Bundle Size**: Monitored and optimized

### API Performance
- **Image Generation**: Fast <10s, Standard 10-30s, High Quality 30-60s
- **Video Generation**: Simple <60s, Standard 1-3min, Complex 3-5min
- **Search Response**: <2 seconds for 95% of queries
- **Storage Operations**: <1 second for metadata, <5 seconds for files

### Success Metrics
- **Uptime Target**: 99.9%
- **Test Coverage**: 90% minimum
- **User Satisfaction**: 4.5/5 average rating
- **API Compliance**: 100% adherence to rate limits

## 🔒 Security

- **HTTPS Enforcement**: All environments
- **Content Security Policy**: Configured headers
- **XSS/CSRF Protection**: Built-in mechanisms
- **Input Validation**: Comprehensive sanitization
- **API Authentication**: Secure key-based access

## 📱 Accessibility

- **Responsive Design**: Mobile and desktop optimized
- **Touch Support**: Mobile device navigation
- **Screen Reader**: Compatible with assistive technologies
- **Keyboard Navigation**: Full keyboard accessibility
- **High Contrast**: Support for high contrast modes

## 🗂️ Database Schema

### Core Tables
- **users**: User accounts and preferences
- **conversations**: Chat threads and messages
- **images**: Generated images with metadata
- **videos**: Video projects and exports
- **storage**: File storage metadata and references
- **search_index**: Full-text search capabilities

### Relationships
- Relational design with foreign key constraints
- Optimized indexes for search and retrieval
- JSON columns for flexible metadata storage

## 🚀 Deployment

### Vercel (Primary)
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy to production
vercel --prod

# Preview deployment
vercel
```

### Environment Variables
Required environment variables:
- `DATABASE_URL`: PostgreSQL connection string
- `NEXTAUTH_SECRET`: Authentication secret
- `ZAI_API_KEY`: z.ai API authentication
- `STORAGE_ENDPOINT`: File storage endpoint

## 📚 Documentation

- **API Documentation**: `/docs/api` (OpenAPI specification)
- **Component Docs**: Storybook for component library
- **Architecture**: `/docs/architecture.md`
- **Deployment Guide**: `/docs/deployment.md`

## 🧪 Testing

### Test Strategy
- **Integration-First**: Focus on integration tests over unit tests
- **Test-First Development**: Write tests before implementation
- **Coverage Requirements**: 90% minimum coverage
- **E2E Testing**: Cypress for critical user workflows

### Test Categories
- **Component Tests**: React Testing Library
- **API Tests**: Endpoint validation and error handling
- **Database Tests**: Schema validation and query performance
- **E2E Tests**: Critical user journey validation

## 📋 Development Workflow

### Branch Strategy
- `main`: Production-ready code
- `develop`: Integration branch
- `feature/*`: Feature development branches
- `hotfix/*`: Critical bug fixes

### Commit Standards
- Conventional commit messages
- Mandatory code reviews
- Automated testing integration
- Feature flags for controlled releases

### Code Review Process
- Architecture review for major changes
- Security review for authentication features
- Performance review for optimizations
- Accessibility review for UI components

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Write tests first (TDD approach)
4. Implement with test coverage
5. Submit pull request with description
6. Address review feedback
7. Merge to develop branch

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

- **Documentation**: Check `/docs` directory
- **Issues**: Create GitHub issue with detailed description
- **Discussions**: Use GitHub Discussions for questions
- **CLI Help**: Run `npx zai-ui --help` for command assistance

---

**Built with ❤️ using Next.js, TypeScript, and PostgreSQL**