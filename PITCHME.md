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

@FieldDefaults
@NonNull

    @RequiredArgsConstructor
    @FieldDefaults(level = AccessLevel.PRIVATE, makeFinal = true)
    public class MyService {

        @NonNull RequiredDependency requiredDependency;

    }

---

@Builder

    @Builder
    class BusinessObject {

        private final String name;

    }

    // new BusinessObject.BusinessObjectBuilder()
    //                 .name("CJUG")
    //                 .build();

---

@Value

    @Builder(toBuilder = true)
    @Value(staticConstructor="of")
    class BusinessObject {

        @Builder.Default String name = "CJUG"

    }

    // businessObject.toBuilder();

}

---

@Value

    @Builder(toBuilder = true)
    @Value(staticConstructor="of")
    class BusinessObject {

        @Builder.Default String name = "CJUG"

    }

    // businessObject.toBuilder();

}

---

@Value (@Data)

    @Builder(toBuilder = true)
    @Value(staticConstructor="of")
    class BusinessObject {

        @Singular Set<String> speakers;

    }

    // new BusinessObject.BusinessObjectBuilder()
    //         .name("Alex")
    //         .name("Freddy")
    //         .build();

}

---

    @Slf4j
    public class MyService {

        // private static final Logger log = org.slf4j.LoggerFactory.getLogger(MyService.class);

        public void log() {
            log.info("Thank you CJUG!");
        }

    }

---

Var

    public class VarExample {

        public void example() {
            val example = new ArrayList<String>();
            example.add("Hello, World!");
        }

    }

---

@FieldNameConstants

    @FieldNameConstants
    public class FieldNameConstantsExample {
        // public static final String FIELD_MY_FIELD = "myField";
        private final String myField;
    }

---

@Accessors(fluent = true)

    @Accessors(fluent = true)
    @Configuration
    public class AccessorsExample {

        @Getter(onMethod=@__({@Bean}))
        MyBean myBean = new MyBean();

    }

---

# Thank You

Other favorites
- `var`
- `val`
- `@Whither`
- `@Delegate`
- `@ExtensionMethod`
- `@UtilityClass`
- `@Helper`
- `@Getter(lazy=true)`
