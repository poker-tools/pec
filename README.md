# pec [![build status](https://secure.travis-ci.org/thlorenz/pec.png)](http://travis-ci.org/thlorenz/pec)

Poker equity calculator. Compares two combos or one combo against a range to compute winning equity.

```js
const { raceRange, rates } = require('../')

const combo = [ 'Jh', 'Js' ]
const range = [
  [ 'Kh', 'Ks' ], [ 'Kh', 'Kd' ], [ 'Kh', 'Kc' ],
  [ 'Ks', 'Kd' ], [ 'Ks', 'Kc' ], [ 'Kd', 'Kc' ],
  [ 'Qh', 'Qs' ], [ 'Qh', 'Qd' ], [ 'Qh', 'Qc' ],
  [ 'Qs', 'Qd' ], [ 'Qs', 'Qc' ], [ 'Qd', 'Qc' ]
]

const { win, loose, tie } = raceRange(combo, range, 1E4)
const { winRate, looseRate, tieRate } = rates({ win, loose, tie })

console.log('JJ performs as follows vs. [ KK, QQ ]')
console.log('win: %d%% (%d times)', winRate, win)
console.log('loose: %d%% (%d times)', looseRate, loose)
console.log('tie: %d%% (%d times)', tieRate, tie)
```

```
JJ performs as follows vs. [ KK, QQ ]
win: 17.87% (21537 times)
loose: 81.68% (98463 times)
tie: 0.45% (542 times)
```

For more examples see the [tests](test/pec.single.js) and the [webworker example](examples/webworker.js).

You can launch the web worker via `npm install && npm run demo`.

## Installation

    npm install pec

## [API](https://thlorenz.github.io/pec)


## License

MIT
