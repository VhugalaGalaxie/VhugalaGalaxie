<div align="center">
   <h1>GitHub Profile Summary Cards</h1>
   
   # IDEs/Editors
   <p align="center">
      ![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)
     ![NetBeans IDE](https://img.shields.io/badge/NetBeansIDE-1B6AC6.svg?style=for-the-badge&logo=apache-netbeans-ide&logoColor=white)
      ![Notepad++](https://img.shields.io/badge/Notepad++-90E59A.svg?style=for-the-badge&logo=notepad%2b%2b&logoColor=black)
      ![Replit](https://img.shields.io/badge/Replit-DD1200?style=for-the-badge&logo=Replit&logoColor=white)
      ![PyCharm](https://img.shields.io/badge/pycharm-143?style=for-the-badge&logo=pycharm&logoColor=black&color=black&labelColor=green)
      ![RStudio](https://img.shields.io/badge/RStudio-4285F4?style=for-the-badge&logo=rstudio&logoColor=white)
      ![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)
      ![Visual Studio](https://img.shields.io/badge/Visual%20Studio-5C2D91.svg?style=for-the-badge&logo=visual-studio&logoColor=white)
     
   </p>
    
      ---
   # Languages
      <p align="center">
      ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
      ![C](https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white)
      ![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white)
      ![C#](https://img.shields.io/badge/c%23-%23239120.svg?style=for-the-badge&logo=c-sharp&logoColor=white)
      ![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)
      ![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
      ![Markdown](https://img.shields.io/badge/markdown-%23000000.svg?style=for-the-badge&logo=markdown&logoColor=white)
      ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
      ![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white)
      ![PHP](https://img.shields.io/badge/php-%23777BB4.svg?style=for-the-badge&logo=php&logoColor=white)
      ![Swift](https://img.shields.io/badge/swift-F54A2A?style=for-the-badge&logo=swift&logoColor=white)
      ![Microsoft](https://img.shields.io/badge/Microsoft-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
      
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

<p align="left" width=47%>
### Top languages used in repository card
![](http://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=VhugalaGalaxie&theme=transparent)


### Top languages in commits card
![](http://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=VhugalaGalaxie&theme=transparent)


### GitHub stats card
![](http://github-profile-summary-cards.vercel.app/api/cards/stats?username=VhugalaGalaxie&theme=transparent&)"


### Productive time card
![](http://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=VhugalaGalaxie&theme=transparent&utcOffset=8)
</p>


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
