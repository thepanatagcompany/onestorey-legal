# onestorey-legal

The privacy notice and terms of use for **OneStorey**, by The Panatag Company,
published here because both app stores require the privacy notice at a public
URL: a reviewer and anybody deciding whether to install has to be able to read
it without installing anything first.

## Do not edit these files

They are **generated**, from `src/content/legal.ts` in the OneStorey repository,
which is the same module both apps render on screen. That is the whole point of
generating them: a hand-written copy here would become a second version of the
document, this one would be the legally operative one, and it would be the one
nobody remembers to update.

To change a word, change it in the app and republish:

```
cd onestorey
node dev/legal-html.mjs /path/to/onestorey-legal
git -C /path/to/onestorey-legal commit -am "Regenerate" && git -C ... push
```

Nothing checks that these pages are current. Each one carries a short hash of
the source file in an HTML comment near the top, so View Source on the live page
and compare it against the repository if you are not sure.

## Files

| | |
|---|---|
| `index.html` | both documents, linked |
| `privacy.html` | the privacy notice — this is the URL the stores want |
| `terms.html` | the terms of use |

No JavaScript and no external requests, deliberately. A page that needs a script
can fail for a crawler or for a reviewer on a bad connection, and a privacy
notice that fetches a font from Google while explaining what it does with your
data is not a page to put your name on.
