# Hoen Scanner Microservice

A Dropwizard microservice developed for Skyscanner to search for hotels and car rentals in the Hoen Archipelago.

## Features

- **Models:** Jackson `@JsonProperty` annotated `Search` and `SearchResult` classes.
- **Resource Endpoint:** `@Path("/search")` POST endpoint returning filtered hotels and rental cars by city.
- **Data Loaders:** Automatically loads `rental_cars.json` and `hotels.json` from resources into a unified search index upon startup.

## Running the Application

1. **Build the microservice:**
   ```bash
   mvn clean package
   ```

2. **Start the Dropwizard server:**
   ```bash
   java -jar target/hoen-scanner-1.0-SNAPSHOT.jar server src/main/resources/config.yml
   ```

3. **Test the Endpoint:**
   Send an HTTP POST request to `http://localhost:8080/search`:
   ```json
   {
     "city": "petalborough"
   }
   ```
