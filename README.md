# Website Sonja Cassiman — rouw- en verlies counselor

Eén HTML-pagina, zonder framework, zonder build-stap. Alles wat je moet uploaden
staat in deze map.

## Wat waar staat

```
index.html                 de volledige website (HTML + CSS + JS in één bestand)
images/                    geoptimaliseerde afbeeldingen (.webp + .png/.jpg als terugval)
fonts/sonja-headings.woff2 titellettertype (zie hieronder)
favicon-32.png             icoontje in het browsertabblad (uit het handen-beeldmerk)
favicon-192.png            groter tabblad-/Android-icoontje
apple-touch-icon.png       icoontje als iemand de site op zijn telefoon bewaart
robots.txt                 instructies voor zoekmachines
sitemap.xml                sitemap voor Google Search Console
originelen/                de originele, onbewerkte afbeeldingen (niet uploaden)
```

## Online zetten

Upload de inhoud van deze map — **behalve `originelen/` en dit bestand** — naar de
hoofdmap (root) van `www.sonjacassiman.be`. Meer is er niet nodig.

Zorg dat de host:
- **HTTPS** afdwingt (verplicht voor Google);
- `sonjacassiman.be` doorstuurt naar `www.sonjacassiman.be` (of omgekeerd, maar dan
  moet de `canonical`-regel in `index.html`, `robots.txt` en `sitemap.xml` mee
  aangepast worden);
- **compressie** (gzip of brotli) aanzet voor `.html`, `.svg`, `.xml`;
- **caching** aanzet voor `images/` en `fonts/` (bv. 1 jaar).

## Lettertypes

| Waar | Lettertype | Status |
|---|---|---|
| Titels | **Dreaming Outdoors** | nog toe te voegen — zie hieronder |
| Lopende tekst | **Aptos** | werkt automatisch |

**Aptos** wordt gebruikt zodra het op het toestel van de bezoeker staat (dat is zo
bij iedereen met Microsoft 365). Staat het er niet, dan valt de tekst terug op het
systeemlettertype, dat er nagenoeg identiek uitziet.

**Dreaming Outdoors** is een betalend lettertype en zit niet in deze map. Zolang het
er niet is, worden de titels gezet in *Shantell Sans* — een gratis handgeschreven
lettertype dat er sterk op lijkt. Om over te schakelen:

1. koop een **weblicentie** van Dreaming Outdoors (een `.woff2`-bestand);
2. zet dat bestand in `fonts/DreamingOutdoors.woff2`;
3. open `index.html`, zoek bovenaan het blok `LETTERTYPES` en haal de
   commentaartekens (`/*` en `*/`) weg rond het `@font-face`-blok van
   Dreaming Outdoors.

Meer hoeft er niet te gebeuren: het lettertype staat al vooraan in de opsomming en
neemt vanzelf over.

## Schaal, telefoon, layout en interactie

- **Alles staat op 90%.** Vanaf 860 px breed schaalt één regel in de stylesheet
  (`html{font-size:90%}`) de hele pagina: tekst, marges én beeldbreedtes staan in
  `rem`, dus ze krimpen samen mee. Op gsm blijft alles op volle grootte —
  daar zou 90% te klein worden om vlot te lezen. Wil je het nog een tikje kleiner
  of net groter, wijzig dan enkel dat ene percentage.
- **Telefoon en WhatsApp.** Het telefoonnummer is gewone tekst (niet klikbaar);
  ernaast staat een zwart-wit WhatsApp-icoon dat naar `https://wa.me/32498474256`
  gaat. Ze staan in de header op dezelfde regel als het menu, in dezelfde kleur
  (grijsbruin) en lettergrootte als de menulinks. Hetzelfde icoon staat in de
  contactsectie naast het nummer. Klik op "Sonja Cassiman" linksboven → sectie
  *Wat*.
- **Fade-in per sectie.** Tekst en afbeelding in één sectie verschijnen tegelijk
  (niet meer met vertraging per element). Elke sectie faded in als je naar haar
  scrollt.
- **Contact-layout.** Contactgegevens (adres, e-mail, telefoonnummer) staan in het
  midden van de linkerkolom; Google Maps kaart rechts. Enkel de titel "CONTACT"
  is blauw; alle gegevens eronder zijn zwart. Het WhatsApp-icoon heeft geen
  underline.
- **Volgorde van de secties**: Mee luisteren → Leren omgaan met wat weg is →
  Een ruimte om te helen → Alles wil gevoeld worden → Een huis voor iedereen →
  Wie ben ik → Contact. Het menu volgt die volgorde (Wat · Hoe · Voor wie ·
  Wie ben ik · Contact), zodat een menuklik nooit naar boven terugspringt.

