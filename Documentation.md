# Documentation — Landing Page ArchiPop
### Testi ottimizzati per la conversione | Stack: Tailwind CSS 4.1+ · Framer Motion 12 · Heroicons

---

## 🛠️ Stack Tecnologico & Indicazioni Implementative

| Layer | Tecnologia | Note |
|---|---|---|
| Stile | Tailwind CSS 4.1+ | Utility-first, variabili CSS per palette brand |
| Animazioni | Framer Motion 12 | `motion.div`, `useInView`, `staggerChildren` |
| Icone | Heroicons | Stile **outline** uniforme in tutta la pagina |
| Font | Inter (Google Fonts) | Pesi: 400 · 600 · 700 · 800 |

**Palette CSS (da definire come variabili globali):**
```
--color-giallo:   #f5d500
--color-blu:      #0da7d8
--color-rosso:    #d11751
--color-bianco:   #ffffff
--color-nero:     #111111
```

---

## 📄 META & SEO

```
<title>Ristrutturazione Casa Roma | Consulenza Gratuita — ArchiPop</title>

<meta name="description"
  content="Ristruttura casa a Roma senza stress. ArchiPop ti guida dall'idea al cantiere: consulenza gratuita, preventivi trasparenti, professionisti selezionati. Rispondiamo in 24h.">
```

**Schema Markup consigliato:** `LocalBusiness` con `areaServed` (Roma, Ciampino, Frascati, Grottaferrata, Marino, Guidonia Montecelio, Tivoli)

---

---

## 🔝 HEADER / NAVBAR

**Logo:** `archipop-logo.svg` — allineato a sinistra  
**Menu voci (link anchor smooth scroll):**
- Chi Siamo
- Come Funziona
- Progetti
- Contatti

**CTA navbar (bottone primario rosso, sempre visibile):**
> Consulenza Gratuita

**Comportamento:** Sticky on scroll con ombra leggera. Su mobile: hamburger menu con overlay.

**🎬 Framer Motion:** `initial={{ y: -80, opacity: 0 }}` → `animate={{ y: 0, opacity: 1 }}` al mount, `duration: 0.5`.

---

---

## 1. HERO SECTION

> **Tag semantico:** `<section id="home">` — above the fold, full viewport height

---

### Headline principale — `<h1>`
```
Ristrutturi Casa a Roma?
Parti da Zero Stress.
```

### Sottotitolo — `<p>` lead
```
ArchiPop ti accompagna dall'idea al cantiere: consulenza gratuita,
professionisti selezionati e trasparenza totale su tempi e costi.
Nessuna sorpresa. Solo risultati.
```

### CTA Primaria — bottone `bg-rosso` testo bianco, large
```
🚀  Richiedi la Tua Consulenza Gratuita
```

### Micro-copy sotto CTA (riduce attrito)
```
Nessun impegno. Ti ricontattiamo entro 24 ore.
```

### Trust Badge — riga orizzontale, 3 elementi con Heroicons `CheckCircleIcon`
| Icona | Testo |
|---|---|
| `CheckCircleIcon` | Consulenza 100% gratuita |
| `LockClosedIcon` | Preventivi trasparenti |
| `StarIcon` | Professionisti selezionati |

---

**🎨 Visual Hero:**
Illustrazione in stile Pop Art di un appartamento romano "prima e dopo". Colori piatti, contorni neri netti, sfondo giallo `#f5d500`. Effetto poster anni '60. Alternativa: fotografia reale con overlay grafico pop (colore `#0da7d8` al 30% di opacità).

**🎬 Framer Motion:**
- Headline: `initial={{ opacity: 0, y: 40 }}` → `animate={{ opacity: 1, y: 0 }}`, delay 0.1s
- Sottotitolo: stesso schema, delay 0.25s
- CTA: delay 0.4s con leggero `scale` da 0.95 → 1
- Trust badges: `staggerChildren: 0.1`, entrata dal basso
- Visual destra: `initial={{ opacity: 0, x: 60 }}` → `animate={{ opacity: 1, x: 0 }}`, delay 0.3s

---

---

## 2. VALUE PROPOSITION / PROBLEMA

> **Tag semantico:** `<section id="problema">` — sfondo bianco, layout 3 card

---

### Titolo sezione — `<h2>`
```
Ristrutturare è complicato.
Lo sappiamo.
```

### Sottotitolo sezione
```
Prima ancora di pensare al cantiere, arrivano le domande difficili.
Quelle che tengono svegli la notte.
```

---

### Card 1 — Icona: `FaceSmileIcon` (con espressione confusa — o `QuestionMarkCircleIcon`)
**Titolo card:**
```
"Non so da dove iniziare"
```
**Testo:**
```
Hai mille idee e zero esperienza in ristrutturazioni.
Non sai chi chiamare per primo, né in che ordine fare le cose.
```

