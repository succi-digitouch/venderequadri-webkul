# CLAUDE.md - Email Template Customizer per Webkul MultiVendor Marketplace

## Panoramica del Progetto
Questo progetto gestisce la personalizzazione dei testi delle email per Webkul MultiVendor Marketplace su Shopify. Claude Code elabora file di testo semplici e genera template email professionali in italiano.

## Struttura del Progetto

```
email-templates/
├── input/              # File .txt con contenuti grezzi
├── output/             # Template email generati
└── templates/          # Template base riutilizzabili
```

## Formato File Input

I file nella cartella `input/` devono seguire questo formato:

**Esempio (`input/seller-registered.txt`):**
```
SUBJECT: Welcome Seller
---
Hello {$seller_name}
Thank you for registering yourself. You are now a part of {$shop}.

Login
Thanks & Regards

{$shop}
---
VARIABLES
{$seller_name} - Seller Name
{$seller_store_name} - Seller Store Name
{$shop} - Shop Name
{$public_url} - Public URL for Sellers
```

## Linee Guida per la Generazione

### Tono e Stile
- **Professionale** ma accessibile
- **Chiaro** e conciso
- **Formale** con il "Lei" quando appropriato

### Struttura Email Standard
1. **Saluto personalizzato** (quando possibile con variabili)
2. **Messaggio principale** chiaro e diretto
3. **Call-to-action** specifica
4. **Informazioni di supporto** (se necessarie)
5. **Chiusura** cortese
6. **Firma** con dati azienda

### Mantieni le tabelle, traduci soltanto le intestazioni e i testi

### Variabili Shopify/Webkul
Mantieni e utilizza correttamente le variabili:
- `{$seller_name}` - Seller Name
- `{$seller_store_name}` - Seller Store Name
- `{$shop}` - Shop Name
- `{$public_url}` - Public URL for Sellers
- mantieni i blocchi condizionali come sono `{if !empty($item_names) &amp;&amp; $item_names}` ... `{/if}`

## Compiti di Claude Code

### 1. Analisi File Input
```bash
# Leggi tutti i file .txt in input/
# Estrai OGGETTO e corpo del messaggio
# Identifica il tipo di email (ordine, spedizione, registrazione, etc.)
```

### 2. Generazione Template
Per ogni file input, genera:
- **Oggetto ottimizzato**: breve, chiaro
- **HTML template**: struttura responsive con stile professionale
- **Testo plain**: versione testuale per client email semplici

### 3. Output Richiesto
Crea nella cartella `output/` per ogni email:
- `nome_email.html` - Template HTML completo
- `nome_email.txt` - Versione plain text

## Best Practices Lingua Italiana

### Formule di Apertura
- "Gentile {$seller_name}," (formale)

### Formule di Chiusura
- "Cordiali saluti,"
- "Il team di {$shop}"

### Terminologia E-commerce
- **Ordine** non "order"
- **Spedizione** non "shipping"
- **Venditore** non "vendor"
- **Acquisto** non "purchase"
- **Carrello** non "cart"

## Tipi di Email Comuni

### Email Venditori
- Nuova registrazione venditore
- Approvazione account venditore
- Nuovo ordine ricevuto
- Prodotto in attesa approvazione
- Pagamento disponibile

### Email Clienti
- Conferma ordine
- Spedizione prodotto
- Consegna completata
- Rimborso processato
- Reset password

## Validazione

Claude Code deve verificare:
- ✅ Tutte le variabili sono nel formato corretto `{$variabile}`
- ✅ Nessun errore grammaticale o refuso
- ✅ HTML ben formato e responsive
- ✅ Testo alternativo presente
- ✅ Link e CTA chiari

## Esempi di Utilizzo

```bash
# Genera template da tutti i file input
claude code "Genera i template email da tutti i file in input/"

# Genera singolo template
claude code "Crea template professionale da input/welcome_vendor.txt"

# Aggiorna template esistente
claude code "Migliora il tono di output/order_confirmation.html rendendolo più cordiale"
```

## Note Tecniche

- **Charset**: UTF-8 per caratteri accentati italiani
- **HTML**: Tabelle per compatibilità email client
- **CSS**: Inline per massima compatibilità
- **Immagini**: Usa placeholder se necessario
- **Responsive**: Media queries per mobile

## Obiettivi di Qualità

Ogni email generata deve:
1. Comunicare **chiaramente** lo scopo
2. Avere una **call-to-action** evidente
3. Essere **grammaticalmente perfetta** in italiano
4. Funzionare su **tutti i client email** principali
5. Riflettere un brand **professionale** e **affidabile**

---

**Versione**: 1.0  
**Ultimo aggiornamento**: 2025-11-04