

# DOM



# CSS

## SASS

## CSS Selectors



# JAVASCRIPT

## FUNCTIONS
- ` functionName() ` --> Kalder på den pågældende funktion
- ` functionName ` --> Giver hele funktionen

## "DRY"
- DRY står for "Don't repeat yourself"
- Det er bad practice at gentage den samme funktion og lignende i sin kode --> Ofte

## PSEUDO CODE
- Når man skrive en stump kode der ikke er korrekt --> Formålet er opstille en instruktion for hvad de forskellige kodestumper skal gøre - for at bidrage til et bedre overblik over sin syntax og opbygning af kode
- EKSEMPEL

## "NINJA CODE"
- Kode der er skrevet som nærmest ulæseligt for mennesker
- Her benyttes der ofte arrow functions
- Man gør koden så kort som mulig

## METHODS
- Methods eller metoder er noget som bliver defineret efter et ` . ` 
- Eksempelvis ` .addEventlistener `


## PARAMETERS
- UNDERVISNING -->  https://kea-alt-del.dk/courses/frontend-elective/4-callbacks.php#/2/3

## CALLBACKS
- UNDERVISNING -->  https://kea-alt-del.dk/courses/frontend-elective/4-callbacks.php#/6 
- "Simply put: A callback is a function that is to be executed after another function has finished executing — hence the name ‘call back’."
- Er hver gang man kalder på en funktion
- EKSEMPEL#1 - ved en funktion ved klik - her kaldes der på en funktion der hedder ` changeColor ` 
-->   
document.querySelector("svg").addEventListener("mouseover",` changeColor `); 
- EKSEMPEL#2
--> 
const app = document.querySelector("#app");

//doStuff is the function called when the "eventtarget" is clicked
app.addEventListener("click", ` doStuff `);

function doStuff(evt){
    console.log("clicked");
}

## ARROW FUNCTIONS
- UNDERVISNING: -->  https://kea-alt-del.dk/courses/frontend-elective/4-callbacks.php#/4 
- se evt. -->  https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions 


# GITHUB

## NODE MODULES

### NPM



# USEFUL LINKS

## VS CODE EMMET SNIPPETS
- https://docs.emmet.io/cheat-sheet/ 

## Cool HEX colour codes
- http://bada55.io/

