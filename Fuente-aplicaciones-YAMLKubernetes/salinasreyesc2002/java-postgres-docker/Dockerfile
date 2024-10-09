# Usar una imagen base de Java
FROM openjdk:17-jdk-alpine AS build

# Establecer el directorio de trabajo
WORKDIR /app

# Copiar el pom.xml y mvnw
COPY pom.xml ./
COPY mvnw ./
COPY .mvn ./.mvn

# Hacer mvnw ejecutable
RUN chmod +x mvnw

# Copiar el código fuente
COPY src ./src

# Ejecutar la construcción de Maven
RUN ./mvnw clean package -DskipTests

# Usar una imagen base de Java para el runtime
FROM openjdk:17-jdk-alpine

# Establecer el directorio de trabajo
WORKDIR /app

# Copiar el JAR construido desde la etapa de construcción
COPY --from=build /app/target/*.jar app.jar

# Comando para ejecutar la aplicación
ENTRYPOINT ["java","-jar","app.jar"]