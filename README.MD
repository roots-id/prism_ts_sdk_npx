Ensure that you have Node.js (preferably the latest LTS version) installed on your computer. 

Create a new directory for your project and navigate to it using your terminal or command prompt.
```bash
mkdir simple-ts-project
cd simple-ts-project
```

TODO: Link to GitHub PAT instructions

Create .npmrc and add the following lines. Remember to put the PAT Token
```
@input-output-hk:registry=https://npm.pkg.github.com/
//npm.pkg.github.com/:_authToken=<token>
```

Run the following command to create a package.json file with default values.
```bash
npm init -y
```

Install TypeScript, ts-node (to run TypeScript directly), and the Atala Prism Wallet SDK.
```bash
npm install @input-output-hk/atala-prism-wallet-sdk
npm install ts-node 
npm install typescript 
```

Create a tsconfig.json file for TypeScript configuration.
```bash
npx tsc --init
```

---------------------
```json
{
  "compilerOptions": {
    /* Visit https://aka.ms/tsconfig to read more about this file */
    /* Language and Environment */
    "target": "es2016",                        /* Set the JavaScript language version for emitted JavaScript and include compatible library declarations. */
    /* Modules */
    "moduleResolution": "node",                /* Specify how TypeScript looks up a file from a given module specifier. */
    /* Emit */
    "outDir": "./dist",                        /* Specify an output folder for all emitted files. */
    /* Interop Constraints */
    "esModuleInterop": true,                   /* Emit additional JavaScript to ease support for importing CommonJS modules. This enables 'allowSyntheticDefaultImports' for type compatibility. */
    "forceConsistentCasingInFileNames": true,  /* Ensure that casing is correct in imports. */
    /* Type Checking */
    "strict": true,                            /* Enable all strict type-checking options. */
    "skipLibCheck": true                       /* Skip type checking all .d.ts files. */
  },
  "include": [
    "src/**/*"
  ],
  "exclude": [
    "node_modules",
    "**/*.spec.ts"
  ]
}

```

Create the src directory and the index.ts file containing your code:
```
mkdir src
touch src/index.ts
```
Update the index.ts file with your code:
```TS
import * as sdk from "@input-output-hk/atala-prism-wallet-sdk";

let test = new sdk.Apollo();
console.info(test.createRandomSeed());
```

Open the package.json file and add the following scripts in the "scripts" section:
```json
"scripts": {
  "build": "tsc",
  "start": "ts-node index.ts"
},
```
Now you can compile and run your TypeScript project using the following commands:

```bash
npm run build
npm run start

```