> [!WARNING]
> DEPRECATED: Move all stuff to new home: <https://github.com/ithaquaKr/homelab/tree/master>

# Stack-Compose 🐳

A curated collection of production-ready Docker Compose templates for popular
application stacks. Deploy development environments in seconds with
pre-configured services like PostgreSQL, Redis, MySQL, and more.

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

## Philosophy 🌱

This project is built on three core principles:

1. **Simplicity First**
   Minimal configurations with sane defaults. No unnecessary abstractions or
   complex tooling.

2. **Zero Black Magic**
   Explicit configurations over hidden automation. You always know exactly
   what's running.

3. **Modular by Design**
   Mix-and-match components like LEGO blocks. Each service is self-contained
   yet interoperable.

We believe in **documentation-driven development** - every template comes with
detailed setup guides and operational notes.

## Features ✨

- 🚀 Production-inspired configurations
- 🔒 Secure defaults (proper user permissions, isolated networks)
- 📁 Environment variable driven setups
- 🔄 Easy version switching
- 📈 Optional monitoring stacks
- 🔍 Healthchecks and proper service dependencies

## Getting Started

### Prerequisites

- Docker Engine ≥ 20.10
- Docker Compose ≥ 2.17

### Basic Usage

1. Clone the repository:

   ```bash
   git clone https://github.com/ithaquaKr/stack-compose.git
   cd stack-compose
   ```

2. Navigate to desired component:

   ```bash
   cd composes/postgres
   ```

3. Start the stack:

   ```bash
   docker compose up -d
   ```

**Example - PostgreSQL + pgAdmin:**

```bash
docker compose -f docker-compose.yml -f docker-compose.pgadmin.yml up -d
```

**Example - Redis with Persistent Storage:**

```bash
docker compose -f docker-compose.yml -f docker-compose.persistence.yml up -d
```

## Repository Structure 📂

```
stack-compose/
├── composes/
│   ├── postgres/
│   │   ├── docker-compose.yml
│   │   ├── docker-compose.pgadmin.yml  # Optional extensions
│   │   └── README.md                   # Component-specific docs
│   ├── redis/
│   ├── mysql/
│   └── .../
├── .env.example            # Common environment variables
└── README.md               # This global documentation
```

Each component includes:

- Base `docker-compose.yml` file
- Optional extension files for additional tooling
- Detailed README with:
  - Service configuration details
  - Connection strings
  - Security considerations
  - Backup/restore procedures
  - Common troubleshooting steps

## Customization 🛠️

1. **Environment Variables**
   Copy `.env.example` to `.env` and modify values:

   ```bash
   cp .env.example .env
   ```

2. **Docker Compose Overrides**
   Create `docker-compose.override.yml` for local customizations that won't affect upstream:

   ```yaml
   version: "3.8"
   services:
     postgres:
       ports:
         - "5432:5432"
       volumes:
         - ./local-data:/var/lib/postgresql/data
   ```

## Contributing 🤝

We welcome contributions through:

- 🐛 Bug reports
- 💡 Feature requests
- 📚 Documentation improvements
- 🧪 New stack components

Please read our [Contribution Guidelines](CONTRIBUTING.md) before submitting changes.

## License 📄

This project is licensed under the MIT License - see the [LICENSE](LICENSE)
file for details.

## Support ❤️

For help or questions:

- [Open an Issue](https://github.com/yourusername/stack-compose/issues)
- Join our [Community Discussion Forum](#) (link your preferred platform)

## Acknowledgements

- Inspired by real-world deployment patterns
- Security guidance from [CIS Docker Benchmarks](https://cisecurity.org/benchmark/docker)
- Documentation templates from [Awesome Compose](https://github.com/docker/awesome-compose)

---

**Happy Containerizing!** 🐳 + ❤️ = 😊
