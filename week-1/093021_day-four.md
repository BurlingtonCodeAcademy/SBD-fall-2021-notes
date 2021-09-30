# Loops

The Programming Code: _first make it work, then make it right, and, finally, make it fast_
A loop is a program that does something many times

## While Loops

The simplest loop, this loops says that while some condition is true, do this. Once the condition becomes false, the loop is broken and continues on through the the rest of your program

`while (true) {Do this}`
  Infinite Loops are loops that never break and go on and on and on and on and on, they are useful as long as you have a condition to stop the loop. For instance, a loop that counts to 100...

```
  let count = 1

  while(count <= 100) {
      count += 1
      console.log(count)
  }
```

The key word _break_ stops a loop immediately

```
let count = 0;
while (true) {
    console.log(count);
    count = count + 1;
    if (count > 100) {
        break;
    }
}
```

## Functional Decomposition

Allows you to decompose the problem into smaller ones and "divide conquer"
Great for team oriented development
Functional decomposition is also a great way to write a program that you haven't quite figured out yet, and can allow you to move on if you become stuck on something.

## For Loops

For loops are cumbersome loops that takes multiple different arguments within the body `for(argument1; argument2; argument3;){Do this}`

For of Loops loops over an array and hides the messy details of initializing and incrementing a counter `for(let something of somethings){Do this}`