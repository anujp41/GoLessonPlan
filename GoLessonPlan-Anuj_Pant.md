# Lesson Plan - Plunge into Go

#### Total Time - Approx 90 min

---

### Overview

Today's class is focused on providing students with the very basics of Go. This lesson plan is targeted at students who have never programmed before.

`Summary: Complete relevant Activities for Go`

##### Instructor Priorities

- Students should understand what each of the following terms means:
  `package`, `main`, `import`, `fmt`, `var`, `const`, `function`, `for`,`if/else`, and `switch`.
- Students should be given an understanding of Go and guided through various examples.
- Students should be made aware of history of Go, why it was created, and some features of Go like statically typed nature of the language.

##### Instructor Notes

- Welcome to the Go Week. This will be the first week where many students in class will work with a programming language. Hence, instructors and TAs should be aware of helping students with the simplest of issues ranging from installation issues to proper syntax.

- As there are tonnes of programming languages, instructor should be prepared to talk to students about why they are learning Go. Instructors should also gently introduce the concept of statically typed language to students who have a non-CS background. Since these are important differences between Go and other popular languages like JavaScript, students could find it beneficial to know, as early as possible during their lesson, why they should study Go.

- However instructors should keep in mind as today's lessons cover a lot of topic and new syntax, aforementioned CS concepts related to Go should not be extremely detailed as to crowd out time for in-class activities and instructors demonstrations.

---

### Class Objectives

- To gain a beginner level understanding of Go and syntax as well as related concepts.
- Utilize Go Playground to write introductory code and create variables, constants, if/else statements, and functions.

---

### 1. Everyone Do: Welcome Students (3 min)

- Welcome students to the first week of serious programming. Re-assure them that while the topic at hand is difficult, students should not despair at the issues that they will undoubtedly have over the course of this lesson.

### 2. Instructor Do: Today's Class (2 min)

Proceed to opening the presentation slides.

- Briefly describe students the agenda for the class.
- Check with the students to ensure that everyone has Go installed in their laptop as it will be absolutely required for future classes
  > However remind students have the option to use an online IDE (`the Go Playground`) at `https://play.golang.org/` today; this will ensure that everyone can start coding today despite not having Go installed but have TAs check during office hours or break that everyone has Go

### 3. Instructor Do: How to learn a new language (5 mins)

- Students will undoubtedly be scared as this is their first-time learning a new language.

- Stress to the students that any issues they have today should not be thought of as insurmountable; let them know that with enough practice and following the Always Be Coding rule, they can learn coding.

### 4. Instructor Do: What is Go? (2 min)

- Let students know that Go was created at Google and has a lot of developers that use it everyday; tying programming language to real-world application, in this case managing Google servers, will help students understand the importance of what they are learning.

- Instructors can choose to throw some CS terms to let students know everything they will be learning in the rest of the Go lessons.

### 5. Instructor Do: Code Dissection (5 mins)

- Walk students through the "Hello World" code and explain all the new unfamiliar terms in the screen; namely, `package`, `import`, `fmt`, `func`, and `main`.

```go
package main

import "fmt"

func main() {
	fmt.Println("Hello World")
}
```

- **Instructor / TA Note:** Do not discuss variables or data types at this point and focus rather on the code provided above. We will come back later to those topics.

### 6. Student Do: Println Activity (5 min)

- Using the recently learned `Println` method, ask students to print out the names of 4 students that are sitting closest to them in the class as well as the favorite book of the 4 students.

- This activity will also help students introduce themselves to one another.

### 6. Instructor Do: Introduce Variables & Data Types + Demo (8 mins)

- **Note:** Instructors should be prepared to talk about static typechecking in this section as variables will be initialized with the relevant data type.

- Introduce students to the variables and the various data types in Go that can be variables with a focus on `string`, `int`, `float`, `boolean`.

- Also introduce students to the `time` package as this package allows students to use data and time and will also be helpful to the students for the activity to be followed later.

```go
package main

import (
	"fmt"
)

var name string = "Sylvester"
var age int = 2
var cat bool = true
var pi float32 = 3.14

func main() {
  fmt.Println("Your name is: ", name)
  fmt.Println("Your age is : ", age)
  fmt.Println("Are you a cat?  ", cat)
  fmt.Println("You get a pie if you can tell me what pi is? ", pi)
}
```

- **Note:** Let students know that the code above shows a different way of writing `import` statement.

- Instructor can also re-factor code to re-write the variable declaration such as:

```go
package main

import (
	"fmt"
)

var (
  name string = "Sylvester"
  age int = 2
)

//Initializing as constants
const pi float32 = 3.14

func main() {
  // Remind students that := only works inside functions
  cat := true

  fmt.Println("Your name is: ", name)
  fmt.Println("Your age is : ", age)
  fmt.Println("Are you a cat?  ", cat)
  fmt.Println("You get a pie if you can tell me what pi is? ", pi)
}
```

