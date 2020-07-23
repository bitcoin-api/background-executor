# background-executor

[![npm version](https://badge.fury.io/js/background-executor.svg)](https://badge.fury.io/js/background-executor)

NodeJS Background Executor Function


## About

Execute asynchronous operations in sequence in the background


## Example

When you code starts up:

```.js

const backgroundExecutor = require( 'background-executor' );


backgroundExecutor.start();
```


When you want to add an operation to the background execution queue:

```.js
const backgroundExecutor = require( 'background-executor' );


backgroundExecutor.addOperation({

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