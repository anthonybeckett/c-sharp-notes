# .Net Notes

# Contents
- [Contents](#contents)
- [Documentation & Learning Resources](#documentation--learning-resources)
- [Oh My Posh](#oh-my-posh)
- [VS Code Extensions](#vs-code-extensions)
- [Useful Commands](#useful-commands)
- [Setup New Project Notes](#setup-new-project-notes)
- [Setup Secure Configuration](#setup-secure-configuration)
    - [Initial Config](#initial-config) 
    - [Setting Up Environment Variables Linux](#setting-up-environment-variables-linux)
    - [Accessing Environment Variables](#accessing-environment-variables)
    - [Azure Key Vault On Ubuntu]()
- [C# Topics](#c-topics)
    - [Extension Methods](#extension-methods)
- [Dotnet CLI Tips And References](#dotnet-cli-tips-and-references)
    - [Create A New Solution](#create-a-new-solution) 
    - [Add New Web API Project](#add-new-web-api-project)
    - [Add New Class Library Project](#add-new-class-library-project)
    - [Link Projects To Solution](#link-projects-to-solution)
    - [Link Projects As Dependencies](#link-projects-as-dependencies)
    - [Create A Migration In Another Project Folder](#create-a-migration-in-another-project-folder)
- [Mapping Custom Endpoints For Razor Pages](#mapping-custom-endpoints-for-razor-pages)
- [Creating A Library For Shared Code](#creating-a-library-for-shared-code)
- [Database](#database)
    - [Setup SQLite](#setup-sqlite)
- [Docker](#docker)
    - [Example Docker Compose With MS SQL Database](#example-docker-compose-with-ms-sql-database)
    - [Setting Up Docker For Production & Development Environments](#setting-up-docker-for-production--development-environments)
    - [Docker Issues](#docker-issues)
    - [Docker Images & Tags](#docker-images--tags)
- [Architecture](#architecture)
    - [Abstracting Dependency Injection Away From Program.cs](#abstracting-dependency-injection-away-from-programcs)
- [Clean Architecture & DDD](#clean-architecture--ddd)
    - [Introduction](#introduction)
    - [Layer Breakdown Examples](#layer-breakdown-examples)
    - [Implementing A Repository From Interface With DI](#implementing-a-repository-from-interface-with-di)
    - [Unit & Integration Testing](#unit--integration-testing) 
    - [Overriding Validation Filter Attribute](#overriding-validation-filter-attribute)
- [API](#api)
    - [Setup Authentication With Identity](#setup-authentication-with-identity)
    - [Setup Authentication With Identity For Older Versions](#setup-authentication-with-identity-for-older-versions)
    - [Example CRUD Controller using .NET API](#example-crud-controller-using-net-api)
    - [Using REST Client Extension For API Calls](#using-rest-client-extension-for-api-calls)
    - [Using HTTP-Repl In The Command Line](#using-http-repl-in-the-command-line)
    - [Middleware](#middleware)
    - [Extracting Custom Middleware Outside Program.cs](#extracting-custom-middleware-outside-programcs)
    - [Setting Up Swagger](#setting-up-swagger)
    - [Adding Swagger UI Or Scalar In Dotnet 9](#adding-swagger-ui-or-scalar-in-dotnet-9)
    - [Implementing XSRF Tokens](#implementing-xsrf-tokens)
- [Authentication & Authorisation With Identity & Razor Pages](#authentication--authorisation-with-identity--razor-pages)
    - [Install](#install)
    - [Configure The Database Connection](#configure-the-database-connection)
    - [Customise The User Account Data](#customise-the-user-account-data)
    - [Two Factor Authentication](#two-factor-authentication)
    - [Useful Identity Links](#other-useful-identity-links)
- [Entity Framework Core](#entity-framework-core)
    - [Adding NuGet Packages](#adding-nuget-packages)
    - [Updating packages](#updating-packages)
    - [Adding A Context](#adding-a-context)
    - [Create And Run Migration](#create-and-run-migration)
    - [Example CRUD service using EF Core](#example-crud-service-using-ef-core)
    - [Seeding The Database](#seeding-the-database)
    - [Reverse-engineer from an existing database](#reverse-engineer-from-an-existing-database)
    - [MSSQL Connection String Example](#mssql-connection-string-example)
- [Sending Emails](#sending-emails) 
    - [Getting Started Example](#getting-started-example)
    - [Setting Up Mailpit](#setting-up-mailpit)
    - [Building Text Only Based Emails](#building-text-only-based-emails)
    - [Using Fluid To Generate HTML Template Emails](#using-fluid-to-generate-html-template-emails)
    - [Other Template Libraries](#other-template-libraries)
    - [MJML](#mjml)
    - [Understanding SPF, DKIM, and DMARC for Email Sending](#understanding-spf-dkim-and-dmarc-for-email-sending)
- [Dotnet MAUI](#dotnet-maui)
    - [Community ToolKit](#community-toolkit)
- [Optimising MSSQL Queries](#optimising-mssql-queries)
- [Unit testing](#unit-testing)
    - [Libraries](#libraries)
- [Integration Testing](#integration-testing)
    - [Setup Notes](#setup-notes)
- [CI/CD](#cicd)
    - [Setting Up GitHub Actions](#setting-up-github-actions)
    - [GitHub Marketplace](#github-marketplace)
    - [Deploying A DotNet Application Example](#deploying-a-dotnet-application-example)
    - [Adding Sensitive Data through Secrets](#adding-sensitive-data-through-secrets)
- [Publishing A Project](#publishing-a-project)
    - [Deploying To Linux](#deploying-to-linux)
    - [Setting Up A Jenkins Pipeline](#setting-up-a-jenkins-pipeline) 
- [Cool Nuget Packages](#cool-nuget-packages)

## Documentation & Learning Resources

Documentation - https://learn.microsoft.com/en-us/aspnet/core/introduction-to-aspnet-core?view=aspnetcore-8.0

Learning - https://learn.microsoft.com/en-us/training/browse/

Dotnet Stuff - https://dotnet.microsoft.com/

Awesome video series - https://dotnet.microsoft.com/en-us/learn/videos?wt.mc_id=dotnetconfstudent_dotnetvids_video_studios

Entity Framework Core - https://learn.microsoft.com/en-us/ef/

## Oh My Posh

This is just the set up guide to make powershell look better like `Oh My Zsh` in linux.

https://ohmyposh.dev/

## VS Code Extensions

- .NET Extension Pack
- .NET Install Tool
- C# Dev Kit
- C#
- C# Extensions (JosKreativ)
- NuGet Gallary (pcislo)
- Rest Client (Works with .http files to send API calls quickly)

## Useful Commands

```bash
# Run the application
dotnet run watch

# Run migrations
dotnet ef database update
```

## Setup New Project Notes

When using .NET api, add MapControllers() to the program.cs to enable controllers

```c#
app.UseEndpoints(endpoints => {
    endpoints.MapRazorPages();

    endpoints.MapControllers();
});

// Or if not using a razor frontend

app.MapControllers();

```  

## Setup Secure Configuration

### Initial Config

Do Not Store Secrets in `appsettings.json`

- Keep appsettings.json for non-sensitive defaults.
- Use placeholders for secrets (e.g., `"ConnectionString": "<your-database-connection>"`).

Use `dotnet user-secrets` for Local Development

This tool securely stores secrets outside your project folder.

```bash
dotnet user-secrets init
dotnet user-secrets set "ConnectionStrings:Default" "your-connection-string"
```
Access it in `Program.cs`

```c#
builder.Configuration.AddUserSecrets<Program>();
```

### Setting Up Environment Variables Linux

To set up environment variables in Linux we can add them to `.bashrc` or `/etc/environment`
depending if we want them to be local user based or system wide.

Example of adding the variable in the file

```bash
ConnectionStrings__Default="Server=myserver;Database=mydb;User Id=myuser;Password=mypassword;"
```

### Accessing Environment Variables

In `program.cs`

```C#
builder.Configuration.AddEnvironmentVariables();
```

In our setup if abstracted or `Program.cs`

```C#
var connectionString = builder.Configuration["ConnectionStrings:Default"];
Console.WriteLine($"DB Connection String: {connectionString}");
```

### Azure Key Vault On Ubuntu

Azure Key Vault stores secrets (e.g., API keys, connection strings) securely. Your Ubuntu-hosted .NET app can access Key Vault to fetch these secrets at runtime instead of storing them in appsettings.json or environment variables.

- Register Your Application in Azure
    - Go to Azure Portal → Azure Active Directory → App registrations.
    - Click "New registration", name your app, and select "Single tenant".
    - Copy the Application (client) ID and Directory (tenant) ID.

- Create an Azure Key Vault
    - Go to Azure Portal → Key Vaults.
    - Click "Create", select a resource group, name your Key Vault, and create it.
    - Inside the Key Vault, go to Secrets → Generate/Import → Add a new secret (e.g., DatabaseConnectionString).

- Grant Access to Your Application
    - In Key Vault, go to Access policies → Add Access Policy.
    - Select "Get" and "List" for secrets.
    - Under "Principal", search for your app registration name and select it.
    - Click Save.

Install Required NuGet Packages in Your .NET App

Run this in your Ubuntu machine:  

```bash
dotnet add package Azure.Identity
dotnet add package Azure.Security.KeyVault.Secrets
```

Modify `Program.cs` to use Key Vault:

```C#
using Azure.Identity;
using Azure.Security.KeyVault.Secrets;

var builder = WebApplication.CreateBuilder(args);

// Load environment variables
builder.Configuration.AddEnvironmentVariables();

// Get Azure Key Vault URL from environment variable
string keyVaultUrl = builder.Configuration["AZURE_KEYVAULT_URL"];

// Add Azure Key Vault to configuration
if (!string.IsNullOrEmpty(keyVaultUrl))
{
    var credential = new DefaultAzureCredential();
    builder.Configuration.AddAzureKeyVault(new Uri(keyVaultUrl), credential);
}

var app = builder.Build();

// Fetch secret from Key Vault
var secretClient = new SecretClient(new Uri(keyVaultUrl), new DefaultAzureCredential());
var secret = secretClient.GetSecret("DatabaseConnectionString");

Console.WriteLine($"Database Connection String: {secret.Value.Value}");

app.Run();
```

On your Ubuntu machine, set the Key Vault URL:

```bash
export AZURE_KEYVAULT_URL="https://your-keyvault-name.vault.azure.net/"
```

## C# Topics

### Extension methods

Sometimes we need to extend the functionality of classes we do not have the source code for or
are sealed so we cannot inherit from them. To do this we can use extension methods.  

We need a static class with one or more static methods within. For the methods argument, the first
parameter needs to start with `this` followed by the class e.g. `String` then give it a name.

Any following arguments will now work as usual when calling the method.

```C#
public static class StringExtensions
{
    public static string Shorten(this String str, int numberOfWords)
    {
        if (numberOfWords < 0) {
            throw new ArgumentOutOfRangeException("numberOfWords should be greater than 0");
        }

        if (numberOfWords == 0) {
            return "";
        }

        var words = str.Split(' ');

        if (words.Length <= numberOfWords) {
            return str;
        }

        return string.Join(" ", words.Take(numberOfWords));
    }
}
```

## Dotnet CLI Tips And References

### Create A New Solution

To create a new sln for all our projects, we can run the following.

```bash
dotnet new sln -o ${PROJECT_NAME}
```

### Add New Web API Project

```bash
dotnet new webapi -o ProjectName.Api
```

### Add New Class Library Project

```bash
dotnet new classlib -o ProjectName.Application
```

### Link Projects To Solution

This is a fast way to link all projects to a solution

```bash
dotnet sln add (ls -r **\*.csproj)
```

### Link Projects As Dependencies

This example adds two projects as dependencies.

```bash
dotnet add ./ProjectName.Api reference ./ProjectName.Application ./ProjectName.Infrastructure
```

### Create A Migration In Another Project Folder

This command is useful when it comes to DDD or multiple projects when you want to generate
a migration from our API project but place it in the Infrastructure with our context etc.

```bash
dotnet ef --startup-project ./ApartmentBooking.Api/ApartmentBooking.Api.csproj migrations add MyMigration --output-dir Migrations --project ./ApartmentBooking.Infrastructure/ApartmentBooking.Infrastructure.csproj
```

## Mapping Custom Endpoints For Razor Pages

This can be done in `Startup.cs` but is a bit messy and better to be done in a controller.

```C#
    app.UseEndpoints(endpoints => {
        endpoints.MapRazorPages();

        endpoints.MapGet("/products", context => {
            var products = app.ApplicationServices.GetService<JsonFileProductService>().GetProducts()

            var json = JsonSerializer.Serialize<IEnumberable<Product>>(products);

            return context.Response.WriteAsync(json);
        })
    });
```

## Creating A Library For Shared Code

Right click on the solution and click Add -> New Project.

Search for library.

Move code over and update the namespaces.

Right click on the project you want to insert it into and add as a dependency to be able to import it.

## Database

### Setup SQLite

Create a project then add the following packages to get it running with Entity Framework Core

```bash
dotnet add package Microsoft.EntityFrameworkCore
dotnet add package Microsoft.EntityFrameworkCore.Sqlite
dotnet add package Microsoft.EntityFrameworkCore.Tools
```

Add a connection string field to your `AppSettings.json`

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Data Source=appsettings.db"
  }
}
```

Create a context to use. The connection string can be moved to 

```C#
public class AppDbContext : DbContext
{
    public DbSet<User> Users => Set<User>();
    private readonly string _connectionString;

    public AppDbContext(string connectionString)
    {
        _connectionString = connectionString;
    }

    protected override void OnConfiguring(DbContextOptionsBuilder options)
        => options.UseSqlite(_connectionString);
}
```

## Docker

### Example Docker Compose With MS SQL Database

```yml
services:
  apartmentbooking.api:
    image: ${DOCKER_REGISTRY-}apartmentbookingapi
    container_name: ApartmentBooking.Api
    build:
      context: .
      dockerfile: ApartmentBooking.Api/Dockerfile
    depends_on:
        - apartmentbooking-db

  apartmentbooking-db:
    image: mcr.microsoft.com/mssql/server:latest
    container_name: ApartmentBooking.Db
    user: root
    environment:
        - ACCEPT_EULA=true
        - MSSQL_SA_PASSWORD=Passw0rd!
        - MSSQL_PID=Express 
    volumes:
        - ./data:/var/opt/mssql/data
    ports:
        - 1433:1433
```

This works with this connection string in the json config file

```json
{
  "ConnectionStrings": {
    "Database" : "Server=apartmentbooking-db,1433;Database=apartmentbooking;User Id=sa;Password=Passw0rd!;TrustServerCertificate=True;Encrypt=False;"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  }
}
```

### Setting Up Docker For Production & Development Environments

In this section, we will set up a DotNet application with docker to use in a production environment and a development environment with hot reloading.

To start, lets make a `Dockerfile` for the production environment

```Dockerfile
FROM mcr.microsoft.com/dotnet/sdk:9.0-alpine AS base
USER $APP_UID
WORKDIR /app
EXPOSE 8080
EXPOSE 8081

FROM mcr.microsoft.com/dotnet/sdk:9.0-alpine AS build
ARG BUILD_CONFIGURATION=Release
WORKDIR /src
COPY ["DockerExample/DockerExample.csproj", "DockerExample/"]
RUN dotnet restore "DockerExample/DockerExample.csproj"
COPY . .
WORKDIR "/src/DockerExample"
RUN dotnet build "./DockerExample.csproj" -c $BUILD_CONFIGURATION -o /app/build

FROM build AS publish
ARG BUILD_CONFIGURATION=Release
RUN dotnet publish "./DockerExample.csproj" -c $BUILD_CONFIGURATION -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "DockerExample.dll"]
```

We can now add this to a `docker-compose.yml` file normally created in the root of the project.

```yml
services:
  dockerexample:
    build:
      context: .
      dockerfile: DockerExample/Dockerfile
    ports:
      - "5000:8080"
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
```

Next, we can create an override file which will automatically run our Development environment.

Create a `docker-compose.override.yml` in your project root. We want to use the SDK directly and run the watch command against our app.

```yml
services:
  dockerexample:
    image: mcr.microsoft.com/dotnet/sdk:9.0-alpine
    command: dotnet watch  --project DockerExample run --no-launch-profile
    ports:
      - "5001:8080"
    volumes:
      - .:/app
    working_dir: /app
    environment:
      - DOTNET_USE_POLLING_FILE_WATCHER=1 
      - ASPNETCORE_ENVIRONMENT=Development
```

### Docker Issues

As of the time of writing this, I ran into some issues with the `mcr.microsoft.com/dotnet/sdk:9.0` image as it would not find the SDK when trying to build or run a container.

At first I tried replacing it with `mcr.microsoft.com/dotnet/sdk:9.0-azurelinux3.0` which would run the first time, but then complain about a user not existing in the `passwd` file on the second run.

Secondly I just replaced this and used the `mcr.microsoft.com/dotnet/sdk:9.0-alpine` as a workaround until the original 9.0 image is working again.

### Docker Images & Tags

Docker images and tags can be found here - https://mcr.microsoft.com/en-us/artifact/mar/dotnet/sdk/tags

## Architecture

### Abstracting Dependency Injection Away From Program.cs

Create an Extension Method for Dependency Injection

Create a static class with an extension method for IServiceCollection. This class should handle all your service registrations.

Example: `DependencyInjection.cs`

```C#
using Microsoft.Extensions.DependencyInjection;

namespace YourNamespace
{
    public static class DependencyInjection
    {
        public static IServiceCollection AddApplicationServices(this IServiceCollection services)
        {
            // Register your services here
            services.AddScoped<IMyService, MyService>();
            services.AddTransient<IOtherService, OtherService>();
            services.AddSingleton<ISingletonService, SingletonService>();

            // Add any other configurations or third-party libraries
            services.AddHttpClient();

            return services;
        }
    }
}
```

Include the Extension Method in Program.cs

In your Program.cs, call the extension method to apply the service registrations.

Example: `Program.cs` (for .NET 6+ minimal hosting model)

```C#
using YourNamespace;

var builder = WebApplication.CreateBuilder(args);

// Add services to the container.
builder.Services.AddApplicationServices(); // Call your extension method here

var app = builder.Build();

// Configure the HTTP request pipeline (if necessary)
app.MapControllers();

app.Run();
```

Organize Further if Needed

If you have a large number of services or different layers (e.g., repositories, services, external integrations), you can create multiple extension methods for better separation of concerns.

Example: Multiple Files

`ServiceExtensions.cs`:
```C#
public static class ServiceExtensions
{
    public static IServiceCollection AddBusinessServices(this IServiceCollection services)
    {
        services.AddScoped<IBusinessService, BusinessService>();
        return services;
    }
}
```

`RepositoryExtensions.cs`:

```C#
public static class RepositoryExtensions
{
    public static IServiceCollection AddRepositories(this IServiceCollection services)
    {
        services.AddScoped<IRepository, Repository>();
        return services;
    }
}
```

Include in `Program.cs`:

```C#
builder.Services
    .AddBusinessServices()
    .AddRepositories();
```

## Clean Architecture & DDD

### Introduction

Clean Architecture and Domain-Driven Design (DDD) help structure applications to be maintainable, testable, and scalable. 
Both patterns emphasize separation of concerns, where:

- Clean Architecture ensures that dependencies flow from outer layers (infrastructure, UI) toward inner layers (domain, business logic).
- DDD helps model business logic using domain-driven principles like entities, aggregates, value objects, repositories, and services.

Clean Architecture Layers  

A Clean Architecture project typically consists of the following layers:

- Domain Layer (Core Business Logic - DDD)
    - Entities, Value Objects, Aggregates, Domain Events, Repositories (Interfaces)
- Application Layer (Use Cases)
    - DTOs, Application Services, Query & Command Handlers, Validation, Mediators
- Infrastructure Layer (External Dependencies)
    - Repositories (Implementations), Persistence, Email, Logging, External APIs, Identity
- Presentation Layer (User Interaction)
    - Controllers (API, MVC), Views, gRPC, GraphQL, etc.

Each layer depends only on the layers below it (dependencies flow inward).

Folder & File Structure Example

```mathematica
/MyProject
│── src/
│   ├── MyProject.Domain/
│   │   ├── Entities/
│   │   ├── ValueObjects/
│   │   ├── Aggregates/
│   │   ├── Events/
│   │   ├── Repositories/
│   │   ├── Exceptions/
│   │   ├── Enums/
│   │   ├── Specifications/
│   │   └── SharedKernel/
│   ├── MyProject.Application/
│   │   ├── DTOs/
│   │   ├── Services/
│   │   ├── Commands/
│   │   ├── Queries/
│   │   ├── Handlers/
│   │   ├── Validation/
│   │   └── Interfaces/
│   ├── MyProject.Infrastructure/
│   │   ├── Persistence/
│   │   ├── Repositories/
│   │   ├── Email/
│   │   ├── Logging/
│   │   ├── Identity/
│   │   ├── APIs/
│   │   ├── Configurations/
│   │   └── Services/
│   ├── MyProject.Presentation/
│   │   ├── API/
│   │   ├── Controllers/
│   │   ├── Filters/
│   │   ├── Middleware/
│   │   ├── Views/ (if MVC)
│   │   ├── gRPC/GraphQL/
│   │   └── Models/
│── tests/
│   ├── MyProject.UnitTests/
│   ├── MyProject.IntegrationTests/
│── MyProject.sln

```

### Layer Breakdown Examples

Domain Layer (Core Business Logic):

- Contains: Entities, Aggregates, Value Objects, Domain Events, Business Rules, Interfaces.
- Does NOT include: Infrastructure (DB, API calls, etc.).

Entities (Core Domain Objects)

```C#
public class Order
{
    public Guid Id { get; private set; }
    public List<OrderItem> Items { get; private set; } = new();
    public OrderStatus Status { get; private set; }

    public Order() { }

    public Order(Guid id, List<OrderItem> items)
    {
        Id = id;
        Items = items;
        Status = OrderStatus.Pending;
    }

    public void MarkAsShipped()
    {
        if (Status != OrderStatus.Pending)
            throw new InvalidOperationException("Order must be pending to ship.");

        Status = OrderStatus.Shipped;
    }
}

```  

Value Objects (Immutable Business Concepts):

```C#
public class Money
{
    public decimal Amount { get; }
    public string Currency { get; }

    public Money(decimal amount, string currency)
    {
        if (amount < 0) throw new ArgumentException("Amount cannot be negative.");
        Amount = amount;
        Currency = currency;
    }
}
```

Repository Interface (Abstraction for Infrastructure):

```C#
public interface IOrderRepository
{
    Task<Order> GetByIdAsync(Guid orderId);
    Task SaveAsync(Order order);
}
```

Application Layer (Use Cases, CQRS, Services):

- Contains: DTOs, Commands, Queries, Use Cases, Handlers, Validation.
- Does NOT include: Business logic or direct DB access.

DTOs (Data Transfer Objects):

```C#
public class CreateOrderDto
{
    public List<OrderItemDto> Items { get; set; }
}
```

Commands (Write Operations):

```C#
public class CreateOrderCommand : IRequest<Guid>
{
    public List<OrderItemDto> Items { get; set; }
}
```

Command Handler (CQRS - Write):

```C#
public class CreateOrderHandler : IRequestHandler<CreateOrderCommand, Guid>
{
    private readonly IOrderRepository _orderRepository;

    public CreateOrderHandler(IOrderRepository orderRepository)
    {
        _orderRepository = orderRepository;
    }

    public async Task<Guid> Handle(CreateOrderCommand request, CancellationToken cancellationToken)
    {
        var order = new Order(Guid.NewGuid(), request.Items.Select(i => new OrderItem(i.ProductId, i.Quantity)).ToList());
        await _orderRepository.SaveAsync(order);
        return order.Id;
    }
}
```

Infrastructure Layer (DB, Email, APIs, Logging):

- Contains: EF Core repositories, Email, Logging, External Integrations.
- Implements: Interfaces from the Domain Layer.

Repository Implementation (EF Core)

```C#
public class OrderRepository : IOrderRepository
{
    private readonly AppDbContext _context;

    public OrderRepository(AppDbContext context)
    {
        _context = context;
    }

    public async Task<Order> GetByIdAsync(Guid orderId)
    {
        return await _context.Orders.Include(o => o.Items).FirstOrDefaultAsync(o => o.Id == orderId);
    }

    public async Task SaveAsync(Order order)
    {
        _context.Orders.Add(order);
        await _context.SaveChangesAsync();
    }
}
```

Presentation Layer (Controllers, API, UI):

- Contains: Controllers, Middleware, Filters, API Endpoints.
- Does NOT include: Business logic.

Controller (Exposes API):

```C#
[ApiController]
[Route("api/orders")]
public class OrderController : ControllerBase
{
    private readonly IMediator _mediator;

    public OrderController(IMediator mediator)
    {
        _mediator = mediator;
    }

    [HttpPost]
    public async Task<IActionResult> CreateOrder([FromBody] CreateOrderDto dto)
    {
        var command = new CreateOrderCommand { Items = dto.Items };
        var orderId = await _mediator.Send(command);
        return CreatedAtAction(nameof(GetOrder), new { id = orderId }, orderId);
    }

    [HttpGet("{id}")]
    public async Task<IActionResult> GetOrder(Guid id)
    {
        var order = await _mediator.Send(new GetOrderQuery(id));
        if (order == null) return NotFound();
        return Ok(order);
    }
}
```

### Implementing A Repository From Interface With DI

1: Define the Repository Interface (Domain Layer):

The domain layer should only define abstractions (interfaces), without knowledge of the database.

`MyProject.Domain/Repositories/IOrderRepository.cs`

```C#
using System;
using System.Collections.Generic;
using System.Threading.Tasks;
using MyProject.Domain.Entities;

namespace MyProject.Domain.Repositories
{
    public interface IOrderRepository
    {
        Task<Order> GetByIdAsync(Guid orderId);
        Task<IEnumerable<Order>> GetAllAsync();
        Task AddAsync(Order order);
        Task UpdateAsync(Order order);
        Task DeleteAsync(Guid orderId);
    }
}
```

2: Implement the Repository in the Infrastructure Layer

The infrastructure layer contains the actual implementation using Entity Framework Core.

`MyProject.Infrastructure/Persistence/Repositories/OrderRepository.cs`

```C#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.EntityFrameworkCore;
using MyProject.Domain.Entities;
using MyProject.Domain.Repositories;
using MyProject.Infrastructure.Persistence;

namespace MyProject.Infrastructure.Repositories
{
    public class OrderRepository : IOrderRepository
    {
        private readonly AppDbContext _context;

        public OrderRepository(AppDbContext context)
        {
            _context = context;
        }

        public async Task<Order> GetByIdAsync(Guid orderId)
        {
            return await _context.Orders.Include(o => o.Items).FirstOrDefaultAsync(o => o.Id == orderId);
        }

        public async Task<IEnumerable<Order>> GetAllAsync()
        {
            return await _context.Orders.ToListAsync();
        }

        public async Task AddAsync(Order order)
        {
            await _context.Orders.AddAsync(order);
            await _context.SaveChangesAsync();
        }

        public async Task UpdateAsync(Order order)
        {
            _context.Orders.Update(order);
            await _context.SaveChangesAsync();
        }

        public async Task DeleteAsync(Guid orderId)
        {
            var order = await _context.Orders.FindAsync(orderId);
            if (order != null)
            {
                _context.Orders.Remove(order);
                await _context.SaveChangesAsync();
            }
        }
    }
}
```

3: Register the Repository for Dependency Injection

In Clean Architecture, dependency injection is configured in the Infrastructure Layer, usually inside `InfrastructureModule` or `Program.cs`.

`MyProject.Infrastructure/DependencyInjection.cs`

```C#
using Microsoft.EntityFrameworkCore;
using Microsoft.Extensions.DependencyInjection;
using MyProject.Domain.Repositories;
using MyProject.Infrastructure.Persistence;
using MyProject.Infrastructure.Repositories;

namespace MyProject.Infrastructure
{
    public static class DependencyInjection
    {
        public static IServiceCollection AddInfrastructure(this IServiceCollection services, string connectionString)
        {
            services.AddDbContext<AppDbContext>(options =>
                options.UseSqlServer(connectionString));

            // Register Repository for DI
            services.AddScoped<IOrderRepository, OrderRepository>();

            return services;
        }
    }
}
```

4: Use the Repository in the Application Layer

Now that the repository is registered, it can be injected and used inside application services, command handlers (CQRS), or directly in controllers.

Example: Using in an Application Service:

`MyProject.Application/Services/OrderService.cs`

```C#
using System;
using System.Collections.Generic;
using System.Threading.Tasks;
using MyProject.Domain.Entities;
using MyProject.Domain.Repositories;

namespace MyProject.Application.Services
{
    public class OrderService
    {
        private readonly IOrderRepository _orderRepository;

        public OrderService(IOrderRepository orderRepository)
        {
            _orderRepository = orderRepository;
        }

        public async Task<IEnumerable<Order>> GetAllOrdersAsync()
        {
            return await _orderRepository.GetAllAsync();
        }

        public async Task<Order> GetOrderByIdAsync(Guid id)
        {
            return await _orderRepository.GetByIdAsync(id);
        }

        public async Task AddOrderAsync(Order order)
        {
            await _orderRepository.AddAsync(order);
        }
    }
}
```

6: Register Dependencies in Program.cs (Minimal API):

`MyProject/Program.cs`

```C#
var builder = WebApplication.CreateBuilder(args);

string connectionString = builder.Configuration.GetConnectionString("DefaultConnection");

builder.Services.AddInfrastructure(connectionString);  // Add Repositories + DbContext
builder.Services.AddScoped<OrderService>();  // Register Application Service

builder.Services.AddControllers();
builder.Services.AddEndpointsApiExplorer();
builder.Services.AddSwaggerGen();

var app = builder.Build();

app.UseSwagger();
app.UseSwaggerUI();

app.UseAuthorization();
app.MapControllers();

app.Run();
```

Main points:

- Domain Layer: Contains interfaces only (no implementation).
- Infrastructure Layer: Implements repositories using `Entity Framework Core`.
- Dependency Injection: The repository is registered in DI using `AddScoped<IOrderRepository, OrderRepository>()`.
- Application Layer: Calls repository methods inside services or handlers.
- Presentation Layer: Injects the service in controllers or APIs.

This setup ensures separation of concerns, testability, and maintainability in a Clean Architecture project.

### Unit & Integration Testing

Testing is essential in a Clean Architecture project to ensure correctness, maintainability, and scalability.

Unit Tests:

- What? Tests isolated components like domain logic and application services.
- Does NOT depend on databases, external APIs, or infrastructure.
- Uses Mocking Frameworks (e.g., Moq) for dependencies.

Example Test Directory Structure:

```bash
/tests
│── MyProject.UnitTests/
│   ├── Domain/
│   │   ├── OrderTests.cs
│   ├── Application/
│   │   ├── CreateOrderHandlerTests.cs
```

Testing Domain Logic:

`MyProject.UnitTests/Domain/OrderTests.cs`

```C#
using System;
using System.Collections.Generic;
using MyProject.Domain.Entities;
using Xunit;

public class OrderTests
{
    [Fact]
    public void MarkAsShipped_ChangesStatusToShipped()
    {
        // Arrange
        var order = new Order(Guid.NewGuid(), new List<OrderItem>());

        // Act
        order.MarkAsShipped();

        // Assert
        Assert.Equal(OrderStatus.Shipped, order.Status);
    }

    [Fact]
    public void MarkAsShipped_ThrowsException_IfAlreadyShipped()
    {
        // Arrange
        var order = new Order(Guid.NewGuid(), new List<OrderItem>());
        order.MarkAsShipped();

        // Act & Assert
        var exception = Assert.Throws<InvalidOperationException>(() => order.MarkAsShipped());
        Assert.Equal("Order must be pending to ship.", exception.Message);
    }
}
```

Testing Application Service (Using Moq):

`MyProject.UnitTests/Application/CreateOrderHandlerTests.cs`

```C#
using System;
using System.Collections.Generic;
using System.Threading;
using System.Threading.Tasks;
using Moq;
using MyProject.Application.Commands;
using MyProject.Application.Handlers;
using MyProject.Domain.Entities;
using MyProject.Domain.Repositories;
using Xunit;

public class CreateOrderHandlerTests
{
    private readonly Mock<IOrderRepository> _orderRepositoryMock;
    private readonly CreateOrderHandler _handler;

    public CreateOrderHandlerTests()
    {
        _orderRepositoryMock = new Mock<IOrderRepository>();
        _handler = new CreateOrderHandler(_orderRepositoryMock.Object);
    }

    [Fact]
    public async Task Handle_ShouldCallAddAsync()
    {
        // Arrange
        var command = new CreateOrderCommand
        {
            Items = new List<OrderItemDto> { new OrderItemDto { ProductId = Guid.NewGuid(), Quantity = 2 } }
        };

        // Act
        await _handler.Handle(command, CancellationToken.None);

        // Assert
        _orderRepositoryMock.Verify(repo => repo.AddAsync(It.IsAny<Order>()), Times.Once);
    }
}
```

- We mock IOrderRepository using Moq.
- We verify that AddAsync is called exactly once when CreateOrderHandler is executed.

Integration Tests:

- What? Tests multiple layers together (e.g., Repository, API).
- Uses In-Memory Databases (Microsoft.EntityFrameworkCore.InMemory).
- Uses WebApplicationFactory (for API testing).

Project Structure Example:

```bash
/tests
│── MyProject.IntegrationTests/
│   ├── Repositories/
│   │   ├── OrderRepositoryTests.cs
│   ├── API/
│   │   ├── OrderControllerTests.cs
```

Testing Repository with In-Memory Database:

`MyProject.IntegrationTests/Repositories/OrderRepositoryTests.cs`

```C#
using System;
using System.Threading.Tasks;
using Microsoft.EntityFrameworkCore;
using MyProject.Domain.Entities;
using MyProject.Infrastructure.Persistence;
using MyProject.Infrastructure.Repositories;
using Xunit;

public class OrderRepositoryTests
{
    private readonly AppDbContext _context;
    private readonly OrderRepository _repository;

    public OrderRepositoryTests()
    {
        var options = new DbContextOptionsBuilder<AppDbContext>()
            .UseInMemoryDatabase(databaseName: "TestDatabase")
            .Options;

        _context = new AppDbContext(options);
        _repository = new OrderRepository(_context);
    }

    [Fact]
    public async Task AddOrder_ShouldPersistToDatabase()
    {
        // Arrange
        var order = new Order(Guid.NewGuid(), new List<OrderItem>());

        // Act
        await _repository.AddAsync(order);
        var savedOrder = await _repository.GetByIdAsync(order.Id);

        // Assert
        Assert.NotNull(savedOrder);
        Assert.Equal(order.Id, savedOrder.Id);
    }
}
```

- We use an In-Memory Database (UseInMemoryDatabase).
- AddAsync inserts an order, and GetByIdAsync verifies persistence.

Testing API with WebApplicationFactory

`MyProject.IntegrationTests/API/OrderControllerTests.cs`

```C#
using System;
using System.Net;
using System.Net.Http;
using System.Text;
using System.Text.Json;
using System.Threading.Tasks;
using Microsoft.AspNetCore.Mvc.Testing;
using MyProject.Presentation;
using Xunit;

public class OrderControllerTests : IClassFixture<WebApplicationFactory<Program>>
{
    private readonly HttpClient _client;

    public OrderControllerTests(WebApplicationFactory<Program> factory)
    {
        _client = factory.CreateClient();
    }

    [Fact]
    public async Task CreateOrder_ShouldReturn201()
    {
        // Arrange
        var newOrder = new { Items = new[] { new { ProductId = Guid.NewGuid(), Quantity = 1 } } };
        var content = new StringContent(JsonSerializer.Serialize(newOrder), Encoding.UTF8, "application/json");

        // Act
        var response = await _client.PostAsync("/api/orders", content);

        // Assert
        Assert.Equal(HttpStatusCode.Created, response.StatusCode);
    }
}
```

- Uses WebApplicationFactory to start the API.
- Sends a real HTTP request using HttpClient.
- Asserts that the response is 201 Created.

Key points:

- Unit Tests → Test business logic without dependencies.
- Mock Repositories in unit tests using Moq.
- Integration Tests → Test database interactions & APIs.
- Use In-Memory Databases for repository tests.
- Use WebApplicationFactory for real HTTP calls in API tests.

### Overriding Validation Filter Attribute

In DotNet, we have the ability to override the Validation Filter Attribute and handle the errors ourselves. In the format of Domain Driven Design and Clean Architecture, this can be done in the API layer within a Filters section. The Class would then look like something below.


```C#
namespace CleanArchitectureApi.Api.Filters;

public class ValidationFilterAttribute : ActionFilterAttribute
{
    public override void OnActionExecuting(ActionExecutingContext context)
    {
        if (context.ModelState.IsValid) return;
        
        var errors = context
            .ModelState
            .Values
            .SelectMany(v => v.Errors)
            .Select(e => e.ErrorMessage)
            .ToList();

        throw errors.Any(x => x.Contains("request"))
            ? new PayloadFormatException(errors)
            : new RequestValidationException(errors);
    }
}
```

## API

### Setup Authentication With Identity

There is a new, more simple way of implementing Authentication and Authorisation in .Net8.0+. This uses the `MapIdentityApi` to automatically add endpoints for implementing authentication. We can set it up like so.

Start with installing some packages needed:

```bash
dotnet add package Microsoft.AspNetCore.Identity.EntityFrameworkCore
dotnet add package Microsoft.EntityFrameworkCore.Sqlite
dotnet add package Microsoft.EntityFrameworkCore.Design

# Optional for later
dotnet add package Microsoft.AspNetCore.Authentication.JwtBearer
```

Next, instead of making our own `User` model like we did in the old way, we can extend the `IdentityUser` class now included in Identity to add additional properties and fields. If we just want the defaults provided we can skip this step and just pass in the `IdentityUser` to the Context.

```C#
using Microsoft.AspNetCore.Identity;

public class ApplicationUser : IdentityUser
{
    public string? DisplayName { get; set; }
}
```

For our `AppDbContext` we inherit from `IdentityDbContext<>` instead of the old `DbContext`.

```C#
using Microsoft.AspNetCore.Identity.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore;

public class AppDbContext : IdentityDbContext<ApplicationUser>
{
    public AppDbContext(DbContextOptions<AppDbContext> options) : base(options) { }
}
```

Next, in our `Program.cs` file, we can add the Authorization service and map the new endpoints. This is an example of the basic setup.

```C#
using Microsoft.AspNetCore.Identity;
using Microsoft.AspNetCore.Identity.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore;

var builder = WebApplication.CreateBuilder(args);

// Add services to the container.
// Authorization
builder.Services.AddAuthorization();

// Configure identity database access via EF Core.
builder.Services.AddDbContext<ApplicationDbContext>(
    options => options.UseInMemoryDatabase("AppDb")
);

// Activate identity APIs. By default, both cookies and proprietary tokens
// are activated. Cookies will be issued based on the `useCookies` querystring
// parameter in the login endpoint.
builder.Services.AddIdentityApiEndpoints<IdentityUser>()
    .AddEntityFrameworkStores<ApplicationDbContext>();

var app = builder.Build();

app.UseHttpsRedirection();

// Built-in endpoints like /register, /login, /me
app.MapIdentityApi<IdentityUser>();

app.Run();
```

Once this is all set up, we just need to run our migration and can test the endpoints

```bash
# Create a migration
dotnet ef migrations add {migrationName}

# Run the migration
dotnet ef database update
```

By default, the above uses token based authentication.

To use a cookie based authentication method provided by Identity, we can simply set `useCookies` to `true` when calling the `/login` endpoint.

```json
{
  "email": "string",
  "password": "string",
  "useCookies": true
}
```

Should we need to use JWT token based authentication for Mobile apps or other use cases, we can add this before calling the `builder.Services.AddIdentityApiEndpoints<>` service.

```C#
// JWT settings
var jwtKey = "ThisIsAReallyStrongSecretForJwtDontUseInProd";
var signingKey = new SymmetricSecurityKey(Encoding.UTF8.GetBytes(jwtKey));

// Configure JWT auth
builder.Services.AddAuthentication(options =>
{
    options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
    options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;
})
.AddJwtBearer(options =>
{
    options.TokenValidationParameters = new TokenValidationParameters
    {
        ValidateIssuer = false,
        ValidateAudience = false,
        ValidateIssuerSigningKey = true,
        IssuerSigningKey = signingKey
    };
});
```

To make this more simple and re-usable in other projects, we can extract this logic into it's own class extension and call that instead.

```C#
using Microsoft.AspNetCore.Authentication.JwtBearer;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.IdentityModel.Tokens;
using System.Text;

public static class JwtExtensions
{
    public static IServiceCollection AddJwtAuthentication(this IServiceCollection services, IConfiguration config)
    {
        var jwtKey = config["Jwt:Key"];
        var signingKey = new SymmetricSecurityKey(Encoding.UTF8.GetBytes(jwtKey));

        services.AddAuthentication(options =>
        {
            options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
            options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;
        })
        .AddJwtBearer(options =>
        {
            options.TokenValidationParameters = new TokenValidationParameters
            {
                ValidateIssuer = false,
                ValidateAudience = false,
                ValidateIssuerSigningKey = true,
                IssuerSigningKey = signingKey
            };
        });

        return services;
    }
}

```

Then we just need to add this to our `Program.cs` file.

```C#
builder.Services.AddJwtAuthentication(builder.Configuration);
```

Make sure we have this configured in our `appsettings.json`

```json
{
  "Jwt": {
    "Key": "ThisIsAReallyStrongSecretForJwtDontUseInProd"
  }
}
```

### Setup Authentication With Identity For Older Versions

First we need to add some NuGet packages. We will also pull in a bCrypt package for hasing our password later on.

```bash
dotnet add package Microsoft.EntityFrameworkCore.Sqlite
dotnet add package Microsoft.AspNetCore.Authentication.JwtBearer
dotnet add package Microsoft.IdentityModel.Tokens
dotnet add package BCrypt.Net-Next
```

Next we will create a simple User model.

```C#
namespace JwtAuthApi.Models;

public class User
{
    public int Id { get; set; }
    public string Username { get; set; } = string.Empty;
    public string PasswordHash { get; set; } = string.Empty;
}
```

Now we want to add our DbContext.

```C#
using JwtAuthApi.Models;
using Microsoft.EntityFrameworkCore;

namespace JwtAuthApi.Data;

public class AppDbContext : DbContext
{
    public AppDbContext(DbContextOptions<AppDbContext> options) : base(options) { }

    public DbSet<User> Users => Set<User>();
}
```

Next, lets create an AuthController and setup our basic endpoints for registering and logging in a User.

```C#
using System.IdentityModel.Tokens.Jwt;
using System.Security.Claims;
using System.Text;
using BCrypt.Net;
using JwtAuthApi.Data;
using JwtAuthApi.Models;
using Microsoft.AspNetCore.Authorization;
using Microsoft.AspNetCore.Mvc;
using Microsoft.IdentityModel.Tokens;

namespace JwtAuthApi.Controllers;

[ApiController]
[Route("[controller]")]
public class AuthController : ControllerBase
{
    private readonly AppDbContext _db;
    private readonly IConfiguration _config;

    public AuthController(AppDbContext db, IConfiguration config)
    {
        _db = db;
        _config = config;
    }

    [HttpPost("register")]
    public async Task<IActionResult> Register(User user)
    {
        if (_db.Users.Any(u => u.Username == user.Username))
            return BadRequest("User already exists.");

        user.PasswordHash = BCrypt.Net.BCrypt.HashPassword(user.PasswordHash);
        _db.Users.Add(user);
        await _db.SaveChangesAsync();

        return Ok("User registered successfully.");
    }

    [HttpPost("login")]
    public IActionResult Login(User login)
    {
        var user = _db.Users.FirstOrDefault(u => u.Username == login.Username);
        if (user == null || !BCrypt.Net.BCrypt.Verify(login.PasswordHash, user.PasswordHash))
            return Unauthorized("Invalid username or password.");

        var tokenHandler = new JwtSecurityTokenHandler();
        var key = Encoding.UTF8.GetBytes(_config["Jwt:Key"]);

        var tokenDescriptor = new SecurityTokenDescriptor
        {
            Subject = new ClaimsIdentity(new[]
            {
                new Claim(ClaimTypes.NameIdentifier, user.Id.ToString()),
                new Claim(ClaimTypes.Name, user.Username)
            }),
            Expires = DateTime.UtcNow.AddHours(1),
            SigningCredentials = new SigningCredentials(new SymmetricSecurityKey(key), SecurityAlgorithms.HmacSha256Signature)
        };

        var token = tokenHandler.CreateToken(tokenDescriptor);
        return Ok(new { token = tokenHandler.WriteToken(token) });
    }

    [HttpGet("secure")]
    [Authorize]
    public IActionResult Secure()
    {
        return Ok("You are authenticated!");
    }
}
```

Finally, lets update our `Program.cs` file with some config parameters.

```C#
using System.Text;
using JwtAuthApi.Data;
using Microsoft.AspNetCore.Authentication.JwtBearer;
using Microsoft.EntityFrameworkCore;
using Microsoft.IdentityModel.Tokens;

var builder = WebApplication.CreateBuilder(args);

builder.Services.AddControllers();
builder.Services.AddDbContext<AppDbContext>(options =>
    options.UseSqlite("Data Source=users.db"));

builder.Services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
    .AddJwtBearer(options =>
    {
        var key = Encoding.UTF8.GetBytes(builder.Configuration["Jwt:Key"]);
        options.TokenValidationParameters = new TokenValidationParameters
        {
            ValidateIssuer = false,
            ValidateAudience = false,
            ValidateIssuerSigningKey = true,
            IssuerSigningKey = new SymmetricSecurityKey(key),
            ValidateLifetime = true
        };
    });

builder.Services.AddAuthorization();

var app = builder.Build();

app.UseAuthentication();
app.UseAuthorization();

app.MapControllers();

using (var scope = app.Services.CreateScope())
{
    var db = scope.ServiceProvider.GetRequiredService<AppDbContext>();
    db.Database.EnsureCreated();
}

app.Run();
```

### Example CRUD Controller using .NET API

```C#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using ContosoPizza.Models;
using ContosoPizza.Services;
using Microsoft.AspNetCore.Mvc;

namespace ContosoPizza.Controllers;

[ApiController]
[Route("[controller]")]
public class PizzaController : ControllerBase
{
    [HttpGet]
    public ActionResult<List<Pizza>> GetAll() => PizzaService.GetAll();

    [HttpGet("{id}")]
    public ActionResult<Pizza> Get(int id)
    {
        var pizza = PizzaService.Get(id);

        if (pizza == null)
            return NotFound();

        return pizza;
    }

    [HttpPost]
    public IActionResult Create(Pizza pizza)
    {
        PizzaService.Add(pizza);
        return CreatedAtAction(nameof(Get), new { id = pizza.Id }, pizza);
    }

    [HttpPut("{id}")]
    public IActionResult Update(int id, Pizza pizza)
    {
        if (id != pizza.Id)
            return BadRequest();

        var existingPizza = PizzaService.Get(id);
        if (existingPizza is null)
            return NotFound();

        PizzaService.Update(pizza);

        return NoContent();
    }

    [HttpDelete("{id}")]
    public IActionResult Delete(int id)
    {
        var pizza = PizzaService.Get(id);

        if (pizza is null)
            return NotFound();

        PizzaService.Delete(id);

        return NoContent();
    }
}

```

### Using REST Client Extension For API Calls

Install the extension.

Create a .http file and then create endpoints for your API like below

```c#
@ContosoPizza_HostAddress = http://localhost:5147

GET {{ContosoPizza_HostAddress}}/weatherforecast/
Accept: application/json

###

GET {{ContosoPizza_HostAddress}}/pizza/
Accept: application/json

###

GET {{ContosoPizza_HostAddress}}/pizza/1
Accept: application/json

###

GET {{ContosoPizza_HostAddress}}/pizza/5
Accept: application/json

###

POST {{ContosoPizza_HostAddress}}/pizza/
Content-Type: application/json

{
    "name": "Hawaii",
    "isGlutenFree": false
}

###

PUT {{ContosoPizza_HostAddress}}/pizza/3
Content-Type: application/json

{
    "id": 3,
    "name": "Hawaiian",
    "isGlutenFree": false
}

###

DELETE {{ContosoPizza_HostAddress}}/pizza/3

###
```

Click on the `Send Request` link above each url to send and return the result

### Using HTTP-Repl In The Command Line

Open a new integrated terminal from Visual Studio Code by selecting Terminal > New Terminal from the main menu, then run the following command:

```bash
dotnet tool install -g Microsoft.dotnet-httprepl
```

The preceding command installs the .NET HTTP Read-Eval-Print Loop (REPL) command-line tool that you use to make HTTP requests to the web API.

Connect to the web API by running the following command:

```bash
httprepl https://localhost:{PORT}
```

Alternatively, run the following command at any time while HttpRepl is running:

```bash 
connect https://localhost:{PORT}
```

Explore available endpoints by running the following command:

```bash
ls
```

The preceding command detects all APIs available on the connected endpoint and lists them, as in the following output:

```bash
https://localhost:{PORT}/> ls
.                 []
WeatherForecast   [GET]
```

Go to the `WeatherForecast` endpoint by running the following command:

```bash
cd WeatherForecast
```

The preceding command shows an output of available APIs for the WeatherForecast endpoint:

```bash
https://localhost:{PORT}/> cd WeatherForecast
/WeatherForecast    [GET]
```

Make a GET request in HttpRepl by using the following command:

```bash
get
```

End the current HttpRepl session by using the following command:

```bash
exit
```

### Middleware

Each middleware can be thought of as terminal or nonterminal. Nonterminal middleware processes the request and then calls the next middleware in the pipeline. Terminal middleware is the last middleware in the pipeline and doesn't have a next middleware to call.

Delegates added with `app.Use()` can be terminal or nonterminal middleware. These delegates expect a HttpContext object and a RequestDelegate object as parameters. Typically the delegate includes `await next.Invoke();`. This passes control to the next middleware on the pipeline. Code before that line runs before the next middleware, and code after that line runs after the next middleware. A delegate added with app.Use() gets two opportunities to act on a request before the response is sent to the client; once before the response is generated by the terminal middleware, and again after the response is generated by the terminal middleware.

Delegates added with `app.Run()` are always terminal middleware. They don't call the next middleware in the pipeline. They're the last middleware component that runs. They only expect a HttpContext object as a parameter. app.Run() is a shortcut for adding terminal middleware.

Some examples of built in middleware can be found in the documentation here:

https://learn.microsoft.com/en-us/aspnet/core/fundamentals/middleware/?view=aspnetcore-9.0&preserve-view=true

```c#
app.UseRewriter(new RewriteOptions().AddRedirect("history", "about"));
```

This code adds a URL rewriter middleware component that redirects requests from /history to /about. The AddRedirect() method takes two parameters: a regular expression pattern to match the request path, and the replacement path to redirect to.

```C#
app.Use(async (context, next) =>
{
    Console.WriteLine($"{context.Request.Method} {context.Request.Path} {context.Response.StatusCode}");
    await next(); 
});
```

In the preceding code:

- `app.Use()` adds a custom middleware component to the pipeline. The component takes a `HttpContext` object and a `RequestDelegate` object as parameters.
- The delegate writes the request method, path, and response status code to the console.
- `await next()` calls the next middleware component in the pipeline.

### Extracting Custom Middleware Outside Program.cs

Create the Middleware Class

Define a class that implements your custom middleware logic.

```C#
using Microsoft.AspNetCore.Http;
using System.Threading.Tasks;

public class CustomMiddleware
{
    private readonly RequestDelegate _next;

    public CustomMiddleware(RequestDelegate next)
    {
        _next = next;
    }

    public async Task InvokeAsync(HttpContext context)
    {
        // Custom logic before the next middleware
        await context.Response.WriteAsync("Before Middleware\n");

        // Call the next middleware in the pipeline
        await _next(context);

        // Custom logic after the next middleware
        await context.Response.WriteAsync("After Middleware\n");
    }
}
```

Create an Extension Method

```C#
using Microsoft.AspNetCore.Builder;

public static class CustomMiddlewareExtensions
{
    public static IApplicationBuilder UseCustomMiddleware(this IApplicationBuilder app)
    {
        return app.UseMiddleware<CustomMiddleware>();
    }
}

```

Use the Middleware in Program.cs

```C#
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

// Use the custom middleware
app.UseCustomMiddleware();

// Add other middleware, if needed
app.MapGet("/", () => "Hello World!");

app.Run();
```

### Setting Up Swagger

Documentation is something you want for your API. You want it for yourself, your colleagues, and any third-party developers who might want to use your API. It's key to keep the documentation in sync with your API as it changes. A good approach is to describe your API in a standardized way and ensure it's self-documenting. By self-documenting, we mean that if the code changes, the documentation changes with it.

Swagger implements the OpenAPI specification. This format describes your routes but also what data they accept and produce. Swagger UI is a collection of tools that render the OpenAPI specification as a website and let you interact with your API via the website.

To use Swagger and the Swagger UI in your API, you do two things:

Install a package. To install Swagger, you specify to install a package called Swashbuckle, like this:

```bash
dotnet add package Swashbuckle.AspNetCore
```

Configure it. After the package is installed, you configure it via your code. You add a few different entries:

Add a namespace. You need this namespace when you later call SwaggerDoc() and provide the header information for your API.

```C#
using Microsoft.OpenApi.Models;
```

Add AddSwaggerGen(). This method sets up header information on your API, like what it's called and the version number. Note that Swagger should be limited to development time, as it can be a security risk if it's available in production.

Add UseSwagger() and UseSwaggerUI(). These two code lines tell the API project to use Swagger and also where to find the specification file swagger.json.

```C#
builder.Services.AddEndpointsApiExplorer();
if (app.Environment.IsDevelopment())
{
    builder.Services.AddSwaggerGen(c =>
    {
       c.SwaggerDoc("v1", new OpenApiInfo { Title = "Todo API", Description = "Keep track of your tasks", Version = "v1" });
    });

    app.UseSwagger();

    app.UseSwaggerUI(c =>
    {
      c.SwaggerEndpoint("/swagger/v1/swagger.json", "Todo API V1");
    });
}
```

### Adding Swagger UI Or Scalar In Dotnet 9

This is a guide to add the Swagger UI or Scalar into a project using OpenApi

Open Nuget And Add `Swashbuckle.AspNetCore` back into the project.

Now add it into the development configuration inside `Program.cs`

```C#
if (app.Environment.IsDevelopment()) {
    app.MapOpenApi();

    app.UseSwaggerUI(options => {
        options.SwaggerEndpoint("/openapi/v1.json", "Name Of Api");
    });
}
```

For Scalar we can go into Nuget package manager and install `Scalar.AspNetCore` into the project.

```C#
if (app.Environment.IsDevelopment()) {
    app.MapOpenApi();

    // The options parameters are optional and just change the functionality
    app.MapScalarApiReference(options => {
        options
            .WithTitle("Api Name")
            .WithTheme(ScalarTheme.Mars)
            .WithDefaultHttpClient(ScalarTarget.CSharp, ScalarClient.HttpClient);
    });
}
```

The URL to access this is now `localhost/scalar/v1`

### Implementing XSRF Tokens

In your Program.cs, register the antiforgery services in the dependency injection container:

```c#
var builder = WebApplication.CreateBuilder(args);

// Add services to the container
builder.Services.AddAntiforgery(options =>
{
    options.HeaderName = "X-CSRF-TOKEN"; // Default header for CSRF validation
});

var app = builder.Build();
```

Create an endpoint that provides the CSRF token. You can return the token as part of a response or embed it in a response header or JavaScript.

```C#
app.MapGet("/get-csrf-token", (IAntiforgery antiforgery, HttpContext context) =>
{
    var tokens = antiforgery.GetAndStoreTokens(context); // Generate and store tokens in cookies
    return Results.Ok(new { token = tokens.RequestToken });
});
```

Add the CSRF token as a hidden field in forms. In your frontend HTML, retrieve the token and include it:

```HTML
<form id="myForm" method="post" action="/submit-data">
    <input type="hidden" name="__RequestVerificationToken" id="csrfToken" />
    <input type="text" name="exampleInput" />
    <button type="submit">Submit</button>
</form>

<script>
    fetch('/get-csrf-token')
        .then(response => response.json())
        .then(data => {
            document.getElementById('csrfToken').value = data.token;
        });
</script>

```

Include the CSRF token in the X-CSRF-TOKEN header when making requests:

```JavaScript
fetch('/submit-data', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
        'X-CSRF-TOKEN': '<csrf-token-goes-here>'
    },
    body: JSON.stringify({ exampleInput: 'exampleValue' })
});
```

For routes that require CSRF protection, validate the token using `IAntiforgery`.

```C#
app.MapPost("/submit-data", async (HttpContext context, IAntiforgery antiforgery) =>
{
    try
    {
        // Validate the CSRF token
        await antiforgery.ValidateRequestAsync(context);
        // Proceed if the token is valid
        return Results.Ok(new { message = "Data submitted successfully!" });
    }
    catch
    {
        // Handle CSRF validation failure
        return Results.BadRequest(new { error = "Invalid CSRF token" });
    }
});
```

The antiforgery system uses cookies by default to store tokens. Configure the cookie settings for additional security.

```C#
builder.Services.AddAntiforgery(options =>
{
    options.Cookie.Name = "XSRF-TOKEN";
    options.Cookie.HttpOnly = true;
    options.Cookie.SecurePolicy = CookieSecurePolicy.Always; // Require HTTPS
    options.Cookie.SameSite = SameSiteMode.Strict;
    options.HeaderName = "X-CSRF-TOKEN"; // Header name for token validation
});
```

- HTTPS: Always use HTTPS for secure cookie handling and token transmission.

- Token Lifecycle: CSRF tokens are tied to user sessions. Ensure proper logout and token invalidation.

- Exclude CSRF for GET Requests: Since GET requests should not modify data, CSRF protection is typically unnecessary for them.

## Authentication & Authorisation With Identity & Razor Pages

### Install

Install the ASP.NET Core code scaffolder:

```bash
dotnet tool install dotnet-aspnet-codegenerator --version 9.0.* --global
```

The scaffolder is a .NET tool that:

- Is used to add the default Identity components to the project.
- Enables customization of Identity UI components in the next unit.
- Is invoked via dotnet aspnet-codegenerator in this module.

Add the following NuGet packages to the project:

```bash
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design --version 9.0.*
dotnet add package Microsoft.AspNetCore.Identity.EntityFrameworkCore --version 9.0.*
dotnet add package Microsoft.AspNetCore.Identity.UI --version 9.0.*
dotnet add package Microsoft.EntityFrameworkCore.Design --version 9.0.*
dotnet add package Microsoft.EntityFrameworkCore.SqlServer --version 9.0.*
dotnet add package Microsoft.EntityFrameworkCore.Tools --version 9.0.*
```

Tip:

To view the available generators:

- In the command shell, run `dotnet aspnet-codegenerator -h`.
- When in Visual Studio, right-click the project in Solution Explorer and select Add > New Scaffolded Item.

Use the scaffolder to add the default Identity components to the project. Run the following command in the terminal:

```bash
dotnet aspnet-codegenerator identity --useDefaultUI --dbContext RazorPagesPizzaAuth --userClass RazorPagesPizzaUser
```

In the preceding command:

- The generator identified as identity is used to add the Identity framework to the project.
- The --useDefaultUI option indicates that a Razor class library (RCL) containing the default UI elements is used. Bootstrap is used to style the components.
- The --dbContext option specifies the name of an EF Core database context class to generate.
- The --userClass option specifies the name of the user class to generate. The default user class is IdentityUser, but since the user class is extended in a later unit, a custom user class named RazorPagesPizzaUser is specified. The RazorPagesPizzaUser class is derived from IdentityUser.

### Configure The Database Connection

The ConnectionStrings section in `appsettings.json` should look similar to the following JSON:

```json
"ConnectionStrings": {
    "RazorPagesPizzaAuthConnection": "Server=(localdb)\\mssqllocaldb;Database=RazorPagesPizza;Trusted_Connection=True;MultipleActiveResultSets=true"
}
```

In Codespaces or Dev Containers, the connection string is incorrect. If you are using the Codespace or Dev Container, you must change the connection string as follows! Be sure to save your changes.

```json
"ConnectionStrings": {
    "RazorPagesPizzaAuthConnection": "Data Source=localhost;Initial Catalog=RazorPagesPizza;Integrated Security=False;User Id=sa;Password=P@ssw0rd;MultipleActiveResultSets=True;Encrypt=False"
}
```

Now that you verified the connection string, you can generate and run a migration to build the database.

Run the following command to build the app:

```bash
dotnet build
```

Install the Entity Framework Core migration tool:

```bash
dotnet tool install dotnet-ef --version 8.0.* --global
```

To update the database, create and run an EF Core migration:

```bash
dotnet ef migrations add CreateIdentitySchema
dotnet ef database update
```

Press Ctrl+Alt+D to switch to the SQL Server pane.

Expand the nodes under the existing database connection. Expand the Databases node, the RazorPagesPizza node, and finally the Tables node. Note the list of tables. This confirms the migration succeeded.

### Customise The User Account Data

This is more used when building a monolith application with Razor.

Add the user registration files to be modified to the project:

```bash
dotnet aspnet-codegenerator identity --dbContext RazorPagesPizzaAuth --files "Account.Manage.EnableAuthenticator;Account.Manage.Index;Account.Register;Account.ConfirmEmail"
```

- The --dbContext option provides the tool with knowledge of the existing DbContext-derived class named RazorPagesPizzaAuth.
- The --files option specifies a semicolon-delimited list of unique files to be added to the Identity area.
    - Account.Manage.Index is the profile management page. This page is modified later in this unit.
    - Account.Register is the user registration page. This page is also modified in this unit.
    - Account.Manage.EnableAuthenticator and Account.ConfirmEmail are scaffolded but not modified in this unit.

Tip:

Run the following command from the project root to view valid values for the --files option: `dotnet aspnet-codegenerator identity --listFiles`

To extend identity user add the FirstName and LastName properties:

```c#
using System.ComponentModel.DataAnnotations;
using Microsoft.AspNetCore.Identity;

namespace RazorPagesPizza.Areas.Identity.Data;

public class RazorPagesPizzaUser : IdentityUser
{
    [Required]
    [MaxLength(100)]
    public string FirstName { get; set; } = string.Empty;

    [Required]
    [MaxLength(100)]
    public string LastName { get; set; } = string.Empty;
}
```

Ensure that all your changes are saved.

Create and apply an EF Core migration to update the underlying data store:

```bash
dotnet ef migrations add UpdateUser
dotnet ef database update
```

The UpdateUser EF Core migration applied a DDL change script to the AspNetUsers table's schema. Specifically, FirstName and LastName columns were added.

### Two Factor Authentication

Generating QR codes: 

Multiple strategies exist for generating the QR code. An example in the documentation uses a client-side JavaScript library. In this unit, however, a third-party NuGet package is used to generate the QR code with C# on the server. The resulting QR code image is injected into an HTML placeholder element as a base-64 encoded string.

In the terminal pane, install the QRCoder NuGet package:

```bash
dotnet add package QRCoder --version 1.6.0
```

In the Explorer pane, right-click on the Services folder and add a new file named QRCodeService.cs. Add the following code:

```c#
using QRCoder;

namespace RazorPagesPizza.Services;
public class QRCodeService
{
    private readonly QRCodeGenerator _generator;

    public QRCodeService(QRCodeGenerator generator)
    {
        _generator = generator;
    }

    public string GetQRCodeAsBase64(string textToEncode)
    {
        QRCodeData qrCodeData = _generator.CreateQrCode(textToEncode, QRCodeGenerator.ECCLevel.Q);
        var qrCode = new PngByteQRCode(qrCodeData);

        return Convert.ToBase64String(qrCode.GetGraphic(4));
    }
}
```

The preceding code:

- Uses constructor injection to gain access to an instance of the library's QRCodeGenerator class.
- Exposes the GetQRCodeAsBase64 method to return the base-64 encoded string. The integer value passed to GetGraphic determines the QR code dimensions. In this case, the generated QR code is composed of blocks sized four pixels squared.

In Program.cs, add the highlighted lines:

```C#
using QRCoder;

builder.Services.AddSingleton(new QRCodeService(new QRCodeGenerator()));
```

QRCodeService is registered as a singleton service in the IoC container within Program.cs.

### Useful Identity Links

Set Up Authentication With A SPA - https://learn.microsoft.com/en-us/aspnet/core/security/authentication/identity-api-authorization?view=aspnetcore-9.0

Identity model customization in ASP.NET Core - https://learn.microsoft.com/en-us/aspnet/core/security/authentication/customize-identity-model?view=aspnetcore-9.0

Claims-based authorization in ASP.NET Core - https://learn.microsoft.com/en-us/aspnet/core/security/authorization/claims?view=aspnetcore-9.0


## Entity Framework Core

### Adding NuGet Packages 

In the terminal pane, run the following command:

```bash
dotnet add package Microsoft.EntityFrameworkCore.Sqlite
```

This command adds the NuGet package that contains the EF Core SQLite database provider and all its dependencies, including the common EF Core services.

```bash
dotnet add package Microsoft.EntityFrameworkCore.Design
```

This command adds packages that are required for the EF Core tools.

```bash
dotnet tool install --global dotnet-ef
```

This command installs `dotnet ef`, the tool you use to create migrations and scaffolding.

### Updating packages

If dotnet ef is already installed, you can update it by running `dotnet tool update --global dotnet-ef`.

### Adding A Context

Now you add and configure a DbContext implementation. DbContext is a gateway through which you can interact with the database.

Right-click the ContosoPizza directory and add a new folder called Data.

In the Data folder, create a new file named PizzaContext.cs. Add the following code to the empty file:

```C#
using Microsoft.EntityFrameworkCore;
using ContosoPizza.Models;

namespace ContosoPizza.Data;

public class PizzaContext : DbContext
{
    public PizzaContext (DbContextOptions<PizzaContext> options)
        : base(options)
    {
    }

    public DbSet<Pizza> Pizzas => Set<Pizza>();
    public DbSet<Topping> Toppings => Set<Topping>();
    public DbSet<Sauce> Sauces => Set<Sauce>();
}
```

In the preceding code:

- The constructor accepts a parameter of type DbContextOptions<PizzaContext>. The constructor allows external code to pass in the configuration so that the same DbContext can be shared between test and production code, and even be used with different providers.
- The DbSet<T> properties correspond to tables to create in the database.
- The table names match the DbSet<T> property names in the PizzaContext class. You can override this behavior if needed.
- When instantiated, PizzaContext exposes the Pizzas, Toppings, and Sauces properties. Changes you make to the collections that those properties expose are propagated to the database.

In `Program.cs`, replace // Add the PizzaContext with the following code:

```C#
builder.Services.AddSqlite<PizzaContext>("Data Source=ContosoPizza.db");
```

The preceding code:

- Registers PizzaContext with the ASP.NET Core dependency injection system.
- Specifies that PizzaContext uses the SQLite database provider.
- Defines a SQLite connection string that points to a local file, ContosoPizza.db.

SQLite uses local database files, so it's okay to hard-code the connection string. For network databases like PostgreSQL and SQL Server, you should always store your connection strings securely. For local development, use Secret Manager. For production deployments, consider using a service like Azure Key Vault.

https://learn.microsoft.com/en-us/aspnet/core/security/app-secrets?view=aspnetcore-9.0&tabs=windows

Also in Program.cs, replace // Additional using declarations with the following code.

```C#
using ContosoPizza.Data;
```

### Create And Run Migration

Next, create a migration that you can use to create your initial database.

In the terminal scoped to the ContosoPizza project folder, run the following command to generate a migration for creating the database tables:

```bash
dotnet ef migrations add InitialCreate --context PizzaContext
```

In the preceding command:

- The migration is named: InitialCreate.
- The --context option specifies the name of the class in the ContosoPizza project, which derives from DbContext.

A new Migrations directory appears in the ContosoPizza project root. The directory contains a <timestamp>_InitialCreate.cs file that describes the database changes to be translated to a Data Definition Language (DDL) change script.

Run the following command to apply the InitialCreate migration:

```bash
dotnet ef database update --context PizzaContext
```

### Example CRUD service using EF Core

```C#
using ContosoPizza.Models;
using ContosoPizza.Data;
using Microsoft.EntityFrameworkCore;

namespace ContosoPizza.Services;

public class PizzaService
{
    private readonly PizzaContext _context;

    public PizzaService(PizzaContext context)
    {
        _context = context;
    }

    public IEnumerable<Pizza> GetAll()
    {
        /*
        * The AsNoTracking extension method instructs EF Core to disable change tracking. Because this operation is read-only, AsNoTracking can optimize performance.
        */

        return _context.Pizzas
            .AsNoTracking()
            .ToList();
    }

    public Pizza? GetById(int id)
    {
        /*
            The Include extension method takes a lambda expression to specify that the Toppings and Sauce navigation properties are to be included in the result by using eager loading. 
            Without this expression, EF Core returns null for those properties.

            The SingleOrDefault method returns a pizza that matches the lambda expression.
                If no records match, null is returned.
                If multiple records match, an exception is thrown.
                The lambda expression describes records where the Id property is equal to the id parameter.
        */
        return _context.Pizzas
            .Include(p => p.Toppings)
            .Include(p => p.Sauce)
            .AsNoTracking()
            .SingleOrDefault(p => p.Id == id);
    }

    public Pizza Create(Pizza newPizza)
    {
        /*
            newPizza is assumed to be a valid object. EF Core doesn't do data validation, so the ASP.NET Core runtime or user code must handle any validation.
        */
        _context.Pizzas.Add(newPizza);
        _context.SaveChanges();

        return newPizza;
    }

    public void AddTopping(int pizzaId, int toppingId)
    {
        /*
            References to existing Pizza and Topping objects are created by using Find.
            The Topping object is added to the Pizza.Toppings collection with the .Add method. A new collection is created if it doesn't exist.
            The SaveChanges method instructs EF Core to persist the object changes to the database.
        */
        var pizzaToUpdate = _context.Pizzas.Find(pizzaId);
        var toppingToAdd = _context.Toppings.Find(toppingId);

        if (pizzaToUpdate is null || toppingToAdd is null)
        {
            throw new InvalidOperationException("Pizza or topping does not exist");
        }

        if (pizzaToUpdate.Toppings is null)
        {
            pizzaToUpdate.Toppings = new List<Topping>();
        }

        pizzaToUpdate.Toppings.Add(toppingToAdd);

        _context.SaveChanges();
    }

    public void UpdateSauce(int pizzaId, int sauceId)
    {
        /*
            References to existing Pizza and Sauce objects are created by using Find. Find is an optimized method to query records by their primary key. Find searches the local entity graph first before it queries the database.
            The Pizza.Sauce property is set to the Sauce object.
            An Update method call is unnecessary because EF Core detects that you set the Sauce property on Pizza.
            The SaveChanges method instructs EF Core to persist the object changes to the database.
        */
        var pizzaToUpdate = _context.Pizzas.Find(pizzaId);
        var sauceToUpdate = _context.Sauces.Find(sauceId);

        if (pizzaToUpdate is null || sauceToUpdate is null)
        {
            throw new InvalidOperationException("Pizza or sauce does not exist");
        }

        pizzaToUpdate.Sauce = sauceToUpdate;

        _context.SaveChanges();
    }

    public void DeleteById(int id)
    {
        var pizzaToDelete = _context.Pizzas.Find(id);
        
        if (pizzaToDelete is not null)
        {
            _context.Pizzas.Remove(pizzaToDelete);
            _context.SaveChanges();
        }
    }
}
```

### Seeding The Database

Add a new file E.g `DbInitializer.cs`.

Example code for a seeder class

```C#
using ContosoPizza.Models;

namespace ContosoPizza.Data
{
    public static class DbInitializer
    {
        public static void Initialize(PizzaContext context)
        {

            if (context.Pizzas.Any()
                && context.Toppings.Any()
                && context.Sauces.Any())
            {
                return;   // DB has been seeded
            }

            var pepperoniTopping = new Topping { Name = "Pepperoni", Calories = 130 };
            var sausageTopping = new Topping { Name = "Sausage", Calories = 100 };
            var hamTopping = new Topping { Name = "Ham", Calories = 70 };
            var chickenTopping = new Topping { Name = "Chicken", Calories = 50 };
            var pineappleTopping = new Topping { Name = "Pineapple", Calories = 75 };

            var tomatoSauce = new Sauce { Name = "Tomato", IsVegan = true };
            var alfredoSauce = new Sauce { Name = "Alfredo", IsVegan = false };

            var pizzas = new Pizza[]
            {
                new Pizza
                    { 
                        Name = "Meat Lovers", 
                        Sauce = tomatoSauce, 
                        Toppings = new List<Topping>
                            {
                                pepperoniTopping, 
                                sausageTopping, 
                                hamTopping, 
                                chickenTopping
                            }
                    },
                new Pizza
                    { 
                        Name = "Hawaiian", 
                        Sauce = tomatoSauce, 
                        Toppings = new List<Topping>
                            {
                                pineappleTopping, 
                                hamTopping
                            }
                    },
                new Pizza
                    { 
                        Name="Alfredo Chicken", 
                        Sauce = alfredoSauce, 
                        Toppings = new List<Topping>
                            {
                                chickenTopping
                            }
                        }
            };

            context.Pizzas.AddRange(pizzas);
            context.SaveChanges();
        }
    }
}
```

- The DbInitializer class and Initialize method are both defined as static.
- Initialize accepts a PizzaContext object as a parameter.
- If there are no records in any of the three tables, Pizza, Sauce, and Topping objects are created.
- The Pizza objects (and their Sauce and Topping navigation properties) are added to the object graph by using AddRange.
- The object graph changes are committed to the database by using SaveChanges.

The DbInitializer class is ready to seed the database, but it needs to be called from Program.cs. The following steps create an extension method for IHost that calls DbInitializer.Initialize:

In the Data folder, add a new file named Extensions.cs.

Add the following code to Data\Extensions.cs:

```C#
namespace ContosoPizza.Data;

public static class Extensions
{
    public static void CreateDbIfNotExists(this IHost host)
    {
        {
            using (var scope = host.Services.CreateScope())
            {
                var services = scope.ServiceProvider;
                var context = services.GetRequiredService<PizzaContext>();
                context.Database.EnsureCreated();
                DbInitializer.Initialize(context);
            }
        }
    }
}
```

In the preceding code:

- The CreateDbIfNotExists method is defined as an extension of IHost.
- A reference to the PizzaContext service is created.
- EnsureCreated ensures that the database exists.
- The DbIntializer.Initialize method is called. The PizzaContext object is passed as a parameter.

Finally, in Program.cs, replace the // Add the CreateDbIfNotExists method call comment with the following code to call the new extension method:

```C#
app.CreateDbIfNotExists();
```

### Reverse-engineer from an existing database

This is to implement an existing database into Entity Framework Core

Run the following command:

```bash
dotnet ef dbcontext scaffold "Data Source=Promotions/Promotions.db" Microsoft.EntityFrameworkCore.Sqlite --context-dir Data --output-dir Models
```
The preceding command:

- Scaffolds DbContext and model classes by using the provided connection string.
- Specifies to use the Microsoft.EntityFrameworkCore.Sqlite database provider.
- Specifies directories for the resulting DbContext and model classes.

Since SQLite has a limited set of types compared to C#, the scaffolding tool made inferences as to what C# types to use. For example, the Expiration database column was defined as a string because SQLite doesn't have a date data type. The scaffolding tool inferred that the C# type should be DateOnly? based on the data in the database.

### MSSQL Connection String Example

This is for connecting to a local instance of the database

```json
"ConnectionStrings": {
    "DefaultConnection": "Data Source=WinDev2401Eval\\SQLEXPRESS;Initial Catalog=financial-app;Integrated Security=True;Connect Timeout=30;Encrypt=False;TrustServerCertificate=False;ApplicationIntent=ReadWrite;MultiSubnetFailover=False"
},
```

## Sending Emails

### Getting Started Example

The most common way these days to send emails with .NET is using NuGet packages.

To start, add `MailKit` to your project.

```bash
dotnet add package MailKit
```

As a quick example, we can use something like this to construct emails and send.

```C#
using MailKit.Net.Smtp;
using MimeKit;
using MimeKit.Text;

# Init the MIME message
var message = new MimeMessage();

# Set a from user
var from = new MailboxAddress("From User", "fromuser@example.com");
message.from.Add(from);

# Set a to user, or users
var to = new MailboxAddress("To User", "toUser@example.com");
message.To.Add(to);

# Add a subject
message.Subject = "Example Subject";

# Create the message body
message.Body = new TextPart(TextFormat.Plain) {
    Text = """
    This is using a normal text output for a basic email.
    """
};

# Using the BodyBuilder for different types
var bodyBuilder = new BodyBuilder();

bodyBuilder.TextBody = "Example using the text body";
bodyBuilder.HtmlBody = "<p>Example using the html body</p>"

message.body = bodyBuilder.ToMessageBody();

# Adding an attachment
bodyBuilder.Attachments.Add("image.jpg");

# Adding an image into the message instead of an attachment
var imageEntity = bodyBuilder.LinkedResources.Add("image.jpg");
imageEntity.ContentId = MimeUtils.GenerateMessageId();

bodyBuilder.HtmlBody = $"""
<p>Test example text</p>

<p>
    <img src="cid:{imageEntity.ContentId}" />
</p>
""";

# Connect to the SMTP server and send the message
# When importing, make sure to use the SMTP Client from MailKit
# and not the older one included in the dotnet library.
using var smtp = new SmtpClient();

await smtp.ConnectAsync("localhost", 1025);
await smtp.SendAsync(message);
await smtp.DisconnectAsync(true);
```

### Setting Up MailPit

To set up MailPit, we can either run it directly on our machine using the Binary from Github or add it as a service with Docker Compose.

To run with the Binary, download it to your machine and then run 

```bash
./mailpit --listen 0.0.0.0:1025 --ui-bind 0.0.0.0:8025
```

if we are using Docker Compose, we can add a service like this.

```yml
services:
  mailpit:
    image: axllent/mailpit:latest
    container_name: mailpit
    ports:
      - "1025:1025"
      - "8025:8025"
    environment:
      MP_UI_BIND_ADDR: 0.0.0.0:8025
      MP_SMTP_BIND_ADDR: 0.0.0.0:1025
```

Once this is up and running, we can then just add some parameters to our `.env` file and map them inside our application.

```bash
SMTP_HOST=localhost
SMTP_PORT=1025
SMTP_USER=
SMTP_PASS=
```

### Building Text Only Based Emails

When building text only based emails, a good suggestion is to create a method then use the `StringBuilder` found in the `System.Text` library. This can make it easier when it comes to padding and adding dynamic data into your email.

More information on the StringBuilder can be found here.

https://learn.microsoft.com/en-us/dotnet/standard/base-types/stringbuilder

A small code example using the `StringBuilder`

```C#
var sb = new StringBuilder();

// Subject
sb.AppendLine($"Subject: Your Order Confirmation - {productName}");
sb.AppendLine();

// Greeting
sb.AppendLine($"Hello {recipientName},");
sb.AppendLine();

// Body
sb.AppendLine($"Thank you for purchasing {productName}!");
sb.AppendLine($"Your order number is {orderNumber}.");
sb.AppendLine("We will notify you once your order has shipped.");
sb.AppendLine();

sb.AppendLine("If you have any questions, feel free to reply to this email or contact us at:");
sb.AppendLine(supportEmail);
sb.AppendLine();

// Signature
sb.AppendLine("Kind regards,");
sb.AppendLine(senderName);
```

### Using Fluid To Generate HTML Template Emails

Fluid is a templating engine we can use to easily generate emails.

The Github Repo and Documentation can be found here:
https://github.com/sebastienros/fluid

To get started, we can install the package from NuGet

```bash
dotnet add package Fluid.Core
```

Fluid templates are just text files with placeholders and logic.

Create a file named something like `OrderConfirmation.liquid.html` (the `.html` is not required here but helps with editors parsing the syntax)

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <title></title>
</head>

<body>
    <p>
        Hello {{ recipientName }},

        Thank you for purchasing {{ productName }}
        Your order number is {{ orderNumber }}.

        We will notify you once your order has shipped.
    </p>

    <p>Order items included:</p>

    <ul>
        {% for item in Items %}
            <li>{{ item.Name }}</li>
        {% endfor %}
    </ul>

    <p>
        If you have any questions, contact us at:
        {{ supportEmail }}

        Kind regards,
        {{ senderName }}
    </p>
</body>
</html>
```

We can then render this in C# passing in a Model to populate any data we need to be dynamic.

```C#
using Fluid;

namespace EmailTesting.Templates

public class FluidEmailRenderer : IRenderHtmlEmails
{
    private static readonly FluidParser parser = new FluidParser();

    private IFluidTemplate? template;

    private static readonly TemplateOptions options = new();

    // Example of giving the template engine access to nested objects inside the model.
    static FluidEmailRenderer() {
        options.MemberAccessStrategy.Register<Order>();
        options.MemberAccessStrategy.Register<OrderItem>();

        // If we want to disable this safe behaviuor, we can just add the following instead
        // and give access to eevrything.
        options.MemberAccessStrategy = new unsafeMemberAccessStrategy();
    }

    static IFluidTemplate ParseTemplate(string path) {
        var liquid = File.ReadAllText(path);

        return parser.Parse(liquid);
    }

    public string RenderHtmlBody(Order order)
    {
        template ??= ParseTemplate("Templates/Emails/OrderConfirmation.liquid.html");

        var context = new TemplateContext(order, options);

        return template.Render(context);
    }
}
```

When adding this into our DI Container, we may want to render it as a transient in debug mode so we see any changes made to the file each time. For production, we can just add this as a Singleton. This is an example of something we can add to our `Program.cs` or extension method when adding this service to our container. 

This is just a basic example and in a real app, you would likely map it to use an interface which can switch out a new Renderer and sticking to the Open/Closed Principle.

```C#
#if DEBUG
builder.Services.AddTransient<FluidEmailRenderer>();
#else
builder.Services.AddSingleton<FluidEmailRenderer>();
#endif
```

We can also apply more things like filters for formatting and displaying information. This can be found in the documentation in the Github link at the start of this section.

### Other Template Libraries

Here is some more templating libraries available should Fluid not be the right choice.

RazorEngine.NetCore - https://github.com/Antaris/RazorEngine

Razor Components - https://learn.microsoft.com/en-us/aspnet/core/blazor/components/render-components-outside-of-aspnetcore?view=aspnetcore-9.0

### MJML

When trying to generate HTML emails, different clients handle the way they are received differently. Styles and CSS may work in one client but not the other. This is where MJML comes in. It is an open source framework used to generate HTML emails and make it easier to style your emails.

You can get started by visiting their site - https://mjml.io/

If you're using Visual Studio Code, you can also find an extension to help by searching MJML. You want the version which is by MJML as the one with the most downloads has now been archived. This helps with syntax highlighting and has a preview window to see what your email looks like.

To get started with using NJNL with .NET, we first need to install the NuGet package

```bash
dotnet add package Mjml.Net

# We may also need this package for adding some styles inline instead of using a style tag in the header
dotnet add package mjml.Net.PostProcessors
```

We then can import a template using the MJML syntax and render out the HTML

```C#
using Mjml.Net;

public class MjmlEmailRenderer(MjmlRenderer mjml)
{
    public string RenderHtmlBody() {
        var mjmlSource.File.ReadAllText("Templates/Emails/OrderEmail.mjml");

        var options = new MjmlOptions();

        var (output, errrors) = mjml.Render(mjmlSource, options);

        if (errors.Any()) throw new(errors.First().Error);

        return output;
    }
}
```

To implement Liquid based templating syntax into MJML, we need to make some changes.

Example of a template

```xml
<mjml>
  <mj-head>
    <mj-title>Order Confirmation</mj-title>
    <mj-preview>Thanks for your purchase, {{ recipientName }}!</mj-preview>
  </mj-head>
  <mj-body>
    <mj-section>
      <mj-column>
        <mj-text font-size="20px" font-weight="bold">
          Hello {{ recipientName }},
        </mj-text>

        <mj-text>
          Thank you for purchasing <strong>{{ productName }}</strong>!
          Your order number is <strong>{{ orderNumber }}</strong>.
        </mj-text>

        <mj-button background-color="#346DB7" color="white" href="{{ orderUrl }}">
          View Your Order
        </mj-button>

        <mj-text font-size="12px" color="#555">
          If you have any questions, contact us at {{ supportEmail }}.
        </mj-text>
      </mj-column>
    </mj-section>
  </mj-body>
</mjml>
```

We can then parse this and render it using something like this

```C#
using System;
using System.Diagnostics;
using System.IO;
using System.Threading.Tasks;
using Fluid;

class Program
{
    static async Task Main()
    {
        // Load MJML file
        var mjmlPath = Path.Combine(Directory.GetCurrentDirectory(), "OrderConfirmation.mjml");
        var mjmlTemplate = await File.ReadAllTextAsync(mjmlPath);

        // Parse the Liquid template
        var parser = new FluidParser();
        if (!parser.TryParse(mjmlTemplate, out var template, out var error))
        {
            Console.WriteLine($"Template parse error: {error}");
            return;
        }

        // Template data
        var model = new
        {
            recipientName = "Anthony",
            productName = "Testing Email",
            orderNumber = "MS-2025-000123",
            orderUrl = "https://example.com/orders/MS-2025-000123",
            supportEmail = "support@example.com"
        };

        var context = new TemplateContext(model);
        var renderedMjml = await template.RenderAsync(context);

        // Save the rendered MJML to file
        var tempMjmlFile = Path.GetTempFileName() + ".mjml";
        await File.WriteAllTextAsync(tempMjmlFile, renderedMjml);

        // Use mjml CLI to convert to HTML
        var process = new Process
        {
            StartInfo = new ProcessStartInfo
            {
                FileName = "mjml",
                Arguments = $"{tempMjmlFile} -o output.html",
                RedirectStandardOutput = true,
                RedirectStandardError = true,
                UseShellExecute = false
            }
        };

        process.Start();
        process.WaitForExit();

        Console.WriteLine("Email HTML generated in output.html");
    }
}
```

### Understanding SPF, DKIM, and DMARC for Email Sending


When sending email, especially from your own domain, three important protocols help ensure deliverability and protect against spoofing and phishing: **SPF**, **DKIM**, and **DMARC**.

---

### 1. SPF (Sender Policy Framework)

**Purpose:** Prevents spammers from sending emails pretending to be from your domain.

**How it works:**
- SPF is a **DNS TXT record** you add to your domain.
- It lists the mail servers or services allowed to send emails on behalf of your domain.
- When a recipient gets an email claiming to be from you, their email server checks your SPF record to see if the sending server is allowed.

**Example DNS record:**

```makefile
v=spf1 include:sendgrid.net include:spf.protection.outlook.com -all
```

- `include:` → services allowed to send mail for your domain.
- `-all` → fail if the sender is not on the list.

To see what is being included from the addresses in the allowed list, we can use `nslookup`

```bash
# Run nslookup
nslookup

# Now we get a terminal instance we type commands into
> set type=TXT
> spf.protection.outlook.com

# Should get a response like this
Server:  TestRouter
Address:  192.168.0.1

Non-authoritative answer:
spf.protection.outlook.com      text =

"v=spf1 ip4:40.92.0.0/15 ip4:40.107.0.0/16 ip4:52.100.0.0/15 ip4:52.102.0.0/16 ip4:52.103.0.0/17 ip4:104.47.0.0/17 ip6:2a01:111:f400::/48 ip6:2a01:111:f403::/49 ip6:2a01:111:f403:8000::/51 ip6:2a01:111:f403:c000::/51 ip6:2a01:111:f403:f000::/52 -all"
```

**Why it matters:** Without SPF, attackers can spoof your address and send fake emails in your name.

---

### 2. DKIM (DomainKeys Identified Mail)

**Purpose:** Ensures your email content hasn’t been altered and really came from your domain.

**How it works:**
- When you send an email, your mail server adds a **DKIM signature** (a cryptographic hash of the email) using a **private key**.
- The recipient's mail server retrieves your **public key** from DNS and verifies the signature.
- If the email is altered in transit, the verification fails.

**Example DKIM DNS record (TXT):**

```
Name: selector1._domainkey.example.com
Value: v=DKIM1; k=rsa; p=MIGfMA0GCSqGSIb3DQE...
```

- `selector1` → allows key rotation.
- `p=` → your public key.

**Why it matters:** DKIM confirms that the message wasn’t forged or tampered with in transit.

---

### 3. DMARC (Domain-based Message Authentication, Reporting, and Conformance)

**Purpose:** Tells recipients’ mail servers what to do if SPF and/or DKIM checks fail, and provides reports.

**How it works:**
- DMARC is another **DNS TXT record**.
- It sets a policy for handling failed checks: accept, quarantine, or reject.
- It can send **daily reports** showing who’s sending mail using your domain.

**Example DMARC record:**

```
v=DMARC1; p=quarantine; rua=mailto:dmarc-reports@example.com; sp=reject; aspf=s
```

- `p=quarantine` → suspicious emails go to spam.
- `p=reject` → block the emails.
- `rua=` → address for aggregate reports.
- `aspf=s` → strict SPF alignment.

**Why it matters:** DMARC ties SPF and DKIM together with an enforcement policy, making spoofing much harder.

You can use record generators to help with this part. one example is by Mimecast and can be found here - https://www.mimecast.com/content/dmarc-record-generator/

---

### How They Work Together

1. **SPF** → Checks *who* is allowed to send.
2. **DKIM** → Checks if the email content is genuine.
3. **DMARC** → Decides what happens if checks fail, and sends reports.

**Analogy (Airport Security):**
- **SPF** → Checks if the passenger is on the approved list.
- **DKIM** → Confirms their ID matches and hasn’t been altered.
- **DMARC** → Decides to let them in, send them to security, or deny entry — and logs the event.

---


## Dotnet MAUI

### Community ToolKit

The community toolkit is a dotnet MAUI add on for extra features which can be dropped into your application to help build certain parts of your application faster.

It can be downloaded as a NuGet package.

More information can be found here.

https://learn.microsoft.com/en-gb/dotnet/communitytoolkit/maui/

## Optimising MSSQL Queries

Start by wrapping the query in a `SHOWPLAN_ALL`

```SQL
SET SHOWPLAN_ALL ON;
GO

SELECT * FROM YourTable WHERE Column1 = 'SomeValue';
GO

SET SHOWPLAN_ALL OFF;
GO
```

| Column Name                   | Why It Matters                                | Optimization Strategy                      |
|--------------------------------|----------------------------------------------|-------------------------------------------|
| Estimated vs. Actual Rows      | Bad estimates lead to slow queries           | Update statistics, use better indexes    |
| Execution Mode                 | Row mode vs. Batch mode performance          | Use columnstore indexes for analytics    |
| Operator Cost                  | Shows most expensive operations              | Reduce high-cost operations              |
| Table Access (Scan vs. Seek)   | Seeks are faster than scans                  | Add proper indexes                       |
| Key Lookups                    | Causes extra reads                           | Use covering indexes                     |
| Join Type                      | Nested Loops, Merge, Hash affects speed      | Optimize join strategy                   |
| Sort Operator                  | Sorting is slow                              | Use indexed sorting                      |
| Parallelism (DOP, CXPACKET)     | Unnecessary parallelism can slow queries     | Adjust MAXDOP, optimize indexing         |
| CPU Time vs. Elapsed Time       | Shows if query is CPU-bound                  | Optimize calculations, indexes           |    

- Look for "Table Scan", "Clustered Index Scan" or "Hash Joins" in the plan.

```SQL
CREATE NONCLUSTERED INDEX IX_YourTable_Column1 
ON YourTable (Column1);
```


## Unit testing

To setup, right click the solution and Add -> New Project

Select the test suite to use. Recommend XUnit as it's cross platform.

XUnit tests need a `[Fact]` attribute above the methods.

Test Example:

```C#
using XUnit;

namespace UnitTestExample
{
    public class ExampleTests
    {
        // Basic Assert Style Test
        [Fact]
        public void Test1()
        {
            Assert.True(true);
        }

        // Example on using exception checking in tests 
        [Fact]
        public void Test2()
        {
            var example = new ExampleItem();

            Assert.Throws<ExceptionType>(() => example.SomeFailingMethod());
        }
    }
}
```

### Libraries

Some nice to have libraries to make testing a little easier.

Shouldly - https://docs.shouldly.org/

## Integration Testing

### Setup Notes

When working with integration tests, we need to make sure the tests project is 
referencing the API. 

To make sure we can read the Program we are about to use, we need to add this to the bottom of our `Program.cs` file in our API/Presentation Layer

```C#
public partial class Program { }
```

Next we can set up our integration tests using this kind of layout as an example.

```C#
using System.Net;
using System.Text;
using System.Text.Json;
using Microsoft.AspNetCore.Mvc.Testing;
using Microsoft.VisualStudio.TestPlatform.TestHost;

namespace tddapi.Tests.Endpoints;

public class OrderEndpointTests : IClassFixture<WebApplicationFactory<Program>>
{
    private readonly HttpClient _client;

    public OrderEndpointTests(WebApplicationFactory<Program> factory)
    {
        _client = factory.CreateClient();
    }

    [Fact]
    public async Task CreateOrder()
    {
        var newOrder = new { productId = 1, quantity = 2 };
        var content = new StringContent(JsonSerializer.Serialize(newOrder), Encoding.UTF8, "application/json");
        
        var response = await _client.PostAsync("api/orders", content);
        
        Assert.Equal(HttpStatusCode.Created, response.StatusCode);
    }
}
```
## CI/CD

### Setting Up GitHub Actions

To begin, we need to use a specific folder structure to place our YAML file inside our repo.

```bash
# ./.github/workflows/hello-world.yaml

mkdir .github

cd .github

mkdir workflows

cd workflows

touch hello-world.yaml
```

Inside the YAML file, we can start defining our name and triggers

```yaml
# Name of our workflow
name: Hello World

# Trigger to run our jobs
on:
    workflow_dispatch:

# Jobs and scripts we want to run when triggered
jobs:
    print-hello-world:
        runs-on: ubuntu-latest

        steps:
            - name: Say hello
              run: "Hello World"
```

Once we have finished defining our YAML file, we can commit the changes and push them to GitHub. 

On GitHub, there should now be a new workflow defined in the actions tab. We can run the example by going to the `Run Workflow` dropdown and click Run Workflow button.

### GitHub Marketplace

To speed up our workflow or make things simpler, we can use some workflows created by other developers and hosted on GitHub marketplace.

To use an existing workflow, we just need to use the `uses` keyword in our steps of our YAML file as below:

```yaml
name: Hello World

on:
    workflow_dispatch:

jobs:
    checkout-repo:
        runs-on: ubuntu-latest

        steps:
            # This is how we use a workflow in the marketplace
            # It is a good idea to use a specific version to avoid broken changes
            - uses: actions/checkout@v2
            # This is for passing arguments which are usually documented in the usages on the marketplace page
              with: # Not defined (comment out this line)
```

### Deploying A DotNet Application Example

```yaml
name: Build and Deploy .NET Project

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build-and-test:
    name: Build and Test
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Setup .NET
        uses: actions/setup-dotnet@v4
        with:
          dotnet-version: '8.0.x' # Change based on your project version

      - name: Restore dependencies
        run: dotnet restore

      - name: Build solution
        run: dotnet build --no-restore --configuration Release

      - name: Run Unit Tests
        run: dotnet test tests/YourProject.UnitTests/YourProject.UnitTests.csproj --no-build --configuration Release --logger "trx"

      - name: Run Integration Tests
        run: dotnet test tests/YourProject.IntegrationTests/YourProject.IntegrationTests.csproj --no-build --configuration Release --logger "trx"

  deploy:
    name: Deploy
    needs: build-and-test
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main' && github.event_name == 'push'

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Setup .NET
        uses: actions/setup-dotnet@v4
        with:
          dotnet-version: '8.0.x'

      - name: Publish project
        run: dotnet publish src/YourProject/YourProject.csproj -c Release -o ./publish

      - name: Deploy to server
        run: |
          echo "Deploying to production..."
          # Example deployment command
          # rsync, scp, Azure CLI, AWS CLI, Docker, etc.

```

### Adding Sensitive Data through Secrets

On GitHub you can click on the settings tab and add secret environment variables under Security > Secrets > Actions.

Click on `New repository secret`

These are stored as a Name: Value key pair.

In our workflow files, we then use them like this:

```yaml
name: Secret Workflow

on:
    workflow_dispatch:

jobs:
    test-secret:
        runs-on: ubuntu-latest

        steps:
            - name: Test secret
              run: |
                echo "Secrets:"
                echo ${{ secrets.TEST_SECRET }}
```

## Publishing A Project

This is what we need to do when we are distributing it to other users etc.

Right click on the project and select `Publish`

You can update the publish profile settings by clicking the edit button and updating the options.

A good one to be aware of is deployment mode. `Framework dependant` is when the user has .NET framework installed on their machine. `Self-contained` is to keep the framework and everything in one place to distribute to different a OS etc.

With a folder publish profile, it puts it in the `/bin` directory by default.

### Deploying To Linux

<u>Prepare Your Application:</u>

Ensure your .NET application is ready for deployment.

Publish the Application: Use the dotnet publish command to create a self-contained or framework-dependent deployment.

For a Framework-Dependent Deployment:

```bash
dotnet publish -c Release -o ./publish
```

This requires .NET Runtime installed on the Linux server.

For a Self-Contained Deployment:

```bash
dotnet publish -c Release -r linux-x64 --self-contained true -o ./publish
```

Replace `linux-x64` with the appropriate runtime identifier (RID) for your server's architecture. This bundles the .NET runtime with your application, so it doesn't require the runtime to be installed on the server.

<u>Set Up the Linux Server: </u>

Prepare the Linux environment to host your application.

Install .NET (if not using a self-contained deployment): Follow the instructions for your Linux distribution from the .NET installation guide.

Example for Ubuntu:

```bash
sudo apt update
sudo apt install -y dotnet-runtime-8.0
```

Install a Web Server (optional): Install Nginx or Apache if you plan to use a reverse proxy.

Example for Nginx:

```bash
sudo apt update
sudo apt install -y nginx
```

Create a User (optional): Create a dedicated user to run your application securely.

```bash
sudo adduser myappuser
```

<u>Transfer the Application to the Server:</u>

Copy your published application to the Linux server using a method like:

```bash
scp -r ./publish myappuser@your-server-ip:/var/www/myapp
```

<u>Configure and Run the Application</u>

Set Permissions: Ensure the application folder has the correct permissions.

```bash
sudo chown -R myappuser:myappuser /var/www/myapp
```

Run the Application: Navigate to the application directory and run it.

Example:

```bash
cd /var/www/myapp
dotnet MyApp.dll
```

For self-contained deployments:

```bash
./MyApp
```

Run the Application as a Background Service: Create a systemd service to keep your application running.

Example: /etc/systemd/system/myapp.service

```ini
[Unit]
Description=My .NET Application
After=network.target

[Service]
WorkingDirectory=/var/www/myapp
ExecStart=/usr/bin/dotnet MyApp.dll
Restart=always
User=myappuser
Environment=DOTNET_CLI_TELEMETRY_OPTOUT=1
Environment=ASPNETCORE_ENVIRONMENT=Production

[Install]
WantedBy=multi-user.target
```

Reload systemd, enable and start the service:

```bash
sudo systemctl daemon-reload
sudo systemctl enable myapp.service
sudo systemctl start myapp.service
```

<u>Configure a Reverse Proxy (Optional)</u>

If you're hosting a web application, use Nginx to forward requests to your .NET app.

Example: /etc/nginx/sites-available/myapp

```nginx
server {
    listen 80;
    server_name yourdomain.com;

    location / {
        proxy_pass http://localhost:5000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection keep-alive;
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}
```

Enable the configuration and restart Nginx:

```bash
sudo ln -s /etc/nginx/sites-available/myapp /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl restart nginx
```

### Setting Up A Jenkins Pipeline

Prepare Your Jenkins Environment

Install Jenkins: Make sure Jenkins is installed and running. You can install Jenkins on your local machine, a dedicated server, or use a cloud service.

Install Necessary Plugins:

Pipeline
Git Plugin (for pulling your repository)
SSH Agent Plugin (for deploying to the Linux server)
Install .NET SDK on the Jenkins Server: Install the .NET SDK on the Jenkins server to build and publish your .NET application.

For Ubuntu:

```bash
wget https://packages.microsoft.com/config/ubuntu/22.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install -y dotnet-sdk-7.0
```

Set Up Credentials for Linux Server:

- Go to Jenkins Dashboard → Manage Jenkins → Manage Credentials.
- Add an SSH key or password credentials for the Linux server.

Create a Jenkins Pipeline

Create a Jenkinsfile in Your Repository
This file defines your pipeline steps.

Example Jenkinsfile:

```groovy
pipeline {
    agent any

    environment {
        APP_NAME = "MyApp"
        PUBLISH_DIR = "publish"
        DEPLOY_DIR = "/var/www/myapp"
        SSH_CREDENTIALS = "your-ssh-credentials-id"
        SSH_SERVER = "my-linux-server.com"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/your-repo.git' // Update with your repository URL
            }
        }

        stage('Build and Publish') {
            steps {
                script {
                    // Ensure the publish directory is clean
                    sh 'rm -rf ${PUBLISH_DIR}'

                    // Publish the application
                    sh 'dotnet publish -c Release -o ${PUBLISH_DIR}'
                }
            }
        }

        stage('Deploy to Linux Server') {
            steps {
                sshagent(credentials: [env.SSH_CREDENTIALS]) {
                    script {
                        // Transfer the application files to the Linux server
                        sh """
                        scp -r ${PUBLISH_DIR}/* ${env.SSH_SERVER}:${DEPLOY_DIR}
                        """
                        
                        // Restart the application (assuming a systemd service)
                        sh """
                        ssh ${env.SSH_SERVER} "
                        sudo systemctl restart ${APP_NAME}.service
                        "
                        """
                    }
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
```

Set Up Jenkins Job

Go to Jenkins Dashboard and create a new pipeline job.
In the Pipeline section, specify the repository and branch where your Jenkinsfile is located.
Save the job.

Set Up the Linux Server
Ensure your Linux server is prepared for deployment:

Install .NET Runtime if using framework-dependent deployment:

```bash
sudo apt install -y dotnet-runtime-7.0
```

Create a directory for the app:

```bash
sudo mkdir -p /var/www/myapp
sudo chown -R myappuser:myappuser /var/www/myapp
```
Configure a systemd service (check deploy instructions)

Trigger the Pipeline

Run the Jenkins job, and it will:

Clone your repository.
Build and publish the .NET application.
Transfer the application to the Linux server.
Restart the application on the server.

Notes:
- Automated Rollbacks: You can extend the pipeline to include rollback steps if deployment fails.
- Logging: Add detailed logging to your pipeline steps for easier debugging.
- Security: Use environment variables or Jenkins credentials to store sensitive data like server details or SSH keys.

This setup provides a robust CI/CD pipeline for deploying a .NET application to a Linux server using Jenkins.

## Cool Nuget Packages

- Humaniser - https://github.com/Humanizr/Humanizer - Cool methods like humanizing strings, dates and numbers. E.g Last seen 2 hours ago.

- AngleSharp - https://github.com/AngleSharp/AngleSharp - Provides a way of picking HTML formatted text with CSS seelctors etc.

- PDFPig - https://github.com/UglyToad/PdfPig - PdfPig supports reading text and content from PDF files. It also supports basic PDF file creation.

