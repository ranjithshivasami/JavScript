# JavaScript
JavaScript is a High-level, prototype-based, Object-oriented. multi-paradigm, interpreted or just-in-time compiled. dynamic, single-threaded, garbage-collected programming language with first-class functions and a non-blocking event loop concurrency model.

### map(), filter() and reduce() functions
The map() method creates a new array populated with the results of calling a provided function on every element in the calling array.

The map() method is an iterative method. It calls a provided callbackFn function once for each element in an array and constructs a new array from the results.
 #### Syntax
    // Arrow function
    map((element) => { /* … */ })

    // Callback function
    map(callbackFn)

    map(function (element) { /* … */ })
    
#### Exapmle
    const array1 = [1, 4, 9, 16];

    //Get doble the values of the array items
    const arrayDpuble = array1.map((x) => x*2);
    console.log(arrayDpuble);

### filter()
The filter() method creates a shallow copy of a portion of a given array, 
filtered down to just the elements from the given array that pass the test implemented by the provided function.

The filter() method is an iterative method. It calls a provided callbackFn function once for each element in an array, and constructs a new array of all the values for which callbackFn returns a truthy value. Array elements which do not pass the callbackFn test are not included in the new array.

### Syntax
    // Arrow function
    filter((element) => { /* … */ })
   

    // Callback function
    filter(callbackFn)
   

    // Inline callback function
    filter(function (element) { /* … */ })
    
### Example

    const array1 = [1, 4, 9, 16, 28, 30, 50, 75, 80 ,90];

    //Get Value grater then 40
    const graterThen40 = array1.filter((x) => x>40);
    console.log(graterThen40);

   

### reduce()
The reduce() method executes a user-supplied "reducer" callback function on each element of the array, in order, passing in the return value from the calculation on the preceding element. The final result of running the reducer across all elements of the array is a single value.

The first time that the callback is run there is no "return value of the previous calculation". If supplied, an initial value may be used in its place. Otherwise the array element at index 0 is used as the initial value and iteration starts from the next element (index 1 instead of index 0).

### Syntax

    // Arrow function
    reduce((accumulator, currentValue) => { /* … */ }, initialValue);   

    // Callback function    
    reduce(callbackFn, initialValue)

    // Inline callback function
    reduce(function (accumulator, currentValue) { /* … */ }initialValue);
    
### Example

    const array1 = [1, 4, 9, 16, 28, 30, 50, 75, 80 ,90];

    //Get sum of the array
    const sum = array1.reduce((accumulator, currentValue) =>{
            accumulator +=  currentValue;
            return accumulator;
    }, 0);
    console.log(sum);

    // get the largest value
    const laregest = array1.reduce((accumulator,  currentValue) => {
        if(accumulator < currentValue){
            accumulator = currentValue
        }
    return currentValue;
    }, 0);

     console.log(laregest);

### Advanced Example
     array1 = [
        {"gender":"female","first_name":"melissa","last_name":"fleming","age":22},
        {"gender":"male","first_name":"christoffer","last_name":"christiansen",  "age":22},
        {"gender":"male","first_name":"valtteri","last_name":"pulkkinen","age":21},
        {"gender":"male","first_name":"todd","last_name":"beck","age":20},
        {"gender":"female","first_name":"kayla","last_name":"hall","age":22},
        {"gender":"female","first_name":"kala","last_name":"mathiev","age":24},
        {"gender":"female","first_name":"Rose","last_name":"David","age":24},
        {"gender":"male","first_name":"jimmie","last_name":"simmons","age":51},
        {"gender":"male","first_name":"benedikt","last_name":"hein","age":50},
        {"gender":"male","first_name":"aloïs","last_name":"moulin","age":49},
        {"gender":"male","first_name":"noah","last_name":"smith","age":22},
        {"gender":"male","first_name":"noah","last_name":"dupont","age":22}
    ]

    // get the users who all are in 22 years old
        const age22 = array1.filter((x) => {return x.age === 22});
        console.log(age22);
    //get the full name 
        const arrFullName = array1.map((x) => { return x.first_name+ ' ' +x.last_name});
        console.log(arrFullName);
    
    //get the female who all are in 22 years old
        const female22 = array1.filter((x) => {
            return x.age ===22 && x.gender === 'female';
        });
        console.log(female22);
    // get age value like the below
        //{22:6, 21:1, 20:1, 51:1, 50:1, 49:1}

        const reduce1 = array1.reduce((accoumulator, currrentValue) => {
            if(accoumulator[currrentValue['age']]){
                 accoumulator[currrentValue['age']] = accoumulator[currrentValue['age']]+1 ;
            } else {
                accoumulator[currrentValue['age']] = 1;
            }
            return accoumulator;
        }, {});
        console.log(reduce1);
