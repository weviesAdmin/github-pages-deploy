# 🦖 Deploy Docusaurus to GitHub Pages
This action allows you to deploy a Docusaurus site to GitHub Pages.
## Usage

### `main.yml` Example

Place the following code in a `.yml` file, such as `main.yml`, in your `.github/workflows` folder. [Refer to the documentation on workflow YAML syntax here.](https://help.github.com/en/articles/workflow-syntax-for-github-actions)

```yaml
name: 🦕 Deploy Docusaurus to GitHub Pages
on: [push]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: docuactions/github-pages@main
        env:
          DOCUACTIONS_TOKEN: ${{ secrets.DOCUACTIONS_TOKEN }}
          DOCUACTIONS_DEPLOYMENT: ${{ secrets.DOCUACTIONS_DEPLOYMENT }}
```

## Configuration

The following settings must be passed as environment variables as shown in the example. Sensitive information, especially `GITHUB_TOKEN`, should be [set as encrypted secrets](https://help.github.com/en/articles/virtual-environments-for-github-actions#creating-and-using-secrets-encrypted-variables) — otherwise, they'll be public to anyone browsing your repository's source code and CI logs.

| Key                    | Value                                               | Suggested Type | Required |
|------------------------|-----------------------------------------------------|----------------|----------|
| GITHUB_TOKEN           | Github token                                        | `secret env`   | Yes      |
| DOCUACTIONS_DEPLOYMENT | The deployment branch (different from the main one) | `secret env`   | Yes      |


## Credits
* [Henry Newman](https://github.com/henrynewman)