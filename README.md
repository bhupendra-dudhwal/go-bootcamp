# Golang Bootcamp
A practical, hands-on Go (Golang) bootcamp for beginners and backend developers — build APIs, learn concurrency, testing, and more.

## 🧠 Overview

This hands-on bootcamp is designed to take you from Go fundamentals to building scalable, concurrent REST APIs in just three days. You'll walk away with a strong grasp of Go syntax, core principles, concurrency patterns, and API design — all reinforced through practical projects.

---

## 📅 Agenda

### Day 1: Go Language Foundations

**Objective:** Equip participants with the essential syntax, data structures, and type system of Go.

- Introduction to Golang & Environment Setup  
- Go Syntax: Variables, Functions, Loops  
- Data Structures: Arrays, Slices, and Maps  
- Structs, Pointers, Value & Pointer Receivers  
- Interfaces & Composition  
- Type Assertions and Type Casting  

**Hands-on Project:** CLI-based Mini App (To-do App or Quiz)

---

### Day 2: Error Handling, REST APIs & Concurrency

**Objective:** Understand real-world application development with Go including API building and safe concurrency.

- Error Handling: In-built, Custom, Panic/Recover  
- Request/Response Validation using Validator  
- Building REST APIs (CRUD) using Go  
- Introduction to Goroutines & WaitGroups  
- Channels and Concurrency Patterns  
- Race Conditions & Mutex  

**Hands-on Project:** Concurrent REST API (Task Manager or Data Processor)

---

### Day 3: Context, Scalable REST Design & Testing

**Objective:** Explore scalable Go REST practices and build production-style apps.

- Working with `context` Package in Go  
- REST API Best Practices (Versioning, Status Codes, Middleware)  
- Structuring Large REST Applications (MVC-style separation)  
- Design Patterns in Go (Singleton, Factory, etc.)  
- Testing, Linting, and Best Practices  

**Capstone Project:** Build and Present a Scalable REST API with Concurrency

---

## 🎯 What You’ll Gain

- Solid understanding of Go fundamentals and intermediate concepts  
- Confidence to build production-grade REST APIs and handle concurrency safely  
- Experience working with real-world validation, structuring, and context handling  
- A mini-project portfolio to showcase your skills and learnings




# Golang Bootcamp - Day 1: Language Foundations

## 🧠 Objective
Learn Go's syntax, data structures, functions, and how interfaces & composition work.

---

## 🛠️ Environment Setup

1. Install Go from https://golang.org/dl
2. Verify with `go version`
3. Set up your workspace:
```sh
mkdir golang-bootcamp && cd golang-bootcamp
go mod init bootcamp
```

---

## 🔤 Variables, Constants, and Functions

### ✅ Variables
```go
package main
import "fmt"

func main() {
    var name string = "Go"
    age := 10
    const version = 1.18
    fmt.Println(name, age, version)
}
```

### ✅ Functions (with named returns)
```go
func swap(a, b string) (x, y string) {
    x = b
    y = a
    return
}
```

---

## 🔁 Loops and Control Flow

```go
for i := 0; i < 5; i++ {
    fmt.Println("Iteration:", i)
}

if num := 10; num > 5 {
    fmt.Println("Greater than 5")
}
```

---

## 📦 Arrays, Slices, and Maps

### ✅ Arrays & Slices
```go
arr := [3]int{1, 2, 3}
slice := []string{"apple", "banana"}
slice = append(slice, "cherry")
```

### ✅ Maps
```go
scores := map[string]int{"Alice": 90, "Bob": 80}
scores["Charlie"] = 85
delete(scores, "Bob")
```

---

## 🧱 Structs & Pointers

```go
type Person struct {
    Name string
    Age  int
}

func (p Person) Greet() {
    fmt.Println("Hello", p.Name)
}

func (p *Person) Birthday() {
    p.Age++
}
```

---

## 🔌 Interfaces & Composition

```go
type Speaker interface {
    Speak()
}

type Dog struct{}

func (d Dog) Speak() {
    fmt.Println("Woof!")
}

func makeSpeak(s Speaker) {
    s.Speak()
}
```

---

# 💡 Exercises (with hidden solutions)

### 1. Reverse a slice of integers

```go
// TODO: Write a function that takes []int and returns it reversed
```

<details><summary>✅ Solution</summary>

```go
func reverse(nums []int) []int {
    for i, j := 0, len(nums)-1; i < j; i, j = i+1, j-1 {
        nums[i], nums[j] = nums[j], nums[i]
    }
    return nums
}
```

</details>

---

### 2. Student Grade Map
- Create a map of student names to grades.
- Add, delete, and update entries.
- Print all students with grade > 75.

```go
// TODO: Implement using map[string]int
```

---

### 3. Interface-based Calculator

```go
type Operation interface {
    Execute(a, b int) int
}

type Add struct{}
func (Add) Execute(a, b int) int { return a + b }

type Subtract struct{}
func (Subtract) Execute(a, b int) int { return a - b }

// TODO: Use interface to perform operation based on input
```

---

# 🧪 Mini Project: CLI To-Do App

## ✅ Features
- Add a task
- List tasks
- Mark complete

## 🧱 Sample Structure
```go
type Task struct {
    ID int
    Title string
    Done bool
}

var tasks []Task
```

## 🔄 Operations
- `go run main.go add "Buy milk"`
- `go run main.go list`

(Provide full code separately with explanations)

---

📌 **Next:** Day 2 – REST API & Concurrency

