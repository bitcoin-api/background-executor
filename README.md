# bqe

[![npm version](https://badge.fury.io/js/bqe.svg)](https://badge.fury.io/js/bqe)

bqe - Background Queue Executor


## About

Execute asynchronous operations in sequence in the background


## Example

When you code starts up:

```.js
'use strict';

const bqe = require( 'bqe' );


bqe.start();
```


When you want to add an operation to the background execution queue:

```.js
'use strict';

const bqe = require( 'bqe' );


bqe.addOperation({

    operation: async () => {

        await new Promise( resolve => {

            setTimeout( () => {

                console.log( 'operation in background log' );

                resolve();

            }, 1000 );
        });
    }
});
```