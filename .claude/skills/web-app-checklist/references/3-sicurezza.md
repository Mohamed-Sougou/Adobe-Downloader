# 3. Sicurezza tecnica

Da ricontrollare in ogni code review e prima di ogni deploy.

## Dipendenze e codice
- [ ] Dipendenze vulnerabili: `npm audit`, Dependabot.
- [ ] Pacchetti malevoli: verifica nome, autore, download; attenzione al typosquatting.
- [ ] Codice non revisionato: rileggi il codice generato prima del deploy.

## AI
- [ ] Prompt injection: input utente e contenuti esterni sono dati, mai istruzioni.
- [ ] Accesso AI senza permessi: l'AI legge e agisce solo entro i permessi dell'utente corrente.

## Database e dati
- [ ] Permessi DB minimi (least privilege); mai service key lato client.
- [ ] HTTPS ovunque; cifratura a riposo per dati sensibili.
- [ ] Isolamento tra tenant: ogni query filtrata per utente/organizzazione.
- [ ] Mass assignment: whitelist dei campi aggiornabili, mai il body intero all'ORM.
- [ ] Backup automatici e restore testato.

## Injection e input
- [ ] Command injection: mai input utente in `exec` o shell.
- [ ] Deserializzazione/validazione: ogni input validato con schema (es. Zod) lato server.

## Auth, web e infrastruttura
- [ ] OAuth: redirect URI esatti, parametro `state`, PKCE.
- [ ] Cookie: `HttpOnly`, `Secure`, `SameSite`.
- [ ] Header: CSP, HSTS, X-Frame-Options, X-Content-Type-Options.
- [ ] Dashboard/admin interne dietro autenticazione e ruoli.

## Monitoraggio
- [ ] Audit log: chi ha fatto cosa e quando.
- [ ] Alert su errori, login sospetti, superamento rate limit.
