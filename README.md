# ASP.NET Core API with JWT Bearer Token Authentication

This repository contains an ASP.NET Core 3.1 Web API project demonstrating authentication and authorization using JWT (JSON Web Tokens) Bearer Tokens. The project includes basic CRUD operations with six types of data, utilizing a Master-Detail approach to manage complex data relationships effectively.

## Features

- **JWT Bearer Token Authentication**: Secure API endpoints with JSON Web Tokens for authentication and authorization.
- **ASP.NET Core 3.1**: Built using the .NET Core 3.1 framework for a modern, high-performance API.
- **CRUD Operations**: Supports Create, Read, Update, and Delete operations for managing data.
- **Master-Detail Approach**: Implements a Master-Detail design pattern to handle related data entities.
- **Data Types**: Manages six different types of data to demonstrate versatile data handling.

## Technologies Used

- **ASP.NET Core 3.1**: Framework for building web APIs.
- **JWT (JSON Web Tokens)**: Token-based authentication for securing API endpoints.
- **Entity Framework Core**: ORM for managing database interactions.
- **SQL Server**: Database system for storing and managing data.

## Getting Started

### Prerequisites

Ensure you have the following installed:

- [Microsoft Visual Studio](https://visualstudio.microsoft.com/) with support for ASP.NET Core
- [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet/3.1)
- [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) or a compatible database system

### Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/ChowdhuryMunir/AspDotNetCoreApi_WithJWTBearerToken_Authentication.git
   cd AspDotNetCoreApi_WithJWTBearerToken_Authentication
   ```

2. **Open the Project**
   - Open the solution file (`.sln`) in Visual Studio.

3. **Update Database Connection String**
   - Open the `appsettings.json` file and update the connection string:
     ```json
     "ConnectionStrings": {
       "DefaultConnection": "Server=your_server;Database=your_database;User Id=your_user;Password=your_password;"
     }
     ```

4. **Configure JWT Settings**
   - Open the `appsettings.json` file and configure JWT settings:
     ```json
     "Jwt": {
       "Key": "your_secret_key",
       "Issuer": "your_issuer",
       "Audience": "your_audience"
     }
     ```

5. **Build the Project**
   - Restore NuGet packages and build the project using Visual Studio.

6. **Apply Migrations**
   - Open the Package Manager Console and run:
     ```powershell
     Update-Database
     ```

7. **Run the Application**
   - Start the application using Visual Studio. The API will be available at `http://localhost:your_port`.

## Project Structure

- **Controllers**: Contains API controllers for handling requests and responses.
- **Models**: Defines the data entities and DTOs (Data Transfer Objects).
- **Data**: Includes the DbContext and Entity Framework configurations.
- **Services**: Implements business logic and JWT authentication services.
- **Configurations**: Contains settings for JWT and other configurations.
- **Migrations**: Database migrations for initializing and updating the database schema.

## API Endpoints

- **Authentication**:
  - `POST /api/auth/login`: Authenticate user and obtain a JWT token.
  
- **CRUD Operations** (for Master-Detail entities):
  - **Master Entity**:
    - `GET /api/masters`: Retrieve all master entities.
    - `POST /api/masters`: Create a new master entity.
    - `PUT /api/masters/{id}`: Update an existing master entity.
    - `DELETE /api/masters/{id}`: Delete a master entity.
  - **Detail Entity**:
    - `GET /api/masters/{masterId}/details`: Retrieve all detail entities for a specific master entity.
    - `POST /api/masters/{masterId}/details`: Create a new detail entity.
    - `PUT /api/masters/{masterId}/details/{id}`: Update an existing detail entity.
    - `DELETE /api/masters/{masterId}/details/{id}`: Delete a detail entity.

## Usage

1. **Obtain a JWT Token**: Use the `/api/auth/login` endpoint with valid credentials to receive a JWT token.
2. **Authenticate Requests**: Include the JWT token in the `Authorization` header of subsequent requests as a Bearer token.
3. **Perform CRUD Operations**: Use the appropriate endpoints to manage master and detail entities.

## Contributing

Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -m 'Add new feature'`).
4. Push the branch (`git push origin feature/your-feature`).
5. Open a pull request with a description of your changes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For questions or feedback, please contact [MunirchowdhurySaif](https://github.com/chowdhuryMunir).
