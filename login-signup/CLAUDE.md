# CLAUDE.md - Customizzazione Template Webkul MultiVendor Marketplace

## Obiettivo del Progetto
Customizzare i template HTML di login e signup di Webkul MultiVendor Marketplace per Shopify seguendo una grafica di riferimento, con traduzione in italiano e creazione di fogli di stile CSS dedicati.

## Struttura Directory

```
project/
├── input/
│   ├── esempio-grafica.png    # File di riferimento per il design
│   ├── login.html              # Template originale login
│   └── signup.html             # Template originale signup
└── output/
    ├── login.html              # Template login customizzato
    ├── login.css               # Foglio di stile per login
    ├── signup.html             # Template signup customizzato
    └── signup.css              # Foglio di stile per signup
```

## Requisiti Tecnici

### 1. Analisi del Design di Riferimento
- Esamina attentamente il file `input/esempio-grafica.png`
- Identifica:
  - Schema colori (colori primari, secondari, accenti)
  - Typography (font, dimensioni, pesi)
  - Layout e spaziature
  - Stile elementi form (input, button, link)
  - Elementi decorativi o icone
  - Responsive behavior se visibile

### 2. Preservazione della Logica Template

**CRITICAL**: Devi mantenere intatta tutta la logica del template:

- **Variabili Smarty**: Mantieni tutte le variabili nel formato `{$variabile}`
  - Esempio: `{$shop}`, `{$error}`, `{$form_data}`, etc.
  
- **Blocchi condizionali**: Preserva tutti i blocchi `{if}...{/if}`
  ```smarty
  {if $error}
      <div class="error">{$error}</div>
  {/if}
  ```

- **Blocchi di funzione**: Mantieni i blocchi `{function}...{/function}`
  ```smarty
  {function name=renderField}
      <!-- contenuto funzione -->
  {/function}
  ```

- **Altri tag Smarty**: Loop `{foreach}`, include `{include}`, etc.

### 3. Traduzione in Italiano

Traduci **TUTTI** i testi statici in italiano professionale:

**Testi comuni da tradire:**
- "Login" → "Accedi"
- "Sign Up" → "Registrati"
- "Email" → "Email" (invariato)
- "Password" → "Password" (invariato)
- "Confirm Password" → "Conferma Password"
- "Remember me" → "Ricordami"
- "Forgot password?" → "Password dimenticata?"
- "Don't have an account?" → "Non hai un account?"
- "Already have an account?" → "Hai già un account?"
- "Submit" → "Invia"
- "Create Account" → "Crea Account"
- "First Name" → "Nome"
- "Last Name" → "Cognome"
- "Company Name" → "Nome Azienda"
- "Phone Number" → "Numero di Telefono"

**NON tradurre:**
- Nomi di variabili e attributi HTML/CSS
- Commenti nel codice (mantieni in inglese per compatibilità)
- Valori di attributi tecnici

### 4. Creazione CSS

Crea due file CSS separati (`login.css` e `signup.css`):

**Struttura CSS raccomandata:**

```css
/* ==========================================================================
   Reset e Base Styles
   ========================================================================== */

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* ==========================================================================
   Variables (CSS Custom Properties)
   ========================================================================== */

:root {
    /* Colori dal design di riferimento */
    --primary-color: #...;
    --secondary-color: #...;
    --accent-color: #...;
    --text-color: #...;
    --background-color: #...;
    --error-color: #...;
    --success-color: #...;
    
    /* Typography */
    --font-family-primary: ...;
    --font-family-secondary: ...;
    
    /* Spacing */
    --spacing-xs: 0.25rem;
    --spacing-sm: 0.5rem;
    --spacing-md: 1rem;
    --spacing-lg: 1.5rem;
    --spacing-xl: 2rem;
    
    /* Border Radius */
    --border-radius-sm: 4px;
    --border-radius-md: 8px;
    --border-radius-lg: 12px;
    
    /* Shadows */
    --shadow-sm: 0 2px 4px rgba(0,0,0,0.1);
    --shadow-md: 0 4px 6px rgba(0,0,0,0.1);
    --shadow-lg: 0 10px 15px rgba(0,0,0,0.1);
}

/* ==========================================================================
   Layout Container
   ========================================================================== */

.login-container,
.signup-container {
    /* Layout principale */
}

/* ==========================================================================
   Form Styles
   ========================================================================== */

.form-group {
    /* Stile gruppi form */
}

.form-control {
    /* Stile input */
}

.form-control:focus {
    /* Stile input in focus */
}

/* ==========================================================================
   Button Styles
   ========================================================================== */

.btn {
    /* Stile base button */
}

.btn-primary {
    /* Stile button primario */
}

.btn:hover {
    /* Hover effect */
}

/* ==========================================================================
   Error/Success Messages
   ========================================================================== */

.error-message {
    /* Stile messaggi errore */
}

.success-message {
    /* Stile messaggi successo */
}

/* ==========================================================================
   Responsive Design
   ========================================================================== */

@media (max-width: 768px) {
    /* Mobile styles */
}

@media (min-width: 769px) and (max-width: 1024px) {
    /* Tablet styles */
}
```

