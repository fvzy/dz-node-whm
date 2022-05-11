# dz-node-whm
WHM API 1 for NodeJS

This is a library that allows you to remotely control your web hosting server that is running cPanel.

This library is built for personal use. If you would like to use it and there is a missing feature, please submit an issue on the Github repo and I will do my best to add it ASAP.

To build this, run `tsc` at the root directory. Or install via npm `npm install dz-node-whm`

## Usage
### JavaScript
```javascript
var WHM = require('dz-node-whm');
var whmClient = new WHM.Client({
    serverUrl: 'https://myserver.com:2087',
    remoteAccessKey: 'remoteAccessKeyHere',
    username: 'resellerOrRootUser'
});

whmClient.createAccount({
    username: 'myuser',
    password: 'mySecurePassword!',
    plan: 'Pro',
    domain: 'clientdomain.com'
}).then(
    function(success){ 
        console.log(success);
        // do something with data
    },
    function(error) {
        console.error(error);
        // do something with data
    }
);

```

### Typescript
```typescript
import { Client, WHMOptions } from 'dz-node-whm';

const whmClientOptions: WHMOptions = {
   serverUrl: 'https://myserver.com:2087',
   remoteAccessKey: 'remoteAccessKeyHere',
   username: 'resellerOrRootUser'
};

const client: Client = new Client(whmClientOptions);

client.createAccount({
           username: 'myuser',
           password: 'mySecurePassword!',
           plan: 'Pro',
           domain: 'clientdomain.com'
       }).then(
           success => { 
               console.log(success);
               // do something with data
           },
           error => {
               console.error(error);
               // do something with data
           }
       );
```




## Methods

#### `createAccount(options: CreateAccountOptions): Promise<any>`

#### `terminateAccount(user: string): Promise<any>`

#### `listAccounts(): Promise<AccountData[]>`

#### `listIPAddresses(): Promise<any>`




## Interfaces _`TypeScript`_

#### `WHMOoptions`

#### `CreateAccountOptions`

#### `AccountData`