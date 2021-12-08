# JavaScript the Hards Parts  (Uderstand JavaScript Under the Hood)

> Learning Goals 
* JavaScript principles 
* Callbacks & Higher Order functions (Functional Programming)
* Closures
* Classes/Prototypes & Asynchronicity 

# Focus of the Workshop 

1. Anayltical Problem Solving
2. Technical communication
3. Engineering Approach 
4. Non-technical communcation 
5. JavaScript and Programming experience


# Thread of Execution 

JavaScript goes through the code line by line and runs/executes each line 
- knownas as the thread of teh execution. 

Saves data like strings and arrays so we can use that data later - in its memory 

```
const num =3 
function multiplyBy2(number){
    const result = number *2;
    return result;
}
const output = multiplyBy2(num);
const newOutput = multiplyBy2(10);

```


# Functions 

Code we save(define) functions and can use (call/invoke/execute/run) later with the functions name 

# Execution context

Created to run the code of a function - has 2 parts 
* Thread of execution
* Memory 


# Repeating Functionality 

```
function copyArrayAndMultiplyBy2(array){
    const output=[]
    for(let i =0; i< array.length; i++){
        output.push(array[i]*2)
    }
    return output 
}
const myArray =[1,2,3]
const result = copyArrayAndMultiplyBy2(array)

```

What is we want to copy array and divide it by 2 ??? 

```
function copyArrayAndMultiplyBy2(array){
    const output=[]
    for(let i =0; i< array.length; i++){
        output.push(array[i]/2)
    }
    return output 
}
const myArray =[1,2,3]
const result = copyArrayAndMultiplyBy2(array)
```

# Higher Order Functions 

We could generalize our function - so we pass in our specific instruction
only when we run copyArrayAndManipulate!


```
function copyArrayAndManipulate(array, instruction){
    const output=[]
    for(let i=0; i< array.length; i++){
        output.pus(instruction(array[i]))
    }
    return output
}
function multiplyBy2(input){
    return input *2 
}

const result = copyArrayAndManipulate([1,2,3], multiplyBy2)

```


# How was this possible ? 

Functions in javascript = first class objects (meaning they have all the features of Object )

They can co-exist and can be treated like any other javascrpit object 
1. Assigned to variables and properties of other objects
2. Passed as arugments into functions 
3. Returned as values from functions

> The outer function that takes in our baby function that is our Higher order function.
> The function that we insert in our Outer function is our Callback Function



# Callbacks and Higher Order Functions simplify our code and keep it DRY 

* Declarative readable code: Map, filter, reduce - the most reaadable way to write code to work with data 

* Asynchronous JavaScript: Callbacks are a core aspect of async JavaScript, and are under the hood promoses, async/await. 

# Arrow Functions 

```
function multiplyBy2(input) {return input *2;}

const multiplyBy2 = (input) => {return input*2}

const multiplyBy2 = (input) => input*2 

const multiplyBy2 = input = input*2 

const output = multiplyBy2(3)

```

# Updating our callback function as an arrow Function 



```

function copyArrayAndManipulate(array, instruction){
    const output=[]
    for(let i=0; i< array.length; i++){
        output.pus(instruction(array[i]))
    }
    return output
}
    const multiplyBy2 = input => input*2 

const result = copyArrayAndManipulate([1,2,3], multiplyBy2)

```
OR 


```
function copyArrayAndManipulate(array, instruction){
    const output=[]
    for(let i=0; i< array.length; i++){
        output.pus(instruction(array[i]))
    }
    return output
}

const result = copyArrayAndManipulate([1,2,3], input=> input*2 )


```
