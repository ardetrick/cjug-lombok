# Project Lombok!

Alex Detrick

https://projectlombok.org/

--- 

### What is it?

- library for improving Java code
- introduces "language level features"

---

### How to use: Gradle

```java
dependencies {
  compileOnly 'org.projectlombok:lombok:1.18.0'
}
```

---

### How to use: IntelliJ

- install plugin
- check "enable annotation preprocessing" setting

---

## Examples!

---

@RequiredArgsConstructor

```java
@RequiredArgsConstructor
public class MyService {

    private final RequiredDependency requiredDependency;

//  public MyService(RequiredDependency requiredDependency) {
//      this.requiredDependency = requiredDependency;
//  }

}
```

---

@FieldDefaults
@NonNull

```java
@RequiredArgsConstructor
@FieldDefaults(level = AccessLevel.PRIVATE, makeFinal = true)
public class MyService {

    @NonNull RequiredDependency requiredDependency;

}
```

---

@Builder

```java
@Builder
class BusinessObject {

    private final String name;

}

// new BusinessObject.BusinessObjectBuilder()
//         .name("CJUG")
//         .build();
```

---

@Value (@Data)

```java
@Builder(toBuilder = true)
@Value(staticConstructor="of")
class BusinessObject {

    @Builder.Default String name = "CJUG"

}

// BusinessObject.of("CJUG").toBuilder();
```

---

@Singular

```java
@Builder(toBuilder = true)
class BusinessObject {

    @Singular Set<String> speakers;

}

// new BusinessObject.BusinessObjectBuilder()
//         .name("Alex")
//         .name("Freddy")
//         .build();
```

---

@Slf4j

```java
@Slf4j
public class MyService {

    // private static final Logger log =
    //     org.slf4j.LoggerFactory.getLogger(MyService.class);

    public void log() {
        log.info("Thank you CJUG!");
    }

}
```

---

Val

```java
public class ValExample {

    public void example() {
        val example = new ArrayList<String>();
        example.add("Hello, World!");
    }

}
```

---

@FieldNameConstants

```java
@FieldNameConstants
public class FieldNameConstantsExample {

    // public static final String FIELD_MY_FIELD = "myField";
    private final String myField;

}
```

---

# Thank You

Other favorites
- `@Accessors(fluent = true)`
- `@Whither`
- `@Delegate`
- `@ExtensionMethod`
- `@UtilityClass`
- `@Helper`
- `@Getter(lazy=true)`
