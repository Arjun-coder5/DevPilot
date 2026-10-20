# 🚀 DevPilot — AI-Powered Codebase Assistant

**Understand your codebase. Ask questions. Get code-aware answers.**

DevPilot is a full-stack AI-powered codebase assistant designed to help developers explore GitHub repositories, understand code, and get contextual answers through an interactive chat interface.

Instead of manually searching through multiple files, developers can use DevPilot to interact with their repository and understand its structure and implementation more efficiently.

## ✨ Features

- 💬 **AI-Powered Chat** — Ask questions about your codebase through an interactive chat interface.
- 🐙 **GitHub Integration** — Connect with GitHub repositories.
- 🔍 **Codebase Indexing** — Organize and process source files for contextual retrieval.
- 🧠 **Context-Aware Responses** — Retrieve relevant code context to help generate useful answers.
- 📚 **Source Citations** — Display references to supporting code context where available.
- 🔐 **Authentication** — Authentication and authorization support in the backend.
- 📊 **Dashboard** — Manage repositories and view indexing status.
- ⚙️ **Settings** — Configure application preferences through the UI.
- 🐳 **Docker Support** — Run the PostgreSQL database locally using Docker Compose.

## 🛠️ Tech Stack

| Layer | Technologies |
|---|---|
| Frontend | Next.js, React, TypeScript |
| UI | Tailwind CSS, reusable UI components |
| Backend | Java, Spring Boot, Maven |
| Database | PostgreSQL |
| Vector Search | pgvector |
| AI / Retrieval | Retrieval-Augmented Generation (RAG) architecture |
| Integration | GitHub API |
| Infrastructure | Docker, Docker Compose |
| Version Control | Git, GitHub |

## 🏗️ Project Structure

```text
DevPilot/
├── backend/
│   ├── src/
│   │   ├── main/
│   │   │   └── java/devPilot/backend/
│   │   │       ├── config/
│   │   │       ├── controllers/
│   │   │       ├── dto/
│   │   │       ├── entity/
│   │   │       ├── exceptions/
│   │   │       ├── repository/
│   │   │       ├── security/
│   │   │       └── services/
│   │   ├── test/
│   ├── pom.xml
│   └── mvnw
├── client/
│   ├── app/
│   ├── components/
│   ├── hooks/
│   ├── lib/
│   └── package.json
├── docker/
│   └── postgres/
│       └── init-extensions.sql
├── docker-compose.yml
└── README.md
```

## ⚙️ Prerequisites

Install the following before running the project:

- [Git](https://git-scm.com/)
- [Java JDK](https://adoptium.net/) — use a version compatible with the backend's Maven configuration.
- [Node.js](https://nodejs.org/) and npm
- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- GitHub OAuth credentials and any required AI provider configuration

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Arjun-coder5/DevPilot.git
cd DevPilot
```

### 2. Start PostgreSQL

Make sure Docker Desktop is running, then execute:

```bash
docker compose up -d
```

The PostgreSQL container uses the `pgvector/pgvector:pg16` image and exposes port `5433` on your machine.

Local database defaults in the Compose configuration:

```text
Database: devpilot
Username: postgres
Password: postgres
Port: 5433
```

**Important:** These are development defaults. Use secure credentials for production deployments.

### 3. Run the Backend

Open a terminal:

```bash
cd backend
```

Start the Spring Boot application using the Maven Wrapper:

```powershell
.\mvnw.cmd spring-boot:run "-Dspring-boot.run.arguments=--spring.datasource.url=jdbc:postgresql://localhost:5433/devpilot --spring.datasource.username=postgres --spring.datasource.password=postgres"
```

The backend is expected to run on `http://localhost:8080` if the configured server port is 8080.

Configure the required GitHub OAuth, AI provider, database, and other application settings according to the backend configuration before using features that depend on them.

### 4. Run the Frontend

Open another terminal:

```bash
cd client
npm install
npm run dev
```

Open the local frontend at:

**http://localhost:3000**

Keep the backend and database running while testing features that depend on them.

## 🔐 Environment Configuration

Do not commit API keys, OAuth secrets, database passwords, or other credentials.

Configure the values required by your environment, including:

- PostgreSQL connection settings
- GitHub OAuth client ID and secret
- GitHub API access configuration
- AI model or provider settings
- Frontend API base URL

Use the application's supported environment variables and configuration properties. Never put private backend secrets in frontend variables exposed to the browser.

## 🧠 How It Works

1. **Connect** — The developer connects a GitHub repository.
2. **Index** — DevPilot processes supported source files and prepares code context.
3. **Ask** — The developer asks a question through the chat interface.
4. **Retrieve** — The backend finds relevant code context for the question.
5. **Respond** — The AI generates a contextual answer, with supporting references where available.

## 🎯 Use Cases

- Understanding an unfamiliar codebase
- Exploring project architecture and file relationships
- Finding relevant implementation details
- Getting explanations of existing code
- Helping developers navigate larger repositories

## 🔮 Future Improvements

Potential areas for further development include:

- More advanced code search and retrieval
- Improved multi-language code understanding
- Repository-wide dependency visualization
- Automated code review and debugging assistance
- Production deployment and monitoring
- Expanded testing and performance optimization

## 🤝 Contributing

Contributions, bug reports, and feature suggestions are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Commit your changes.
4. Push your branch.
5. Open a Pull Request describing your changes.

## 👨‍💻 Author

**Arjun Sorout**

- GitHub: [@Arjun-coder5](https://github.com/Arjun-coder5)
- Project: [DevPilot](https://github.com/Arjun-coder5/DevPilot)

---

⭐ If you find this project interesting, consider giving the repository a star!

*Built to make understanding codebases easier with AI.*
