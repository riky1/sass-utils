# Sass Utilities

Questo pacchetto contiene una serie di utility Sass progettate per semplificare lo sviluppo di progetti web. Attualmente, il pacchetto include moduli per la gestione della **tipografia** e delle **media query**.

## Struttura del pacchetto

### Typography
Il modulo `typography` fornisce strumenti per gestire stili tipografici in modo scalabile e personalizzabile. Include:

- **Font Variables**: Variabili per definire font-family, font-size, line-height, font-weight, e letter-spacing ([`_variables.scss`](assets/scss/typography/_variables.scss)).
- **Custom Properties**: Generazione di variabili CSS globali per la tipografia tramite il file [`_root.scss`](assets/scss/typography/_root.scss).
- **Font Faces**: Definizione dei font-face per il font "Kanchenjunga" ([`_fonts.scss`](assets/scss/typography/_fonts.scss)).
- **Headings**: Stili predefiniti per titoli `h1`, `h2`, `h3` ([`_headings.scss`](assets/scss/typography/_headings.scss)).
- **Text Utilities**: Classi utilitarie per dimensioni del testo come `.txt--sm`, `.txt--lg`, ecc. ([`_text.scss`](assets/scss/typography/_text.scss)).
- **Paragraphs**: Stili per paragrafi, inclusi line-height e spaziatura ([`_paragraph.scss`](assets/scss/typography/_paragraph.scss)).
- **Aggregazione**: Il file [`_index.scss`](assets/scss/typography/_index.scss) aggrega tutti i moduli tipografici per un facile utilizzo.

### Media Query
Il modulo `mediaquery` semplifica la gestione delle media query con mixin e variabili predefinite. Include:

- **Breakpoints**: Definizione di breakpoint comuni come `sm`, `md`, `lg`, ecc. ([`_breakpoints.scss`](assets/scss/mediaquery/_breakpoints.scss)).
- **Mixin Media Query**: Mixin per creare media query flessibili con supporto per `min-width` e `max-width` ([`_media-query.scss`](assets/scss/mediaquery/_media-query.scss)).

## Come utilizzare

1. Importa il file principale `main.scss` nel tuo progetto:
   ```scss
   @use './assets/scss/main.scss' as *;

2. Usa le utility disponibili, ad esempio:
- Per applicare stili tipografici:
h1 {
  font-family: var(--font-family-base);
  font-size: var(--font-size-4xl);
}

- Per utilizzare una media query:

@include media-query(md) {
  body {
    background-color: lightgray;
  }
}
