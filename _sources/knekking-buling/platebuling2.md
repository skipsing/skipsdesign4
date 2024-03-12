# Platebuling forts

<p style="text-align:center;">
    ✍️ Lars Erik Nygård  <a href="mailto:lars.e.nygard@ntnu.no">📧</a> 10.03.2024 📅 
</p>

## Korrektive tiltak ved buling 

Vi har bulespenningsformelen gitt ved: 

$$ \sigma_{Euler} = \frac{ C }{1-\nu^2 } \times \frac{\pi^2 \times E}{12} \times (\frac{t}{s})^2$$

Vi deler denne formelen gjerne i 3 deler: 

### Bulekoeffisienten C  ###

Bulekoeffisienten bestemmes på bakgrunn av stiverretning og spenningsfordeling over platefeltet.

<a href="https://cdn.jsdelivr.net/gh/skipsing/skipsdesign4/ressurser/bulekoeffisienter.pdf" download>Last ned bulekoeffisientark</a>

I figur under er bulekoeffisienten plottet for spenningsretning parallelt med stiverretningen og der $ \psi $ varierer mellom -1 og 1. 

```{figure} https://cdn.jsdelivr.net/gh/skipsing/skipsdesign4/knekking-buling/images/bulekoeffisient_lang_plot.PNG
---
scale: 50 %
align: center
--- 
Bulekoeffisient for spenning parallelt med stiverretningen. Ved jevnt trykk er minste verdi 4. 
```

<a href="https://cdn.jsdelivr.net/gh/skipsing/skipsdesign4/ressurser/bulekoeffisient.ipynb" download>Plottet er generert i en Jupyter Notebook (nedlastingslink) </a>

Videre følger i figur under bulekoeffisienten plottet for spenningsretning på tverrs av stiverretningen og der $ \psi $ varierer mellom -1 og 1. 

```{figure} https://cdn.jsdelivr.net/gh/skipsing/skipsdesign4/knekking-buling/images/bulekoeffisient_tver_plot.PNG
---
scale: 50 %
align: center
--- 
Bulekoeffisient for spenning på tvers av stiverretningen. Ved jevnt trykk er minste verdi ned mot 1.25. 
```

Ved å sammenligne tilfellene over for jevnt trykk ser en at C vil kunne økes fra typisk 1.25 til 4 ved å snu avstivningsretningen! (Ufordelaktig å ha trykkspenning langs langsiden) 
Dette er ganske vanlig på skipskonstruksjoner å da la avstivningsretningen være langskips på grunn av trykkspenningene fra de globale momentene.     

 ### Materialkonstantenten  ###

$$ \frac{\pi^2 \times E}{ ({1-\nu^2) } \times 12} $$ 
 
For stål 189800, og kun avhengig av E-modul. Ingen betydning i flytspenningen. 

 ### Slankheten  ###
 
 $$ (\frac{t}{s})^2 $$
 
 Avhengig av platetykkelsen og korteste avstand til avstivningselementer.
 - En økning i platetykkelse vil som regel være meget vektintensivt, i forhold til å minske stiveravstanden s. 
 - Det motsatte gjelder når produksjonsvennlighet er ønskelig. 
 
### Introdusere *bulestivere*

I noen tilfeller kan det være slik at avstivningsretningen blir styrt av andre designparametere. 
En kan da introdusere et ekstra sett med stivere, kalt *bulestivere*. Dette er avstivningselementer som har en eneste funksjon og det er å dele platefeltet inn i mindre deler. Merk at siden den er opplagret i primærstiverne vil den ikke bidra *styrkemessig*. 

```{figure} https://cdn.jsdelivr.net/gh/skipsing/skipsdesign4/knekking-buling/images/bulestiver_tegning.PNG
---
scale: 50 %
align: center
--- 
Horisontal bulestiver midt på platefeltet på et vertikalavstivet skott. 
```

Det kan tilogmed lønne seg å introdusere flere rader med bulestivere. Under ser man et skjermbilde av en 3d modell der 2 rader er vist. 

```{figure} https://cdn.jsdelivr.net/gh/skipsing/skipsdesign4/knekking-buling/images/bulestiver_modell.PNG
---
scale: 50 %
align: center
--- 
Dobbel rad med bulestivere på et vertikalavstivet skott. 
```

## Øvinger

I link under finner du noen øvingsoppgaver som ser på vektkonsekvens av ulike avstivninger 

<a href="https://cdn.jsdelivr.net/gh/skipsing/skipsdesign4/knekking-buling/platebuling-oppgaver2.ipynb" download>Last ned Jupyter Notebook med øvingsoppgaver</a>

