# Maven Simple App – Jenkins CI Pipeline

This project is a **simple Java Maven application** with **unit test cases**, built to demonstrate a **Jenkins CI pipeline** using **Docker-based Maven builds**.

The goal of this project is to:
- Write application code and test cases locally
- Push the code to Git
- Use Jenkins to automatically build and test the project using Docker

---

## 🛠️ Technologies Used

- Java 17
- Maven
- JUnit 5
- Jenkins (Declarative Pipeline)
- Docker
- Git & GitHub

---

## 📂 Project Structure

maven-simple-app/
├── pom.xml
|-- Jenkinsfile
└── src
    ├── main
    │   └── java
    │       └── com
    │           └── example
    │               └── app
    │                   └── Calculator.java
    └── test
        └── java
            └── com
                └── example
                    └── app
                        └── CalculatorTest.java

