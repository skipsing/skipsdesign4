# Platebuling 

<p style="text-align:center;">
    ✍️ Lars Erik Nygård  <a href="mailto:lars.e.nygard@ntnu.no">📧</a> 27.02.2024 📅 
</p>

## Bakgrunn

Skipskrog er bygd opp av slanke *skallkonstruksjoner* som ofte viser seg å være kritiske for stabilitet og platebuling. Kunnskap om buleteori og kjennskap til hensiktsmessige designgrep for å unngå buling er viktige ferdigheter for skipsingenører. 

## Teori 

Vi har fra tidligere sett at kritisk *knekklast* på en aksialt trykkbelastet bjelke er definert som: 

$$ P_{kr}= \frac{\pi^2 \times E \times I }{L^2} $$

Vi skal nå se på tilsvarende knekkingsfenomen for et platefelt. Ut fra skipets *topologi* så vil størrelsen på et uavstivet platefelt være bestemt av spanteavstanden ($s$), og webrammeavstanden ($l$). 


```{figure} https://cdn.jsdelivr.net/gh/skipsing/skipsdesign4/knekking-buling/images/platefelt-del-av-skip.PNG
---
scale: 50 %
align: center
--- 
Uavstivet platefelt som del av en større skrogkonstruksjon
```
### Platestripe som ekvivalent bjelke 
I platefeltet over så tar vi ut en liten platestripe med bredde $b$ (markert i rødt over). Platestripen betrakter vi som en søyle og anvender knekklastformelen for som for bjelker $P_{kr}$:

$$ P_{kr} = \frac{\pi^2 \times E \times (\frac{b \times t^3}{12}) }{s^2} $$

Annet arealmoment for det sammensatte bjelkesnittet ($I$) er her erstattet med annet arealmoment for en rektangulær plate $(\frac{b \times t^3}{12})$ der høyde er $b$ og tykkelse er $t$. Videre er lengden $L$ erstattet med $s$, 
se figur under. <br>  


```{figure} https://cdn.jsdelivr.net/gh/skipsing/skipsdesign4/knekking-buling/images/platestripe-ekvivalent-bjelke.PNG
---
scale: 50 %
align: center
--- 
Platestripe med bredde *b* som ekvivalent bjelke
```
### Eulerspenning 

Eulerspenningen beregnes videre som knekklast delt på areal: 

$$ \sigma_{Euler} = \frac{P_{Kr}}{A} = \frac{\pi^2 \times E \times (\frac{b \times t^3}{12}) }{(b \times t) \times s^2} $$

$$ \downarrow $$

$$ \sigma_{Euler} = \frac{\pi^2 \times E}{12} \times (\frac{t}{s})^2 $$

For tilfellene der platen er opplagret langs kantene (som den ofte er) så korrigeres det på samme måte som for bjelker med effektive knekklengder, men her inkluderes også spenningsvariasjon over platefeltet. 

$$ \frac{ C }{1-\nu^2 } $$

Der $C$ er en koeffisient som sier noe om platefeltets aspektforhold og spenningsbilde. 

Denne er ofte også benevnt *bulekoeffisienten*. $\nu$ er [*Poisson's ratio*](https://en.wikipedia.org/wiki/Poisson%27s_ratio), eller også kalt *tverrkontrakssjonstallet*. For stål er $\nu = 0.3 $.

Vi står da igjen med følgende uttrykk for Eulerspenning $ \sigma_{Euler} $ i et uavstivet platefelt:
<br>
<br>

$$ \sigma_{Euler} = \frac{ C }{1-\nu^2 } \times \frac{\pi^2 \times E}{12} \times (\frac{t}{s})^2 $$

<br>
<br>
### Johnson-Ostenfeld korreksjon 

Der slankhetsforholdet (lengde over stivhet) blir svært høyt er man nødt til å introdusere "Johnson-Ostenfelds korreksjonsfaktor". I figur under ser en at denne korreksjonsfaktoren interpolerer mellom flytspenningen og Eulerspenningen. 

```{figure} https://cdn.jsdelivr.net/gh/skipsing/skipsdesign4/knekking-buling/images/johnson-ostenfeld-korreksjon.PNG
---
scale: 50 %
align: center
--- 
Johnson-Ostenfeld korreksjon for høye *slankhetsforhold*
```

En ser fra figur over at denne korreksjonen inntreffer **kun** om $\sigma_{Euler} > 0.5\times \sigma_{flyt}
$. 

Det gir følgende korreksjon:

$$ \sigma_{kr} = \sigma_{Euler}  \textrm{  når  } \sigma_{Euler} \le  \frac{\sigma_{flyt}}{2}   $$
<br>

$$ \sigma_{kr} = \sigma_{flyt} \times (1-\frac{\sigma_{flyt}}{4 \times\sigma_{Euler} })  \textrm{  når  } \sigma_{Euler} \ge  \frac{\sigma_{flyt}}{2}   $$

```{admonition} Prosedyre for bulekontroll av uavstivet platefelt 
:class: tip

- Identifiser bulekoeffienttilfelle basert på topologi og spenningsretning
- Beregn spenningsvariasjonen $\psi$.  
- Beregn tilhørende bulekoeffisient $C$. 
- Beregn $\sigma_{Euler}$ gitt aspektforhold ($\frac{t}{s}$) og materialparameterene ( $E$ og $\nu$ ) 
- korriger (eventuelt) $\sigma_{kr}$ for Johnson Ostenfeld korreksjonsfaktoren
- platen vil ikke bule om $\sigma_{kr} \ge \sigma_{max}$ 

```
Vi benytter anledningen til å vise et regneeksempel der prosedyren over er brukt. 

```{admonition} Regneeksempel 
:class: note

Vi skal kontrollere platefeltet som skissert under for buling. Platefeltet er belastet med en varierende trykkspenning langs kortsiden. 

```{figure} https://cdn.jsdelivr.net/gh/skipsing/skipsdesign4/knekking-buling/images/eksempel-platebuling.PNG
---
scale: 50 %
align: center
--- 
uavstivet platefelt utsatt for lineært varierende trykkspenning langs kortsiden 

```
Videre er følgende opplysinger gitt: 

$$ E_{modul} = 210 000 \frac{N}{mm^2} $$

$$ \sigma_{flyt} = 235 \frac{N}{mm^2} $$

#### Løsningsforslag ####

En ser her at  $\sigma_{2} = 0\frac{N}{mm^2}$, og $\psi$ blir dermed også $0$.  

$$ \downarrow $$

Dette er et tilfelle a), og som gir bulekoeffisient: 

$$ C = \frac{8.4}{0 + 1.1} = 7.63 $$


Beregner videre Eulerspenningen; 

$$ \sigma_{Euler} = \frac{ 7.63 }{1-0.3^2 } \times \frac{\pi^2 \times 210 000\frac{N}{mm^2}}{12} \times (\frac{8mm}{600mm})^2 = 257.4\frac{N}{mm^2} $$

En ser her at $\sigma_{Euler} > 0.5\times \sigma_{flyt}$ og må derfor korrigere for Johnson Ostenfeld effekten:
<br>
<br>

$$ \sigma_{kr} = 235\frac{N}{mm^2} \times (1-\frac{235\frac{N}{mm^2}}{4 \times 257.4\frac{N}{mm^2} })=234.7\frac{N}{mm^2} $$

$$ \downarrow $$

Kontroll opp mot opptredende spenning: $ \sigma_{kr} \ge \sigma_{max} $ ->  :+1: !!

```
