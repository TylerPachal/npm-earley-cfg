# earley-cfg
An npm module containing an implementation of the a Context Free Grammar (CFG) using the Earley algorithm.
This is my take on [this](https://www.npmjs.com/package/earley-node) NPM module, with changes to suit my needs.

## Example

```javascript
var earley = require('earley-cfg');

var grammar = new earley.Grammar('grammar.cfg');
var parser = new earley.Parser(grammar);

var sentence = new earley.Sentence.SentenceFromString('time/time<N> flies/fly<N>/fly<V> like/like<V>/like<P> an/a<D> arrow/arrow<N>');

var result = parser.parse(sentence);

if(result.valid === true){
    console.log('Valid');
    var trees = new earley.ParseTrees(result);
    console.log(trees.toString());
}
else{
    console.log('Invalid');
}
```

## Download

Install using Node Package Manager (`npm`):

    npm install earley-cfg
