<!-- .slide: data-background="#111111" -->

# C ++ basics

## Conditional statements

<a href="https://coders.school">
    <img width="500" data-src="../coders_school_logo.png" alt="Coders School" class="plain">
</a>

___

## Manual `if`

A conditional instruction is nothing more than asking the program a question, for example:

* Have you received all the data? <!-- .element: class="fragment fade-in" -->
* Has the boss's life dropped to 0? <!-- .element: class="fragment fade-in" -->
* Has the achievement been earned by the player? <!-- .element: class="fragment fade-in" -->
* Is the number greater than the maximum allowed? <!-- .element: class="fragment fade-in" -->

___

## Construction `if`

```cpp
if (condition) {
    // do sth
}
```

___

## Combining conditions

What if a lot of information has to be fulfilled?
We can combine conditions with an operator **or** (`||`, `or`) be **and** (`&&`, `and`)

```cpp
if (are_potatoes_eatten && is_meat_eatten && is_salad_eatten)
```
<!-- .element: class="fragment fade-in" -->

All 3 conditions must be met <!-- .element: class="fragment fade-in" -->

```cpp
if (player_has_20_dex || player_has_18_int || player_has_22_str)
```
<!-- .element: class="fragment fade-in" -->

In this case, it is enough to meet one of 3 conditions. They can all be met, but it is enough for any one to be met. <!-- .element: class="fragment fade-in" -->

___

## Manual `else`

If the program can react differently to meeting certain conditions, we can use constructions `if else`

```cpp
if (number < 2) {
    critical_miss();
} else if (number < 18) {
    hit();
} else {
    critical_hit();
}
```

___

## Manual `switch/case`

```cpp
char option = getInput();
switch (option) {
case 'l':
    goLeft();
    break;
case 'r':
    goRight();
    break;
default:
    exit();
}
```

* `case` stands for a specific case
* `break` announces that we are exiting the conditional statement `switch` and we continue to constitute the program. Its absence will result in the execution of the instructions from the next one `case`.
* `deafult` this is where the program will arrive if no other condition is met

___

## Task

Add a function `max`. It is supposed to return the maximum of the three given values. [Download the task][homework]

```cpp
#include <iostream>

// Write your function here

int main() {
    std::cout << "max (1, 2, 3): " << max(1, 2, 3) << "\n";
    std::cout << "max (2, 3, 1): " << max(2, 3, 1) << "\n";
    std::cout << "max (3, 2, 1): " << max(3, 2, 1) << "\n";

    return 0;
}
```

[homework]: https://github.com/coders-school/cpp-fundamentals/blob/master/module1/task2.cpp