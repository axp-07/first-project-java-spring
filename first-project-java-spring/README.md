# first-project-java-spring

This is my first Spring Boot app, made for Exercise 16 at Vistula University. It's small on purpose. The goal was to get a Spring project running, write a first controller, and see how a web page gets built with Thymeleaf.

## What it does

- `GET /` returns a plain text message: "Hello Vistula, in my first Spring controller."
- `GET /greeting?name=Vistula` shows an HTML page that says "Hello, Vistula!" with the Vistula logo under it. If you leave out the `name`, it says "Hello, World!".

## Built with

- Java
- Spring Boot (Spring Web, Thymeleaf, Lombok)
- Maven

## How to run it

1. Clone the repo and open it in IntelliJ (or any Java IDE).
2. Let Maven download the dependencies.
3. Run `FirstProjectJavaSpringApplication`.
4. Open http://localhost:8080 and http://localhost:8080/greeting?name=Vistula in your browser.

You can also run it from a terminal:

```
./mvnw spring-boot:run
```

## How it's put together

```
src/main
├── java/pl/edu/vistula/first_project_java_spring
│   ├── FirstProjectJavaSpringApplication.java   (starts the app)
│   └── HelloController.java                      (the two endpoints)
└── resources
    ├── templates/greeting.html                   (Thymeleaf page)
    └── static/vistula.jpeg                       (the logo)
```

## What I learned

- `@RestController` sends back whatever the method returns as text. `@Controller` treats the returned string as the name of a view, so `return "greeting"` loads `greeting.html`. That's why `hello()` needs `@ResponseBody` once the class is a `@Controller`.
- `@RequestParam` reads values from the URL, and `Model` carries them over to the template.
- Files in `static` are served as they are. Files in `templates` get processed by Thymeleaf first.
- Spring only finds controllers that sit in the main package or below it.

Made by Adwaidh.
