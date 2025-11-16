# [Backstage](https://backstage.io)

- Follow installation documentation [here](https://backstage.io/docs/getting-started/). Use node version as specified in the documentation if not, Backstage will encounter issues.

- To start the app, run:
```sh
yarn install
yarn start
```

### Environment Variables
```
# For auth
export AUTH_GITHUB_CLIENT_SECRET=""
export AUTH_GITHUB_CLIENT_ID=""

# For pulling/pushing from/to remote
export GITHUB_TOKEN=""

# Locations file
export MAIN_LOCATIONS_FILE="https://github.com/Pela647/backstage-templates/blob/main/locations.yaml"

# Required for nodejs >= v20
export NODE_OPTIONS=--no-node-snapshot
```