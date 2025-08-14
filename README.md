# PERN-Fortress Monorepo Template 🏰

![GitHub](https://img.shields.io/github/license/33SLueck/Pern-docker-fortress)
![Node.js Version](https://img.shields.io/badge/node-%3E%3D20-brightgreen)
![TypeScript](https://img.shields.io/badge/typescript-5.9+-blue)
![React](https://img.shields.io/badge/react-19+-blue)
![Docker](https://img.shields.io/badge/docker-ready-blue)
![CI](https://img.shields.io/github/actions/workflow/status/33SLueck/Pern-docker-fortress/ci.yml?branch=main&label=CI)

Ein modernes, flexibles PERN Stack Monorepo-Template mit TypeScript, Docker und CI/CD – ready für Production & eigene Projekte!

## ✨ Features

- 🏗️ **Monorepo Architecture** mit npm Workspaces
- ⚡ **Modern Tech Stack** (React 19, Express 5, TypeScript 5.9+)
- 🐳 **Docker Ready** mit Multi-stage Builds
- 🔄 **Automated CI/CD** mit GitHub Actions
- 🛡️ **Code Quality Gates** (ESLint, Prettier, Husky)
- 📦 **Dependency Management** mit Dependabot
- 🧪 **Testing Setup** (Vitest, React Testing Library)
- 🎯 **Production Ready** mit Health Checks

## 🏗️ Tech Stack

### Frontend

- **React 19** (oder eigene Version) mit TypeScript
- **Vite** als Build-Tool
- **Tailwind CSS v4** (optional)
- **Vitest** für Unit Tests
- **React Testing Library**

### Backend

- **Express.js v5** (oder eigene API) mit TypeScript
- **Node.js** Runtime
- RESTful API Architektur
- Health Check Endpoints

### Dev Tools

- **ESLint v9** (Flat Config)
- **Prettier**
- **Husky v9** Git Hooks
- **lint-staged**
- **Commitlint**
- **npm Workspaces**

### CI/CD & Automation

- **GitHub Actions** Multi-stage Pipeline
- **Dependabot** Automated Security Updates
- **Docker Compose** Development & Production
- **Automated Testing** auf jeder PR
- **Quality Gates** vor Deployment
- Multi-stage Dockerfiles (Production-ready)

---

## 🚀 Quick Start

### Voraussetzungen

- Node.js 20+
- npm 10+
- Docker & Docker Compose
- Git

### Installation & Start (Development)

```bash
# 1. Repository klonen
git clone <dein-repo-url>
cd <projektname>

# 2. Dependencies installieren (Monorepo)
npm install

# 3. Dev-Server starten (Frontend & Backend)
npm run dev
```

**Standard-Ports:**

Um potentiellen Port-Konflikten vorzubeugen nutzen wir diese Ports . Dies lässt sich einfach im docker-compose.yml verändern.

- Frontend: http://localhost:5176
- Backend: http://localhost:3006

### Production mit Docker

```bash
# Images bauen & starten
docker-compose up --build

# Stoppen & aufräumen
docker-compose down
```

---

## 📁 Projekt Struktur (Template)

```
pern-monorepo-template/
├── README.md
├── package.json              # Root package mit Workspace-Scripts
├── docker-compose.yml        # Docker Compose für alle Services
├── .github/
│   ├── workflows/
│   │   └── ci.yml           # GitHub Actions Pipeline
│   └── dependabot.yml       # Automated Dependency Updates
├── .husky/                  # Git Hooks
│   ├── pre-commit          # Lint-staged Checks
│   ├── commit-msg          # Commitlint Validation
│   └── pre-push            # Build & Test Checks
├── .vscode/                 # VS Code Settings
│   ├── settings.json       # Editor Config + Action Buttons
│   └── tasks.json          # Build Tasks
├── frontend/                # React Frontend Workspace
│   ├── Dockerfile           # Multi-stage Build für Vite
│   ├── nginx.conf           # NGINX Config für SPA-Routing
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   └── __tests__/
│   ├── package.json
│   ├── vite.config.ts
│   ├── eslint.config.js
│   └── tsconfig.json
├── backend/                 # Express Backend Workspace
│   ├── Dockerfile           # Multi-stage Build für Node.js
│   ├── src/
│   │   └── index.ts
│   ├── package.json
│   ├── eslint.config.js
│   └── tsconfig.json
├── eslint.config.js         # Root ESLint Config
├── commitlint.config.js     # Commit Message Rules
└── .prettierrc             # Code Formatting Rules
```

---

## 🛠️ Development

### Wichtige Scripts (Root)

```bash
npm run dev              # Startet Frontend & Backend (Entwicklung)
npm run build            # Build für alle Workspaces
npm run lint             # Lint für alle Workspaces
npm run lint:fix         # Lint + Auto-fix für alle Workspaces
npm run test             # Tests für alle Workspaces
npm run format           # Prettier Formatierung
npm run type-check       # TypeScript Checks
```

### Frontend Scripts

```bash
npm run frontend:dev     # Vite Dev Server
npm run frontend:build   # Production Build
npm run frontend:test    # Vitest Tests
npm run frontend:lint    # ESLint Check
npm run frontend:format  # Prettier Format
```

### Backend Scripts

```bash
npm run backend:dev      # Express Dev Server
npm run backend:build    # TypeScript Compilation
npm run backend:start    # Production Server
npm run backend:lint     # ESLint Check
npm run backend:format   # Prettier Format
```

### Docker Compose

```bash
docker-compose up --build   # Build & Start aller Container
docker-compose down         # Stop & Remove aller Container
```

---

### Git Workflow & Quality

- **Conventional Commits** (commitlint enforced)
- **pre-commit**: Lint & Format staged files
- **pre-push**: Build & Test

**Commit Message Format:**

```
type(scope): description
feat: Neue Features
fix: Bugfixes
docs: Dokumentation
style: Code-Formatierung
refactor: Refactoring
test: Tests
chore: Build/Tooling
```

---

## 🧪 Testing

### Frontend Testing (Vitest)

```bash
npm run frontend:test          # Run Tests
npm run frontend:test:watch    # Watch Mode
npm run frontend:test:ui       # Test UI Interface
npm run frontend:test:coverage # Coverage Report
```

### Backend Testing

```bash
npm run backend:test           # Run Backend Tests
```

### Test Coverage

- **Automatische Coverage Reports** in `frontend/coverage/`
- **CI Integration** mit Coverage Thresholds
- **Test Artifacts** in GitHub Actions

---

## 🔧 API Endpoints

### Health Check Endpoints

- `GET /health` → Basic Health Status
- `GET /api/health` → Detailed API Health Check

### Development URLs

- **Frontend Development**: http://localhost:5176
- **Backend Development**: http://localhost:3006
- **Frontend Production** (Docker): http://localhost:5176
- **Backend Production** (Docker): http://localhost:3006

### API Documentation

- Erweitere die API-Dokumentation nach Bedarf
- Swagger/OpenAPI Integration möglich
- Postman Collections empfohlen

---

## 🐳 Docker

### Development mit Docker

```bash
# Alle Container starten
docker-compose up --build

# Im Hintergrund starten
docker-compose up -d --build

# Logs verfolgen
docker-compose logs -f

# Stoppen & Cleanup
docker-compose down
```

### Production Deployment

```bash
# Production Build
docker-compose -f docker-compose.prod.yml up --build

# Mit Volumes für Persistence
docker-compose up -v ./data:/app/data --build
```

### Container Architecture

- **Frontend Container**:
  - Build: Vite → Static Files
  - Runtime: NGINX Alpine
  - Port: 80 → 5176 (extern)
- **Backend Container**:
  - Build: TypeScript → JavaScript
  - Runtime: Node.js Alpine
  - Port: 3000 → 3006 (extern)

### Docker Features

- **Multi-stage Builds** für optimale Image-Größe
- **Health Checks** für Container-Monitoring
- **Volume Mounts** für Development
- **Environment Variables** für Konfiguration

---

## 🚀 CI/CD Pipeline

### GitHub Actions Workflow

**Multi-Stage Pipeline:**

1. **Setup**: Node.js 20, npm ci, Cache Management
2. **Frontend**: Build, Test, Lint, Type-Check
3. **Backend**: Build, Lint, Type-Check
4. **Integration**: Health Checks, End-to-End Tests
5. **Docker**: Multi-stage Build & Push (optional)

**Trigger Events:**

- Push to `main` branch
- Pull Requests zu `main`
- Manual Dispatch
- Scheduled runs (optional)

### Dependabot Integration

**Automated Dependency Updates:**

- 📦 **npm packages** (Root, Frontend, Backend)
- ⚙️ **GitHub Actions** workflow updates
- 📅 **Weekly schedule** (Montags 09:00)
- 🏷️ **Auto-labeling** nach Workspace
- 👥 **Auto-assignment** zu Maintainer
- 📝 **Conventional commits** formatting

**Dependency Grouping:**

- React-related packages
- TypeScript tooling
- Vite ecosystem
- Express framework

---

## 📦 Dependencies & Versioning

### Production Dependencies

- **React 19.1+** (Latest with Concurrent Features)
- **Express 5.1+** (Modern HTTP Framework)
- **TypeScript 5.9+** (Type Safety & Performance)
- **Tailwind CSS 4+** (Modern CSS Framework)

### Development Tools

- **ESLint 9.33+** (Code Linting mit Flat Config)
- **Prettier 3.4+** (Code Formatting)
- **Vite 7.0+** (Fast Build Tool)
- **Vitest 3.1+** (Unit Testing Framework)
- **Husky 9.1+** (Git Hooks Management)

### Dependency Management

- **Dependabot** hält Dependencies automatisch aktuell
- **Grouped Updates** für verwandte Packages
- **Security Patches** werden priorisiert
- **Weekly Updates** jeden Montag

---

## 🤝 Contributing

### Contribution Workflow

1. **Fork** das Template Repository
2. **Clone** deinen Fork lokal
3. **Branch** erstellen: `git checkout -b feature/amazing-feature`
4. **Develop** mit allen Quality Checks
5. **Test** sicherstellen: `npm run test`
6. **Commit** mit Conventional Commits: `npm run commit` (Commitizen)
7. **Push** deinen Branch: `git push origin feature/amazing-feature`
8. **Pull Request** erstellen mit detaillierter Beschreibung

### Code Quality Standards

- ✅ **ESLint** Rules müssen erfüllt sein
- ✅ **Prettier** Formatierung angewendet
- ✅ **TypeScript** ohne Errors
- ✅ **Tests** müssen passieren
- ✅ **Build** muss erfolgreich sein
- ✅ **Conventional Commits** befolgen

### Development Setup

```bash
# Repository klonen
git clone https://github.com/33SLueck/Pern-docker-fortress.git
cd Pern-docker-fortress

# Dependencies installieren
npm install

# Pre-commit hooks aktivieren
npm run husky:install

# Development starten
npm run dev
```

---

## 📝 License

MIT License – gerne für eigene Projekte verwenden!

---

**Template by 33SLueck – Star willkommen!**