## Processo di Lavoro Step-by-Step

### Step 1: Analisi File Input
```bash
# Verifica presenza file
ls -la input/

# Visualizza contenuto HTML
cat input/login.html
cat input/signup.html
```

### Step 2: Analisi Grafica
- Apri `input/esempio-grafica.png`
- Documenta colori, font, spacing, stili
- Crea palette colori e style guide

### Step 3: Creazione CSS
Per ogni file (login.css e signup.css):
1. Definisci variabili CSS custom properties
2. Imposta reset e base styles
3. Crea stili per layout container
4. Definisci stili form elements
5. Definisci stili button e link
6. Aggiungi stili per messaggi errore/successo
7. Implementa responsive design
8. Aggiungi transizioni e animazioni

### Step 4: Modifica HTML
Per ogni file (login.html e signup.html):
1. **Backup originale**: Copia contenuto originale
2. **Link CSS**: Aggiungi riferimento al CSS
   ```html
   <link rel="stylesheet" href="login.css">
   ```
3. **Struttura HTML**: Mantieni struttura esistente
4. **Classi CSS**: Aggiungi classi per styling
5. **Traduzione**: Sostituisci tutti i testi statici
6. **Verifica**: Controlla che tutte le variabili e blocchi Smarty siano intatti

### Step 5: Quality Check
Verifica finale per ogni file:
- [ ] Tutte le variabili `{$...}` sono presenti
- [ ] Tutti i blocchi `{if}...{/if}` sono corretti
- [ ] Tutti i blocchi `{function}...{/function}` sono preservati
- [ ] Tutti i testi sono in italiano
- [ ] I CSS sono linkati correttamente
- [ ] Il design segue l'esempio grafico
- [ ] Il codice è formattato correttamente

## Linee Guida per il Design

### Accessibilità
- Contrasto colori conforme WCAG 2.1 AA
- Dimensioni font leggibili (minimo 16px per body)
- Focus states visibili per navigazione keyboard
- Labels associati correttamente agli input

### User Experience
- Feedback visivo chiaro per interazioni
- Messaggi di errore ben visibili
- Call-to-action evidenti
- Caricamento veloce (CSS ottimizzato)

### Mobile-First
- Design responsive da mobile a desktop
- Touch targets sufficientemente grandi (min 44x44px)
- Form fields facilmente compilabili su mobile

## Validazione Output

Prima di considerare completato il lavoro, verifica:

1. **Sintassi HTML**: Valida HTML5
2. **Sintassi CSS**: Valida CSS3
3. **Template Logic**: Tutte le variabili e blocchi Smarty intatti
4. **Traduzione**: Nessun testo in inglese rimanente
5. **Design**: Corrispondenza con esempio grafico
6. **File Output**: 4 file nella cartella output/

## Note Importanti

- **NON modificare** la logica del template Smarty
- **NON rimuovere** variabili o blocchi condizionali
- **Mantieni** la stessa struttura HTML base
- **Aggiungi** solo classi CSS e styling
- **Traduci** solo testi visibili all'utente

## Esempio di Conversione

**Prima (originale):**
```html
<form method="post" action="{$form_action}">
    {if $error}
        <div class="error">{$error}</div>
    {/if}
    <label>Email</label>
    <input type="email" name="email" value="{$form_data.email}" required>
    <button type="submit">Login</button>
</form>
```

**Dopo (customizzato):**
```html
<link rel="stylesheet" href="login.css">

<div class="login-container">
    <form method="post" action="{$form_action}" class="login-form">
        {if $error}
            <div class="error-message">{$error}</div>
        {/if}
        <div class="form-group">
            <label for="email" class="form-label">Email</label>
            <input type="email" 
                   id="email"
                   name="email" 
                   value="{$form_data.email}" 
                   class="form-control" 
                   required>
        </div>
        <button type="submit" class="btn btn-primary">Accedi</button>
    </form>
</div>
```

## Troubleshooting

### Problema: Variabili Smarty non funzionano
- **Causa**: Sintassi modificata o rimossa
- **Soluzione**: Confronta con originale e ripristina sintassi esatta

### Problema: Stili non applicati
- **Causa**: Path CSS errato o specificità bassa
- **Soluzione**: Verifica path e aumenta specificità selettori

### Problema: Layout rotto su mobile
- **Causa**: Mancano media queries
- **Soluzione**: Aggiungi breakpoint responsive

## Deliverables Finali

Al termine del lavoro, la cartella `output/` deve contenere:

1. ✅ `login.html` - Template login customizzato e tradotto
2. ✅ `login.css` - Foglio di stile per login
3. ✅ `signup.html` - Template signup customizzato e tradotto
4. ✅ `signup.css` - Foglio di stile per signup

Tutti i file devono essere pronti per l'uso in produzione su Webkul MultiVendor Marketplace per Shopify.
