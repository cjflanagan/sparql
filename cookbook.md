# Sparql Queries Cookbook

## Countries in EU with their associated heads of states of info about them
```sql
SELECT 
  ?country
  ?countryLabel
  ?capitalLabel
  ?populationcountry
  ?populationcapital
  ?headofstate
  ?headofstateLabel
  ?headofstate_sexLabel
WHERE 
{
  ?country wdt:P463 wd:Q458.
  # country # member of # EU
  ?country wdt:P36 ?capital.
  ?country wdt:P1082 ?populationcountry.
  ?capital wdt:P1082 ?populationcapital.
  ?country wdt:P6 ?headofstate.
  ?head wdt:P21 ?headofstate_sex.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "   [AUTO_LANGUAGE],en". }
}
```
