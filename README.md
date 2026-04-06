# Library App

## Description

Library App is a library management system built with C# and .NET 8.0. It allows users to search for patrons, manage book loans, renew memberships, and handle book returns through a console-based interface. The project is structured in layers to separate business logic, data persistence, and the user interface.

## Project Structure

- `AccelerateDevGitHubCopilot.sln`
- `src/`
  - `Library.ApplicationCore/`
    - `Library.ApplicationCore.csproj`
    - `Entities/`
      - `Author.cs`
      - `Book.cs`
      - `BookItem.cs`
      - `Loan.cs`
      - `Patron.cs`
    - `Enums/`
      - `EnumHelper.cs`
      - `LoanExtensionStatus.cs`
      - `LoanReturnStatus.cs`
      - `MembershipRenewalStatus.cs`
    - `Interfaces/`
      - `ILoanRepository.cs`
      - `ILoanService.cs`
      - `IPatronRepository.cs`
      - `IPatronService.cs`
    - `Services/`
      - `LoanService.cs`
      - `PatronService.cs`
  - `Library.Console/`
    - `Library.Console.csproj`
    - `Program.cs`
    - `ConsoleApp.cs`
    - `ConsoleState.cs`
    - `CommonActions.cs`
    - `appSettings.json`
    - `Json/`
      - `Authors.json`
      - `BookItems.json`
      - `Books.json`
      - `Loans.json`
      - `Patrons.json`
  - `Library.Infrastructure/`
    - `Library.Infrastructure.csproj`
    - `Data/`
      - `JsonData.cs`
      - `JsonLoanRepository.cs`
      - `JsonPatronRepository.cs`
- `tests/`
  - `UnitTests/`
    - `UnitTests.csproj`
    - `LoanFactory.cs`
    - `PatronFactory.cs`
    - `ApplicationCore/`
      - `LoanService/`
        - `ExtendLoan.cs`
        - `ReturnLoan.cs`
      - `PatronService/`
        - `RenewMembership.cs`

## Key Classes and Interfaces

- **`ConsoleApp`**: Manages the console user interaction flow using a state machine, handling patron search, loan details, and membership renewal.
- **Entities**: Core domain objects representing `Book`, `Patron`, `Loan`, `Author`, and `BookItem`.
- **Enums**: Define operation outcomes and statuses:
  - `LoanExtensionStatus`
  - `LoanReturnStatus`
  - `MembershipRenewalStatus`
- **Interfaces**:
  - `IPatronRepository` / `ILoanRepository`: Contracts for data access operations.
  - `IPatronService` / `ILoanService`: Contracts for business logic operations.
- **Services**:
  - `PatronService`: Handles patron-related business logic such as membership renewal.
  - `LoanService`: Handles loan-related business logic such as extending and returning loans.
- **Infrastructure**:
  - `JsonPatronRepository` / `JsonLoanRepository`: JSON file-based implementations of the repository interfaces.
  - `JsonData`: Handles loading and saving data from/to JSON files.

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/Willians167/AccelerateDevGitHubCopilot.git
   ```

2. Navigate to the project directory:
   ```bash
   cd AccelerateDevGitHubCopilot
   ```

3. Restore dependencies and build:
   ```bash
   dotnet restore
   dotnet build
   ```

4. Run the console application:
   ```bash
   dotnet run --project src/Library.Console/Library.Console.csproj
   ```

5. Run the unit tests:
   ```bash
   dotnet test
   ```

6. Follow the on-screen prompts to search for patrons, view loan details, extend loans, return books, and renew memberships.

## License

This project is licensed under the MIT License.
