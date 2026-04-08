# PplTracker

PplTracker is an ASP.NET Core web application for managing and tracking people within an organisation. It provides a Razor Pages UI and a versioned REST API backed by Entity Framework Core and SQL Server.

## Technology Stack

| Layer | Technology |
|-------|-----------|
| UI | ASP.NET Razor Pages (.NET 8+) |
| API | ASP.NET Core Web API (RESTful, versioned `/api/v1/`) |
| Business Logic | C# Application Services (Clean Architecture) |
| ORM | Entity Framework Core 8 (Code-First) |
| Database | SQL Server 2019+ |
| Testing | xUnit · Moq · FluentAssertions |

## Development Agent Team

This project is built and maintained by a team of specialised GitHub Copilot agents. Each agent has a defined role, responsibilities, and interactions with the rest of the team.

| Agent | File | Role |
|-------|------|------|
| 🗂️ Project Manager | [`.github/agents/project-manager.md`](.github/agents/project-manager.md) | Collects features, writes user stories, manages the backlog, coordinates the team |
| 🏛️ Solutions Architect | [`.github/agents/solutions-architect.md`](.github/agents/solutions-architect.md) | Designs system architecture, data models, API contracts, and ADRs |
| 🖥️ Frontend Developer | [`.github/agents/frontend-developer.md`](.github/agents/frontend-developer.md) | Implements Razor Pages UI, forms, and client-side behaviour |
| ⚙️ Backend Developer | [`.github/agents/backend-developer.md`](.github/agents/backend-developer.md) | Implements API controllers, application services, EF Core, and migrations |
| 🧪 QA Engineer | [`.github/agents/qa-engineer.md`](.github/agents/qa-engineer.md) | Writes unit, integration, and end-to-end tests; enforces coverage thresholds |
| 📝 Documentation Writer | [`.github/agents/documentation-writer.md`](.github/agents/documentation-writer.md) | Maintains README, API reference, setup guides, ADR log, and CHANGELOG |

### Agent Workflow

```
Stakeholder
    │
    ▼
🗂️ Project Manager
  ├─ Writes User Stories
  ├─► 🏛️ Solutions Architect  ──► produces architecture design, API contracts, data models
  │         │
  │         ├─► 🖥️ Frontend Developer  ──► implements Razor Pages UI
  │         └─► ⚙️ Backend Developer   ──► implements API, services, EF Core, SQL Server
  │
  ├─► 🧪 QA Engineer          ──► writes unit & integration tests for every story
  └─► 📝 Documentation Writer ──► documents all areas (README, API, setup, CHANGELOG)
```

Each story follows this **Definition of Done**:
1. Code implemented and reviewed
2. Unit and integration tests written and passing (≥ 80% coverage)
3. API documented in Swagger + `docs/api-reference.md`
4. `CHANGELOG.md` updated
5. PR approved and merged

## Quick Start

See [`docs/developer-setup.md`](docs/developer-setup.md) for the full setup guide.

```bash
git clone https://github.com/jmccann1010/PplTracker.git
cd PplTracker
dotnet restore
dotnet ef database update --project src/PplTracker.Infrastructure --startup-project src/PplTracker.Api
dotnet run --project src/PplTracker.Web
```

Navigate to `https://localhost:5001` for the UI and `https://localhost:5001/swagger` for the API docs.

## Documentation Index

- [Architecture Overview](docs/architecture.md)
- [API Reference](docs/api-reference.md)
- [Developer Setup Guide](docs/developer-setup.md)
- [Database Schema](docs/database-schema.md)
- [User Guide](docs/user-guide.md)
- [ADR Log](docs/adr/)
- [CHANGELOG](CHANGELOG.md)

## License

MIT