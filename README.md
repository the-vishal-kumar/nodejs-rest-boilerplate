# nodejs-typescript-rest-boilerplate

A [NodeJs] / [TypeScript] rest application boilerplate with [Express] framework.

- It contains a simple signup-signin mechanism.
- It uses [Joi] for schema validation.
- It can be run with or without [Docker] containerization software.
- It has some tests written using [Jest] and [Supertest].
- It uses [ESLint], [Prettier], [CommitLint], [Husky] for maintaining code quality.
- It uses [New Relic] for error logging, application performance monitoring, log monitoring.

## Initial setup

1. Clone from Github
   ```bash
   git clone https://github.com/the-vishal-kumar/nodejs-typescript-rest-boilerplate.git
   ```
1. Install dependencies using npm

   ```bash
   cd nodejs-typescript-rest-boilerplate
   npm i
   ```

1. Set environment variables

   - Make a `.env` file
   - Copy the contents of `.env.sample` to `.env`
   - Put appropriate values to for empty variables
     ```bash
     JWT_SECRET_KEY="some-strong-jwt-secret-key | keep-it-safe"
     NEW_RELIC_LICENSE_KEY="get-key-from-https://docs.newrelic.com/docs/apm/agents/nodejs-agent/getting-started/introduction-new-relic-nodejs/"
     ```

1. Setup Docker

   - Install `docker` and `docker-compose` on your machine
   - When it's ready, please make a copy of `docker-compose.sample.yml` as `docker-compose.yml`

## Development

1. Run server locally without docker-compose with either of the following commands:
   ```bash
   npm start
   ```
   ```bash
   npm run dev # start with nodemon
   ```
1. Run server locally with docker-compose with either of the following commands:
   ```bash
   npm run docker-compose # runs the already built docker image
   ```
   ```bash
   npm run docker-compose-build # rebuilds the docker image and then runs
   ```

## Testing

1. Some unit and end-to-end tests are included in `src/test` directory
1. Tests are run using [Jest] and [Supertest]
1. Run tests
   ```bash
   npm test
   ```

## Technology

