# Mail API – Hasura Exploration Example

Deze repository bevat een voorbeeldimplementatie van een Mail API, ontwikkeld als opdracht voor een potentiële werkgever.
De API maakt het mogelijk om e-mails te beheren en te verzenden via een Hasura back-end.

## Functionaliteiten

- **Aanmaken, wijzigen en verwijderen van e-mails**  
    Beheer e-mails die nog verzonden moeten worden via GraphQL-mutations.

- **Verzenden van e-mails**  
    Verstuur aangemaakte e-mails naar de ontvanger via een SendGrid-integratie.

## Technische details

- **Back-end:**  
    Hasura is gebruikt als back-end framework. De basisconcepten zoals tables, mutations, actions en scheduled events zijn toegepast.

- **Database:**  
    Verbonden met een PostgreSQL database (`my_connector`).

- **E-mailprovider:**  
    SendGrid is gekoppeld via Hasura's DDN als externe service (`mysendgrid`) voor het verzenden van e-mails.

## Quickstart die gevolgd werd

1. **Clone deze repository**
2. **Volg de standaard Hasura quickstart**  
     Zie [Hasura Docs](https://hasura.io/docs/latest/getting-started/) voor installatie en setup.
3. **Configureer de database**  
     Verbind met een PostgreSQL database en noem deze `my_connector`.
4. **Stel SendGrid in**
     Voeg je SendGrid API key toe als DDN en noem deze `mysendgrid`.
5. **Gebruik GraphQL**  
     Gebruik de Hasura Console om e-mails aan te maken, te wijzigen, te verwijderen en te verzenden via GraphQL-mutations en actions.

## Lokaal draaien

### Vereisten

- Volg de [prerequisites](https://hasura.io/docs/3.0/quickstart/#prerequisites) uit de Hasura documentatie (zoals Docker, Node.js, DDN CLI, etc.).
- Zorg dat je de benodigde ENV-variabelen toevoegt (zoals database connectiestrings en SendGrid API key). Zie het bestand [`.env.example`](./.env.example) voor details.

### Stappen

1. **Controleer of DDN werkt:**
   ```sh
   ddn doctor
   ```
   Dit controleert of DDN lokaal correct is geïnstalleerd en geconfigureerd.

2. **Build de supergraph lokaal:**
   ```sh
   ddn supergraph build local
   ```
   Hiermee wordt een lokale, immutable versie van de supergraph gebouwd.

3. **Start de lokale omgeving via Docker:**
   ```sh
   ddn run docker-start
   ```
   Dit start alle benodigde Docker-instances (zoals Hasura, PostgreSQL, etc.).

4. **Open de Hasura Console:**
   Open een nieuwe terminal en voer uit:
   ```sh
   ddn console --local
   ```
   Hiermee wordt de Hasura Console in je browser geopend.

5. **(Optioneel) Controleer logs en debugging:**
   - Gebruik `docker ps` om te zien of alle containers draaien.
   - Bekijk logs met `docker logs <container_name>` indien nodig.

6. **Gebruik de Hasura Console:**
   - Maak verbinding met je database en configureer de SendGrid DDN.
   - Test de GraphQL-mutations en actions.


