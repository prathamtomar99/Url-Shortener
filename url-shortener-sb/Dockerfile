# ===============================
# Stage 1: Build the Application
# ===============================
FROM eclipse-temurin:17-jdk-jammy AS build

# Set the working directory inside the container
WORKDIR /app

# 1. Copy Maven wrapper and configuration first (for caching dependencies)
COPY .mvn/ .mvn/
COPY mvnw pom.xml ./

# 2. Grant execution rights to the Maven wrapper
RUN chmod +x mvnw

# 3. Download dependencies (this layer will be cached if pom.xml doesn't change)
RUN ./mvnw dependency:go-offline

# 4. Copy the application source code
COPY src ./src

# 5. Build the application (skipping tests to speed up the build)
RUN ./mvnw clean package -DskipTests

# ===============================
# Stage 2: Run the Application
# ===============================
FROM eclipse-temurin:17-jre-jammy

# Set the working directory
WORKDIR /app

# 1. Copy the compiled JAR file from the 'build' stage
#    (We use a wildcard *.jar so we don't have to know the exact version number)
COPY --from=build /app/target/*.jar app.jar

# 2. Expose the port the app runs on
EXPOSE 8080

# 3. Define the command to run the app
ENTRYPOINT ["java", "-jar", "app.jar"]