- Language - [NodeJs] | [TypeScript]
- Framework - [Express]
- Containerization Software - [Docker]
- Version Control - [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

## Code Quality

- [ESLint]
- [Prettier]
- [CommitLint]

## Code Review

- A feature branch is created from _dev_ branch, and after completion of code, a PR is generated to _dev_ branch
- If changes are requested by a reviewer on Github, then the person who has made the PR makes appropriate changes. The reviewer reviews again and marks the comments as resolved
- If there are no new changes required, then PR is merged with _dev_ branch

## Managing Credentials

- Credentials live in `.env` file

<!---
## Hosting

 - [Heroku]
-->

<!---
## Environments

Create three new heroku apps in the `nodejs-typescript-rest-boilerplate` pipeline:

- Development
- UAT/Staging
- Production

In app's settings, set correctly all required config variables

**Note**: Development server is used to run Test Cases before deploying on Staging
-->

## Git Workflow

- A branch is created for each ticket from _dev_ branch
- Example of Branch Name:
  - feature/{ticket_number}
  - bugfix/{ticket_number}
  - hotfix/{ticket_number}
  - dev
  - staging
  - master
- Read next section for more information

<!--
## CI and Deployment

- Auto deployment is triggered on Heroku CI itself when code is pushed to respective branches. If all the test cases (feature, unit, postman, http, console etc.) doesn't pass, then build won't be deployed
- On pushing the code to `dev` branch, test cases will run. On passing all the tests, the build
  will deploy on `Development` environment
- On pushing the code to `staging` branch, test cases will run. On passing all the tests, the build will deploy on `Staging` environment
- On pushing the code to `master` branch, test cases will run. On passing all the tests, the build will deploy on `Production` environment
-->

## Error Logging

- [New Relic]

## Application Performance Monitoring

- [New Relic]

## Log Monitoring

- [New Relic]

<!---
## Backups

- Database backups are made every 24 hours at 2100 hours UTC time by Heroku for Staging and Production environment
-->

## Folder Structure

      📦nodejs-typescript-rest-boilerplate
      ┣ 📂.husky
      ┃ ┣ 📂_
      ┃ ┃ ┣ 📜.gitignore
      ┃ ┃ ┗ 📜husky.sh
      ┃ ┣ 📜commit-msg
      ┃ ┣ 📜pre-commit
      ┃ ┗ 📜pre-push
      ┣ 📂src
      ┃ ┣ 📂app
      ┃ ┃ ┣ 📜index.ts
      ┃ ┃ ┣ 📜node-server.ts
      ┃ ┃ ┗ 📜test-database.ts
      ┃ ┣ 📂controller
      ┃ ┃ ┣ 📜auth.ts
      ┃ ┃ ┗ 📜index.ts
      ┃ ┣ 📂error
      ┃ ┃ ┣ 📜custom.ts
      ┃ ┃ ┣ 📜index.ts
      ┃ ┃ ┣ 📜notFound.ts
      ┃ ┃ ┗ 📜validation.ts
      ┃ ┣ 📂middleware
      ┃ ┃ ┣ 📜auth.ts
      ┃ ┃ ┣ 📜index.ts
      ┃ ┃ ┣ 📜logRequestResponse.ts
      ┃ ┃ ┣ 📜validateAccessToken.ts
      ┃ ┃ ┗ 📜validateSchema.ts
      ┃ ┣ 📂route
      ┃ ┃ ┣ 📜auth.ts
      ┃ ┃ ┣ 📜home.ts
      ┃ ┃ ┗ 📜index.ts
      ┃ ┣ 📂schema
      ┃ ┃ ┣ 📜auth.ts
      ┃ ┃ ┗ 📜index.ts
      ┃ ┣ 📂test
      ┃ ┃ ┣ 📂e2e
      ┃ ┃ ┃ ┗ 📜auth.e2e.test.ts
      ┃ ┃ ┗ 📂unit
      ┃ ┃ ┃ ┣ 📂controller
      ┃ ┃ ┃ ┃ ┗ 📜auth.unit.test.ts
      ┃ ┃ ┃ ┗ 📂util
      ┃ ┃ ┃ ┃ ┗ 📜password.unit.test.ts
      ┃ ┣ 📂type
      ┃ ┃ ┣ 📂express
      ┃ ┃ ┃ ┗ 📜index.d.ts
      ┃ ┃ ┣ 📜IAccessToken.ts
      ┃ ┃ ┣ 📜index.ts
      ┃ ┃ ┣ 📜IResponseHandler.ts
      ┃ ┃ ┗ 📜IUser.ts
      ┃ ┣ 📂util
      ┃ ┃ ┣ 📜index.ts
      ┃ ┃ ┣ 📜logger.ts
      ┃ ┃ ┣ 📜pagination.ts
      ┃ ┃ ┣ 📜password.ts
      ┃ ┃ ┗ 📜responseHandler.ts
      ┃ ┗ 📜index.ts
      ┣ 📜.commitlintrc.json
      ┣ 📜.dockerignore
      ┣ 📜.env
      ┣ 📜.env.sample
      ┣ 📜.env.test
      ┣ 📜.eslintrc.json
      ┣ 📜.gitignore
      ┣ 📜.nvmrc
      ┣ 📜.prettierrc.json
      ┣ 📜docker-compose.sample.yml
      ┣ 📜docker-compose.yml
      ┣ 📜Dockerfile
      ┣ 📜jest.config.js
      ┣ 📜LICENSE
      ┣ 📜newrelic.js
      ┣ 📜newrelic_agent.log
      ┣ 📜package-lock.json
      ┣ 📜package.json
      ┣ 📜README.md
      ┗ 📜tsconfig.json

## Project Specific Knowledge

- [JWT]

<!---
## Production Setup

## External Services/API Reference

## FAQ
-->

## License

- AGPL-3.0-or-later

## Meet The Maker

[Vishal Kumar] - Software Engineer 👨‍💻 and an Aspiring Entrepreneur👨‍💼

[Vishal Kumar]: https://www.linkedin.com/in/the-vishal-kumar/
[NodeJs]: https://nodejs.org/en
[TypeScript]: https://www.typescriptlang.org/
[Express]: https://expressjs.com/
[Joi]: https://joi.dev/
[Docker]: https://www.docker.com/
[ESLint]: https://eslint.org/
[Prettier]: https://prettier.io/
[CommitLint]: https://commitlint.js.org/
[Husky]: https://typicode.github.io/husky/
[Jest]: https://jestjs.io/
[Heroku]: https://www.heroku.com/
[Supertest]: https://github.com/ladjs/supertest
[New Relic]: https://newrelic.com
[JWT]: https://jwt.io/
[Git]: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
