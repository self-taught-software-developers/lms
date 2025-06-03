# LMS Project

An open-source, modern Learning Management System (LMS) designed to be self-hosted or deployed to cloud services with no modifications.

## Key Features

- **User Management with RBAC**
  - Administrator, Teacher, Parent, and Student roles
  - Granular access control
  - Special access flags

- **Comprehensive Learning Pathways**
  - Create structured learning journeys with multiple courses
  - Track pathway progress for students
  - Manage pathways with an intuitive UI

- **Course & Module Management**
  - Create and manage courses with attached modules
  - Weighted grading system
  - Support for various content types (assessments, assignments, videos)
  - Interactive AI-powered lessons

- **Assessment & Grading**
  - Create tests, quizzes, and assignments
  - Automatic and manual grading options
  - Performance insights and analytics
  - Exportable grade reports

- **AI-Powered Learning Assistant**
  - School-controlled AI chat bot for tutoring
  - Logged interactions for oversight
  - Support for both remote and local AI models

- **Reporting & Analytics**
  - Insights into student performance and engagement
  - Course completion/failure rates
  - Customizable dashboards

## Tech Stack

- **Frontend**: [NextJS (App Router)](https://nextjs.org/docs), [ShadCN](https://ui.shadcn.com/docs/), [TailwindCSS](https://tailwindcss.com/)
- **Backend**: [tRPC](https://trpc.io/), [Prisma](https://www.prisma.io/), [NextAuth.JS](http://NextAuth.JS)
- **Database**: [PostgreSQL (CockroachDB)](https://www.cockroachlabs.com/)
- **Infrastructure**: [Docker](https://www.docker.com/), [Ansible](https://docs.ansible.com/), [LXC](https://linuxcontainers.org/)
- **Testing**: [Cypress](https://www.cypress.io/)
- **Type Safety**: [TypeScript](https://www.typescriptlang.org/), [Zod](https://zod.dev/)

# Prerequisites
To make use of this repository, we recommend you have the following pre-installed on your **Windows WSL 2 or Linux based development Environment**.

Guides are listed below on official documentation to guide you through the most up-to-date installation:

- [WSL 2 & Ubuntu (Official Ubuntu Documentation)](https://documentation.ubuntu.com/wsl/stable/howto/install-ubuntu-wsl2/)
- [Docker Desktop (Enable the WSL 2 Engine in settings post-install)](https://www.docker.com/products/docker-desktop/)
- [NodeJS (22.16.0 LTS, installed on WSL)](https://nodejs.org/en/download)

# Development Environment Setup

```bash
# Clone the repository
git clone git@github.com:self-taught-software-developers/lms.git

# Checkout to the web app and install
cd web-application
npm install

# Create a .env file with CockroachDB connection details
cat > .env << EOL
# Environment variables for Prisma
DATABASE_URL="postgresql://root@localhost:26257/lms?sslmode=disable"

# Next Auth
NEXTAUTH_SECRET="your-secret-key-here"
NEXTAUTH_URL="http://localhost:3000"
EOL

# Start CockroachDB and Keycloak
docker-compose up -d
# Apply the database schema
npx prisma db push

# Run the development server
npm run dev
```

## Default Logins for Development

### CockroachDB
- Username: root
- Password: (none)
- Admin UI: http://localhost:8080
- Connection string: postgresql://root@localhost:26257/lms?sslmode=disable

### Keycloak
- Username: admin
- Password: admin
- Admin UI: http://localhost:8081

# Project Scope

All details related to project scope can be found in the [Google Docs](https://docs.google.com/document/d/1Gw8n6seCFe3vWQk9iShwyRD_7ShJcKR0nKDFUWrWgpk/edit?usp=sharing).

# Contribution Guidelines

## Reporting Issues

Please use the GitHub issue tracker to report bugs or suggest features. When reporting issues:

1. Use the provided issue template
2. Describe the issue in detail, including steps to reproduce
3. Include relevant error messages and logs
4. Specify your environment (browser, OS, Node.js version)

## Code Contribution

1. Fork the repository and create a new branch for your feature
2. Follow the existing code style and conventions
3. Write meaningful commit messages
4. Add tests for new features
5. Update documentation as needed
6. Submit a pull request with a clear description of your changes

## Pull Request Process

1. Ensure your PR addresses an existing issue or clearly describes the problem
2. Include screenshots or examples for UI changes
3. Make sure all tests pass
4. Request review from at least one maintainer
5. Be open to feedback and be prepared to make requested changes

## Community Guidelines

As a community of self-taught developers:

- Be respectful and inclusive in all communications
- Help each other learn and grow through constructive feedback
- Document your code and contributions to help others understand
- Share knowledge freely and celebrate each other's successes
- Remember that everyone is at different stages in their learning journey

We value contributions from developers of all skill levels. Don't hesitate to ask questions if you're unsure about anything!

# Licensing

[MIT License](https://www.tldrlegal.com/license/mit-license)
