# 1. Fondamenta anti-hack

Da impostare all'inizio, non a fine progetto.

- [ ] **Provider di autenticazione vero**: Clerk, Supabase Auth, Auth.js. Mai login fatto in casa (hash, sessioni, reset password).
- [ ] **Row Level Security**: ogni riga con dati utente ha `user_id`; policy che consente lettura/scrittura solo al proprietario. Senza Supabase/Postgres RLS: filtro per utente obbligatorio in un livello centralizzato di accesso ai dati.
- [ ] **Segreti solo lato server**: chiavi API e credenziali DB in variabili d'ambiente, `.env` non committato, mai prefisso `NEXT_PUBLIC_` / `VITE_` per segreti. Chiamate ad API esterne solo da route/server action.
- [ ] **Rate limiting** su API e login, per IP o per utente (Upstash Ratelimit, middleware Vercel, Traefik).
- [ ] **Cache e deduplica**: debounce/disabilitazione dei bottoni durante l'invio, caching lato server delle richieste ripetute, idempotenza sulle operazioni critiche (pagamenti).
