# Big-O Notation Exercises

What is the worst-case time complexity for the following algorithms?

#### #1

```javascript
function wordOccurrence(word, phrase){
  let result = 0
  const array  = phrase.split(' ')
  for(let i = 0; i < array.length; i++){
    if(word.toLowerCase() === array[i].toLowerCase()){
      result++;
    }
  }
  return result
}
```
WC Complexity: O(N) - linear complexity
-- as the phrase grows in number of words or separations by space, the algorithm will perform split, iterate, check each index, and increment result.


#### #2

```javascript
function bubble_sort(list){
  for(let i = 0; i < list.length - 1; i++){
    for(let j  = 0; j < list.length - 2; j++){
      if(list[j+1] < list[j]){
        const temp = list[j];
        list[j] = list[j+1];
        list[j+1] = temp;
      }
    }
  }
  return list;
}
```
WC Complexity: O(N^2) - quadratic complexity
-- the outer loop runs, and the inner loop runs for each iteration of the outer loop to check conditions and make assignments.

#### #3
```javascript
function factorial(n){
  if(n === 0){
    return 1;
  }else{
    return n * factorial(n-1);
  }
}
```

WC Complexity: O(N!) - factorial complexity
-- this algorithm will repeat itself until it n strictly equals 0 and it returns 1. 

#### #4

```javascript
function bobIsFirst(people){
  return people[0] == 'bob'
}
```

WC Complexity: O(1)
-- this algorithm will run once, regardless of the number of people. It will return true or false one time. 

#### #5

```javascript
function isPalindrome(input){
  const stack = [];
  let output = "";
  for(let i = 0; i < input.length; i++){
    stack.push(input[i]);
  }
  while(stack.length){
    output += stack.pop();
  }
  return output == input
}
```
WC Complexity: O(n) - linear complexity 
-- Stack operation


#### #6
```javascript
function sumOfDivisors(n){
  let result = 0;
  let i = 1;
  while(i < n){
    if( n % i == 0){
      result += i;
    }
  }
  return result
}
```
WC Complexity : O(N!) - factorial complexity
-- this is a potentially infinite loop, possibility of infinite loop increases with the vaue of n


#### #7
```javascript
function printAllNumbersThenSumPairs(numArray){
  numArray.forEach((num)=>{
    console.log(num);
  });
  numArray.forEach((num, index)=>{
    if(index < numArray.length - 1){
      console.log(num + numArray[index+1])
    }
  });
}
```

WC Complexity: O(N) - linear complexity
The algorithm will run forEach two times for each array element, no matter the length of the array.

#### #8
```javascript
function isPrime(num){
  if(num == 1 || num == 2){
    return false
  }
  for(let i = 2; i < num - 1; i++){
    if(num % i == 0){
      return false
    }
  }
  return true
}
```

WC Complexity: O(1) - constant complexity
-- Loop will run the same number of times no matter the input to check if the input is prime or not.