### Card 2 — Icona: `ExclamationTriangleIcon`
**Titolo card:**
```
"Ho paura di spendere male i soldi"
```
**Testo:**
```
Preventivi che variano del 50%, lavori che si allungano,
sorprese in corso d'opera. Il budget finale diventa un'incognita.
```

### Card 3 — Icona: `UserGroupIcon`
**Titolo card:**
```
"Non conosco nessuno di fiducia"
```
**Testo:**
```
Trovare un'impresa seria, un geometra affidabile e fornitori onesti
a Roma è una lotteria che nessuno vuole giocare.
```

---

### Transizione — banner full-width `bg-giallo` testo nero bold centrato
```
ArchiPop esiste per risolvere esattamente questi tre problemi.
```

---

**🎬 Framer Motion:**
- Titolo sezione: `useInView` con `once: true`, entrata dal basso
- Card: `staggerChildren: 0.15`, `initial={{ opacity: 0, y: 30 }}` → `animate={{ opacity: 1, y: 0 }}`
- Banner transizione: `whileInView={{ scaleX: [0.8, 1] }}` + fade-in

---

---

## 3. SOLUZIONE / CHI È ARCHIPOP

> **Tag semantico:** `<section id="chi-siamo">` — sfondo `bg-blu` o bianco con accenti

---

### Titolo sezione — `<h2>`
```
Non un'impresa. Non uno studio.
Il tuo alleato nella ristrutturazione.
```

### Paragrafo descrittivo
```
ArchiPop non esegue i lavori e non ti vende progetti standard:
ti affianca nelle scelte giuste, ti mette in contatto con i
professionisti del suo network e controlla che tutto fili liscio —
nei tempi, nei costi e nella qualità.
Perché la casa deve essere un luogo sicuro e bello da vivere,
costruito su basi di fiducia e chiarezza.
```

---

### 3 Colonne Valore — Icone Heroicons outline

**Colonna 1 — `AdjustmentsHorizontalIcon`**
```
Titolo: Solo ciò che ti serve
Testo: Analizziamo le tue esigenze reali e ti proponiamo esclusivamente
i servizi che fanno la differenza per il tuo progetto.
Niente di più, niente di meno.
```

**Colonna 2 — `MagnifyingGlassIcon`**
```
Titolo: Trasparenza totale
Testo: Preventivi chiari, professionisti selezionati, aggiornamenti
costanti. Sai sempre dove sei, quanto spendi e cosa aspettarti.
```

**Colonna 3 — `HandshakeIcon` (o `ShieldCheckIcon`)**
```
Titolo: Al tuo fianco fino alla fine
Testo: Non sparisce dopo il primo incontro. ArchiPop monitora ogni
fase dei lavori e tutela i tuoi interessi dall'inizio alla consegna.
```

---

**🎨 Visual suggerito:**
Illustrazione pop art a 3 vignette in stile fumetto: 1) persona confusa davanti casa, 2) consulente ArchiPop che spiega con entusiasmo (bolla di testo gialla), 3) casa finita e persona soddisfatta. Palette brand, stile coerente con hero.

**🎬 Framer Motion:**
- Titolo: `whileInView`, slide dal basso
- Colonne: `staggerChildren: 0.2`, ciascuna con leggero `rotateY` da -5° → 0° per effetto tridimensionale pop
- Visual: `initial={{ scale: 0.9, opacity: 0 }}` → `whileInView={{ scale: 1, opacity: 1 }}`

---

---

## 4. COME FUNZIONA — 5 STEP

> **Tag semantico:** `<section id="come-funziona">` — sfondo bianco o `bg-nero` testo bianco per contrasto

---

### Titolo sezione — `<h2>`
```
5 Step. Semplici. Trasparenti.
```

### Sottotitolo
```
Un metodo chiaro che elimina il caos e ti porta
dalla prima idea alle chiavi di casa.
```

---

### Step 1 — Icona: `ClipboardDocumentListIcon`
```
Numero: 01
Titolo: Richiedi
Testo: Compila il form o scrivici su WhatsApp.
La consulenza iniziale è sempre gratuita e senza impegno.
```

### Step 2 — Icona: `EarIcon` (o `ChatBubbleLeftRightIcon`)
```
Numero: 02
Titolo: Ascoltiamo
Testo: Ti incontriamo — anche online — e capiamo cosa vuoi davvero,
senza fretta e senza pressioni commerciali.
```

### Step 3 — Icona: `SparklesIcon`
```
Numero: 03
Titolo: Proponiamo
Testo: Ti presentiamo solo i servizi utili al tuo progetto,
con preventivo chiaro e voci dettagliate.
```

