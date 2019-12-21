# Foodnome Static

## Warning ⚠️
**Any changes to `press.json` will pushed to production!**

---

👋 Hello! This is where we are keeping the static `JSON` files for the press page of the website.

Each press item has a `id`, `featured`, `date` (as ISOString), `title`, `summary`, `source`, `sourceLogo`, `url`, and `imageUrl`.

```json
{
  "id": 1,
  "featured": true,
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

~~Important to Note: Please add the press items in reverse chronological order (newest at the front, oldest at the back. This is important because the newest press item will be featured in the hero in the Press page.)~~ **I've added a `featured` property which indicates whether or not a press item is featured as the first article on the top of the press page however, please still keep the newest press items at the front of the `press` array.**

You can see the raw JSON file [here](https://raw.githubusercontent.com/foodnome/foodnome-static/master/press.json).
