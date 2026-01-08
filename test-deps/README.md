# Test Dependencies for Dependabot Pull Request Limit Testing

This directory contains 12 subdirectories (project1 through project12), each with a `package.json` file containing 10 intentionally outdated npm packages.

## Purpose

This setup is designed to test the `open-pull-requests-limit` configuration in Dependabot by creating a scenario where Dependabot will attempt to open at least 120 pull requests.

## Configuration

- **Total test projects**: 12
- **Dependencies per project**: 10
- **Total outdated dependencies**: 120
- **Dependabot open-pull-requests-limit**: 150

## Package Categories

Each project focuses on different types of npm packages:

1. **project1**: Core frameworks (express, lodash, moment, axios, react, vue, webpack, typescript, prettier)
2. **project2**: Testing tools (babel, eslint, jest, mocha, chai, sinon, karma, protractor, jasmine, ts-node)
3. **project3**: Application frameworks (next, nuxt, gatsby, create-react-app, angular, ember, svelte, preact, backbone, jquery)
4. **project4**: State management (redux, redux-thunk, redux-saga, mobx, mobx-react, recoil, zustand, immer, normalizr, rxjs)
5. **project5**: Routing libraries (react-router, react-router-dom, vue-router, connected-react-router, history, path-to-regexp, query-string, qs, url-parse, uri-js)
6. **project6**: Styling tools (styled-components, emotion, sass, less, stylus, postcss, autoprefixer, tailwindcss, bootstrap, material-ui)
7. **project7**: GraphQL tools (graphql, apollo-client, apollo-server, relay-runtime, urql, type-graphql, graphql-tools, graphql-tag, graphql-request, dataloader)
8. **project8**: Real-time communication (socket.io, socket.io-client, ws, mqtt, amqplib, kafka-node, redis, ioredis, bull, agenda)
9. **project9**: Database ORMs (mongoose, sequelize, typeorm, knex, bookshelf, objection, pg, mysql, mysql2, sqlite3)
10. **project10**: Authentication & middleware (passport, bcrypt, jsonwebtoken, cookie-parser, express-session, cors, helmet, morgan, compression, body-parser)
11. **project11**: CLI tools (dotenv, config, yargs, commander, inquirer, chalk, ora, listr, blessed, vorpal)
12. **project12**: File system & utilities (fs-extra, glob, rimraf, mkdirp, chokidar, nodemon, pm2, cross-env, concurrently, npm-run-all)

## How Dependabot Will Process This

When Dependabot runs, it will:

1. Scan the root directory and each of the 12 test-deps subdirectories
2. Detect that all 120 packages are outdated
3. Attempt to create pull requests for each outdated package
4. Be limited by the `open-pull-requests-limit: 150` setting
5. Since 120 < 150, Dependabot should be able to create PRs for all packages

## Expected Behavior

Dependabot should create approximately 120 pull requests (one for each outdated dependency), which is below the configured limit of 150. This tests that Dependabot can handle a large number of pull requests without hitting the limit.

Note: The actual number of PRs may vary depending on:
- Whether some packages are no longer available or have been deprecated
- Dependabot's grouping behavior
- Any other Dependabot configuration settings
