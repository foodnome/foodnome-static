# Foodnome Static

👋 Hello! This is where we are keeping the static `JSON` files for the press page of the website.

Each press item has a `date` (as ISOString), `title`, `summary`, `source`, `sourceLogo`, `url`, and `imageUrl`.

```json
{
  "date": "2019-07-24T07:00:00.000Z",
  "title": "The only place to get a home-cooked meal you didn’t cook is in Riverside County",
  "summary": "Meghan McConaghy Chane made her debut as a chef sporting a Boston Celtics T-shirt rather than a chef’s coat, sautéing spinach in a cast iron skillet. But she’s the first of what could be a new kind of chef, one with...",
  "source": "Press Enterprise",
  "sourceLogo": "",
  "url": "https://www.pe.com/2019/07/24/how-to-get-a-home-cooked-meal-you-didnt-cook/?fbclid=IwAR0dS4FMGNfqA9oIPHC8f6pYuhpqPWUgixYNl0r4PmiuwlpPTIIxkNhnZ3E",
  "imageUrl": ""
}
```

I have been using this short helper function to quickly generate the `summary` which has a max charater count of `214` (excluding the ellipsis at the end.

```javascript
function getSummary(text) {
  return (
    text
      .replace(/\r?\n|\r/g, "")
      .slice(0, 214)
      .trim() + "..."
  );
}
```

You can see the raw JSON file [here](https://raw.githubusercontent.com/foodnome/foodnome-static/master/press.json).
