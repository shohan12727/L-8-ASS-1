# TypeScript Compilation and the Role of tsconfig.json

## Introduction

Typescript is a static type programming language which is made on the top of javascript with type safety. This completion process of typescript by   `tsc`, that convert the real typescript code into the javascript then it can execute by node js. and in tsconfig we manage compilerOptions,Typechecking Options,  Recommended Options etc.    


## What exactly happens during compilation?

When anyone run `tsc` syntax in his/her terminal, the compiler reads the typsript file and the project configuration in side tsconfig.json. Then is processes the source code and build AST. after that compiler check the type things like for example: 

```typescript
const name : string = 'King Shohan';
name = 12 // this will show an error 
```

Here the compiler reads the type and then check. As it is not matching the type , that's the reason why compiler will through an error.


``` typescript
// TypeScript
const username: string = "King Shohan";

// Compiled version of  JavaScript
const username = "King Shohan";
```

This is how each and every line of typescript convert into javascript with the help of `tsc` command.


## The Importance of tsconfig.json file
 
The `tsconfig.json` file contains all the compilerOptions,  Environment Settings, Other Outputs, Recommended Options,  Style Options. We all can control all of this inside the tsconfig.json file. 


Here i give you my tsconfig.json file : (for demo)
``` json
{
  // Visit https://aka.ms/tsconfig to read more about this file
  "compilerOptions": {
    // File Layout
    "rootDir": "./src",
    "outDir": "./dist",

    // Environment Settings
    // See also https://aka.ms/tsconfig/module
    "module": "esnext",
    "target": "esnext",
    "types": [],
    // For nodejs:
    // "lib": ["esnext"],
    // "types": ["node"],
    // and npm install -D @types/node

    // Other Outputs
    "sourceMap": true,
    "declaration": true,
    "declarationMap": true,

    // Stricter Typechecking Options
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true,

    // Style Options
    // "noImplicitReturns": true,
    // "noImplicitOverride": true,
    // "noUnusedLocals": true,
    // "noUnusedParameters": true,
    // "noFallthroughCasesInSwitch": true,
    // "noPropertyAccessFromIndexSignature": true,

    // Recommended Options
    "strict": true,
    "jsx": "react-jsx",
    "verbatimModuleSyntax": true,
    "isolatedModules": true,
    "noUncheckedSideEffectImports": true,
    "moduleDetection": "force",
    "skipLibCheck": true,
  }
}
```



## Conclusion

To sum up we can say that will the process of being compile of ts code is we wrote ts code, then it convert into js and after that it compile into js. And tsconfig file hold all the centralized things for us.
