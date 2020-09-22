# Springboot


## What is Springboot?

 **source: PP Something about SpringBoot v3 by Nuno Silva, Software II**

Springboot is a set of predefined dependencies to simplify the build of a Spring application.

- Opinionated ‘starter’ dependencies to simplify build and application
configuration.
- Embedded server to avoid complexity in application deployment.
- Metrics, Health check, and externalized configuration.
- Automatic config for Spring functionality – whenever possible.

**Simple Springboot application:**
1. Import SpringApplication, SpringBootApplication, GetMapping, RequestParam, RestController.
2. Apply notation `@SpringBootApplication` to the Application class that contains main method.
2.1 Inside main method:
```
SpringApplication.run(<class name>.class, args);
```

**Bootstrapping a SpringBoot project**
To generate a SpringBoot project use Spring Initializer:
https://start.spring.io/

**Add the folder generated to the project structure.**

## What can we do with SpringBoot?
1. Add `@RestController` notation to the Application Class.

Example to use inside Application class:
```
@GetMapping("/hello")
public String hello (@RequestParam())value = "name", defaultValue = "WOrld") String name) {
	return String.format("Hello %s!", name);
}
```

## What are Beans?
Beans are the objects that are managed by  the Spring Inversion of Control. A bean is an object that is instantiated, assembled, and otherwise
managed by a Spring Inversion of Control container.

## What is IoC (Inversion of Control) ?
 [IoC](https://www.baeldung.com/inversion-control-and-dependency-injection-in-spring) is a process in which an object defines
its dependencies without creating them. This object delegates the job of
constructing such dependencies to an IoC container.



## What is Spring and SpringBoot?

IoC containers and Dependency Injection frameworks:

![SpringBoot UML example](images/springbootexamplecdandsd.png)

**Anotation by Stereotypes**
- `@Component`
- `@Repository`
- `@Configuration`
- `@Controller`
- `@Service`
- `@RestController`
- `@Bean`


## Example of SpringBoot application based on G4 project:

**Por terminar!!!! AQUI!!!!!!**
------------------------------


## Dependency Injection

## REST

## Tests

# More sources for SpringBoot:
https://www.tutorialspoint.com/spring_boot/spring_boot_bootstrapping.htm