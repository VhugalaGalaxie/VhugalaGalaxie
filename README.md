<div align="center">
   <h1>GitHub Profile Summary Cards</h1>
   
   
   <p align="center">
      <a href="https://github.com/VhugalaGalaxie/printf">
      <img alt="Stargazers" src="https://img.shields.io/github/stars/VhugalaGalaxie/github-profile-summary-cards?style=for-the-badge&logo=github&color=f4dbd6&logoColor=D9E0EE&labelColor=302D41"></a>
      <a href="https://github.com/VhugalaGalaxie/github-profile-summary-cards/releases/latest">
      <img alt="Releases" src="https://img.shields.io/github/release/VhugalaGalaxie/github-profile-summary-cards.svg?style=for-the-badge&logo=semantic-release&color=f5bde6&logoColor=D9E0EE&labelColor=302D41"/></a>
      <a href="https://www.conventionalcommits.org/en/v1.0.0/">
      <img alt="conventionalcommits" src="https://img.shields.io/badge/Conventional%20Commits-1.0.0-%23FE5196?style=for-the-badge&logo=conventionalcommits&color=ee99a0&logoColor=D9E0EE&labelColor=302D41"></a>
      <a href="https://github.com/VhugalaGalaxie/github-profile-summary-cards/actions/workflows/github-action.yml">
      <img alt="testandlint" src="https://img.shields.io/github/actions/workflow/status/VhugalaGalaxie/github-profile-summary-cards/test-and-lint.yml?branch=main&label=Test%20and%20Lint&style=for-the-badge&color=a6da95"></a>
   </p>
</div>

<div align="center">

![](https://raw.githubusercontent.com/VhugalaGalaxie/VhugalaGalaxie/master/profile-summary-card-output/solarized/0-profile-details.svg)
![](https://raw.githubusercontent.com/VhugalaGalaxie/VhugalaGalaxie/master/profile-summary-card-output/solarized/1-repos-per-language.svg)
![](https://raw.githubusercontent.com/VhugalaGalaxie/VhugalaGalaxie/master/profile-summary-card-output/solarized/2-most-commit-language.svg)
![](https://raw.githubusercontent.com/VhugalaGalaxie/VhugalaGalaxie/master/profile-summary-card-output/solarized/3-stats.svg)
![](https://raw.githubusercontent.com/VhugalaGalaxie/VhugalaGalaxie/master/profile-summary-card-output/solarized/4-productive-time.svg)

</div>


## VhugalaGalaxie

![](https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=VhugalaGalaxie&theme=transparent)

### Profile details card
![](http://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=VhugalaGalaxie&theme=transparent)


### Top languages used in repository card
![](http://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=VhugalaGalaxie&theme=transparent)


### Top languages in commits card
![](http://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=VhugalaGalaxie&theme=transparent)


### GitHub stats card
![](http://github-profile-summary-cards.vercel.app/api/cards/stats?username=VhugalaGalaxie&theme=transparent&)"


### Productive time card
![](http://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=VhugalaGalaxie&theme=transparent&utcOffset=8)



---


## GitHub Actions usage

After the action finished. You can see all of summary cards are in folder which named `profile-summary-card-output`.

`Note: Some summary cards might not be updated in time, because github raw file has cache time.`

```yml
name: GitHub-Profile-Summary-Cards

on:
  schedule: # execute every 24 hours
    - cron: "* */24 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    name: generate-github-profile-summary-cards
    permissions:
      contents: write

    steps:
      - uses: actions/checkout@v3
      - uses: VhugalaGalaxie/github-profile-summary-cards@release
        env: # default use ${{ secrets.SUMMARY_GITHUB_TOKEN }}, you should replace with your personal access token
          GITHUB_TOKEN: ${{ secrets.SUMMARY_GITHUB_TOKEN }}
        with:
          USERNAME: ${{ github.repository_owner }}
          # BRANCH_NAME is optional, default to main, branch name to push cards
          BRANCH_NAME: "main"
          # UTC_OFFSET is optional, default to zero
          UTC_OFFSET: 8 
          # EXCLUDE is an optional comma seperated list of languages to exclude, defaults to ""
          EXCLUDE: ""
          # AUTO_PUSH is optional, a boolean variable default to true, whether automatically push generated files to desired branch 
          AUTO_PUSH: true
```