### Step 4 — Icona: `CheckBadgeIcon`
```
Numero: 04
Titolo: Decidi
Testo: Sei libero di procedere come preferisci.
Zero pressioni, zero impegni automatici. La scelta è tua.
```

### Step 5 — Icona: `EyeIcon`
```
Numero: 05
Titolo: Monitoriamo
Testo: Seguiamo l'esecuzione dei lavori e ti aggiorniamo ad ogni fase,
fino alla consegna finale delle chiavi.
```

---

### CTA ripetuta — bottone `bg-rosso`, centrata
```
🚀  Inizia dal Passo 1 — Consulenza Gratuita
```

---

**🎬 Framer Motion:**
- Percorso step: linea di connessione animata con `pathLength` da 0 → 1 durante scroll (`useScroll` + `useTransform`)
- Ogni step card: `whileInView` con `staggerChildren: 0.12`, entrata alternata sinistra/destra
- Numeri: counter animation da 0 → numero finale al `whileInView`

---

---

## 5. PORTFOLIO / PROGETTI

> **Tag semantico:** `<section id="portfolio">` — griglia 3 colonne

---

### Titolo sezione — `<h2>`
```
Alcuni Progetti che Abbiamo Seguito a Roma
```

### Sottotitolo
```
Ristrutturazioni seguite a Roma e comuni limitrofi.
Ogni progetto è partito da una chiacchierata gratuita.
```

---

### Card progetto — struttura ripetuta per ogni item
```
[Immagine progetto]
Tag categoria (es. "Ristrutturazione completa")
Zona: es. "Roma — Pigneto"
Superficie: es. "75 m²"
Breve nota: es. "Rifacimento totale impianti, nuova distribuzione spazi, render 3D incluso"
```

### Hover card — overlay `bg-blu` al 90% con testo bianco centrato
```
→ Scopri il progetto
```

---

### Micro-copy sotto griglia — centrato, italic
```
Il tuo progetto potrebbe essere il prossimo.
Scopri come iniziare.
```

### CTA sotto griglia — bottone outline `border-rosso` testo `rosso`
```
Guarda tutti i progetti →
```

---

**🎬 Framer Motion:**
- Griglia: `staggerChildren: 0.1`, ogni card `initial={{ opacity: 0, scale: 0.95 }}`
- Hover card: `whileHover={{ opacity: 1 }}` con overlay blu — transition `duration: 0.25`
- Immagine: `whileHover={{ scale: 1.05 }}` con `overflow: hidden` sul container

---

---

## 6. SOCIAL PROOF — TESTIMONIANZE + NUMERI

> **Tag semantico:** `<section id="recensioni">` — sfondo `bg-giallo` per rottura visiva

---

### Titolo sezione — `<h2>`
```
Cosa Dicono i Nostri Clienti
```

### Sottotitolo
```
Persone reali, progetti reali, risultati misurabili.
```

---

### Testimonianza 1 — card bianca, bordo sinistro `rosso` 4px
```
★★★★★
"Non avevo idea da dove iniziare. ArchiPop mi ha spiegato tutto
step by step, mi ha trovato un'impresa seria e ha seguito ogni fase.
Casa trasformata, zero stress."

— Marco R. | Roma · Ristrutturazione completa 85 m²
```

### Testimonianza 2
```
★★★★★
"Finalmente qualcuno che ti dice la verità sui costi invece di dirti
quello che vuoi sentire. Il preventivo è stato rispettato al 100%."

— Giulia M. | Frascati · Rifacimento bagno e cucina
```

### Testimonianza 3
```
★★★★★
"Pensavo fosse l'ennesima consulenza per poi sparire.
Invece ci hanno seguiti per 4 mesi, fino alla consegna.
Lo consiglio a tutti, senza esitazioni."

— Famiglia Benedetti | Tivoli · Ristrutturazione parziale
```

> ⚠️ *Nota per il cliente: sostituire con testimonianze reali. Se disponibili, aggiungere foto del cliente o dell'intervento.*

---

### Numeri — riga `bg-nero` testo bianco, 4 stat affiancate

| Numero | Label |
|---|---|
| **50+** | Progetti seguiti |
| **7** | Comuni serviti |
| **24h** | Risposta garantita |
| **100%** | Consulenze gratuite |

---

**🎬 Framer Motion:**
- Numeri: counter animation con `useInView`, interpolazione 0 → valore finale su 1.5s
- Card testimonianze: `staggerChildren: 0.18`, slide dal basso con leggero `y`
- Riga stat: `whileInView={{ opacity: 1 }}` con un solo `delay: 0.2`

---

---

## 7. CTA FINALE — FORM DI CONTATTO

> **Tag semantico:** `<section id="contatti">` — sfondo `bg-rosso` (o `bg-nero`)

---

