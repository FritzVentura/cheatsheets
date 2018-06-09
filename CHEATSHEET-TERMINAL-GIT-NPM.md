



# ---* GENERAL TERMINAL SNIPPETS / CHEAT SHEET *---
NB se evt. cheat sheet --> https://github.com/jofhatkea/front-end/blob/master/git-in-the-terminal.md 
## Init
- opret et lokalt git projekt/repo --> ` git init ` 

## ADD ("tilføj fil til projekt")
- Tilføj filer manuelt til projekt/repository --> ` git add filnavn1.filtype1 filnavn2.filtype `
- Tilføj alle filer --> ` git add --all `

## Status
- få overblik over hvilke filer der er oprettet eller ændret i --> ` git status `

## Commit ("save")
- Commit --> commit ændrede og add'et filer --> ` git commit -m "my commit message" ` 

## CD ("change directory") 
- Gå til et specifikt directory/mappe --> ` cd mappenavn  ` 
- Gå 1 op / Gå tilbage til forrige mappe --> ` cd ..  `

## Touch
- Touch --> opret ny fil --> ` touch filnavn.filtype ` 

## Copy
- Kopiering af indhold fra en mappe til en anden --> `cp ./framappe/* ./tilmappe/`
NB '*' tager alt fra mappen - man kan også isolere én fil eller filtype der skal kopieres

## Clone
- Clone --> kopiér og klon et repository lokalt fra GIT --> ` git clone repositoryname.git `

## Push
- Push / upload til online repository --> ` git push `

## Pull
NB kopiér URL'en til det pågældende online repository og prop ind i kommandoen
- Pull / download/opdatér et lokalt repository --> ` git pull https://github.com/brugerensnavn/repositorynavn.git `




# ---* CREATING A NEW PROJECT WITH GIT & NPM / NODE SASS *---

## STEP ONE / CREATE FOLDER STRUCTURE
Common starting points
1. set up a folder structure
Create a ` "source" ` folder and a ` "dist" ` folder + CSS, JS + IMAGES FOLDER
NB One for the code we write, and one for the optimized sources
- source folder --> for the working files / developing files
- dist folder --> for the final versions / files to be uploaded/deployed

// EXAMPLE OF A FOLDER STRUCTURE: 

dist/
    ...
source/
    js/
        vendor/
    css/
    assets/
        gfx/
        img/
    index.html
.git/
.gitignore
package.json
README.md

## STEP TWO.1 / SETUP GIT
2. set up git
- write ` git init ` --> to create a local git repository

## STEP TWO.2 / CREATE GITIGNORE
NB gitignore filen kan eksludere specifikke/udvalgte unødvendige filtyper,filnavne etc. --> til når siden skal uploades til git
NB se common "ignores" --> https://gist.github.com/octocat/9257657 

1. Opret en ny gitignore fil i roden af projektet --> ` .gitignore `
NB skriv evt. ` git status ` for at få et overblik over hvilke filer og mapper der ikke er commit'et
2. tilføj hvilke filtyper, filnavne etc. der skal eksluderes i filen
// filer der oftest skal ignoreres/tilføjes til .gitignore filen
--> node_modules/
--> TODO.md
--> Thumbs.db
--> .DS_Store
--> Desktop.ini
--> node_modules/
--> *.psd og lignende (* definerer alle filtyper der ender på .psd)
--> dist/

NB man kan herefter bruge ` git add --all ` i stedet for at add'e dem én for en

## STEP THREE / SETUP NPM
3. set up NPM

NB if you already cloned or have an package.json with a ` "scripts":{} ` for node modules and a ` "devDependencies":{} ` with the developing modules/versions you can always:
- delete all the other files, 
- clone the repo, 
- move package.json to the root of your project
- and do a ` npm install `
//Then you don't have to build your own npm modules

NB if you don't have a package.json with node modules defined in the scripts and devDependencies
--> GO TO THE BUILD WALKTHROUGH SECTION: #---* BUILD MODULES WALKTHROUGH FOR CSS *---

## STEP FOUR
4. create working files
- index.html
- style.css
- main.js
- etc.

## STEP FIVE
5. create a repo on your own github and push your local repo online
- after you've git add'ed and git commit'ed you should --> 
- ` git remote add origin https://github.com/YourProfileName/repoName.git ` 
- ` git push -u origin master `
NB After this procedure - you only have to write ` git push ` in the command to push your repo online





# ---* SITE OPTIMIZATION / MINIMIZE BLOATING *---
NB Minimize "bloated" files as much as possible

## CSS
    minify
    sass
    autoprefix
    concatenate

## JS
    minify
    transpile
    concatenate
    obfuscate / uglify --> Making code, fundtions, variables etc. unreadable to humans



# ---* BUILD MODULES WALKTHROUGH FOR CSS & JS *---

NB `npm` is the package manager for JavaScript and the world’s largest software registry. Discover packages of reusable code — and assemble them in powerful new ways. --> from https://www.npmjs.com/

NB npm is way to download JS projects (called modules)

