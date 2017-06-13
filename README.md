***Komme i gang med skatteberegning***

POST følgende innhold til ```http://skatteberegning.app.skatteetaten.no/2017```:

```
{
  "skatteplikt":
  {
    "alder":35,
    "skattekommunenummer":"0301"
  },
  "skattegrunnlag":
  [
    {"fastloenn":{"kr":456000}},
    {"likningsverdiPrimaerbolig":{"kr":1356000}},
    {"likningsverdiFritidsbolig":{"kr":1356000,"kommunenummer":"1403"}},
    {"innskuddBank":{"kr":61456}},
    {"laanBank":{"kr":1890431}},
    {"opptjenteRenter":{"kr":655}}
  ]
}
```
