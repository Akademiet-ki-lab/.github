# .github for Akademiet-ki-lab

Felles maler for organisasjonen.

## KI-lab CI

`workflow-templates/kilab-ci.yml` er en mal for automatisk sjekk av et repo. Den kjører testene, lint og typesjekk ved hver push til main og ved hver pull request.

Slik legger du den til i et repo:

1. Åpne fanen **Actions** i repoet. Har repoet workflows fra før, trykker du **New workflow**.
2. Finn **KI-lab CI** under «By Akademiet-ki-lab» og trykk **Configure**.
3. Trykk **Commit changes…**.

Når sjekken har kjørt, viser KI-lab-dashboardet om den gikk gjennom, i stedet for «Ingen CI».
