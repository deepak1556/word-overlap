#word-overlap

[![NPM version](https://badge.fury.io/js/word-overlap.svg)](http://badge.fury.io/js/word-overlap) [![Build Status](https://travis-ci.org/sayanee/word-overlap.svg?branch=master)](https://travis-ci.org/sayanee/word-overlap) [![Coverage Status](https://img.shields.io/coveralls/sayanee/word-overlap.svg)](https://coveralls.io/r/sayanee/word-overlap) [![Dependency Status](https://gemnasium.com/sayanee/word-overlap.svg)](https://gemnasium.com/sayanee/word-overlap)

> Check the number of words overlapping between 2 phrases or sentences

Used in cases to check whether 2 titles / sentences / phrases are referring to the same context. E.g. 2 event names.


##Install

```js
npm install word-overlap
```

##Usage

```js
var overlap = require('word-overlap');

var sentence1 = 'A Hitchhiking Meetup in Betelgeuse by Ford Prefect';
var sentence2 = 'A hitchhiking meetup meetup by the hitchhiker';
```

###simple case

```js
overlap(sentence1, sentence2);
// [ 'A', 'by' ]
```

###option: ignore case

```js
overlap(sentence1, sentence2, {
   ignoreCase: true
});
// [ 'a', 'hitchhiking', 'meetup', 'by' ]
```

###option: min word length

```js
overlap(sentence1, sentence2, {
  ignoreCase: true,
  minWordLength: 2
});
// [ 'hitchhiking', 'meetup', 'by' ]
```

###option: ignore default common words

Common words by default include: *a, an, the, this, that, there, it, in, on, for, not, your, you, at,
to, is, us, out, by, I*

```js
overlap(sentence1, sentence2, {
  ignoreCase: true,
  minWordLength: 2,
  ignoreCommonWords: true
});
// [ 'hitchhiking' ]
```

###option: add your common words to ignore

```js
overlap(sentence1, sentence2, {
  ignoreCase: true,
  minWordLength: 2,
  ignoreCommonWords: true,
  common: [ 'meetup' ]
});
// [ 'hitchhiking' ]
```

Try out the examples in file `example.js` with the command `node example.js`

##Contribute

Please see [`CONTRIBUTING.md`](CONTRIBUTING.md) for details.

##Versioning

This repository follows the [Semantic Versioning](http://semver.org/) guidelines:

1. For **patches**, run `grunt bump`
- For **minor release**, run `grunt bump:minor`
- For **major release**, run `grunt bump:major`

##License

(C) Sayanee Basu 2014, released under an MIT license