### Titolo sezione — `<h2>` testo bianco
```
Raccontaci la Tua Casa.
È Gratis.
```

### Sottotitolo — testo bianco/opaco
```
Compila il form: ti ricontattiamo entro 24 ore per fissare
la consulenza. Nessun impegno. Solo ascolto.
```

---

### Campi Form

```
Nome *                    [input text]
Cognome *                 [input text]
Telefono *                [input tel]
Email *                   [input email]
Comune *                  [select: Roma · Ciampino · Frascati ·
                           Grottaferrata · Marino ·
                           Guidonia Montecelio · Tivoli]
Tipo di intervento *      [select: Ristrutturazione completa ·
                           Ristrutturazione parziale ·
                           Rifacimento bagno · Altro]
Descrizione progetto      [textarea — opzionale]
                          placeholder: "Raccontaci il tuo progetto..."
Privacy *                 [checkbox] Accetto la Privacy Policy
                          e il trattamento dei dati personali
```

---

### Bottone submit — `bg-giallo` testo nero bold, full-width su mobile
```
🚀  Richiedi Consulenza Gratuita
```

### Micro-copy sotto bottone — testo bianco piccolo, centrato
```
🔒  I tuoi dati sono al sicuro.
Non riceverai spam, solo una chiamata dal nostro team.
```

### Alternativa WhatsApp — link testuale o bottone ghost
```
Preferisci scrivere su WhatsApp? →
```
Link: `https://wa.me/393516446119`

---

### Messaggio di conferma (post-submit) — da mostrare in-page
```
✅ Richiesta inviata con successo!
Ti ricontattiamo entro 24 ore lavorative.
Nel frattempo, puoi scriverci su WhatsApp.
```

---

**🎬 Framer Motion:**
- Titolo + form: entrata coordinata con `staggerChildren: 0.1`
- Bottone submit: `whileHover={{ scale: 1.03 }}` + `whileTap={{ scale: 0.97 }}`
- Messaggio confirm: `AnimatePresence` con `initial={{ opacity: 0, y: 20 }}` → `animate={{ opacity: 1, y: 0 }}`
- Input focus: ring `bg-giallo` con transizione CSS 150ms

---

---

## 8. FOOTER

> **Tag semantico:** `<footer>` — sfondo `bg-nero` testo bianco/grigio

---

### Logo + Claim
```
[Logo ArchiPop]
Il tuo partner per ristrutturazioni smart a Roma e dintorni.
Chiarezza, trasparenza e servizi su misura.
```

### Colonna Servizi
```
Servizi
—
Consulenza gratuita
Pratiche Edilizie
Coordinamento lavori
Preventivi Gratuiti
Convenzioni forniture
```

### Colonna Comuni serviti
```
Comuni serviti
—
Roma
Ciampino · Frascati
Grottaferrata · Marino
Guidonia Montecelio
Tivoli
```

### Colonna Contatti
```
Contatti
—
📧  info@archipop.it
📞  +39 06 513 7687
🏢  Viale della Primavera, 103 — 00172 Roma
🕒  Lun–Ven · 9:00–18:00
```

### Bottom bar — separata, testo grigio piccolo
```
© 2025 ArchiPop S.r.l. — P.IVA: IT18189391008
Privacy Policy  ·  Cookie Policy  ·  Termini e Condizioni
```

---

---

## 📱 STICKY CTA MOBILE

**Visibile solo su mobile (`< 768px`), fixed bottom, full-width:**
```
🚀  Consulenza Gratuita — È Gratis
```
`bg-rosso` testo bianco, `z-index: 50`

**🎬 Framer Motion:** `initial={{ y: 100 }}` → `animate={{ y: 0 }}` dopo 2s dal mount

---

## 💬 WHATSAPP FLOATING BUTTON

**Fixed bottom-right, su tutti i breakpoint:**
```
Icona WhatsApp — bg-verde #25D366
aria-label="Scrivici su WhatsApp"
```
Tooltip on hover:
```
"Ciao! Vuoi una consulenza gratuita?"
```

---

## ♿ NOTE ACCESSIBILITÀ (WCAG 2.1)

- Tutti i bottoni CTA hanno `aria-label` esplicito
- Input form con `<label>` associato tramite `htmlFor` / `id`
- Contrasto testo: ratio ≥ 4.5:1 per body, ≥ 3:1 per headings large
- `alt` descrittivi su tutte le immagini dei progetti
- Skip link `"Vai al contenuto principale"` nascosto, visibile on focus
- Ordine di tabulazione logico (navbar → hero CTA → sezioni → form → footer)
- Animazioni Framer Motion con `prefers-reduced-motion` check:
  ```js
  const prefersReduced = window.matchMedia('(prefers-reduced-motion: reduce)').matches
  ```

---

*Fine Documentation.md — ArchiPop Landing Page*
