# 2. Compliance legale e privacy

GDPR (UE), CCPA (California), DMCA, CAN-SPAM. Spunti operativi, non consulenza legale.

## Privacy policy
- [ ] Coerente con i tracker realmente attivi: con Google Analytics o Meta Pixel non scrivere "non vendiamo dati" (per il CCPA è vendita/condivisione).
- [ ] Informativa artt. 13-14 GDPR: titolare, finalità, base giuridica per ogni trattamento, destinatari, trasferimenti extra-UE, conservazione, diritti dell'interessato, DPO se previsto. Link nel footer di ogni pagina.
- [ ] Basi giuridiche (art. 6) documentate: consenso (marketing, cookie non tecnici), contratto (account, servizio), obbligo legale (fatturazione), legittimo interesse (sicurezza, antifrode).
- Sanzioni: GDPR fino a 20 M€ o 4% del fatturato; cookie fino a 10 M€ o 2%.

## Cookie banner
- [ ] Blocco preventivo di ogni script non tecnico fino al consenso (verifica in DevTools > Network).
- [ ] Accetta e Rifiuta con uguale evidenza, più Personalizza granulare. Niente dark pattern. Revoca sempre possibile.
- [ ] Google Consent Mode v2: `analytics_storage`, `ad_storage`, `ad_user_data`, `ad_personalization` collegati al banner.
- [ ] Cookie policy con nome, dominio, durata, finalità, base giuridica. CMP: Iubenda, Cookiebot, Complianz.

## Contenuti caricati dagli utenti (UGC)
- [ ] Registrare un DMCA designated agent su copyright.gov (circa 6 $) — azione dell'utente.
- [ ] Clausola di takedown nei Termini di servizio + canale di segnalazione nell'app.

## Email marketing
- [ ] CAN-SPAM: link di disiscrizione chiaro, oggetto onesto, indirizzo fisico nel footer.
- [ ] UE: consenso preventivo (opt-in) prima di inviare marketing.

## Abbonamenti
- [ ] Prezzo, rinnovo automatico e condizioni chiari prima del checkout.
- [ ] Cancellazione semplice dall'app; in UE diritto di recesso di 14 giorni.
