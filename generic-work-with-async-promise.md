# Understanding Generics in TypeScript and Asynchronous Promise Responses

## Introduction

In typescript, generics feature is one of the most significant feature. This feature allows reusable, flexible and type-safety. Asynchronous Promise Responses is another powerful feature in ts. This allows us to operate request, response in this single threaded language. This become more useful with generics.like `Promise<T>`


## Understanding Generics

Generics is works as a placeholder for a datatype in typescript. In stead of assigning all type, generics allows to use custom  data. And we the developer use T as for this even though others letter can be used.

For example:

``` typescript
function identity<T>(value: T): T {
    return value;
}

const age = identity<number>(20);
const name = identity<string>("King Shohan");
```

Here if you notice I write this generics type function by <T>. and later i use this function will two different data type number and string. So, here generics help me to use custom data type.




## Understanding Promise with generics data type


Lets see few lines of code:

``` typescript
function getUser(): Promise<string> {
    return new Promise((resolve) => {
        setTimeout(() => {
            resolve("King Shohan");
        }, 1000);
    });
}
```

In this code, `Promise<string>` defines the asynchronous function will give me a string value, which is specific data type.

Now, we call also define this function with generics (custom data type)  with greater than and less than sign and T (`<T>`)

``` typescript
async function fetchData<T>(data: T): Promise<T> {
    return data;
}

const user = fetchData<string>("Shohan");
const age = fetchData<number>(20);
```

Look at this, when it is time for calling i use two different data type (string and number) and its works fine with asynchronous function and can return the promise.

## Conclusion

Generics make the ts code more reusable with type safely. To sum up, to combine with generics and asychronous function, we can get a great type safely code that gives us better control for working with API.

