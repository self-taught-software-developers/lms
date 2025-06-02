# LMS Project

# How do I run this on my machine?

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

## Project Scope & Google Document
[Google Docs](https://docs.google.com/document/d/1Gw8n6seCFe3vWQk9iShwyRD_7ShJcKR0nKDFUWrWgpk/edit?usp=sharing)

## Licensing

[MIT License](https://www.tldrlegal.com/license/mit-license)
