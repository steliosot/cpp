## LAB: C++ Foundations for Data-Driven Decisions

**Duration:** ~60 minutes

**Level:** Beginner

This lab follows the lecture slides and helps you practice basic C++ step by step. You will write small programs that take input, make decisions, and repeat tasks. We will also connect programming to a real-world example: detecting fake news.

---

### Quiz

[Complete the quiz](https://kahoot.it/solo?quizId=2ff195ec-47ff-4960-a3d7-ba81a52f0644) before starting.

------

### Learning Goals

By the end of this lab you should be able to:

- Write and run a simple C++ program
- Understand how a program starts and ends
- Store data in variables
- Ask the user for input
- Use `if` statements to make decisions
- Use loops to repeat actions
- Build a small real-world style program

Do not worry if you are new. We go step by step.

------

### PART 1 — Setup

#### Create a file

Create a file called:

```
lab.cpp
```

This is where your code will go.

#### Compile and run

In the terminal:

```
g++ lab.cpp -o lab
./lab
```

Compile means turning your code into a program.
 Run means executing the program.

If you see output on screen, your setup works.

------

### PART 2 — Your First Program

Write this code:

```
#include <iostream>

int main() {
    std::cout << "Hello student!";
    return 0;
}
```

Run it.

#### What does this code do?

Let’s explain each line.

`#include <iostream>`
 Allows the program to print text and read input.

`int main()`
 Every C++ program starts here.

`std::cout`
 Prints text to the screen.

`return 0`
 Ends the program.

------

#### Exercise 1

Change the message so the program prints:

```
Welcome to the Fake News Lab
```

Run it again.

#### Solution

```
#include <iostream>

int main() {
    std::cout << "Welcome to the Fake News Lab";
    return 0;
}
```

------

### PART 3 — Variables and Input

Programs need to store data.
 We store data in variables.

A variable is like a box that holds information such as a number or text.

#### Tutorial

```
#include <iostream>

int main() {
    double score;

    std::cout << "Enter AI score (0–1): ";
    std::cin >> score;

    std::cout << "Score entered: " << score;

    return 0;
}
```

#### What is happening?

`double`
 A number with decimals (for example 0.75).

`std::cin`
 Reads input from the user.

The value the user types is stored inside the variable `score`.

Run the program and type:

```
0.8
```

You should see the number printed back.

------

#### Exercise 2

Ask the user for:

- temperature in Celsius
- print it back

#### Solution

```
#include <iostream>

int main() {
    double temp;

    std::cout << "Enter temperature in Celsius: ";
    std::cin >> temp;

    std::cout << "You entered: " << temp;

    return 0;
}
```

------

### PART 4 — Decisions (if statements)

Programs can make decisions.
 We use `if` statements to choose what happens next.

#### Tutorial

```
#include <iostream>

int main() {
    double ai_score;

    std::cout << "Enter AI score: ";
    std::cin >> ai_score;

    if (ai_score > 0.7) {
        std::cout << "Warning: Likely fake.";
    }
    else {
        std::cout << "Looks credible.";
    }

    return 0;
}
```

If the score is above 0.7, the program prints a warning.
 Otherwise, it prints that the article looks credible.

------

#### Exercise 3

If temperature is greater than 30
 print `"Hot day"`

Otherwise
 print `"Normal day"`

#### Solution

```
#include <iostream>

int main() {
    double temp;

    std::cout << "Enter temperature: ";
    std::cin >> temp;

    if (temp > 30) {
        std::cout << "Hot day";
    } else {
        std::cout << "Normal day";
    }

    return 0;
}
```

------

### PART 5 — Multiple Decisions

Sometimes we need more than two choices.

Example:

```
if (score >= 0.8)
    std::cout << "High risk";
else if (score >= 0.4)
    std::cout << "Medium risk";
else
    std::cout << "Low risk";
```

The program checks conditions from top to bottom.

------

#### Exercise 4

Classify exam score:

| Score | Output |
| ----- | ------ |
|       |        |

> = 70 → Pass
>  40–69 → Resit
>  < 40 → Fail

#### Solution

```
#include <iostream>

int main() {
    int mark;

    std::cout << "Enter mark: ";
    std::cin >> mark;

    if (mark >= 70)
        std::cout << "Pass";
    else if (mark >= 40)
        std::cout << "Resit";
    else
        std::cout << "Fail";

    return 0;
}
```

------

### PART 6 — Loops

A loop repeats code many times.

Example:

```
for (int i = 1; i <= 5; i++) {
    std::cout << i << "\n";
}
```

This prints numbers from 1 to 5.

`i = 1` start
 `i <= 5` stop after 5
 `i++` increase by 1

------

#### Exercise 5

Ask the user for 5 AI scores and print them.

#### Solution

```
#include <iostream>

int main() {
    double score;

    for (int i = 1; i <= 5; i++) {
        std::cout << "Enter score: ";
        std::cin >> score;
        std::cout << "You entered: " << score << "\n";
    }

    return 0;
}
```

------

### PART 7 — Real Scenario (Mini Project)

We simulate a simple fake news detector.

For 5 articles:

- ask for a score
- if score > 0.7 → show warning

------

#### Exercise 6 (Main Task)

Write a program that:

1. Loops through 5 articles
2. Asks for a score
3. Prints result

#### Solution

```
#include <iostream>

int main() {
    double score;

    for (int i = 1; i <= 5; i++) {
        std::cout << "Article " << i << " score: ";
        std::cin >> score;

        if (score > 0.7)
            std::cout << "Likely fake\n";
        else
            std::cout << "Credible\n";
    }

    return 0;
}
```

------

### Extension Tasks (Advanced)

Task A
 Count how many fake articles were detected.

Task B
 Calculate average score.

Task C
 Stop the loop if the user enters -1.

------

#### Extension Solution (example)

```
#include <iostream>

int main() {
    double score;
    int fake_count = 0;
    double total = 0;

    for (int i = 1; i <= 5; i++) {
        std::cout << "Score: ";
        std::cin >> score;

        total += score;

        if (score > 0.7) {
            std::cout << "Fake\n";
            fake_count++;
        } else {
            std::cout << "Credible\n";
        }
    }

    std::cout << "Fake articles: " << fake_count << "\n";
    std::cout << "Average score: " << total/5;

    return 0;
}
```

------

### Reflection Questions

1. What is a variable?
2. What does an `if` statement do?
3. Why do we use loops?
4. How could this type of program help society?