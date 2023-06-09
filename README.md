# npm-package

See discussion on [how to install an npm package from GitHub directly](https://stackoverflow.com/a/21918559/639133): *""possible since version 1.1.65 and works for github.com only""*

Install this package directly from github
```bash
# Setup
git clone https://github.com/mozey/npm-package.git
cd npm-package

# Test dir must include a package.json file,
# otherwise node_modules is created in ../../
mkdir -p _excluded/test && cd _excluded/test && echo "{}" > package.json

# Install package
npm install mozey/npm-package
```

If the current working (or any parent) dir, doesn't contain a package.json file, `npm install` will fail with
```
no such file or directory, open '...package.json'
```

Follow the instructions to [create a package](https://docs.npmjs.com/creating-a-package-json-file)
```bash
npm init
```

The init sub-command added a bunch of fields, according to [creating a package.json file](https://docs.npmjs.com/creating-a-package-json-file), only the *"name"* and *"version"* fields are required. 

Additionally, *"description"*, *"author"* and *"license"* also seem appropriate, but are not necessary for the package to be installable