### 7. Students Do: Variable Activity (10 mins)

- Students should now write a function that prints the following:

  - Student's name as type `string`
  - Student's age as type `int`
  - Floating number (any of student's choosing) as type `float`
  - True/False depending on if student lives inside NYC as type `bool`
  - Today's date and time using the `time` library as type `time.Time`
    <br>
    > Consider slacking the following url to show students that Go allows users to create date and time in different formats:
    > <br> http://www.golangprograms.com/get-current-date-and-time-in-various-format-in-golang.html

### 8. Instructor Do: Review Variable Activity (4 mins)

- Instructor should now review the activity with a particular focus on the `time` library

```go
package main

import (
  "fmt"
  "time"
)

func main() {
  var name string = "Susie Student"
  var age int = 30
  var pi float32 = 3.14
  var liveNYC bool = true
  var dateTime time.Time = time.Now()

  fmt.Println(name, "\n")
  fmt.Println(age, "\n")
  fmt.Println(pi, "\n")
  fmt.Println(liveNYC, "\n")
  fmt.Println(dateTime.Format("2006.01.02 15:04:05"))
}
```

### 9. Instructor Demo: Scan for inputs and String formatting (8 mins)

- **Note:** Instructor should pay particular attention to string formatting section as students can get confused with the `%` symbols.

- Proceed by explaining how to use the `Scan` method built-in to the `fmt` library and store user input in existing variable.

- To remind students about static type checking built into Go, show them the errors that will occur if they take user input and store in variables with wrong data type.

- Introduce students to string formatting and `Printf` method; limit discussion to the following verbs as this discussion can get complicated very fast:
  - `%v`
  - `%T`

### 10. Student Do: Ask user for name and print it (5 mins)

- Students should write code that will separately ask the user for their first name and then their last name.

- Using string formatting, students should combine the first and last name and print out a full name

### 11. Instructor Do: Review activity (2 min)

- Instructor should review activity

- Instructor could also show the students how to use `%T` to print out the data type in addition to the value.

```go
package main

import "fmt"

func main() {
  var firstName string
  fmt.Printf("What is your first name? ")
  fmt.Scan(&firstName)

  var lastName string
  fmt.Printf("What is your last name? ")
  fmt.Scan(&lastName)
  //Discuss why \n was used in the following code
  fmt.Printf("Your full name is %v %v\n", firstName, lastName)

  //Bonus
  fmt.Printf("firstName is of type: %T\n", firstName)
  fmt.Printf("lastName is of type: %T\n", lastName)
}
```

### 12. Instructor Do: If not, then Else (8 mins)

- Instructor should explain the proper use of if/else statement.

- In addition to the explanations on usage, instructors should also focus on the correct syntax for if/else statements in Go

- Instructors should also discuss the `math` library and especially the random number generator as it will be used for the next exercise.

### 13. Students Do: Guessing Game Activity (15 min)

- **Note:** This activity will be challenging to the students as it will require using the random number generator.

- Students should write code that will do the following:

  - **Instructions**

    - Generate a random number between 0 and 10.

    - **Note:** TAs should ensure that students are able to generate random numbers.

    - Once random number is generated, the code should ask user to enter a random number.

    - If the user input is equal to the random number, the code should print "You won!"

    - If the user input is lower than the random number, the code should print "Guess too low!"

    - If the user input is higher than the random number, the code should print "Guess too high!"

    - **Bonus:** Adventurous students can look up for loop (to be discussed in next class) and use it in the Bonus section. The bonus involves asking the user to guess again in the last two cases where the user input does not match the random number so the user can keep guessing for the correct random number.

### 14. Instructor Do: Review Activity (8 min)

- Demonstrate the correct method of creating the above mentioned game.

```go
//Note: Solution also shows the BONUS
package main

import (
  "fmt"
  "math/rand"
  "time"
  )

func main() {

  rand.Seed(time.Now().UTC().UnixNano())

  var randNumber int
  randNumber = rand.Intn(10)
  fmt.Println(randNumber)

  var correctGuess bool = false

  for correctGuess != true {
    var userGuess int
    fmt.Printf("Enter a number between 0 and 10: ", )
    fmt.Scan(&userGuess)

    if (userGuess == randNumber ) {
      fmt.Println("You won!")
      correctGuess = true
    } else if (userGuess < randNumber) {
      fmt.Println("Guess too low!")
    } else {
      fmt.Println("Guess too high!")
    }
  }
}
```

- If time is available, also walk students through the for loop and demonstrate the code. Remind students that for loop will be discussed in detail in the next class so if this seems confusing for now, they will have opportunity to review it again later.
