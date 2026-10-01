# Poziv

Jednostrana stranica — poziv na dejt. Bez okvira, bez koraka za građenje,
bez servera. Jedan fajl: `index.html`.

## Kako radi

1. **Pitanje** — dugme *Da* raste sa svakim klikom na *Možda*, a *Možda* beži
   na nasumično mesto i menja tekst kroz osam koraka.
2. **Planiranje** — kalendar (prošli dani zaključani), termini 10–21 h,
   aktivnosti sa višestrukim izborom.
3. **Karta** — perforisana ulaznica sa danom, vremenom i planom. Vreme dolaska
   se računa samo, petnaest minuta pre termina. Uz konfete.

Uz to, na prvom ekranu lebde **tri poklončića**. Otvara se samo jedan — ostali
nestanu, a telefon zapamti da je iskorišćen. Poklon vodi na zasebnu karticu sa
nagradom, mestom i terminom koje si ti unapred odredio.

Odgovor se šalje na mejl automatski, čim pritisne *Potvrdi*. Dugme
*Pošalji Bojanu* ostaje kao rezerva ako slanje ne prođe.

## Podešavanje poklona

U `index.html`, pri vrhu skripte:

```js
var POKLON = {
  VERZIJA: "1",          // promeni da se poklončići vrate svima
  nagrada: "BATTLESHIP",
  tajna:   "Ne pitaj šta je. Niko ti neće reći.",
  mesto:   "Kod mene",
  kad:     "subota u 19:00",
  dole:    "Dođi gladna i spremna da gubiš. ❤️"
};
```

Telefon pamti da je poklon otvoren, i to pamćenje je vezano za `VERZIJA`.
Dovoljno je promeniti tu oznaku i objaviti — poklončići se vraćaju.

## Podešavanje mejla

U `index.html`, pri vrhu skripte:

```js
var MEJL = "";
```

Upiši adresu forme (npr. sa `formspree.io`) i mejl stiže sam. Dok je prazno,
stranica radi normalno — samo se odgovor ne šalje, pa ostaje dugme za poruku.

Ta adresa je javna po prirodi i ne može se zloupotrebiti osim za slanje forme,
pa sme da stoji u kodu.

## Objavljivanje

Bilo koji statički hosting, bez podešavanja:

| Gde | Repozitorijum | Napomena |
|---|---|---|
| GitHub Pages | mora **javan** (besplatni plan) | Settings → Pages → grana `main` |
| Netlify | može **privatan** | povežeš repo, bez build komande |
| Cloudflare Pages | može **privatan** | isto |

Nema koraka za građenje — objavljuje se koren repozitorijuma.

## Izmene

Sve je u `index.html`: boje u `:root`, termini u `TERMINI`,
aktivnosti u `AKTIVNOSTI`, tekstovi begajućeg dugmeta u `MOZDA`.
