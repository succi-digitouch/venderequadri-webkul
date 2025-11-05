# Webkul MultiVendor Marketplace - Customizzazione Italiana

Repository di personalizzazione e localizzazione per Webkul MultiVendor Marketplace su Shopify.

## Panoramica Progetto

Questo repository contiene template e risorse per customizzare il marketplace Webkul MultiVendor con design professionale e testi in italiano. Il progetto è suddiviso in due componenti principali:

1. **Email Templates** - Template email professionali in italiano
2. **Login/Signup Templates** - Interfacce di autenticazione customizzate

---

## 📧 Email Templates

### Struttura
```
emails/
├── input/          # File .txt con contenuti grezzi da tradurre
├── output/         # Template HTML email generati
├── templates/      # Template base riutilizzabili
├── backups/        # Backup dei template originali
└── CLAUDE.md       # Documentazione dettagliata
```

### Cosa Contiene
Template email professionali in italiano per tutte le comunicazioni del marketplace:

**Email Venditori:**
- Registrazione e approvazione account
- Notifiche ordini e pagamenti
- Gestione prodotti (creazione, modifica, eliminazione)
- Inventario e fulfillment
- Richieste RMA
- API e webhook
- Modalità vacanza
- Accesso admin al pannello seller

**Email Clienti:**
- Conferma e tracking ordini
- Spedizione e consegna
- Cancellazioni e rimborsi
- Pagamenti e fatture
- Messaggistica con venditori

### Come Funziona
1. I file `.txt` nella cartella `input/` contengono i testi originali in inglese con variabili Shopify/Webkul
2. Claude Code elabora questi file e genera template HTML professionali in italiano
3. Gli output nella cartella `output/` sono pronti per essere integrati nel marketplace

### Caratteristiche Template
- ✅ Italiano professionale e chiaro
- ✅ Design responsive per tutti i client email
- ✅ CSS inline per massima compatibilità
- ✅ Variabili Smarty/Shopify preservate (es. `{$seller_name}`, `{$shop}`)
- ✅ Struttura table-based per compatibilità client email
- ✅ Charset UTF-8 per caratteri accentati

---

## 🔐 Login & Signup Templates

### Struttura
```
login-signup/
├── input/          # Template originali e grafiche di riferimento
├── output/         # Template customizzati + CSS
│   ├── login.html
│   ├── login.css
│   ├── signup.html
│   └── signup.css
└── CLAUDE.md       # Documentazione dettagliata
```

### Cosa Contiene
Template HTML e CSS customizzati per le pagine di autenticazione del marketplace:

- **Login Page** - Pagina di accesso venditori
- **Signup Page** - Pagina di registrazione venditori

### Caratteristiche
- ✅ Design moderno basato su grafica di riferimento
- ✅ Testi completamente tradotti in italiano
- ✅ CSS separati e modulari
- ✅ Responsive design (mobile-first)
- ✅ Template logic Smarty preservata al 100%
- ✅ Variabili e blocchi condizionali intatti
- ✅ Accessibilità WCAG 2.1 AA
- ✅ CSS Custom Properties per facile manutenzione

### Tecnologie
- HTML5 valido
- CSS3 con custom properties
- Smarty Template Engine (variabili preservate)
- Design responsive con media queries

---

## 🚀 Come Usare

### Email Templates

#### Generare Nuovi Template
```bash
# Aggiungi un file .txt nella cartella emails/input/
# Formato richiesto:
# SUBJECT: Oggetto email
# ---
# Corpo del messaggio con variabili {$variabile}
# ---
# VARIABLES
# {$variabile} - Descrizione variabile

# Poi chiedi a Claude Code di generare il template
claude code "Genera template email da input/nuovo_file.txt"
```

#### Modificare Template Esistenti
```bash
# I file nella cartella emails/output/ possono essere modificati direttamente
# oppure rigenerati da Claude Code
```

### Login/Signup Templates

#### Customizzare Design
1. Modifica i file CSS in `login-signup/output/`
2. I template HTML usano classi CSS per lo styling
3. Usa le CSS custom properties (`:root`) per modificare colori e spacing

#### Aggiornare Testi
1. Modifica direttamente i file HTML in `login-signup/output/`
2. **ATTENZIONE**: Non modificare le variabili Smarty `{$variabile}`

---

## 📋 Linee Guida

### Tono e Stile
- **Professionale** ma accessibile
- **Chiaro** e diretto
- Uso del **"Lei"** formale quando appropriato

### Terminologia E-commerce
Usa sempre i termini italiani corretti:
- **Ordine** (non "order")
- **Spedizione** (non "shipping")
- **Venditore** (non "vendor")
- **Acquisto** (non "purchase")
- **Carrello** (non "cart")

### Preservazione Template Logic
⚠️ **CRITICO**: Quando modifichi i template:
- ✅ Mantieni tutte le variabili `{$variabile}`
- ✅ Preserva i blocchi `{if}...{/if}`
- ✅ Non modificare i blocchi `{function}...{/function}`
- ✅ Mantieni intatti `{foreach}`, `{include}`, etc.

---

## 📁 File Importanti

- `emails/CLAUDE.md` - Documentazione completa generazione email
- `login-signup/CLAUDE.md` - Documentazione completa customizzazione login/signup
- `.gitignore` - File e cartelle esclusi dal versioning

---

## 🛠️ Workflow Consigliato

### Per Nuove Email
1. Crea file `.txt` in `emails/input/`
2. Usa Claude Code per generare il template
3. Rivedi l'output in `emails/output/`
4. Integra nel marketplace Webkul

### Per Modifiche UI
1. Modifica `login-signup/output/*.css` per stile
2. Modifica `login-signup/output/*.html` per struttura/testi
3. Testa in ambiente staging
4. Deploy su produzione

---

## 📚 Risorse

### Webkul MultiVendor Marketplace
- [Documentazione Webkul](https://webkul.com/blog/shopify-multi-vendor-marketplace/)
- [Shopify Theme Development](https://shopify.dev/themes)

### Smarty Template Engine
- [Documentazione Smarty](https://www.smarty.net/documentation)

---

## 📝 Note Tecniche

### Charset
- Tutti i file usano **UTF-8** per supportare caratteri accentati italiani

### Compatibilità Email
- HTML table-based per client email legacy
- CSS inline per massima compatibilità
- Fallback text per client senza HTML

### Browser Support
- Template login/signup testati su:
  - Chrome/Edge (ultime 2 versioni)
  - Firefox (ultime 2 versioni)
  - Safari (ultime 2 versioni)
  - Mobile browsers

---

## 🎯 Obiettivi di Qualità

Ogni deliverable deve:
1. Comunicare **chiaramente** lo scopo
2. Essere **grammaticalmente perfetto** in italiano
3. Funzionare su **tutti i dispositivi e client** principali
4. Riflettere un brand **professionale** e **affidabile**
5. Essere **accessibile** (WCAG 2.1 AA minimum)

---

**Versione**: 1.0
**Ultimo aggiornamento**: 2025-11-05
**Progetto**: Venderequadri - Webkul MultiVendor Marketplace Customization
