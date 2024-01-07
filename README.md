## DNA Engineering Full-Stack Assignment
Build a CSV Parser.

## Demo Video
[Watch Demo Video](lien-vers-votre-video-sur-google-drive)

## Backend
### Approach
## Employee Model
The `Employee` class is a simple Java model representing the structure of an employee. It includes fields for the employee's ID, name, job title, and salary. The use of Lombok annotations (`@Getter`, `@Setter`, `@NoArgsConstructor`, `@AllArgsConstructor`, `@ToString`) helps reduce boilerplate code.

## CsvParser Interface
The `CsvParser` interface defines a method `parseCsv` that takes an `InputStream` as input and returns a list of `Employee` objects. This interface provides a contract for different implementations of CSV parsers.

## CsvParserImpl Implementation
The `CsvParserImpl` class implements the `CsvParser` interface. It uses a `BufferedReader` to read the CSV data line by line, skipping the header. It then parses each line into `Employee` objects and adds them to a list.

## ParserService
The `ParserService` class is responsible for handling the logic related to CSV file processing. It uses the `CsvParser` to parse the CSV file and stores the data in a list of `Employee` objects. It provides methods to retrieve all employees and calculate average salaries based on job titles.

## ParseController
The `ParseController` is a Spring MVC controller that handles HTTP requests related to CSV parsing. It uses the `ParserService` to upload, process, and retrieve data. It includes endpoints for uploading a CSV file, getting a list of all employees, and retrieving average salaries by job title.

### Instructions 

- **Instructions to Run the Backend**: mvn spring-boot:run
        - The backend server should be accessible at http://localhost:8080.
- **Instructions to Run Unit Tests**: mvn test  
## Unit Tests

### EmployeeTest
A unit test for the `Employee` class ensures that an `Employee` object is created correctly with the expected values.

### CsvParserImplTest
A unit test for the `CsvParserImpl` class validates that the `parseCsv` method correctly returns a list of `Employee` objects from a valid CSV input file.

### ParserServiceTest
Unit tests for the `ParserService` class validate the correct parsing and processing of a CSV file. One test checks that the upload and processing of a valid input file result in the correct number of stored employees. Another test ensures that the calculation of average salaries returns the expected map of job titles and their corresponding average salaries.


(./static/JunitTests.png)

## Test Endpoints

### Using Postman
#### 1. Upload CSV
- **Method:** `POST`
- **Endpoint:** `http://localhost:8080/api/csvparser/upload`
- **Description:** Upload a CSV file for processing.
(./static/upload.png)

#### 2. Get All Employees
- **Method:** `GET`
- **Endpoint:** `http://localhost:8080/api/csvparser/employees`
- **Description:** Retrieve a list of all employees.
(./static/employeesInformations.png)

#### 3. Get Results (Average Salaries)
- **Method:** `GET`
- **Endpoint:** `http://localhost:8080/api/csvparser/results`
- **Description:** Retrieve average salaries based on job titles.
(./static/averageSalary.png)
 

## Table of content
- [Prerequisites](#prerequisites)
- [Before We begin](#before-we-begin)
- [Assignment](#assignment)
- [What we expect](#what-we-expect)
- [Bonus points](#bonus-points)

## Prerequisites
- Java 17
- Node Js v20.10.0

## Before we begin
- In this assignment, you will be asked to write, and test your code.
- Make sure you respect clean code guidelines.
- Read the assignment carefully.

## Description
You are invited to create a CSV parser using Java/Spring Boot, and build UI to display results using Next.js/React.

## Assignment

### Backend (CSV Parser)

#### Tasks

- Write a service in Java that will read and process the attached CSV(comma separated values) file at `data/employees.csv`.

- This service should read, extract and process data in a suitable data structure.

- Process this data to return the list of employees and a summary indicating the average salary for each job title.

### Frontend

#### Tasks
Implement a simple user interface that will allow the user to upload the file and display the results of your processing.

#### Interfaces

Respect the following design flow:

![Frontend interfaces](./static/interfaces.png)

- **Interface-1**: Contain an upload button.
- **Interface-2**: The Process button is added when you choose a file.
- **Interface-3**: 2 Tables showing the processing results.

**Table 1**: Employee information, displays a paginated list of employees.

**Table 2**: Jobs summary, displays for each job title, the average salary for employees.

## What we expect
- Write a concise, easy to understand code.
- Use good practices.
- Write unit tests for your java code.
- Append to this README your approach and provide instructions to run your project.

## Bonus points
- Implement your own CSV file parser instead of using a library.
- Use design patterns.