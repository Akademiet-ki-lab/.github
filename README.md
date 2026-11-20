# .github for Akademiet-ki-lab

Felles maler for organisasjonen.

## KI-lab CI

`workflow-templates/kilab-ci.yml` er en mal for automatisk sjekk av et repo. Den kjører testene, lint og typesjekk ved hver push til main og ved hver pull request.

Slik legger du den til i et repo:

1. Åpne fanen **Actions** i repoet. Har repoet workflows fra før, trykker du **New workflow**.
2. Finn **KI-lab CI** under «By Akademiet-ki-lab» og trykk **Configure**.
3. Trykk **Commit changes…**.

Når sjekken har kjørt, viser KI-lab-dashboardet om den gikk gjennom, i stedet for «Ingen CI».

## Vis prosjektet under Publikasjoner i KI-lab-dashboardet

Dashboardet viser spill, nettsider og apper fra repoene i organisasjonen under **Publikasjoner**, med et bilde og en kort tekst fra README. Det finner adressen slik, i denne rekkefølgen:

1. **kilab-blokken i README** (se under).
2. **GitHub Pages**, hvis repoet publiserer der.
3. **Website** under «About» på repoets forside (tannhjulet ved «About»).

Publiserer du et annet sted enn GitHub Pages, for eksempel på Vercel eller Netlify, må du altså legge adressen i kilab-blokken eller under «About». Ellers dukker prosjektet ikke opp.

### kilab-blokken

Legg dette øverst i `README.md`, rett under overskriften. Det er en kommentar, så den synes ikke når README vises på GitHub:

```markdown
<!-- kilab
publikasjon: https://mitt-spill.vercel.app/
bilde: docs/skjermbilde.png
-->
```

- `publikasjon:` er adressen til det publiserte bygget. Den må starte med `https://`.
- `bilde:` er bildet som vises på kortet: en sti i repoet (som `docs/skjermbilde.png`) eller en adresse på GitHub.
- `publikasjon: nei` holder repoet **utenfor** Publikasjoner, selv om det har GitHub Pages eller et nettsted under «About». Bruk det for repoer som ikke er ment å vises fram, for eksempel øvingsoppgaver, verktøy eller noe som ikke er ferdig.

Dashboardet leser README på nytt hver gang den endres, så endringene vises ved neste oppdatering.

### Bilde

Uten `bilde:` tar dashboardet selv et skjermbilde av siden. Det fungerer ikke alltid, og da **må** du legge inn et bilde:

- Siden er bare synlig for organisasjonen (privat GitHub Pages).
- Siden krever innlogging.
- Skjermbildet blir svart eller viser bare en laster eller en startknapp. Det skjer ofte med spill som bruker WebGL eller lyd.

Krav til bildet:

- PNG, JPEG, WebP eller GIF (ikke SVG), under 5 MB.
- Liggende, helst 1280 × 800 piksler. Kortet viser et bredt utsnitt fra toppen.
- Vis prosjektet i bruk, for eksempel spillet midt i et brett, ikke bare menyen.
- Ingen personopplysninger: ingen ansikter, ekte navn, e-postadresser eller passord.
- Legg det i repoet, for eksempel som `docs/skjermbilde.png`, og pek på det med `bilde:`.

Har README ingen kilab-blokk, brukes det første bildet i README hvis skjermbildet ikke virker.

### Mal

[`mal/README.md`](mal/README.md) er en ferdig README med kilab-blokken. Kopier den inn i repoet ditt og fyll ut.

Teksten på kortet er første avsnitt i README. Skriv én eller to setninger om hva prosjektet er, hvem det er for og hva det er laget med.
