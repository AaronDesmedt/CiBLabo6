# LaboReeks Git
## **Labo 6**

In dit zesde labo gaan we aan de slag met geautomatiseerde workflows (GitHub actions) en enkele van de besproken git fixes.
We zullen ook in dit labo een lokale repository gaan clonen waar we vervolgens alle lokale wijzigingen gaan synchroniseren met deze remote git repository (GitHub). 

Je eindresultaat van het labo zal op deze manier automatisch in deze GitHub repository terecht komen. Met andere woorden, voor dit labo **upload je niks manueel** op GitHub! 
Alles wat gevraagd wordt, dien je lokaal toe te voegen en vervolgens via de nodige commandos ook in de online repository te brengen.
Indien er GitHub-specifieke features gevraagd worden dan kan je deze uiteraard uitvoeren op de remote repository zelf. Dit zal aangeduid worden op de taken die van toepassing zijn op GitHub-specifieke features.

#### **Aanvullende toets op Leho**
Na het afwerken van dit labo heb je op Leho een aanvullende toets met betrekking tot het labo en de leerstof gekoppeld aan het labo.
Je kan/mag de aanvullende toets steeds afleggen gebruik makend van alle bronnen (cursusmateriaal, labo, online bronnen, ...)

### **Labo 6:** *Takenlijst*
- [ ] Open de Git Bash Console op de locatie waar je dit labo wil gaan clonen. Dit kan via een rechtermuisklik op de locatie in kwestie en vervolgens de keuze **Git Bash Here** te selecteren.

- [ ] Zorg ervoor dat de startsituatie *(deze repository)* van het labo op jouw pc **gecloned** wordt. Maak hiervoor gebruik van het passende git commando. 

- [ ] Ga **na het clonen** via de Console naar de gecloonde repository. Dit kan/mag je uiteraard ook doen door de nieuwe aangemaakt folder aan te klikken en hier opnieuw een Git Bash console te openen via de **Git Bash Here** optie.
>**Tip!** Controleer voor je verder werkt of je al dan niet in de juiste git repository zit! Je kan dit snel visueel vaststellen in je console.

In de les bespraken we hoe je automatisch je C# code kan laten compileren en controleren op stijlfouten via een GitHub actions workflow.
In dit labo ga je aan de slag met een aantal HTML pagina's en een workflow die deze pagina's automatisch valideert.
Je zal hiervoor een aantal zaken zelf moeten opzoeken en uitproberen.

### Deel 1: workflow script klaarzetten
- [ ] Voeg via GitHub op je **master** branch een workflow script toe met de naam **validate.yml** en de default inhoud (template) die GitHub zelf voorstelt.
- [ ] Trek deze wijziging binnen in je lokale **master** branch en verifieer dat je het workflow script **validate.yml** nu ook lokaal ziet staan in je repo.
- [ ] Maak lokaal een **dev** branch aan vanaf **master** en ga meteen naar deze nieuwe branch.
- [ ] Editeer het workflow script (bv. in Visual Studio Code) en verwijder de twee standaard commando's (laatste twee stappen van de build job).
- [ ] Zorg er tevens voor dat de workflow wordt getriggerd bij push en pull request voor zowel **dev** als **master**.
- [ ] Commit en push je wijzigingen op de **dev** branch.
- [ ] Ga op GitHub naar de actions tab en neem een screenshot van de volledige pagina. Plaats deze in de **lokale Screenshot folder** die je in je labo6 folder hebt staan. (Op jouw PC/laptop dus!) Geef deze screenshot de naam **deel1** (met extensie naar keuze).
- [ ] Commit en push de screenshot naar je **dev** branch.

