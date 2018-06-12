# Project Lombok!

Alex Detrick

https://projectlombok.org/

--- 

### What is it?

- library for improving Java code
- introduces "language level features"
- lombok keywords are converted to native Java code

---

### How to use: Gradle

    dependencies {
      compileOnly 'org.projectlombok:lombok:1.18.0'
    }

---

### How to use: IntelliJ

- Need to install plugin
- Then "enable annotation preprocessing" on the project

---

# Practical Examples!

---

@RequiredArgsConstructor

    @RequiredArgsConstructor
    public class MyService {

        private final RequiredDependency requiredDependency;

    //  public MyService(RequiredDependency requiredDependency) {
    //      this.requiredDependency = requiredDependency;
    //  }

    }

---