## SASS INTO CSS / NPM INSTALL
- NB snippets til terminalen for at udvikle SCSS
- NB presets skal navgives --> `_filnavn.scss` --> og defineres: `@import "filnavn";` i den aktive scss
- NB hvis man vil installere NPM globalt --> ` npm install -g node-sass `
1. installér node-sass lokalt --> ` npm install --save-dev node-sass `
2. installèr/opret package.json --> ` npm init ` 
3. ændr' stien i package.json --> Find script tilføj eller erstat "test" med egen definition -->` "my-sass": "node-sass -w style.scss style.css" `
4. Kør modul ved at indtaste i terminalen --> ` npm run my-sass (eller navn på modul) `
5. site deployment / upload til git 
--> kør eventuelt en ` git status ` for at få et overblik over mapper og filer der er oprettet eller ændret
--> ` git add filnavn.filtype ` 
--> ` git commit -m "dit commit" ` 
--> ` git push `

## LIVER SERVER
NB live-server er et npm modul, der reloader og viser en live version af sin kode
1. installér live-server globalt --> ` npm install -g live-server `
2. Kør ved at indtaste i terminalen --> ` live-server `

## TRANSPILING
NB Omdanner/omskriver JS filer til en version, med kode der virker i de fleste browsere
NB babeljs.io er standard --> https://babeljs.io/ 

1. Installér babel globalt: 
--> ` npm install -g babel-cli `
--> ` npm install -g babel-preset-env `
--> eller lokalt --> ` npm install --save-dev babel-cli babel-preset-env `
2. Tilføj i package JSON --> ` "transpilejs": "babel build/main.js --out-file build/js/main.js --presets=env" `
3. Kør transpile ved at skrive i Terminalen --> `npm run transpilejs`

## UGLIFY
NB Omdanner/omskriver JS filer til en compiled version, så "bloated" kode formindskes så vidt muligt
NB Dokumentation--> https://www.npmjs.com/package/uglify-js

1. Installér babel globalt: 
--> ` npm install -g babel-cli `
--> ` npm install -g babel-preset-env `
--> eller lokalt --> ` npm install --save-dev babel-cli babel-preset-env `
2. Tilføj i package JSON --> ` "transpilejs": "babel build/main.js --out-file build/js/main.js --presets=env" `
3. Kør transpile ved at skrive i Terminalen --> `npm run transpilejs`

## CONCATENATE
NB Dette kan samle alle ens css filer i én output fil automatisk
1. Tilføj i package.json til ` "scripts":{} `  --> ` "concat-css": "cat source/css/*.css > build/css/all.css" `
--> Her skal stien for de forskellige filer samt filtype defineres i script
// NB '*' hiver fat i alt med denne filtype eller syntax
2. Kør manuelt ved at indtaste i terminalen --> ` npm run concat-css `

## AUTOPREFIX
1. installer autoprefix module
// ` npm install --save-dev postcss-cli `
// ` npm install --save-dev autoprefixer `
2. Tilføj i package.json til ` "scripts":{} `  --> ` "autoprefix": "postcss input/*.css --use autoprefixer -d output/css/" `
// Her skal stien for de forskellige filer samt filtype defineres i script
// input er en dummy mappe der definerer hvilken fil der skal autoprefixes
// output er en dummy mappe der definerer hvor den autoprefix'et fil skal placeres
NB filen kan tilføjes i en mappe(der kan oprettes en mappe) --> ved at tilføje mappens navn efter ` /css/mappensnavn `
3. Kør manuelt ved at indtaste i terminalen --> ` npm run autoprefix `

## MINIFY
1. installer cssnano module
// ` npm install --save-dev cssnano `
2. Tilføj i package.json til ` "scripts":{} ` --> ` "minifycss": "postcss build/css/*.css --use cssnano -d build/css/" `
// Her skal stien for de forskellige filer samt filtype defineres i script
3. Kør manuelt ved at indtaste i terminalen --> ` npm run autoprefix `
 
## AUTOMATING THE AUTOMATION (MASTER RUN #1)
// Tilføj i package.json til ` "scripts":{} ` --> ` "allcss": "npm run my-sass && npm run concat-css && npm run autoprefix && npm run minifycss" `
1. Definér et scriptnavn
2. Udfyld de forskellige npm run til de pågældende (angivne run scripts)
3. Kør manuelt ved at indtaste i terminalen --> ` npm run allcss `

## WATCHING FOR CHANGES (MASTER RUN #2)
1. installer --> ` npm install --save-dev watch `
2. tilføj i package.json til ` "scripts":{} ` :
PC --> ` "watch": "watch \"npm run allcss\" source/" `
MAC --> ` "watch": "watch 'npm run css' source/" `
3. Kør ved at indtaste i terminalen --> ` npm run watch `
NB denne kommando kører alle de installerede moduler automatisk



## FINALIZE YOU BUILD PROCESS
// Minimize "bloated" as much as possible
1. Remember, if you have your package.json
- you can always delete all the other files, 
- clone the repo, move package.json back in
- and do a npm install