### Deel 2: branch protection
- [ ] Stel via GitHub branch protection in voor zowel je **dev** als **master** branch.
- [ ] Zorg ervoor dat er naar beide branches niet rechtstreeks kan gepusht worden (enkel via pull requests) met als bijkomende vereiste dat de build job van de aangemaakte workflow verplicht moet slagen om een pull request te kunnen mergen.
- [ ] **Belangrijk!** Jullie kregen van ons admin rechten op de remote repo van dit labo, omdat je de instellingen van de repo moet kunnen wijzigen. Bijgevolg krijgen jullie stiekem ook *super powers*: de branch protection rules zijn standaard niet van toepassing voor administrators. We willen deze echter tóch activeren voor iedereen, admin of niet. Zoek hoe je dit kan doen (binnen de branch protection rules) en pas de rules hiervoor aan. Iedereen is gelijk voor de wet!
- [ ] Lokaal zou je nog op je **dev** branch moeten zitten, zo niet: keer dan terug naar **dev**.
- [ ] Maak een sreenshot van de detailpagina van de branch protection rules die je instelde voor de **dev** branch (die van **master** zouden identiek moeten zijn). Plaats deze in de **lokale Screenshot folder** die je in je labo6 folder hebt staan. (Op jouw PC/laptop dus!) Geef deze screenshot de naam **deel2A** (met extensie naar keuze).
- [ ] Commit deze wijziging naar je lokale **dev** branch.
- [ ] Probeer te syncen naar de remote **dev** branch. Dit zou niet mogen lukken aangezien we zonet protection rules instelden die eisen dat je met een pull request werkt en dat het build script volledig doorlopen werd!
- [ ] Maak een screenshot van de output in je git bash console waarop duidelijk zichtbaar is dat de sync naar de remote mislukt is. Plaats deze in de **lokale Screenshot folder** die je in je labo6 folder hebt staan. (Op jouw PC/laptop dus!) Geef deze screenshot de naam **deel2B** (met extensie naar keuze).
- [ ] Commit nu ook deze laatste nieuwe screenshot lokaal op je **dev** branch.
- [ ] Laat het syncen naar de remote even voor wat het is (beide screenshots zullen straks op **dev** belanden in deel 3 van het labo, via een pull request van de feature branch die we zo meteen gaan aanmaken).

### Deel 3: HTML validator toevoegen aan workflow
- [ ] Zoek via <https://github.com/marketplace?type=action> naar de HTML5 validator actie die standaard wordt aangeboden op de marketplace.
- [ ] Bekijk de documentatie om uit te zoeken hoe je deze kan activeren in je workflow.
- [ ] Maak lokaal een nieuwe branch **feature/add-html-validator** vanaf **dev** en ga meteen ook naar deze nieuwe branch.
- [ ] Pas het workflow script hier aan om de HTML5 validator uit te voeren als laatste stap in de build job van je workflow. Zorg ervoor dat alle HTML files in je volledige repo gevalideerd worden.

> **Tip!** De build job zal nu uit twee stappen bestaan: repo uitchecken (stond al in de template) gevolgd door HTML validator uitvoeren (moet je hier zelf toevoegen).

- [ ] Commit en push de aanpassing aan het workflow script. 
- [ ] Maak op GitHub een pull request van de branch **feature/add-html-validator** naar **dev**.
- [ ] Wacht tot de automatische workflow volledig werd doorlopen en verifieer dat er geen fouten opdoken. De HTML files die je van ons kreeg in de startsituatie van het labo, bevatten immers geen validatiefouten.
- [ ] Maak een screenshot van je pull request pagina en zorg ervoor dat zeker het stuk feedback over de **uitgevoerde workflow volledig zichtbaar** is! Plaats deze in de **lokale Screenshot folder** die je in je labo6 folder hebt staan. (Op jouw PC/laptop dus!) Geef deze screenshot de naam **deel3** (met extensie naar keuze).
- [ ] Commit en push de screenshot (nog steeds op je feature branch).
- [ ] Wacht tot de opnieuw getriggerde workflow afgerond is en merge de pull request.

