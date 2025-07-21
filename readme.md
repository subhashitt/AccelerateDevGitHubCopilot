# Library App

A comprehensive library management system built with .NET 8.0 that provides functionality for managing books, patrons, and loans through a console-based interface.

## Description

The Library App is a multi-layered application that demonstrates clean architecture principles and dependency injection patterns. It enables library staff to search for patrons, manage book loans, extend loan periods, return books, and renew patron memberships. The application uses JSON files as a data store and provides a user-friendly console interface for all operations.

Key features include:
- Patron search and management
- Book loan tracking and management
- Loan extension capabilities
- Book return processing
- Membership renewal functionality
- Comprehensive unit testing

## Project Structure

```
AccelerateDevGitHubCopilot/
├── AccelerateDevGitHubCopilot.sln
├── src/
│   ├── Library.ApplicationCore/
│   │   ├── Library.ApplicationCore.csproj
│   │   ├── Entities/
│   │   │   ├── Author.cs
│   │   │   ├── Book.cs
│   │   │   ├── BookItem.cs
│   │   │   ├── Loan.cs
│   │   │   └── Patron.cs
│   │   ├── Enums/
│   │   │   ├── EnumHelper.cs
│   │   │   ├── LoanExtensionStatus.cs
│   │   │   ├── LoanReturnStatus.cs
│   │   │   └── MembershipRenewalStatus.cs
│   │   ├── Interfaces/
│   │   │   ├── ILoanRepository.cs
│   │   │   ├── ILoanService.cs
│   │   │   ├── IPatronRepository.cs
│   │   │   └── IPatronService.cs
│   │   └── Services/
│   │       ├── LoanService.cs
│   │       └── PatronService.cs
│   ├── Library.Infrastructure/
│   │   ├── Library.Infrastructure.csproj
│   │   └── Data/
│   │       ├── JsonData.cs
│   │       ├── JsonLoanRepository.cs
│   │       └── JsonPatronRepository.cs
│   └── Library.Console/
│       ├── Library.Console.csproj
│       ├── Program.cs
│       ├── ConsoleApp.cs
│       ├── ConsoleState.cs
│       ├── CommonActions.cs
│       ├── appSettings.json
│       └── Json/
│           ├── Authors.json
│           ├── Books.json
│           ├── BookItems.json
│           ├── Loans.json
│           └── Patrons.json
└── tests/
    └── UnitTests/
        ├── UnitTests.csproj
        ├── LoanFactory.cs
        ├── PatronFactory.cs
        └── ApplicationCore/
            ├── LoanService/
            │   ├── ExtendLoan.cs
            │   └── ReturnLoan.cs
            └── PatronService/
```

## Key Classes and Interfaces

### Entities
- **Author**: Represents book authors with ID and name
- **Book**: Contains book information including title, author, genre, ISBN, and cover image
- **BookItem**: Represents physical copies of books with condition and acquisition date
- **Loan**: Tracks book loans with dates, patron, and return status
- **Patron**: Library members with membership details and loan history

### Services
- **LoanService**: Handles loan operations including extending and returning books
- **PatronService**: Manages patron membership renewals and validations

### Repositories
- **ILoanRepository/JsonLoanRepository**: Data access layer for loan operations
- **IPatronRepository/JsonPatronRepository**: Data access layer for patron operations

### Enums
- **LoanExtensionStatus**: Status codes for loan extension operations
- **LoanReturnStatus**: Status codes for book return operations
- **MembershipRenewalStatus**: Status codes for membership renewal operations
- **CommonActions**: Available user actions in the console interface

### Infrastructure
- **JsonData**: Centralized data loading and management from JSON files
- **ConsoleApp**: Main application controller managing user interface flow
- **ConsoleState**: Enum defining different application states

## Usage

### Prerequisites
- .NET 8.0 SDK
- Visual Studio 2022 or VS Code

### Running the Application

1. Clone the repository
2. Navigate to the solution directory:
   ```
   cd AccelerateDevGitHubCopilot
   ```
3. Build the solution:
   ```
   dotnet build
   ```
4. Run the console application:
   ```
   dotnet run --project src/Library.Console
   ```

### Running Tests

Execute the unit tests using:
```
dotnet test
```

### Application Workflow

1. **Patron Search**: Start by searching for patrons by name
2. **Patron Selection**: Choose from matching patrons to view details
3. **Loan Management**: View patron's current loans and perform operations:
   - Extend loan periods
   - Mark books as returned
   - Renew patron membership
4. **Navigation**: Use intuitive keyboard shortcuts to navigate between functions

### Configuration

The application uses `appSettings.json` to configure JSON file paths:
```json
{
    "JsonPaths": {
        "Authors": "Json/Authors.json",
        "Books": "Json/Books.json",
        "BookItems": "Json/BookItems.json",
        "Patrons": "Json/Patrons.json",
        "Loans": "Json/Loans.json"
    }
}
```

## License

This project is licensed under the MIT License. See the LICENSE file for details.
