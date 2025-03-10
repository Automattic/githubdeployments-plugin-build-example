# githubdeployments-plugin-build-example

An example plugin repository (of a plugin that registers a block) with a workflow script that generates a build version of the block being registered

The [workflow](.github/workflows/wpcom.yml) does the following:

The workflow is triggered on pushes to the `main` branch or manually via workflow dispatch. It:

- Checkout the repository
- Instals Node with the [Node Action](https://github.com/actions/setup-node)
- Runs `npm install` to install dependencies in `package.json`
- Runs `npm run build` to run the build process
- Creates a build artifact with name `wpcom` which is required for WordPress.com's GitHub Deployment feature. The artifact contains the built plugin files, excluding development files like:

  - Git files
  - Source files
  - Node modules
  - Package files
  - Webpack config
  - README
