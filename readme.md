# Ecolan Calendar Data

Dati dei calendari di Ecolan per l'anno 2021 estratti dall'app ufficiale per Android.

## Esempio Sensore Home Assistant

```yaml
platform: rest
name: Garbage Calendar Mozzagrogna
resource: https://raw.githubusercontent.com/eliseomartelli/Calendari-Ecolan/master/calendars/MOZZAGROGNA.json
value_template: >
  {% set tomorrow = value_json.days[now().strftime('%j') | int].garbage %}
  {% if tomorrow | length > 0 %}
    {{ tomorrow[0] }}
  {% else %}
    NOTHING
  {% endif %}
```
