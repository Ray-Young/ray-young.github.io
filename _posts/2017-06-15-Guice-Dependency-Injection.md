---
layout: post
title: Guice Dependency Injection
comments: true
date: 2017-06-15
tags: [Design Pattern, Java]
---

### Dependency Injection:
The behavior of Dependency Injection is like leave the bag to others.
Not initialize the object each time we use it. We initialize it once and
inject the dependency (pass as reference) each time. Still confused?
Let's split it into an example.

Say we have a TicketService class as follow

```java
public class TicketService {
    private final Ticket ticket

    public TicketService(Ticket ticket) {
        this.ticket = ticket;
    }

    ...
}
```

In the ticket class, it do a complex disk and network manipulation

```java
public class Ticket {
    public Ticket() {
        /**
         * Complex disk and network manipulation
         */
    }
}
```

Ticket is the dependency of TicketService. The way we passing the dependency
(Ticket) to TicketService is called dependency injection.

### Factory Pattern
In a contrast example, we can use factory to initialize the dependecy in
TicketService. Which is called Factory Pattern.

```java
public class TicketService {
    private final Ticket ticket = TicketFactory.getInstance();

    ...
}
```

### Why Guice?
Now think about the scenario we are writing integration tests. TestA()
and TestB() are different classes, and both of them need to use
 TicketService.  What we do now? Shall we initialize TicketService
seperately in TestA and TestB? It's a waste of resource. Here comes
Guice.

### Dependency Binding

```java
public class ServiceTicketModule extends AbstractModule {
    @Override
    protected void configure() {
        bind(TicketService.class).to(Ticket.class);
    }
}
```

```java
public class TestA() {
    Injector injector = Guice.createInjector(new ServiceTicketModule());
    ServiceTicket serviceTicket =
injector.getInstance(TicketService.class);
}
```

Above the a simple example. We can also think about ticket has its
dependency, so on and so on. Which makes Guice more convenient in
implementing Dependency Injection Pattern.

Refer the [official documents][1] for more information.

[1]: https://github.com/google/guice/wiki
