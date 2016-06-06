# Rozcestnik-studovna
Domovská stránka a nápověda pro počítače na studovnách v MZK [vknihovne.mzk.cz](vknihovne.mzk.cz)

# Jak upravovat stránky nápovědy
Stránky jsou napsané ve formátu Markdown. Zde najdete co je to [Markdown](https://cs.wikipedia.org/wiki/Markdown) a [jak jej psát](https://daringfireball.net/projects/markdown/).
Github používá také formát Markdown, stránky se dají tedy upravovat přímo v editoru Markdown na Githubu.

Stránky nápovědy se nachází ve složce `private/` 

![pages](https://github.com/moravianlibrary/Rozcestnik-studovna/blob/master/public/images/readme/pages.png)

Po vybrání určitého souboru stačí kliknout na jeho editaci.

![editace](https://github.com/moravianlibrary/Rozcestnik-studovna/blob/master/public/images/readme/editPage.png)

## Editor formátu Markdown

Editor se skládá ze dvou panelů. V levém panelu můžeme upravovat text Markdown. V pravém panelu se vykreslují HTML změny.

![editor](https://github.com/moravianlibrary/Rozcestnik-studovna/blob/master/public/images/readme/editor.png)

Markdown vypadá takto:

    # Zde si napíšu libovolný nadpis
    Takto se píše text ve formátu Markdown
     
## Uložení změn    
    
Změny se ukládají ve formuláři dole pod editorem. Je nutné vyplnit název změny. Změny se uloží tlačítem `Commit`
    
![editor](https://github.com/moravianlibrary/Rozcestnik-studovna/blob/master/public/images/readme/commit.png)

Změny v textech se projeví jen zde v repozitáři na Githubu. Změny se neprojeví na webu [vknihovne.mzk.cz](vknihovne.mzk.cz)

Změněné texty z tohoto repozitáře je potom nutné nahrát na web [vknihovne.mzk.cz](vknihovne.mzk.cz)  
    
# Spuštění aplikace na lokálním PC  
    $ git clone https://github.com/moravianlibrary/Rozcestnik-studovna.git
    $ cd Rozcestnik-studovna
    $ meteor
    
Po zadání posledního příkazu se aplikace se spustní na adrese [http://localhost:3000/](http://localhost:3000/)

# Docker 
    $ docker build -t moravianlibrary/rozcestnik .
    $ docker push moravianlibrary/rozcestnik

# Google tag manager
 GTM používá balík [meteor-iron-router-gtm](https://github.com/GorillaStack/meteor-iron-router-gtm).
 Id pro GTM se může předat pomocí souboru settings.json, nebo ekvivalentně jako systémová proměnná.
 
### Produkce 
 Id pro GTM se předává jako systémová proměnná v yaml souboru v open shiftu
 
### Test
Pro testovací build s GTM id 
 
    $ meteor build ../vknihovne_build
    $ cd vknihovne_build
    $ ROOT_URL=http://127.0.0.1 PORT=8080 METEOR_SETTINGS='{"public": {"gtm": {"id": "GTM-MBZGH4"}}}' node main.js


