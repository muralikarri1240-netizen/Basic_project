# Jenkins Java Pipeline Sample

This is a small Java project designed for Jenkins pipeline demonstration.

## Project structure

- `pom.xml` — Maven project configuration
- `src/main/java/com/example/App.java` — simple entry point
- `src/test/java/com/example/AppTest.java` — basic JUnit test
- `Jenkinsfile` — Declarative pipeline definition

## Jenkins pipeline

The pipeline performs:
1. Checkout
2. Build with `mvn -B clean package`
3. Run tests with `mvn -B test`
4. Archive generated JAR

## Run locally

```bash
cd c:\java-based-project
mvn clean package
```
