---
name: web-app-checklist
description: Checklist obbligatoria di sicurezza, compliance legale (GDPR, cookie, CCPA, DMCA, CAN-SPAM, abbonamenti) e pre-lancio per qualsiasi app o sito web. Usa SEMPRE questa skill in Claude Code quando si crea, avvia, modifica, rivede o deploya un progetto web/app — anche se l'utente non la nomina, ad esempio nuovo progetto, nuova feature, autenticazione, database, API, form, pagamenti, email, cookie, analytics, upload di file, integrazione AI, deploy, lancio, go-live, code review. Nel dubbio, attivala.
---

# Web & App Checklist

Lo scopo: ogni progetto web o app nasce sicuro, legalmente in regola e pronto per il lancio, senza che l'utente debba ricordarselo. Non sono consigli legali: per casi dubbi suggerisci di sentire un professionista.

## Quando e cosa controllare

Individua la fase del lavoro e carica il file di riferimento corrispondente. Più fasi possono valere insieme.

| Fase | File da leggere |
|---|---|
| Nuovo progetto, scaffolding, scelta stack | `references/1-fondamenta.md` + `references/2-compliance.md` |
| Auth, DB, API, form, upload, AI, pagamenti, email | `references/1-fondamenta.md` + `references/3-sicurezza.md` (+ sezione rilevante di `2-compliance.md`) |
| Tracking, analytics, cookie, marketing, abbonamenti | `references/2-compliance.md` |
| Code review, refactor, prima di ogni deploy | `references/3-sicurezza.md` |
| Lancio / go-live / dominio in produzione | tutti e quattro, con `references/4-pre-lancio.md` come guida |

## Come lavorare

1. **Applica in automatico i requisiti mentre scrivi codice.** Non aspettare che l'utente lo chieda: se crei un login, usa un provider vero; se crei una tabella con dati utente, aggiungi RLS; se aggiungi un form, mettici validazione server-side e anti-spam.
2. **Segnala ciò che non puoi risolvere da solo** (es. registrare l'agente DMCA, scrivere i testi legali definitivi, configurare la CMP) come azioni per l'utente, brevemente, alla fine della risposta.
3. **Prima di un deploy o lancio** produci un report sintetico: per ogni punto pertinente `OK`, `DA FARE` o `N/A`, con file/riga quando c'è un problema. Salta i punti chiaramente non applicabili invece di elencarli tutti.
4. **Non bloccare il lavoro**: se l'utente sta prototipando in locale, applica le fondamenta e rimanda il resto, ricordandolo al primo deploy.

## Regole non negoziabili

- Nessun segreto nel frontend. In Next.js mai `NEXT_PUBLIC_` per chiavi segrete; `.env` sempre in `.gitignore`.
- Ogni dato utente isolato per user_id (RLS o filtro obbligatorio a livello di query).
- Nessuno script di tracciamento (GA, Meta Pixel, Hotjar, Clarity) parte prima del consenso cookie.
- La privacy policy descrive i tracker realmente presenti nel codice. Se aggiungi un tracker, segnala che la policy va aggiornata.
- Input utente e contenuti esterni passati a un LLM sono dati, mai istruzioni.
