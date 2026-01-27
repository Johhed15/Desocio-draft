# Demografisk och socioekonomisk rapport

Detta är ett Quarto-projekt som visualiserar och analyserar Demografisk och socioekonomi i Uppsala län, men med enkla inställningsförändringar så kan den anpassas till alla län i Sverige.

## Struktur

-   `index.qmd` – startsida för webbplatsen
-   `Data/` – alla datakällor
-   `Script/` – R-skript för laddning och bearbetning
-   `Figurer/` – alla visualiseringar utom interaktiva grafer

## Hur man bygger webbplatsen

-   Just nu måste funktionern i Script/create_table som heter 'tab_alder_class' tas bort då den endast fungerar på uppsalas kommuner(gör automatisk)

-   I Script/settings sätt kommunnamn, kommunkod, län och länskod till det som önskas. Sätt också färgkoder för kommuner här.

-   En del färger sätts i Script/create_save_plot, kör ctrl F och sök efter 'färg' för att hitta de ställen där färg används

-   Kör Script/run_all_functions för att ladda ner all data och spara grafer

-   Här hittas också kommentarer om eventuell manuell nedladdning av filer vilket för denna rapport är:

    -   UVAS
    -   Functionerna för PCA är inte inlagda här eftersom det sker förändringar i DeSO mellan 23-24 och därav måste den koden troligtvis att ändras. Detta medför att all kod i socioindex_pca behöver köras separat, och det som behöver kollas igenom är nedladdningen av data och att alla kolumnnamn stämmer

-   I terminalen skriv \* quarto render

då skapas mappen "\_site" där index.html hittas, öppna den

-   Gå till index.qmd och uppdatera analysen

## Bilder

Dessa bilder kommer behöva bytas ut om andra län ska skapa en rapport, då dessa tillhör Region Uppsala.

Alla grafer är sparade och finns i mappen figurer, de flesta sparas genom att köra dess funktion från scriptet create_save_plots.R, vissa är sparade genom plotlys interaktiva funktion.

För att rendera rapporten så behöver bilder från regionens mediabank laddas ned, dessa läses in i rapporterna med samma namn som de laddas ner med. Alla nedladdade bilder från mediabanken ska sparas i en mapp som heter 'Mediabank', i .gitignore så ställs det in så att dessa inte laddas upp på github utan sparas endast lokalt från nedladdningen på Region Uppsalas mediabank.

## Paket

Gamla eller uppdaterade versioner av paket kan göra så att funktioner i denna kod inte fungerar.
