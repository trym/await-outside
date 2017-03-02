# `await-outside`
## A better Node REPL for asynchronous exploration

Thanks to https://github.com/princejwesley/Mancy for inspiration.

### From This

```
$ node
> const request = require('superagent')
undefined
> request.get('https://www.googleapis.com/books/v1/volumes').
... query({key: 'NOT_A_VALID_API_KEY'}).
... query({q: 'paul auster'}).
... then(r => r.body)
Promise { <pending> }
>
```

### To This

```
$ await-outside
> const request = require('superagent')
undefined
> await request.get('https://www.googleapis.com/books/v1/volumes').
... query({key: 'NOT_A_VALID_API_KEY'}).
... query({q: 'paul auster'}).
... then(r => r.body)
{ kind: 'books#volumes',
  totalItems: 2342,
  items: [ ... ] }
>
```
