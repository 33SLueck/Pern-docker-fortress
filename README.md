# PERN Docker Fortress 🏰

Ein modernes PERN Stack Monorepo mit TypeScript, Docker und vollständiger CI/CD Pipeline.

## 🏗️ Tech Stack

### Frontend

- **React 19** mit TypeScript
- **Vite** als Build-Tool
- **Tailwind CSS v4** für Styling
- **Vitest** für Unit Tests
- **React Testing Library** für Component Tests

### Backend

- **Express.js v5** mit TypeScript
- **Node.js** Runtime
- RESTful API Architektur
- Health Check Endpoints

### Development Tools

- **ESLint v9** mit Flat Config
- **Prettier** Code Formatting
- **Husky v9** Git Hooks
- **lint-staged** Pre-commit Checks
- **Commitlint** Conventional Commits
- **npm Workspaces** Monorepo Management

### CI/CD

- **GitHub Actions** Multi-stage Pipeline
- **Docker** Containerization (ready)
- Automated Testing & Building
- Code Quality Gates

## 🚀 Quick Start

### Voraussetzungen

- Node.js 20+
- npm 10+
- Git

### Installation

```bash
# Repository klonen
git clone https://github.com/33SLueck/Pern-docker-fortress.git
cd Pern-docker-fortress

# Dependencies installieren (Root + Workspaces)
npm install

# Development Server starten
npm run dev
```

Das startet:

- Frontend: http://localhost:5173
- Backend: http://localhost:3000

## 📁 Projekt Struktur

```
pern-docker-fortress/
├── README.md
├── package.json              # Root package mit Workspace-Scripts
├── .github/
│   └── workflows/
│       └── ci.yml           # GitHub Actions Pipeline
├── .husky/                  # Git Hooks
│   ├── pre-commit          # Lint-staged Checks
│   ├── commit-msg          # Commitlint Validation
│   └── pre-push            # Build & Test Checks
├── frontend/                # React Frontend Workspace
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   └── __tests__/
│   ├── package.json
│   ├── vite.config.ts
│   ├── eslint.config.js
│   └── tsconfig.json
├── backend/                 # Express Backend Workspace
│   ├── src/
│   │   └── index.ts
│   ├── package.json
│   ├── eslint.config.js
│   └── tsconfig.json
├── eslint.config.js         # Root ESLint Config
├── commitlint.config.js     # Commit Message Rules
└── .prettierrc             # Code Formatting Rules
```

## 🛠️ Development

### Scripts

#### Root Level (Monorepo)

```bash
npm run dev              # Start Frontend + Backend
npm run build            # Build alle Workspaces
npm run test             # Run alle Tests
npm run lint             # Lint alle Workspaces
npm run lint:fix         # Lint + Auto-fix
npm run format           # Format Code mit Prettier
npm run type-check       # TypeScript Checks
```

#### Frontend Workspace

```bash
npm run frontend:dev     # Vite Dev Server
npm run frontend:build   # Production Build
npm run frontend:test    # Vitest Tests
npm run frontend:lint    # ESLint Check
```

#### Backend Workspace

```bash
npm run backend:dev      # Express Dev Server
npm run backend:build    # TypeScript Compilation
npm run backend:start    # Production Server
npm run backend:lint     # ESLint Check
```

### Git Workflow

Das Projekt nutzt **Conventional Commits** und automatische Quality Checks:

```bash
# Feature entwickeln
git checkout -b feature/awesome-feature

# Code schreiben & committen
git add .
git commit -m "feat: add awesome new feature"
```

**Git Hooks (automatisch):**

- **pre-commit**: ESLint + Prettier auf geänderte Dateien
- **commit-msg**: Commitlint validation
- **pre-push**: Build + Test checks

### Code Quality Standards

#### ESLint Konfiguration

- **Frontend**: React + TypeScript Rules
- **Backend**: Node.js + TypeScript Rules
- **Flat Config Format** (ESLint v9+)

#### Commit Message Format

```
type(scope): description

feat: neue Features
fix: Bug fixes
docs: Dokumentation
style: Code formatting
refactor: Code restructuring
test: Tests hinzufügen
chore: Build/Tool changes
```

## 🧪 Testing

### Frontend Tests

```bash
npm run frontend:test        # Run Tests
npm run frontend:test:watch  # Watch Mode
npm run frontend:test:ui     # Test UI Interface
```

### Backend Tests

```bash
npm run backend:test         # Run Backend Tests
```

### Coverage Reports

Test Coverage wird automatisch generiert und in `frontend/coverage/` gespeichert.

## 🔧 API Endpoints

### Backend Health Checks

- `GET /health` - Server Health Status
- `GET /api/health` - API Health Check

### Development URLs

- **Frontend**: http://localhost:5173
- **Backend**: http://localhost:3000
- **Backend Health**: http://localhost:3000/health

## 🐳 Docker (Coming Soon)

```bash
# Docker Build
docker-compose up --build

# Production Deploy
docker-compose -f docker-compose.prod.yml up
```

## 🚀 CI/CD Pipeline

GitHub Actions Workflow mit mehreren Stages:

1. **Setup**: Node.js 20, npm ci
2. **Frontend**: Build, Test, Lint
3. **Backend**: Build, Lint, Type-check
4. **Integration**: Health checks, E2E tests

**Pipeline Trigger:**

- Push to `main`
- Pull Requests
- Manual dispatch

## 📦 Dependencies

### Production

- React 19.1+
- Express 5.1+
- TypeScript 5.9+

### Development

- ESLint 9.33+
- Prettier 3.4+
- Vite 6.0+
- Vitest 2.1+
- Husky 9.1+

## 🤝 Contributing

1. Fork das Repository
2. Erstelle einen Feature Branch
3. Implementiere Changes mit Tests
4. Stelle sicher alle Quality Checks laufen durch
5. Erstelle einen Pull Request

### Development Setup

```bash
git clone https://github.com/33SLueck/Pern-docker-fortress.git
cd Pern-docker-fortress
npm install
npm run dev
```

## 📝 License

MIT License - siehe [LICENSE](LICENSE) für Details.

## 🙋‍♂️ Support

- **Issues**: [GitHub Issues](https://github.com/33SLueck/Pern-docker-fortress/issues)
- **Discussions**: [GitHub Discussions](https://github.com/33SLueck/Pern-docker-fortress/discussions)

---

**Built with ❤️ by 33SLueck**

_PERN Docker Fortress - Modern, Scalable, Production-Ready_
