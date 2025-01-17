[![CodacyBadge](https://api.codacy.com/project/badge/grade/82cc8ebd98b64ed199d7be6021488062)](https://www.codacy.com/app/spencerkelly86/nlp_compromise)
[![npm version](https://badge.fury.io/js/nlp_compromise.svg)](https://www.npmjs.com/package/nlp_compromise)
[![downloads](https://img.shields.io/npm/dm/nlp_compromise.svg)](https://www.npmjs.com/package/nlp_compromise)

**nlp_compromise** does NLP in the browser.
```javascript
nlp.text('She sells seashells').to_past()
// She sold seashells
```
### Yup,
* **100k** js file
* **86%** on the [Penn treebank](http://www.cis.upenn.edu/~treebank/)
* keypress speed, constant-time.
* caniuse, uhuh. **IE9+**
* no dependencies, training, configuration, or prolog.

It's a [handy, and not overly-fancy](https://github.com/nlp-compromise/nlp_compromise/blob/master/docs/justification.md) tool for understanding, changing, and playing with english.

## Off you go,
> `npm install nlp_compromise`

> `<script src="https://npmcdn.com/nlp_compromise@latest/builds/nlp_compromise.min.js"></script>`

```javascript
let nlp = require("nlp_compromise"); // or nlp = window.nlp_compromise

nlp.noun("dinosaur").pluralize();
// "dinosaurs"

nlp.verb("speak").conjugate();
// { past: 'spoke',
//   infinitive: 'speak',
//   gerund: 'speaking',
//   actor: 'speaker',
//   present: 'speaks',
//   future: 'will speak',
//   perfect: 'have spoken',
//   pluperfect: 'had spoken',
//   future_perfect: 'will have spoken'
// }

nlp.text('She sells seashells').negate()
// She didn't sell seashells

nlp.sentence('I fed the dog').replace('the [Noun]', 'the cat')
// I fed the cat

nlp.text("Tony Hawk did a kickflip").people();
// "Tony Hawk"

nlp.person("Tony Hawk").article();
// "he"

nlp.value("five hundred and sixty").number;
// 560

```
#Plugin/Mixins
we've also got a modest, though ambitious [plugin ecosystem](https://github.com/nlp-compromise/nlp_compromise/blob/master/docs/plugins.md):
```javascript
//US-UK localization
nlp.plugin(require("nlp-locale"))
nlp.term("favourite").toAmerican()
// favorite

//syllable hyphenization
nlp.plugin(require("nlp-syllables"));
var t2 = nlp.term('houston texas');
t2.syllables()
//[ [ 'hous', 'ton' ], [ 'tex', 'as' ] ]

//semantic n-gram
nlp.plugin(require("nlp-ngram"));
var t4 = nlp.text(`Tony Hawk played Tony Hawk's pro skater`);
t4.ngram({min_count: 2});
// [{word:'tony hawk', count:2, size:1}]
```

### [View the Full API Documentation](https://github.com/nlp-compromise/nlp_compromise/blob/master/docs/api.md)

## Development
[![Issue Stats](http://issuestats.com/github/nlp-compromise/nlp_compromise/badge/pr)](http://issuestats.com/github/nlp-compromise/nlp_compromise)
[![Issue Stats](http://issuestats.com/github/nlp-compromise/nlp_compromise/badge/issue)](http://issuestats.com/github/nlp-compromise/nlp_compromise)

*Useful NLP is a problem only solved with many hands. [Contributing](https://github.com/nlp-compromise/nlp_compromise/blob/master/contributing.md) in any form is valued.*

Join our [slack group](https://superscriptjs.slack.com/messages/nlp_compromise/) or our infrequent [announcement email-list](http://eepurl.com/bL9YRv).

Or just pickup an [open issue](https://github.com/nlp-compromise/nlp_compromise/issues)

[We're moving fast](https://github.com/nlp-compromise/nlp_compromise/blob/master/docs/changelog.md)

[![MIT license](http://img.shields.io/badge/license-MIT-brightgreen.svg)](http://opensource.org/licenses/MIT)

