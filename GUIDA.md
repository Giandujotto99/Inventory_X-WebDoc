# Stats_X Docs - Guida Editing

## Come funziona

Il sito ha due aree:

- **Sidebar (sinistra)**: menu con le voci cliccabili
- **Contenuto (destra)**: il contenuto che appare quando clicchi una voce

Quando clicchi una voce nella sidebar, appare SOLO quella sezione. Lo scroll non cambia sezione.

---

## 1. Aggiungere una VOCE nel menu (Sidebar)

Apri `docs.html` e trova la sezione `<aside class="sidebar">`.

### Aggiungere una voce in una categoria esistente

```html
<li><a href="#mio-id" data-section="mio-id">Nome Voce</a></li>
```

### Aggiungere una nuova categoria

```html
<div class="sidebar-section">
    <div class="sidebar-title">Nome Categoria</div>
    <ul class="sidebar-nav">
        <li><a href="#voce1" data-section="voce1">Prima Voce</a></li>
        <li><a href="#voce2" data-section="voce2">Seconda Voce</a></li>
    </ul>
</div>
```

⚠️ **IMPORTANTE**: Il valore di `data-section` deve essere UGUALE all'`id` della sezione contenuto!

---

## 2. Aggiungere una SEZIONE contenuto

Trova `<main class="content">` e aggiungi dentro `<div class="content-wrapper">`:

```html
<section id="mio-id" class="tutorial-section">
    <h1>Titolo Sezione</h1>
    <p>Il tuo contenuto qui...</p>
</section>
```

⚠️ L'`id` deve corrispondere al `data-section` del link nella sidebar!

---

## 3. Elementi disponibili per il contenuto

### Testo base

```html
<h1>Titolo Principale</h1>
<h2>Sottotitolo</h2>
<h3>Sotto-sottotitolo</h3>
<p>Paragrafo di testo normale.</p>
```

### Video locale (MP4)

```html
<div class="video-wrapper">
    <video controls>
        <source src="videos/nomefile.mp4" type="video/mp4">
    </video>
</div>
```

**Dimensioni video disponibili** (aggiungi classe al div):

- Default: max 700px
- `small`: max 450px  → `<div class="video-wrapper small">`
- `medium`: max 600px → `<div class="video-wrapper medium">`
- `large`: max 850px  → `<div class="video-wrapper large">`
- `full`: 100% larghezza → `<div class="video-wrapper full">`

### Video YouTube

```html
<div class="video-wrapper youtube">
    <iframe src="https://www.youtube.com/embed/ID_VIDEO" allowfullscreen></iframe>
</div>
```

Sostituisci `ID_VIDEO` con l'ID del video YouTube (es: `dQw4w9WgXcQ`)

### Immagine

```html
<img src="images/nomefile.png" alt="Descrizione immagine">
```

**Dimensioni immagini disponibili** (aggiungi classe all'img):

- Default: max 600px
- `small`: max 350px  → `<img class="small" src="...">`
- `medium`: max 500px → `<img class="medium" src="...">`
- `large`: max 800px  → `<img class="large" src="...">`
- `full`: 100% larghezza → `<img class="full" src="...">`

### Box informativo (4 tipi: tip, warning, danger, info)

```html
<div class="info-box tip">
    <div class="info-title">💡 Suggestion</div>
    <p>Testo del suggerimento...</p>
</div>

<div class="info-box warning">
    <div class="info-title">⚠️ Warning</div>
    <p>Testo warning...</p>
</div>

<div class="info-box danger">
    <div class="info-title">🚫 Danger</div>
    <p>Testo pericolo...</p>
</div>

<div class="info-box info">
    <div class="info-title">ℹ️ Info</div>
    <p>Testo informativo...</p>
</div>
```

### Blocco codice

```html
<div class="code-block">
    <div class="code-header">
        <span class="code-lang">C++</span>
    </div>
    <pre><code>// Il tuo codice qui
void MyFunction() {
    // ...
}</code></pre>
</div>
```

### Lista di passaggi numerati

```html
<div class="steps">
    <div class="step">
        <div class="step-number">1</div>
        <div class="step-content">
            <h3>Titolo Passo 1</h3>
            <p>Descrizione del primo passo...</p>
        </div>
    </div>
    <div class="step">
        <div class="step-number">2</div>
        <div class="step-content">
            <h3>Titolo Passo 2</h3>
            <p>Descrizione del secondo passo...</p>
        </div>
    </div>
</div>
```

### Lista puntata

```html
<ul>
    <li>Elemento 1</li>
    <li>Elemento 2</li>
    <li>Elemento 3</li>
</ul>
```

### Lista numerata

```html
<ol>
    <li>Primo</li>
    <li>Secondo</li>
    <li>Terzo</li>
</ol>
```

### Tabella

```html
<table class="data-table">
    <thead>
        <tr>
            <th>Colonna 1</th>
            <th>Colonna 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Dato 1</td>
            <td>Dato 2</td>
        </tr>
    </tbody>
</table>
```

---

## 4. Esempio completo

### Sidebar

```html
<div class="sidebar-section">
    <div class="sidebar-title">My Tutorial</div>
    <ul class="sidebar-nav">
        <li><a href="#my-tutorial" data-section="my-tutorial">My First Tutorial</a></li>
    </ul>
</div>
```

### Contenuto

```html
<section id="my-tutorial" class="tutorial-section">
    <h1>My First Tutorial</h1>
    
    <p>Benvenuto in questo tutorial! Imparerai a...</p>
    
    <div class="info-box tip">
        <div class="info-title">💡 Prima di iniziare</div>
        <p>Assicurati di aver installato il plugin.</p>
    </div>
    
    <h2>Video Tutorial</h2>
    <div class="video-wrapper youtube">
        <iframe src="https://www.youtube.com/embed/VIDEO_ID" allowfullscreen></iframe>
    </div>
    
    <h2>Passaggi</h2>
    <div class="steps">
        <div class="step">
            <div class="step-number">1</div>
            <div class="step-content">
                <h3>Apri il progetto</h3>
                <p>Apri Unreal Engine e carica il tuo progetto...</p>
            </div>
        </div>
        <div class="step">
            <div class="step-number">2</div>
            <div class="step-content">
                <h3>Aggiungi il componente</h3>
                <p>Cerca Stats_X Component...</p>
                <img src="images/screenshot.png" alt="Screenshot">
            </div>
        </div>
    </div>
    
</section>
```

---

## 5. Struttura cartelle

```
stats-x-docs/
├── index.html          (landing page)
├── docs.html           (documentazione - MODIFICA QUESTO)
├── css/
│   └── style.css       (stili - non toccare)
├── js/
│   └── main.js         (script - non toccare)
├── images/             (metti qui le immagini)
│   └── ...
└── videos/             (metti qui i video MP4)
    └── ...
```

---

## Note

- I video vanno nella cartella `videos/`
- Le immagini vanno nella cartella `images/`
- Non modificare `style.css` o `main.js` se non sai cosa fai
- La prima sezione deve avere `class="tutorial-section active"` (con active!)
