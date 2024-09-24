# Reactive Event Sourcing pattern in Java

This repository is a demo for a series of articles about implementing Event Sourcing with Akka stack in Java.

1. [Reactive Event Sourcing in Java, Part 1: Domain](https://softwaremill.com/reactive-event-sourcing-in-java-part-1-domain/) -
   tag [part_1](https://github.com/softwaremill/reactive-event-sourcing-java/releases/tag/part_1)
2. [Reactive Event Sourcing in Java, Part 2: Actor Model](https://softwaremill.com/reactive-event-sourcing-in-java-part-2-actor-model) -
   tag [part_2](https://github.com/softwaremill/reactive-event-sourcing-java/releases/tag/part_2)
3. [Reactive Event Sourcing in Java, Part 3: Service](https://softwaremill.com/reactive-event-sourcing-in-java-part-3-service) -
   tag [part_3](https://github.com/softwaremill/reactive-event-sourcing-java/releases/tag/part_3)
4. [Reactive Event Sourcing in Java, Part 4: Controller](https://softwaremill.com/reactive-event-sourcing-in-java-part-4-controller) -
   tag [part_4](https://github.com/softwaremill/reactive-event-sourcing-java/releases/tag/part_4)
5. [Reactive Event Sourcing in Java, Part 5: Event Store](https://softwaremill.com/reactive-event-sourcing-in-java-part-5-event-store) -
   tag [part_5](https://github.com/softwaremill/reactive-event-sourcing-java/releases/tag/part_5)
6. [Reactive Event Sourcing in Java, Part 6: Event Store](https://softwaremill.com/reactive-event-sourcing-in-java-part-6-empty-state) -
   tag [part_6](https://github.com/softwaremill/reactive-event-sourcing-java/releases/tag/part_6)
7. [Reactive Event Sourcing in Java, Part 7: Read Model](https://softwaremill.com/reactive-event-sourcing-in-java-part-7-read-model) -
   tag [part_7](https://github.com/softwaremill/reactive-event-sourcing-java/releases/tag/part_7)
8. [Reactive Event Sourcing in Java, Part 8: Akka Projection](https://softwaremill.com/reactive-event-sourcing-in-java-part-8-akka-projection) -
   tag [part_8](https://github.com/softwaremill/reactive-event-sourcing-java/releases/tag/part_8)



## Running the application

1. Launch db in `development` folder:

```
docker-compose -f docker-compose-jdbc.yml up    
```

2. Launch application:
```
./mvnw spring-boot:run -Dspring-boot.run.jvmArguments="--enable-preview"    
```

3. Use curl to interact with the application:

```bash
curl -XPOST -H "Content-Type: application/json" -d '{"showId":"dd062ec2-ce7b-4795-a3c8-05ec07424f2f","title":"order of pete", "maxSeats":2}' http://localhost:8080/shows
```

```bash
curl -XGET -H "Content-Type: application/json" http://localhost:8080/shows/dd062ec2-ce7b-4795-a3c8-05ec07424f2f
```

```bash
curl -XPATCH -H "Content-Type: application/json" -d '{"action":"RESERVE"}' http://localhost:8080/shows/dd062ec2-ce7b-4795-a3c8-05ec07424f2f/seats/0
```

