***Komme i gang med skatteberegning***

POST følgende innhold til ```http://skatteberegning.app.skatteetaten.no/2017```:

```
{
    "skatteplikt":
    {
        "alder":35,
        "skattekommune":"0301"
    },
    "skattegrunnlag":
    [
        {"fastloenn":{"kr":456000}},
        {"likningsverdiPrimaerbolig":{"kr":1356000}},
        {"likningsverdiFritidsbolig":{"kr":1356000,"kommunenummer":"1403"}},
        {"innskuddBank":{"kr":61456}},
        {"laanBank":{"kr":1890431}},
        {"opptjenteRenter":{"kr":655}},
        {"reiseHjemArbeid":{"km":68,"antall":213}}
    ]
}
```

Følgende er et utdrag av svaret:

```
[
    ...
    {"inntektsskattKommune":[{"kr":13134,"kommunenummer":"0301","grunnlag":{"kr":381000}}}],
    {"inntektsskattFylke":[{"kr":7654,"kommunenummer":"0301","grunnlag":{"kr":381000}}}],
    {"fellesskatt":{"kr":6544}},
    {"trinnskatt":{"kr":1356000}},
    {"formueskattKommune":[{"kr":0,"kommunenummer":"0301","grunnlag":{"kr":0}}}],
    {"reisefradrag",{"kr",4344}},
    ...
]

```

Følgende er de mest brukte skatteobjektene

| Skatteobjekt        | Eksempel           | Beskrivelse  |
| ------------- |-------------| -----|
| fastLoenn     | ```{"fastloenn":{"kr":456000}}``` |Årlig, ordinær fastlønnsinntekt utbetalt av arbeidsgiver |
| likningsverdiPrimaerbolig     | ```{"likningsverdiPrimaerbolig":{"kr":1234333}}``` |Likningsverdi av bolig benyttet til opphold  |


