# nest-react-monorepo-template

A template starter for a monorepo with NestJS and ReactJS.

The Nest.js server will serve up the SPA React app in production.

## Technologies

- [NestJS](https://nestjs.com/)
- [ReactJS](https://reactjs.org/)
- [TypeScript](https://www.typescriptlang.org/)
- [TailwindCSS](https://tailwindcss.com/)
- [Prisma](https://www.prisma.io/)
- [PostgreSQL](https://www.postgresql.org/)
- [Docker](https://www.docker.com/)
- [Jest](https://jestjs.io/)

Because we're using workspaces, we can npm install packages in the root of the project and they will be available to both the server and the client.

This app will use Turbo Repo to allow us both develop and deploy the app as a monorepo.

In the apps/client folder under vite.config.ts, we have a proxy set up to proxy all requests to /api to the Nest.js server. Because of this proxy setup, we use the /api prefix in the client to make requests to the server.

To accommodate this we also have changed the main.ts file in the server to use the /api prefix for all routes. This is done by adding:
`app.setGlobalPrefix('api')`.
