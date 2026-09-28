# Hjälp en förälder – Android-app (testversion)

Det här är ett färdigt Android-projekt. Appen från prototypen ligger inbyggd och fungerar utan internet. Det enda som behöver nätet är typsnitten och länkarna till 1177 och andra källor.

## Få fram APK-filen – utan att installera något (cirka 10 minuter)

1. Skapa ett gratis konto på github.com om du inte redan har ett.
2. Klicka på **New repository**. Döp det till exempel till `hjalp-en-foralder-app` och välj **Public**, så att testarna kan ladda ner utan konto. Klicka på **Create repository**.
3. Klicka på länken **uploading an existing file**. Packa upp zip-filen och dra in **alla filer och mappar** från mappen `hjalp-en-foralder-android`. Klicka på **Commit changes**.
   - **Viktigt:** mappen `.github` måste följa med. På Mac är mappar som börjar med punkt dolda. Tryck `Cmd + Shift + .` i Finder för att visa dem.
   - Om `.github` ändå saknas: välj **Add file → Create new file**, skriv namnet `.github/workflows/bygg-apk.yml` och klistra in innehållet från filen med samma namn i zip-filen.
4. Gå till fliken **Actions**. Där byggs appen automatiskt, vilket tar ungefär 4–6 minuter. En grön bock betyder att bygget är klart.
5. Gå till **Releases** (i högerspalten på startsidan för repot) och öppna **Testversion**. Där ligger `hjalp-en-foralder.apk`.

**Länken att skicka till testarna** ser ut så här:
`https://github.com/DITT-ANVÄNDARNAMN/hjalp-en-foralder-app/releases/download/testversion/hjalp-en-foralder.apk`

Länken är densamma varje gång. När du ändrar något och laddar upp igen byggs en ny version automatiskt under samma länk.

## Så installerar testarna appen (Android)

1. Öppna länken på telefonen och ladda ner filen.
2. Tryck på filen. Telefonen frågar om den får installera appar från okända källor. Välj **Tillåt** för webbläsaren eller Filer.
3. Tryck på **Installera**. Om Google Play Protect varnar, välj **Installera ändå**. Det är normalt för appar som inte kommer från Play Butik.
4. Nya testversioner installeras ovanpå den gamla, och testarnas data finns kvar.

iPhone kan inte installera APK-filer. För iPhone-testare fungerar länken till prototypen i webbläsaren.

## Bra att veta

- **Testnyckel:** Appen signeras med en testnyckel (`app/test.keystore`) som ligger öppet i projektet. Det räcker för test. Innan appen läggs upp på Google Play behöver ni skapa en egen, hemlig nyckel.
- **Lagring:** Barn, checklistor och markeringar sparas bara på den egna telefonen. Om appen avinstalleras försvinner de.
- **Innehåll:** Texterna är prototyptext baserad på råd från 1177, Livsmedelsverket med flera. De ska faktagranskas innan appen lanseras på riktigt.
- **Bygga själv:** Öppna mappen i Android Studio och välj **Build → Build APK(s)**.

## Projektets delar

| Fil | Vad den gör |
|---|---|
| `app/src/main/assets/index.html` | Hela appen: innehåll, design och funktioner |
| `app/src/main/java/.../MainActivity.java` | Visar appen och sköter tillbaka-knappen, länkar och telefonnummer |
| `app/build.gradle` | Versionsnummer, signering och Android-inställningar |
| `.github/workflows/bygg-apk.yml` | Bygger APK-filen automatiskt på GitHub |
