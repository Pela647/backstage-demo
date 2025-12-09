# [Backstage](https://backstage.io)

- Follow installation documentation [here](https://backstage.io/docs/getting-started/). Use node version as specified in the documentation if not, Backstage will encounter issues.
- Sample docker-compose is in google drive `tech/platform-engineering`.

- To start the app, run:
```sh
yarn install
 # make sure database is already running, use docker-compose from above note
yarn start
```

### Environment Variables
```
# General
export APP_TITLE=""

# For auth
export AUTH_GITHUB_CLIENT_SECRET=""
export AUTH_GITHUB_CLIENT_ID=""
export AUTH_GITHUB_ENTERPRISE_INSTANCE_URL=""

# For pulling/pushing from/to remote
export GITHUB_TOKEN=""

# Locations file
export MAIN_LOCATIONS_FILE="https://github.com/Pela647/backstage-templates/blob/main/locations.yaml"

# Required for nodejs >= v20
export NODE_OPTIONS=--no-node-snapshot

# POSTGRES_HOST = DB service name
export POSTGRES_HOST=psql
export POSTGRES_PORT=pela
export POSTGRES_USER=pela
export POSTGRES_PASSWORD=5432
```

### How to Create Docker Image
```
$ yarn install --immutable

# tsc outputs type definitions to dist-types/ in the repo root, which are then consumed by the build
$ yarn tsc

# Build the backend, which bundles it all up into the packages/backend/dist folder.
$ yarn build:backend

# Build image from root directory
$ docker image build . -f packages/backend/Dockerfile --tag DOCKER_REPO/backstage:1.0.4

# Push to image repo e.g. docker hub
$ docker push DOCKER_REPO/backstage:1.0.4
```