## SEO — wat al gebeurd is

- `<title>` en meta-omschrijving op zoekwoord *rouw- en verlies counselor Wolvertem*
- canonical URL, `lang="nl-BE"`, robots-meta met `max-image-preview:large`
- Open Graph + Twitter-kaart, met een aparte deelafbeelding (1200×630)
- structured data (JSON-LD): `ProfessionalService` / `LocalBusiness`, `Person` met
  de vier opleidingen, `WebSite` en `WebPage` — inclusief exacte GPS-coördinaten
  van Oppemstraat 8, `logo`, `contactPoint`, een `hasOfferCatalog` met de
  diensten, en een `areaServed` met Wolvertem/Meise en de omliggende gemeenten
  (Grimbergen, Merchtem, Londerzeel, Wemmel, Kapelle-op-den-Bos, Zemst) plus
  Vlaams-Brabant en het Brussels Hoofdstedelijk Gewest
- zaaknaam overal identiek geschreven: **Sonja Cassiman | Rouw- en verlies counselor**
  (met `|`), adres overal **Oppemstraat 8, 1861 Wolvertem (Meise)**
- telefoonnummer is overal doorklikbaar (`tel:`-link) maar in dezelfde stijl als
  gewone tekst
- synoniemen in de zichtbare tekst en in `knowsAbout`: rouwbegeleiding,
  rouwtherapie, verliesverwerking, verliesbegeleiding
- nette kopstructuur: één `h1`, daaronder `h2` per onderdeel
- beschrijvende bestandsnamen en alt-teksten op elke afbeelding
- `robots.txt` en `sitemap.xml`
- afbeeldingen als WebP met terugval; WebP-versies die niet kleiner uitvielen dan
  de PNG/JPG zijn verwijderd (o.a. *alle-emoties* en *mee-luisteren*)
- afmetingen op elke afbeelding, zodat de pagina niet verspringt tijdens het laden
- alle tekstkleuren halen WCAG AA-contrast

## Na het online zetten — in deze volgorde

1. **Google Search Console** → domein toevoegen, eigendom bevestigen,
   `https://www.sonjacassiman.be/sitemap.xml` indienen en de startpagina laten
   indexeren via *URL-inspectie → Indexering aanvragen*.
2. **Google Bedrijfsprofiel** (Google Business Profile) aanmaken of opeisen.
   Gebruik **exact** dezelfde gegevens als op de site — Google vergelijkt ze:

   ```
   Naam     Sonja Cassiman | Rouw- en verlies counselor
   Adres    Oppemstraat 8, 1861 Wolvertem
   Telefoon +32 498 47 42 56
   Website  https://www.sonjacassiman.be/
   ```

   Wijkt de naam in je bedrijfsprofiel af, pas dan ook `"name"` aan in het
   JSON-LD-blok onderaan `index.html`.
3. **Openingsuren** staan bewust *niet* in de structured data, omdat ze nergens
   in het voorstel stonden. Zet ze eerst in je bedrijfsprofiel; wil je ze ook op
   de site, geef ze dan door.
4. **Google Analytics of Search Console-statistieken** — nog niets geïnstalleerd.
   Vraag het als je het wil; houd dan rekening met een cookiemelding.

## Aandachtspunten

- **Google Maps.** De kaart onderaan is een Google-invoegtoepassing en plaatst
  cookies van Google. Voor een strikt GDPR-verhaal kan die vervangen worden door
  een gewone link of een statische kaart. Zeg maar wat je wil.
- **De tekening van de rugzak in de contactsectie** (dia 8 van het voorstel) zat
  niet als los bestand in de map — enkel de versie mét aquarel, die nu bij
  *Mee luisteren* staat. Bezorg je de lijntekening, dan zet ik ze erbij.
- **Openingsuren, tarief, `sameAs` en reviews** zitten nog niet in de structured
  data omdat de gegevens ontbreken. Bezorg openingsuren of "enkel op afspraak",
  een richtprijs per sessie, en de links naar je Google Bedrijfsprofiel en social
  media (voor `sameAs`), dan vullen we die aan. Echte getuigenissen kunnen als
  `Review` toegevoegd worden.
- **Nog geen aparte pagina's** per dienst of doelgroep. Eén pagina beperkt op
  hoeveel zoekopdrachten je kan ranken; losse pagina's (bv. rouwbegeleiding
  kinderen, tarieven, contact) zijn een latere uitbreiding.
- **Geen `www` gebruiken?** Vervang dan overal `https://www.sonjacassiman.be`
  door `https://sonjacassiman.be` in `index.html`, `robots.txt` en `sitemap.xml`.
- **Jaartal in de voettekst** staat op 2026 en moet elk jaar handmatig mee.
