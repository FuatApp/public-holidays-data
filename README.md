# public-holidays-data

Open public holiday data for 131 countries as static JSON and ICS files, with stable URLs, open CORS and no API key. Maintained by [ToolboxDay](https://toolboxday.com/en/developers/).

- Documentation and full list of countries and years: https://toolboxday.com/en/developers/
- Index of all available files: https://toolboxday.com/data/v1/holidays/index.json
- Format: JSON (`/data/v1/holidays/{country}/{year}.json`) and ICS (`/data/v1/holidays/{country}/{year}.ics`), country as lowercase ISO 3166-1 alpha-2 code
- ICS files contain the nationwide public holidays and can be subscribed to in Google Calendar, Outlook or Apple Calendar

This repository only describes the data. The files themselves are served from toolboxday.com.

## Example

```bash
curl -s https://toolboxday.com/data/v1/holidays/de/2027.json
```

```js
const res = await fetch("https://toolboxday.com/data/v1/holidays/de/2027.json");
const data = await res.json();
for (const h of data.holidays.filter((h) => h.nationwide)) {
  console.log(h.date, h.name);
}
```

## License and attribution

The compilation is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Please credit the source, for example:

> Holiday data: [ToolboxDay](https://toolboxday.com/)

For countries other than Germany the data is based on [python-holidays](https://github.com/vacanza/python-holidays) (MIT). Every JSON file lists its sources. No warranty; for legally binding purposes the official source prevails.

## Contact

Found an error or a missing country? See https://toolboxday.com/en/developers/.
