# Map calculation backend

A Java 11 / Spring Boot prototype for calculating geospatial radius bands from an input point, input quantity and obstacles. The implementation is paired with the Angular/Leaflet frontend in [`arpesterev/azs`](https://github.com/arpesterev/azs).

## API

`POST /api/calculate` accepts a JSON request mapped to `model/Request.java` and returns `ResultingRadiuses`. The controller permits cross-origin requests from `http://localhost:4200` for local frontend development.

The calculation service currently supports several input unit/type branches, computes radius values and processes circle and polygon obstacles.

## Run for development

Prerequisites: a Java 11 JDK and the Gradle wrapper included in this repository.

```sh
./gradlew bootRun
```

The HTTP endpoint and service are in:

- [`CalculationRequestController.java`](src/main/java/map/implementation/backend/controllers/CalculationRequestController.java)
- [`CalculationService.java`](src/main/java/map/implementation/backend/services/CalculationService.java)
- [Model classes](src/main/java/map/implementation/backend/model/)

## Important limitations

This is a prototype. The calculation and geometry code have not been independently validated for physical accuracy, coordinate handling or edge cases. **Do not use its output for safety decisions, emergency planning or engineering certification.**

The Gradle command is taken from the project configuration; it has not been run during this documentation update.