### Deel 4: HTML pagina's aanpassen
- [ ] Ga lokaal terug naar de **dev** branch en breng deze up to date met de wijzigingen die op de remote gebeurden.
- [ ] Maak een nieuwe branch **feature/update-site** vanaf **dev** en ga meteen naar deze branch.
- [ ] Open lokaal nu de file **index.html** (bv. in Visual Studio Code) en pas deze aan: verwijder de sluitende `</a>` tag van de link naar de contactpagina:
  ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Home</title>
    </head>
    <body>
        <h1>Welcome!</h1>
        <a href="contact.html">Contact us
    </body>
    </html>
  ```
- [ ] Bewaar, commit & push deze wijziging (op je feature branch).
- [ ] Maak op GitHub een tweede pull request, deze keer van **feature/update-site**, opnieuw naar **dev**.
- [ ] Wacht tot de build uitgevoerd is en verifieer dat de HTML validatie nu faalt (waardoor de pull request niet zomaar gemerged kan worden).

- [ ] Maak een screenshot van de pull request pagina waarop duidelijk zichtbaar is dat de verplichte check (build job) faalt en je hierdoor de pull request niet zomaar kan mergen. Plaats deze in de **lokale Screenshot folder** die je in je labo6 folder hebt staan. (Op jouw PC/laptop dus!) Geef deze screenshot de naam **deel4** (met extensie naar keuze).
- [ ] Commit en push de screenshot (nog steeds op je feature branch).

- [ ] Straks gaan we het probleem oplossen, maar we doen even alsof we het niet meteen hebben opgemerkt. We gaan onze site lustig verder aanpassen.
- [ ] Open het bestand **contact.html** en voeg een mini webformulier toe (op regel 12):
  ```html
     <form action="https://jkorpela.fi/cgi-bin/echo.cgi">
        <label for="message">Message: </label>
        <input type="text" id="message" name="message" />
        <input type="submit" >
    </form> 
  ```
- [ ] Bewaar, commit & push deze wijziging. De net toegevoegde HTML code is perfect valide, maar de build in de pull request zal uiteraard weer falen wegens het probleem in **index.html**.

### Deel 5: foute commit ongedaan maken

- [ ] Open lokaal (nog steeds op de branch **feature/update-site**) terug de **index.html** en roep even luidop "Eureka!" (Oud-Grieks voor "ik heb het gevonden!"). We doen alsof we nu pas het probleem op de home page opmerken.
- [ ] In plaats van het probleem manueel op te lossen, gaan we in de git geschiedenis snuisteren. Daar zou je een commit moeten terugvinden die de validatiefout heeft geïntroduceerd (en verder niks deed).
- [ ] Gebruik een gepast git commando om deze ene specifieke commit ongedaan te maken **zonder met de bestaande history te knoeien**.
- [ ] Push het resultaat naar de remote en wacht tot de build klaar is voor je nog steeds openstaande pull request.
- [ ] De build zou nu moeten slagen, aangezien de validatiefout verholpen is.
- [ ] Maak een screenshot van je **volledige** pull request pagina. Zorg ervoor dat commits die deel uitmaken van de PR zeker zichtbaar zijn, alsook de feedback van de uitgevoerde build job. Plaats deze screenshot in de **lokale Screenshot folder** die je in je labo6 folder hebt staan. (Op jouw PC/laptop dus!) Geef deze screenshot de naam **deel5** (met extensie naar keuze).
- [ ] Commit en push deze screenshot (nog steeds op je feature branch).
- [ ] Merge de pull request (nadat de nieuwe build afgerond is).

### Afronden labo:
- [ ] Ga lokaal terug naar de **dev** branch en trek hier de laatste wijzigingen van de remote binnen.
- [ ] Maak een branch **feature/finish-lab** vanaf **dev** en ga naar deze nieuwe branch.

> **Tip!** We moeten hier verplicht opnieuw met een feature branch en pull request werken wegens onze branch protection rules op GitHub!

- [ ] Controleer of alle stappen in de takenlijst voor dit labo uitgevoerd werden. Pas hiervoor deze readme file aan zodat de checkboxes als afgevinkt weergegeven worden.
- [ ] Commit en push je wijzigingen naar de remote.
- [ ] Maak op GitHub pull request van **feature/finish-lab** naar **dev** en merge deze (nadat de workflow doorlopen is).
- [ ] Maak een laatste pull request van **dev** naar **master** en merge deze (nadat de workflow doorlopen is).
