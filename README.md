# amqp-example project

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Running Apache MQ Artemis

```shell script
docker-compose up -d
```

## Create skeleton application

```shell script
mvn io.quarkus:quarkus-maven-plugin:1.11.5.Final:create \
    -DprojectGroupId=com.redhat.example \
    -DprojectArtifactId=amqp-example \
    -Dextensions="amqp" \
    -DnoExamples
```

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:

```shell script
mvn quarkus:dev
```

or

```shell script
./mvnw compile quarkus:dev
```

## Browser

http://localhost:8080/prices.html

## Packaging and running the application

The application can be packaged using:

```shell script
./mvnw package
```

It produces the `amqp-example-1.0.0-SNAPSHOT-runner.jar` file in the `/target` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `target/lib` directory.

If you want to build an _über-jar_, execute the following command:
```shell script
./mvnw package -Dquarkus.package.type=uber-jar
```

The application is now runnable using `java -jar target/amqp-example-1.0.0-SNAPSHOT-runner.jar`.

## Creating a native executable

You can create a native executable using: 

```shell script
./mvnw package -Pnative
```

Or, if you don't have GraalVM installed, you can run the native executable build in a container using: 

```shell script
./mvnw package -Pnative -Dquarkus.native.container-build=true
```

You can then execute your native executable with: `./target/amqp-example-1.0.0-SNAPSHOT-runner`

