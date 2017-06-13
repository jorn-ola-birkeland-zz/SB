### Komme i gang med skatteberegning 

POST følgende innhold til ```http://skatteberegning.app.skatteetaten.no/2017``` med ```Content-Type=application/json``:

```
{
    "skatteplikt":
    {
        "alder":35,
        "skattekommune":"0301"
    },
    "skattegrunnlag":
    [
        {"fastloenn":{"beloep":456000}},
        {"likningsverdiPrimaerbolig":{"beloep":1356000}},
        {"likningsverdiFritidsbolig":{"beloep":1356000,"kommunenummer":"1403"}},
        {"innskuddBank":{"beloep":61456}},
        {"laanBank":{"beloep":1890431}},
        {"opptjenteRenter":{"beloep":655}},
        {"reiseHjemArbeid":{"km":68,"antall":213}}
    ]
}
```

Følgende er et utdrag av svaret:

```
[
    ...
    {"inntektsskattKommune":[{"beloep":13134,"kommunenummer":"0301","grunnlag":{"beloep":381000}}}],
    {"inntektsskattFylke":[{"beloep":7654,"kommunenummer":"0301","grunnlag":{"beloep":381000}}}],
    {"fellesskatt":{"beloep":6544}},
    {"trinnskatt":{"beloep":1356000}},
    {"formueskattKommune":[{"beloep":0,"kommunenummer":"0301","grunnlag":{"beloep":0}}}],
    {"reisefradrag",{"beloep",4344}},
    ...
]

```

### Oversikt over input

#### Skattegrunnlag

Følgende er de mest brukte skatteobjektene:

| Skatteobjekt        | Eksempel           | Beskrivelse  |
| -------------|---------|----------|
| fastLoenn     | ```{"fastloenn":{"beloep":456000}}``` |Årlig, ordinær fastlønnsinntekt utbetalt av arbeidsgiver |
| likningsverdiPrimaerbolig     | ```{"likningsverdiPrimaerbolig":{"beloep":1234333}}``` | Likningsverdi av bolig benyttet til opphold  |
| [innskuddBank](innskuddBank.md)     | ```{"innskuddBank":{"beloep":61456}}``` | Verdi av innskudd i bank |
| reiseHjemArbeid     | ```{"reiseHjemArbeid":{"km":68,"antall":213}}``` | Lengde på reisevei tur-retur mellom hjem og arbeid i antall km og antall dager |

Se [Alfabetisk liste over alle skatteobjekter](https://www.google.com)

Se [Liste over alle skatteobjekter sortert etter brukshyppighet](https://www.google.com)

Se skatteobjekter gruppert etter tema:

* [Arbeidsinntekter og inntektsfradrag](https://www.google.com)
* [Formue og gjeld](https://www.google.com)
* [Næringsinntekter](https://www.google.com)
* [Fradrag](https://www.google.com)
* [Familie og barn](https://www.google.com)

#### Skatteplikt



|         | Eksempel           | Beskrivelse  |
| -------------|---------|----------|
| alder     | ```"alder":35``` | Alder i inntektsår |
| skattekommune     | ```"skattekommune":"0301"``` | Hjemstestedkommune |
| type     | ```"type":"global"``` | Type skattepliktig tilknytning til Norge; ```global``` (standard) eller ```begrenset``` |
| tolvdelerArbeidsoppholdINorge     | ```"tolvdelerArbeidsoppholdINorge":"12"``` | Antall 12-deler arbeidsopphold i Norge (12 er standard) |
| skattemessigeRelasjoner     | ```"skattemessigRelasjoner":[{"ektefelle":"754545645"}]``` | Liste av skattemessigefamiliemedlemmer |
| saerskilteSkatteplikter     | ```"saerskilteSkatteplikter":[{"utenrikstjenestemann":12}]``` | Lengde på reisevei tur-retur mellom hjem og arbeid i antall km og antall dager |

Se [Komplett oversikt over egenskaper i skatteplikten](https://www.google.com)

### Oversikt over beregningsresultatet
