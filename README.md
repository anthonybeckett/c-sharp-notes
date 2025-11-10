# .Net Notes

# Contents
- [Contents](#contents)
- [Documentation & Learning Resources](#documentation--learning-resources)
- [Oh My Posh](#oh-my-posh)
- [VS Code Extensions](#vs-code-extensions)
- [Useful Commands](#useful-commands)
- [Setup](#setup)
    - [New Project Notes](#new-project-notes)
    - [Setting Up DotNetEnv](#setting-up-dotnetenv)
    - [Mapping Custom Endpoints For Razor Pages](#mapping-custom-endpoints-for-razor-pages)
    - [Creating A Library For Shared Code](#creating-a-library-for-shared-code)
- [Setup Secure Configuration](#setup-secure-configuration)
    - [Initial Config](#initial-config) 
    - [Setting Up Environment Variables Linux](#setting-up-environment-variables-linux)
    - [Accessing Environment Variables](#accessing-environment-variables)
    - [Azure Key Vault On Ubuntu](#azure-key-vault-on-ubuntu)
- [C# Topics](#c-topics)
    - [Extension Methods](#extension-methods)
    - [IHttpContextAccessor](#ihttpcontextaccessor)
    - [Switch Expressions](#switch-expressions)
    - [Collections](#collections)
    - [Enums](#enums)
    - [Structs](#structs)
    - [Records](#records)
    - [Generics](#generics)
    - [Tuples](#tuples)
    - [Strings & Bytes](#strings--bytes)
    - [Streams](#streams)
    - [Working With Files](#working-with-files)
    - [IDisposable](#idisposable)
    - [XML & Json](#xml--json)
    - [Callbacks & Delegates](#callbacks--delegates)
    - [Lazy Class](#lazy-class)
    - [Events](#events)
    - [Threads](#threads)
    - [Background Workers](#background-workers)
    - [With Expression](#with-expression)
- [LINQ](#linq)
    - [Introduction To Linq](#introduction-to-linq)
    - [Where Clauses](#where-clauses)
    - [Ordering Data](#ordering-data)
    - [Custom Comparer](#custom-comparer)
    - [Deferred Execution](#deferred-execution)
    - [Fetching Results](#fetching-results)
    - [Projecting Data To Another Shape](#projecting-data-to-another-shape)
    - [Partial Results](#partial-results)
    - [Deduplicating Data](#deduplicating-data)
    - [Aggregate Functions](#aggregate-functions)
    - [Set Operations](#set-operations)
    - [Select Many](#select-many)
    - [Joins](#joins)
    - [Creating Our Own IEnumerable Methods](#creating-our-own-ienumerable-methods)
    - [PLINQ](#plinq)
- [Reflection](#reflection)
    - [What Is Reflection](#what-is-reflection)
    - [Looking Up Types](#looking-up-types)
    - [Filtering Type Information](#filtering-type-information)
    - [Assembly Scanning](#assembly-scanning)
    - [Binding Flags](#binding-flags)
    - [Fetching Values](#fetching-values)
    - [Calling Methods](#calling-methods)
    - [Activator Class](#activator-class)
    - [Source Generators]()
- [Dotnet CLI Tips And References](#dotnet-cli-tips-and-references)
    - [Create A New Solution](#create-a-new-solution) 
    - [Add New Web API Project](#add-new-web-api-project)
    - [Add New Class Library Project](#add-new-class-library-project)
    - [Link Projects To Solution](#link-projects-to-solution)
    - [Link Projects As Dependencies](#link-projects-as-dependencies)
    - [Create A Migration In Another Project Folder](#create-a-migration-in-another-project-folder)
- [Async & Await](#async--await)
    - [Intro To Async Await](#intro-to-async-await)
    - [What We Used Before](#what-we-used-before)
    - [Parallel Programming](#parallel-programming)
    - [Compiled Code Example](#compiled-code-example)
    - [Creating Our Own Instance](#creating-our-own-instance)
    - [Do's and Dont's Of Async & Await](#dos-and-donts-of-async--await)
    - [IAsyncEnumerable](#iasyncenumerable)
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
    - [Installing CLI Template](#installing-cli-template)
    - [Layer Breakdown Examples](#layer-breakdown-examples)
    - [Setting Up A Project](#setting-up-a-project)
    - [Presentation Layer](#presentation-layer)
    - [Application Layer](#application-layer)
    - [Infrastructure Layer](#infrastructure-layer)
    - [Domain Layer](#domain-layer)
    - [Setting Up Dependency Injection Per Project](#setting-up-dependency-injection-per-project)
    - [Implementing A Repository From Interface With DI](#implementing-a-repository-from-interface-with-di)
    - [Implementing CQRS & Mediatr](#implementing-cqrs--mediatr)
    - [Result Pattern](#result-pattern)
    - [Repository Pattern](#repository-pattern)
    - [Setting Up Entity Framework Core](#setting-up-entity-framework-core)
    - [Unit Of Work Pattern](#unit-of-work-pattern)
    - [Using Fluent Api With Domain Objects And EF Core](#using-fluent-api-with-domain-objects-and-ef-core)
    - [Domain Driven Design](#domain-driven-design)
    - [Unit & Integration Testing](#unit--integration-testing) 
    - [Overriding Validation Filter Attribute](#overriding-validation-filter-attribute)
    - [Validation](#validation)
    - [Validation & MediatR Pipelines](#validation--mediatr-pipelines)
    - [Validation & MediatR Pipelines Using Generic Behaviours](#validation--mediatr-pipelines-using-generic-behaviours)
    - [Domain Events](#domain-events)
    - [Transactional & Eventual Consistency](#transactional--eventual-consistency)
    - [Authentication & Authorization](#authentication--authorization)
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
    - [Returning Problem Details](#returning-problem-details)
    - [Model Binding](#model-binding)
    - [Configuration](#configuration)
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
    - [Example CRUD using Async Await](#example-crud-using-async-await)
    - [Logging Queries Sent To The Database](#logging-queries-sent-to-the-database)
    - [Database Annotations](#database-annotations)
    - [Fluent API](#fluent-api)
    - [Relationships](#relationships)
    - [Value Converters](#value-converters)
    - [Owned And Complex Types](#owned-and-complex-types)
    - [Default Values](#default-values)
    - [Global Query Filters](#global-query-filters)
    - [Migrations](#migrations)
    - [Testing Entity Framework](#testing-entity-framework)
    - [Multi Tenancy](#multi-tenancy)
    - [Inheritence In Models](#inheritence-in-models)
    - [Compound Keys](#compound-keys)
    - [Using Raw Queries](#using-raw-queries)
    - [Keyless Entities](#keyless-entities)
    - [Interceptors](#interceptors)
    - [Types Of Performance Issues](#types-of-performance-issues)
- [Sending Emails](#sending-emails) 
    - [Getting Started Example](#getting-started-example)
    - [Setting Up Mailpit](#setting-up-mailpit)
    - [Building Text Only Based Emails](#building-text-only-based-emails)
    - [Using Fluid To Generate HTML Template Emails](#using-fluid-to-generate-html-template-emails)
    - [Other Template Libraries](#other-template-libraries)
    - [MJML](#mjml)
    - [Understanding SPF, DKIM, and DMARC for Email Sending](#understanding-spf-dkim-and-dmarc-for-email-sending)
    - [Using Thread Channels To Send Emails In The Background](#using-thread-channels-to-send-emails-in-the-background)
    - [Example Of Keeping The SMTP Client Alive For Multiple Messages](#example-of-keeping-the-smtp-client-alive-for-multiple-messages)
- [Dotnet MAUI](#dotnet-maui)
    - [Installing Dotnet MAUI](#installing-dotnet-maui)
    - [Setting Up A Maui Project](#setting-up-a-maui-project) 
    - [Community ToolKit](#community-toolkit)
    - [MauiProgram.cs](#mauiprogramcs)
    - [Creating A Content Page](#creating-a-content-page)
    - [Layouts](#layouts)
    - [BaseContentPage & Global Page Config](#basecontentpage--global-page-config)
    - [Margin & Padding](#margin--padding)
    - [XAML](#xaml)
    - [Collection Views](#collection-views)
    - [Refresh Views](#refresh-views)
    - [Colors](#colors)
    - [Resources](#resources)
    - [Styles & Theming](#styles--theming)
    - [Behaviours](#behaviours)
    - [Gestures](#gestures)
    - [Application Lifecycles](#application-lifecycles)
    - [Shell & Navigation](#shell--navigation)
    - [MVVM](#mvvm)
    - [MVVM Community Toolkit](#mvvm-community-toolkit) 
    - [iOS Issue](#ios-issue)
    - [MAUI Libraries](#maui-libraries)
    - [Creating A Calendar View](#creating-a-calendar-view)
    - [Memory Management](#memory-management)
    - [Connecting To Backend Services](#connecting-to-backend-services)
    - [Local Storage](#local-storage)
    - [SqLite](#sqlite)
    - [GraphQL](#graphql)
    - [GraphQL in MAUI](#graphql-in-maui)
    - [Cross Platform Services](#cross-platform-services)
    - [Unit Testing In Maui](#unit-testing-in-maui)
- [Optimising MSSQL Queries](#optimising-mssql-queries)
- [Unit Testing](#unit-testing)
    - [Libraries](#libraries)
    - [Test Class Lifecycle](#test-class-lifecycle)
    - [Parameterization](#parameterization)
    - [Exposing Internals To Tests](#exposing-internals-to-tests)
    - [Fakes](#fakes)
    - [Mocking](#mocking)
    - [Testing Static And Extension Methods](#testing-static-and-extension-methods)
    - [Class Fixtures](#class-fixtures)
    - [Collection Fixtures](#collection-fixtures)
    - [Parallelization](#parallelization)
    - [Advanced Parameterization](#advanced-parameterization)
    - [Testing DateTime](#testing-datetime)
    - [Code Coverage]()
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

## Setup

### New Project Notes

When using .NET api, add MapControllers() to the program.cs to enable controllers

```c#
app.UseEndpoints(endpoints => {
    endpoints.MapRazorPages();

    endpoints.MapControllers();
});

// Or if not using a razor frontend

app.MapControllers();

```  

### Setting Up DotNetEnv

In some cases, we may want to use a `.env` file to store more sensitive parameters. For this we can use a package called `DotNetEnv`. In your main project (usually with `Program.cs`) add the package.

```bash
dotnet add package DotNetEnv
```

In your `Program.cs` add this line

```C#
// If your .env file is in the same directory as your csprob and Program.cs
DotNetEnv.Env.Load();

// If you have it in your root project but have your project in a src folder, add the relative
// path as an argument
DotNetEnv.Env.Load("../.env");
```

In this instance, we will use this file to store our Database credentials. Lets add this to our `.env`

```
DB_CONNECTION="{Some database connection string goes here}"
```

Next, in our service where we are initialising our database, lets fetch the variable and pass it to our setup function.

```C#
var connString = Environment.GetEnvironmentVariable("DB_CONNECTION");

services.AddDbContext<AppDbContext>(options =>
    options.UseSqlServer(connString));
```

If we are using docker, we can map our .env variables to our Environment in our `compose.yaml` file then access them like this.

```yml
services:
  api:
    build: .
    ports:
      - "5000:5000"
      - "5001:5001"
    environment:
      - DOTNET_ENVIRONMENT=${DOTNET_ENVIRONMENT}
      - JWT__Secret=${JWT_SECRET}
      - JWT__Issuer=${JWT_ISSUER}
      - JWT__Audience=${JWT_AUDIENCE}
      - DB_CONNECTION=${DB_CONNECTION}
    depends_on:
      - db
```

```C#
var jwtSettings = new JwtSettings
{
    Audience = Environment.GetEnvironmentVariable("JWT_AUDIENCE") 
               ?? configuration["Jwt:Audience"],
               
    Issuer = Environment.GetEnvironmentVariable("JWT_ISSUER") 
             ?? configuration["Jwt:Issuer"],
             
    Secret = Environment.GetEnvironmentVariable("JWT_SECRET") 
             ?? configuration["Jwt:Secret"],
             
    TokenValidityInMinutes = int.Parse(
        Environment.GetEnvironmentVariable("JWT_TOKEN_VALIDITY_MINUTES") 
        ?? configuration["Jwt:TokenValidityInMinutes"] 
        ?? "15"),
        
    RefreshTokenValidityInDays = int.Parse(
        Environment.GetEnvironmentVariable("JWT_REFRESH_TOKEN_VALIDITY_DAYS") 
        ?? configuration["Jwt:RefreshTokenValidityInDays"] 
        ?? "60")
};

// We could also just make a helper function 
static class ConfigurationExtensions
{
    public static string GetEnvOrConfig(this IConfiguration config, string envVar, string configKey, string? defaultValue = null)
    {
        return Environment.GetEnvironmentVariable(envVar) ?? config[configKey] ?? defaultValue ?? throw new InvalidOperationException($"Missing configuration for {configKey}");
    }

    public static int GetEnvOrConfigInt(this IConfiguration config, string envVar, string configKey, int defaultValue)
    {
        var value = Environment.GetEnvironmentVariable(envVar) ?? config[configKey];
        return int.TryParse(value, out var result) ? result : defaultValue;
    }
}

// Then do this instead
var jwtSettings = new JwtSettings
{
    Audience = configuration.GetEnvOrConfig("JWT_AUDIENCE", "Jwt:Audience"),
    Issuer = configuration.GetEnvOrConfig("JWT_ISSUER", "Jwt:Issuer"),
    Secret = configuration.GetEnvOrConfig("JWT_SECRET", "Jwt:Secret"),
    TokenValidityInMinutes = configuration.GetEnvOrConfigInt("JWT_TOKEN_VALIDITY_MINUTES", "Jwt:TokenValidityInMinutes", 15),
    RefreshTokenValidityInDays = configuration.GetEnvOrConfigInt("JWT_REFRESH_TOKEN_VALIDITY_DAYS", "Jwt:RefreshTokenValidityInDays", 60)
};
```

The last way we can make this easier is by setting our `.env` variables with `__` and binding it to a object.

```env
Jwt__Audience=https://localhost:5001
Jwt__Issuer=https://localhost:5001
Jwt__Secret=q(v1qc7cfk%9s&gr$s672mw$)nabroi&d3bc6ww8&jf+ia#h+%
Jwt__TokenValidityInMinutes=15
Jwt__RefreshTokenValidityInDays=60
```

```C#
// Create an object to bind to
public class JwtSettings
{
    public string Audience { get; set; } = default!;
    public string Issuer { get; set; } = default!;
    public string Secret { get; set; } = default!;
    public int TokenValidityInMinutes { get; set; } = 15;
    public int RefreshTokenValidityInDays { get; set; } = 60;
}

// Bind in our Program.cs or wherever this is being configured
var jwtSettings = new JwtSettings();
configuration.GetSection("Jwt").Bind(jwtSettings);

// Or shorter with dependency injection
services.Configure<JwtSettings>(configuration.GetSection("Jwt"));
```

Now we can use it like so:

```C#
var jwtSettings = builder.Configuration.GetSection("Jwt").Get<JwtSettings>();

services.AddAuthentication(options =>
{
    options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
    options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;
})
.AddJwtBearer(options =>
{
    options.SaveToken = true;
    options.TokenValidationParameters = new()
    {
        ValidateIssuer = true,
        ValidateAudience = true,
        ValidateIssuerSigningKey = true,
        IssuerSigningKey = new SymmetricSecurityKey(
            Encoding.UTF8.GetBytes(jwtSettings.Secret)
        ),
        ValidIssuer = jwtSettings.Issuer,
        ValidAudience = jwtSettings.Audience,
        ValidateLifetime = true,
        ClockSkew = TimeSpan.Zero
    };
});
```

### Mapping Custom Endpoints For Razor Pages

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

### Creating A Library For Shared Code

Right click on the solution and click Add -> New Project.

Search for library.

Move code over and update the namespaces.

Right click on the project you want to insert it into and add as a dependency to be able to import it.


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

### IHttpContextAccessor

`IHttpContextAccessor` is a service provided by ASP.NET Core that allows you to access the current `HttpContext` (the object representing the incoming HTTP request and response) from places where HttpContext is not normally available like services, background tasks, or classes outside of controllers/middleware.

Normally, you can only access `HttpContext` inside controllers or middleware because it's tied to the current request.

With `IHttpContextAccessor`, you can inject it into a class and get the `HttpContext` from its .HttpContext property.

To enable this, register it in `Program.cs`

```C#
builder.Services.AddHttpContextAccessor();
```

Then use it by injecting it into your class and grabbing the HttpContext

```C#
public class CurrentUserService
{
    private readonly IHttpContextAccessor _httpContextAccessor;

    public CurrentUserService(IHttpContextAccessor httpContextAccessor)
    {
        _httpContextAccessor = httpContextAccessor;
    }

    public string? GetCurrentUserId()
    {
        return _httpContextAccessor.HttpContext?.User?.FindFirst(ClaimTypes.NameIdentifier)?.Value;
    }
}
```

### Switch Expressions

Starting with C# 8.0, you can use switch expressions to make branching code more concise and expressive compared to traditional switch statements.

```C#
// Simple example
static string GetDayType(DayOfWeek day) =>
        day switch
        {
            DayOfWeek.Saturday => "Weekend",
            DayOfWeek.Sunday   => "Weekend",
            _                  => "Weekday" // Default case
        };

// Example using pattern matching
static string DescribeNumber(int number) =>
    number switch
    {
        < 0 => "Negative",
        0   => "Zero",
        > 0 and < 10 => "Small positive number",
        _   => "Large number"
    };
```

- The `switch` keyword is used as an expression instead of a statement.
- The result is returned directly.
- The `_` pattern acts like the `default` case.
- Each arm uses `=>` instead of `:`.


### Collections

This section is going to contain some examples of collections in C#. 

---

Arrays (The original primitive type):

- Arrays are zero based index.
- Arrays are fixed in size.
- Arrays are mutable.

```C#
// Different ways of declaring arrays
int[] numbers = new int[3];

numbers[0] = 1;

int[] numbers2 = new int[]
{
    1,
    2,
    3
};

char[] letters = {
    'a',
    'b',
    'c'
};

char[] letters2 = [
    'd',
    'e',
    'f'
];

// Accessing & Setting Array values
numbers[0] = 1;

int valueFromArray = numbers[1]; // 2
```

---

Lists:

- Zero based index
- Dynamic in size
- Mutable
- Can call functions such as `Add()`, `Remove()`, `Clear()` etc.

```C#
// Initialisation
List<string> words = new();

words.Add("Word One");
words.Add("Word Two");
words.Add("Word Three");

List<int> numbers = new() {
    1,
    2,
    3
};
```

---

Dictionaries:

- Stored in Key, Value pairs
- Dynamic in size
- Can call functions such as `Add()`, `Remove()`, `Clear()` etc.

```C#
// Init a dictionary
Dictionary<string, int> wordsToNumbers = new();

// Setting a value in an already existing dictionary
wordsToNumbers.Add("one", 1);
wordsToNumbers.Add("two", 2);
wordsToNumbers.Add("three", 3);

// Getting values from a dictionary
int one = wordsToNumbers["one"];

// Other ways they can be initialized
Dictionary<string, int> wordsToNumbers2 = new()
{
    { "four", 4 },
    { "five", 5 }
};

Dictionary<string, int> wordsToNumbers3 = new()
{
    ["six"] = 6,
    ["seven"] = 7
};

// Checking if a dictionary has a key
bool contains = wordsToNumbers.ContainsKey("One"); // true

// Checking if a key exists and fetching the value
bool containsAnother = wordsToNumbers.TryGetValue("three", out int? value);

// Looping over a dictionary
foreach (KeyValuePair<string, int> item in wordsToNumbers) {
    Console.WriteLine(item.Key);
    Console.WriteLine(item.Value);
}
```

### Enums

An enum (short for enumeration) in C# is a special value type that lets you define a set of named constants for a variable.

It's useful when a variable should only hold one of a small, fixed number of related values, making code more readable and less error-prone.

```C#
public enum Direction
{
    North,
    East,
    South,
    West
}

Direction move = Direction.North;

if (move == Direction.West)
{
    Console.WriteLine("Heading west!");
}
```

The `[Flags]` attribute lets an enum represent a bit field, so you can combine multiple values with bitwise operators.

This is handy when an item can have more than one option at once. E.g a file that can be Read, Written, and/or Executed.

Values should be powers of two (1, 2, 4, 8...) so that each occupies a unique bit.

```C#
[Flags]
public enum FileAccessRights
{
    None    = 0,
    Read    = 1,   // 0001
    Write   = 2,   // 0010
    Execute = 4,   // 0100
    Delete  = 8    // 1000
}

class Program
{
    static void Main()
    {
        // Combine flags with bitwise OR
        FileAccessRights userRights = FileAccessRights.Read | FileAccessRights.Write;

        Console.WriteLine(userRights); // Output: Read, Write

        // Check if a flag is set using bitwise AND
        if ((userRights & FileAccessRights.Write) != 0)
        {
            Console.WriteLine("User can write.");
        }

        // Add another permission
        userRights |= FileAccessRights.Execute;
        Console.WriteLine(userRights); // Output: Read, Write, Execute

        // Remove a permission
        userRights &= ~FileAccessRights.Read;
        Console.WriteLine(userRights); // Output: Write, Execute
    }
}
```

### Structs

A struct (short for structure) is a value type that groups related data together. Similar to a lightweight class but with some key differences.

Value type: Stored directly on the stack (or inline in containing types) rather than the heap.
When you assign or pass a struct, you get a copy, not a reference.

No inheritance: A struct can implement interfaces but cannot inherit from another struct or class.

Good for small, immutable data: Ideal for types that represent a simple value, like a point, a color, or a coordinate.

```C#
public struct Point
{
    public int X;
    public int Y;

    public Point(int x, int y)
    {
        X = x;
        Y = y;
    }

    public void Translate(int dx, int dy)
    {
        X += dx;
        Y += dy;
    }
}

// Usage
Point p1 = new Point(5, 10);

Point p2 = p1;      // copies the value

p2.Translate(2, 3); // modifies only p2

Console.WriteLine(p1.X); // still 5

Console.WriteLine(p2.X); // 7
```

### Records

A record is a special kind of reference type (introduced in C# 9) designed to make immutable, data-centric objects easy to create and work with. Records are a reference type: Like a class, but focused on holding data rather than complex behavior. Two records are considered equal if all their properties match, even if they're different instances.

Records are immutable by default: You typically declare properties with init accessors so they can be set only during object creation.

These are best to use when representing data models, DTOs, or immutable state.

```C#
public record Person(string FirstName, string LastName);

var p1 = new Person("Jim", "Bloggs");
var p2 = new Person("John", "Doe");

Console.WriteLine(p1 == p2); // True (value equality)

// "with" expression to copy with changes
var p3 = p1 with { LastName = "Byron" };
```

### Generics

Generics in C# let you write type-safe, reusable code by defining classes, methods, or interfaces with type parameters instead of hard-coding a specific type.
This means you can create a single implementation, like a list, stack, or utility method that works with any data type while still getting compile-time checking and avoiding casts.

```C#
// Example on a class
public class Box<T>
{
    private T _item;

    public void Store(T item)
    {
        _item = item;
    }

    public T Retrieve()
    {
        return _item;
    }
}

var intBox = new Box<int>();
intBox.Store(42);
Console.WriteLine(intBox.Retrieve());

var stringBox = new Box<string>();
stringBox.Store("Hello");
Console.WriteLine(stringBox.Retrieve());

// Example of a method
public static T GetFirst<T>(T[] items)
{
    return items[0];
}

// If you define the type, it will be inferred
int firstInt = GetFirst(new[] { 1, 2, 3 });

// You can also apply the angle brackets just to be more clear
string firstStr = GetFirst<string>(new[] { "a", "b", "c" });
```

We can also restrict the generic by using the `where` keyword.

```C#
// An example where the generic passed in has to implement the IEntity interface
public interface IEntity
{
    int Id { get; }
}

public class GenericService<T> where T : IEntity
{
    public void PrintId(T entity)
    {
        Console.WriteLine(entity.Id);
    }
}

public class User : IEntity
{
    public int Id { get; set; }
}


// We can also implement multiple types to each generic by separating with a comma.
public class DataStore<T> where T : class, IEntity, new()
{
    public T CreateDefault()
    {
        return new T(); // Allowed because of 'new()' constraint
    }
}
```

### Tuples

A tuple in C# is a lightweight way to group several values together as a single object without defining a custom class or struct.

It's handy when you want to return or pass around multiple pieces of data that logically belong together but don't justify a separate type.

```C#
// Returning multiple values from a method
(string Name, int Age) GetPerson()
{
    return ("Ada", 36);
}

var person = GetPerson();

// Access by name
Console.WriteLine($"{person.Name} is {person.Age} years old.");

// Or by position
Console.WriteLine($"{person.Item1} is {person.Item2} years old.");

// Example unpacking the tuple into separate variables
var (name, age) = GetPerson();

Console.WriteLine($"{name} is {age} years old.");
```

In C# there are two tuple types you might encounter: the older System.Tuple and the newer System.ValueTuple.

They serve a similar purpose-grouping multiple values, but differ in implementation, syntax, and performance.

System.Tuple<...> (old reference type):

- Reference type (lives on the heap).
- Introduced in .NET 4.0.
- Properties are read-only and named Item1, Item2, etc.
- No deconstruction syntax or friendly field names.

```C#
Tuple<string,int> t1 = Tuple.Create("Ada", 36);
Console.WriteLine(t1.Item1); // "Ada"
Console.WriteLine(t1.Item2); // 36
```

System.ValueTuple<...> (modern value type):

- Value type (struct) lives on the stack when possible, so it's faster and allocates less memory.
- Introduced in C# 7.
- Supports named elements, deconstruction, and concise syntax.
- Used by default when you write (type1, type2).

```C#
ValueTuple<string, int> t2 = new("Ada", 36);
Console.WriteLine(t2.Item1);  // "Ada"
Console.WriteLine(t2.Item2);   // 36

var (name, age) = t2; 
Console.WriteLine($"{name} is {age}");
```

### Strings & Bytes

Strings in C# represent a sequence of characters. When it comes to sending data, computers work with binary. This means we need to `encode` and `decode` between these two types by mapping characters to/from their binary representation.

The most common type you will come across when encoding is `UTF-8`.

```C#
using System.Text;

// Converting to bytes
byte[] data = Encoding.UTF8.GetBytes("Hello");

// Converting bytes back to a string
string text = Encoding.UTF8.GetString(data);
```

### Streams

Streams in C# allow us to work with data in a more abstract way than just having a byte array.

Streams provide us a common API for working with binary data without having to know exactly how that data is represented behind the scenes.

Streams come from an abtract `Stream` class which then provide data such as
- The length of the data
- The current position in the data
- If we can read or write to the data

One common type of Stream is a `MemoryStream`

```C#
// Writing and reading back to a memory stream using a StreamWriter
using var memoryStream = new MemoryStream();

using (var writer = new StreamWriter(memoryStream, Encoding.UTF8, leaveOpen: true))
{
    writer.Write("Hello from MemoryStream!");
}

// Reset position to the start so we can read what we just wrote
memoryStream.Position = 0;

using var reader = new StreamReader(memoryStream, Encoding.UTF8);
string text = reader.ReadToEnd();

Console.WriteLine(text);


// Reading a byte array through a memory stream
byte[] rawData = { 0x41, 0x42, 0x43 }; // ASCII for "ABC"

// We can pass it as an argument to the constructor
using var memoryStream = new MemoryStream(rawData);

// Or we can use the write function
memoryStream.Write(
    rawData,
    offset: 0,
    count: data.Length
);

int currentByte;
// We can loop over each byte individually
while ((currentByte = memoryStream.ReadByte()) != -1)
{
    Console.Write((char)currentByte); // Prints ABC
}

// Or we can use the Read() method
byte[] readBuffer = new byte[memoryStream.Length];

int numberOfBytesRead = memoryStream.Read(
    readBuffer,
    0,
    readBuffer.Length
);

Console.WriteLine(Encoding.UTF8.GetString(readBuffer));

// We can also access properties like this
Console.WriteLine(memoryStream.Position);

Console.WriteLine(memoryStream.Length);

Console.WriteLine(memoryStream.Capacity);
```

### Working With Files

In C#, working with files means using the classes in the `System.IO` namespace to create, read, write, copy, move, and delete files.

```C#
using System;
using System.IO;

// Checking if a file exists
string path = @"C:\Temp\example.txt";

if (File.Exists(path))
{
    Console.WriteLine("File already exists.");
}
else
{
    Console.WriteLine("No file found.");
}


// Writing to a file
File.WriteAllText(path, "Hello World");

// Appending text to a file
File.AppendAllText(path, "\nAnother line");

// Writing larger or continuous data using a StreamWriter
using (var writer = new StreamWriter(path))
{
    writer.WriteLine("First line");
    writer.WriteLine("Second line");
}

// Reading from a file
string content = File.ReadAllText(path);
Console.WriteLine(content);

// Reading a file line by line
string[] lines = File.ReadAllLines(path);
foreach (var line in lines) {
    Console.WriteLine(line);
}

// Reading large files line by line
using var reader = new StreamReader(path);
while (!reader.EndOfStream)
{
    Console.WriteLine(reader.ReadLine());
}

// Reading and writing byte data
byte[] data = { 0x01, 0x02, 0x03 };
File.WriteAllBytes(path, data);

byte[] readBack = File.ReadAllBytes(path);
Console.WriteLine($"Read {readBack.Length} bytes");

// More byte data using FileStream
using var fs = new FileStream(path, FileMode.OpenOrCreate, FileAccess.Write);
byte[] bytes = System.Text.Encoding.UTF8.GetBytes("Streaming example");
fs.Write(bytes, 0, bytes.Length);

// Copy, moving and deleting
File.Copy(path, @"C:\Temp\backup.txt", overwrite: true);
File.Move(path, @"C:\Temp\newname.txt");
File.Delete(@"C:\Temp\backup.txt");

// Using File.Open() with the FileStream
// Open the file for writing (create if it doesn't exist)
using (FileStream fs = File.Open(path, FileMode.OpenOrCreate, FileAccess.Write))
{
    byte[] data = System.Text.Encoding.UTF8.GetBytes("Hello from File.Open!");

    fs.Write(data, 0, data.Length);
}

// Open the file for reading
using (FileStream fs = File.Open(path, FileMode.Open, FileAccess.Read))
{
    byte[] buffer = new byte[fs.Length];

    fs.Read(buffer, 0, buffer.Length);

    string content = System.Text.Encoding.UTF8.GetString(buffer);

    Console.WriteLine(content);
}
```

### IDisposable

`IDisposable` is an interface in C# that provides a standard way to release unmanaged resources (like file handles, database connections, network sockets, or memory outside the .NET garbage collector).

```C#
public interface IDisposable
{
    void Dispose();
}
```

The typical pattern is to wrap the object in a `using` statement, which ensures `Dispose()` is called automatically:

```C#
using (var stream = new FileStream("example.txt", FileMode.Open))
{
    // Work with the stream
    byte[] buffer = new byte[stream.Length];
    stream.Read(buffer, 0, buffer.Length);
} // Dispose() is called automatically here

// Since C# 8 we also can use the using keyword like this, and will call the dispose method 
// when it goes out of scope
using var stream = new FileStream("example.txt", FileMode.Open);
```

Common uses for IDispoable include:
- File I/O: `FileStream`, `StreamReader`, `StreamWriter`
- Database connections: `SqlConnection`, `SqlCommand`
- Network sockets: `TcpClient`, `NetworkStream`
- Timers, graphics objects, and other unmanaged resources

### XML & Json

XML and JSON formats are usually used by API's and are formats used to transport data.

XML is a markup language `eXtensible Markup Language`.

For XML, `System.Xml` and `LINQ-to-XML` (System.Xml.Linq) are commonly used.

Example using the built in `System.Xml`:

```C#
using System;
using System.Xml;

var doc = new XmlDocument();

// Create the XML declaration
XmlDeclaration xmlDecl = doc.CreateXmlDeclaration("1.0", "UTF-8", null);
doc.AppendChild(xmlDecl);

// Create the root element
XmlElement root = doc.CreateElement("Person");
doc.AppendChild(root);

// Add child elements
XmlElement name = doc.CreateElement("Name");
name.InnerText = "Ada Lovelace";
root.AppendChild(name);

XmlElement age = doc.CreateElement("Age");
age.InnerText = "36";
root.AppendChild(age);

// Save to a file
doc.Save("person.xml");

Console.WriteLine("XML file created!");


//Reading back the xml file
var doc = new XmlDocument();
doc.Load("person.xml");

// Select nodes
XmlNode nameNode = doc.SelectSingleNode("/Person/Name")!;
XmlNode ageNode = doc.SelectSingleNode("/Person/Age")!;

Console.WriteLine($"{nameNode.InnerText} is {ageNode.InnerText} years old.");
```

Example using `LINQ-to-XML`:

```C#
// Using the System.Xml.Linq library
using System.Xml.Linq;

// Create an XML document
var xml = new XElement("Person",
    new XElement("Name", "Ada"),
    new XElement("Age", 36)
);

// Save to file
xml.Save("person.xml");

// Or convert to string
string xmlString = xml.ToString();
Console.WriteLine(xmlString);

// reading XML
var loadedXml = XElement.Load("person.xml");
string name = loadedXml.Element("Name")!.Value;
int age = int.Parse(loadedXml.Element("Age")!.Value);

Console.WriteLine($"{name} is {age} years old.");
```

JSON stands for JavaScript Object Notation.

The recommended way is using System.Text.Json (built-in since .NET Core 3.0) or Newtonsoft.Json.

```C#
// Define a model
public record Person(string Name, int Age);

// Serialize to JSON
using System.Text.Json;

var person = new Person("Ada", 36);

// Convert to JSON string
string json = JsonSerializer.Serialize(person);
Console.WriteLine(json);

// Deserialize JSON
string jsonData = @"{""Name"":""Alan"",""Age"":42}";
Person p = JsonSerializer.Deserialize<Person>(jsonData)!;
Console.WriteLine($"{p.Name} is {p.Age} years old.");
```

### Callbacks & Delegates

A callback is a method that you pass as an argument to another method, which is then called ("called back") at some point during execution. Delegates are the main way to implement callbacks in C#. Callbacks are useful for asynchronous operations, event handling, or customizing behavior in libraries.

Callback example:

```C#
delegate void OperationCompleted(string result);

class Program
{
    static void Main()
    {
        // Passing our ShowResult method as an argument 
        // Notice the parenthesis are missing from the end as 
        // we don't want to execute the function yet
        DoWork("Task1", ShowResult);
    }

    static void DoWork(string taskName, OperationCompleted callback)
    {
        
        Console.WriteLine($"Working on {taskName}...");
        

        callback($"{taskName} is done!");
    }

    static void ShowResult(string message)
    {
        Console.WriteLine($"Callback received: {message}");
    }
}
```

A delegate in C# is a type-safe object that references a method.
Think of it as a function pointer in other languages, but safe and managed. Delegates allow you to pass methods as parameters, store them in variables, and invoke them later.

- Delegates define the signature of methods they can point to (return type + parameters).
- They are type-safe: you can only assign a method that matches the delegate signature.
- Can point to static or instance methods.

```C#
// Define a delegate type
delegate void Notify(string message);

class Program
{
    static void Main()
    {
        // Assign a method to the delegate
        Notify notifier = ShowMessage;

        // Invoke the delegate
        notifier("Hello, world!");

        // We can also use the Invoke() method
        notifier.Invoke();
    }

    static void ShowMessage(string msg)
    {
        Console.WriteLine(msg);
    }
}
```

We also have two types built in to C# for delegates called `Action` and `Func`
`Action` represents a method that returns void. `Func` represents a method that returns a value.

`Action` example:

```C#
using System;

class Program
{
    static void Main()
    {
        // Action with one parameter
        Action<string> greet = name => Console.WriteLine($"Hello, {name}!");
        greet("Ada"); // Output: Hello, Ada!

        // Action with two parameters
        Action<int, int> add = (x, y) => Console.WriteLine($"{x} + {y} = {x + y}");
        add(5, 7); // Output: 5 + 7 = 12
    }
}
```

`Func` example:

```C#
using System;

class Program
{
    static void Main()
    {
        // Func with two parameters and a return value
        Func<int, int, int> multiply = (x, y) => x * y;
        int result = multiply(4, 5);
        Console.WriteLine(result); // Output: 20

        // Func with no parameters
        Func<string> getGreeting = () => "Hello from Func!";
        Console.WriteLine(getGreeting()); // Output: Hello from Func!
    }
}
```

### Lazy Class

In C#, `Lazy<T>` is a generic class in the System namespace that provides lazy initialization.It delays creating an object until the first time you actually need it.

Why to use Lazy:

- Performance: Avoids expensive object creation unless required.
- Thread Safety: Ensures that initialization happens only once, even if accessed by multiple threads.
- Clean Code: Handles all the "check if already created" logic for you.

```C#
Lazy<int> lazyValue = new Lazy<int>(() => {
    Console.WriteLine("This will only run once");
    Console.WriteLine("Fixing the max");

    int[] numbers = [35, 20, 30, 40, 50];

    int max = int.MinValue;

    foreach (var number in numbers) {
        if (number > max ) {
            max = number;
        }

        // Simulate an expensive operation
        Thread.Sleep(1000);
    }

    Console.WriteLine($"The max value is {max}");

    return max;
});

// Call the lazy method. To understand what is happening, we can call this multiple times
// and it will run the calculation once then return instantly after the inital call.
Console.WriteLine($"The value of lazy is {lazyValue.Value}");
```

### Events

Events and event handlers in C# are a way we can have delegates be called by "subscribing" them to events. This allows us to create a mechanism where we can notify other components in our systemabout changes they care about.

In the most common scenarios, events use an EventHandler delegate, which accepts a type called `EventArgs`. This delegate signature is:

```C#
public delegate void EventHandler<TEventArgs>(object sender, TEventArgs e)
```

The `sender` parameter is the object that raised the event. The `e` parameter is an instance of the EventArgs class.

Example:

```C#
// Create our own event args
public class MessageEventArgs : EventArgs
{
    public MessageEventArgs(string message)
    {
        Mesage = message;
    }

    public string Message { get; }
}

// Create an event source
public class EventSource
{
    // This declares the event, and the type of event
    // but nothing outside this class can raise the event
    // directly by accessing this.
    public event EventHandler<MessageEventArgs> SourceChanged;

    public void RaiseEvent(string message)
    {
        // SourceChanged can be null if nothing is subscribed
        SourceChanged?.Invoke(this, new MessageEventArgs(message));
    }
}

// Using our event handler
EventSource source = new();

// We hook up new handlers with +=
// We can also use -= to remove events
source.SourceChanged += Source_SourceChanged;

// THis will cause the event to be raised
source.RaiseEvent("Hello event");

// Event we want to subscribe to the EventSource
void Source_SourceChanged(object? sender, MessageEventArgs e)
{
    Console.WriteLine($"Sender: {sender}");
    Console.WriteLine($"Message: {e.Message}");
}
```

Another example:

```C#
using System;

public class Timer
{
    // Declare the event using EventHandler
    public event EventHandler? Tick;

    public void Start()
    {
        for (int i = 0; i < 3; i++)
        {
            System.Threading.Thread.Sleep(1000);
            OnTick();
        }
    }

    // Protected virtual method to raise the event
    protected virtual void OnTick() =>
        Tick?.Invoke(this, EventArgs.Empty);
}

public class Program
{
    public static void Main()
    {
        var timer = new Timer();

        // Subscribe to the event with a lambda
        timer.Tick += (sender, e) =>
            Console.WriteLine($"Tick at {DateTime.Now:T}");

        timer.Start();
    }
}
```

One more example handling emails:

```C#
using System;
using System.Net;
using System.Net.Mail;

public class OrderService
{
    public event EventHandler<OrderEventArgs>? OrderPlaced;

    public void PlaceOrder(string product, int quantity)
    {
        // business logic here ...
        OrderPlaced?.Invoke(this, new OrderEventArgs(product, quantity));
    }
}

public class EmailNotifier
{
    public void OnOrderPlaced(object? sender, OrderEventArgs e)
    {
        using var client = new SmtpClient("smtp.example.com")
        {
            Port = 587,
            Credentials = new NetworkCredential("username", "password"),
            EnableSsl = true
        };

        using var message = new MailMessage(
            "store@example.com",
            "customer@example.com",
            "Order Confirmation",
            $"Your order for {e.Quantity} × {e.Product} has been received."
        );

        client.Send(message);   // Send the email
    }
}

public record OrderEventArgs(string Product, int Quantity) : EventArgs;

class Program
{
    static void Main()
    {
        var service = new OrderService();
        var notifier = new EmailNotifier();

        // Subscribe the email sender to the event
        service.OrderPlaced += notifier.OnOrderPlaced;

        // Trigger it
        service.PlaceOrder("Laptop", 2);
    }
}
```

Make sure to unsubscribe from event handlers as keeping them attached can cause memory leaks.

### Threads

A thread is a separate path of execution inside a process. Your program's main method runs on one thread by default. You can create additional threads to run tasks in parallel, allowing your application to stay responsive or perform work concurrently (e.g., processing data while handling user input).

Each thread has its own call stack but shares the process's memory space with other threads.

```C#
using System;
using System.Threading;

class Program
{
    static void Main()
    {
        // Create a new thread and point it to a method
        Thread worker = new Thread(DoWork);

        Console.WriteLine("Starting worker thread...");
        worker.Start(); // Start running DoWork on a new thread

        // Main thread continues immediately
        Console.WriteLine("Main thread is free to do other work...");

        worker.Join(); // Wait for the worker thread to finish
        Console.WriteLine("Worker thread has completed.");
    }

    static void DoWork()
    {
        Console.WriteLine("Worker thread is running...");
        Thread.Sleep(1000); // Simulate time-consuming task
        Console.WriteLine("Worker thread finished task.");
    }
}
```

You can pass data to a new thread in a few simple ways.

The easiest method is to start the thread with a lambda expression that closes over local variables:

```C#
using System;
using System.Threading;

class Program
{
    static void Main()
    {
        string message = "Hello from worker!";
        int repeat = 3;

        Thread worker = new Thread(() =>
        {
            for (int i = 0; i < repeat; i++)
            {
                Console.WriteLine(message);
                Thread.Sleep(500);
            }
        });

        worker.Start();
        worker.Join();
    }
}
```

### Background Workers

`BackgroundWorker` (from `System.ComponentModel`) is a .NET class that lets you run long-running work on a separate, background thread while safely reporting progress and completion back to the UI thread.

It was popular in Windows Forms and WPF before async/await became common.

Key features:

- Runs work in the background so the UI stays responsive.
- Supports progress reporting (ProgressChanged) and completion events (RunWorkerCompleted).
- Automatically marshals event calls back to the UI thread, so you can update controls directly.

For new development, you'd typically use `Task.Run` with `async/await` or `IProgress<T>` instead of BackgroundWorker.

Example using WinForms:

```C#
using System;
using System.ComponentModel;
using System.Windows.Forms;

public class MainForm : Form
{
    private readonly BackgroundWorker worker = new() { WorkerReportsProgress = true };
    private readonly ProgressBar progressBar = new() { Dock = DockStyle.Top };
    private readonly Button startButton = new() { Text = "Start", Dock = DockStyle.Top };

    public MainForm()
    {
        Controls.Add(progressBar);
        Controls.Add(startButton);

        // Hook up events
        worker.DoWork += Worker_DoWork;
        worker.ProgressChanged += Worker_ProgressChanged;
        worker.RunWorkerCompleted += Worker_RunWorkerCompleted;

        startButton.Click += (_, __) => worker.RunWorkerAsync();
    }

    private void Worker_DoWork(object? sender, DoWorkEventArgs e)
    {
        for (int i = 0; i <= 100; i += 10)
        {
            System.Threading.Thread.Sleep(200);
            worker.ReportProgress(i);
        }
    }

    private void Worker_ProgressChanged(object? sender, ProgressChangedEventArgs e) =>
        progressBar.Value = e.ProgressPercentage;

    private void Worker_RunWorkerCompleted(object? sender, RunWorkerCompletedEventArgs e) =>
        MessageBox.Show("Work complete!");
}

// Entry point
Application.Run(new MainForm());
```

### With Expression

The `with` expression, introduced in C# 9 creates a copy of an existing immutable object while changing one or more of it's properties.

```C#
app.MapPost("/customers", (Customer customer) =>
{
    var createdCustomer = customer with { Id = Guid.NewGuid() };
    return Results.Created($"/customers/{createdCustomer.Id}", createdCustomer);
});

public record Customer(Guid Id, string Name, string Email);
```

- `customer` itself is not modified (immutability).
- The result (`createdCustomer`) is a new object.

The with expression is:

- Common and idiomatic when working with records (introduced in C# 9).
- Less common with regular classes (because with only works with record types by default).

It's used frequently in:

- Domain models that emphasize immutability (e.g., DDD, clean architecture).
- Functional-style programming in C#.
- Minimal APIs or ASP.NET Core apps where DTOs or records are passed around.

Use it when:

- You are using immutable records (e.g., record or record struct).
- You want clear, functional-style updates to immutable data.
- You want to avoid accidental mutations of shared objects.
- You're working with value-based equality (records compare by values, not references).

Avoid it when:

- You're using mutable classes (e.g., normal class with settable properties) the with syntax doesn't work unless you define your own "clone" behavior.
- You need deep copies (it's a shallow copy).
- You're in performance-critical code that creates lots of short-lived objects (immutability can increase GC pressure).


## LINQ

### Introduction To Linq

LINQ (Language Integrated Query) is one of the most powerful and elegant features in C#.
It lets you query, filter, and transform data in a declarative, SQL-like way but using strongly typed C# code instead of strings.

Some benefits include:

- Eliminates manual loops and conditionals.
- Greatly improves readability and maintainability.
- Type-safe and compiler-checked.
- Works seamlessly with Entity Framework Core.
- Reduces the need for hand-written SQL or boilerplate code.

### Where Clauses

In LINQ, the where clause is used to filter data. It lets you select only the elements that satisfy a given boolean condition.

It works just like an if statement inside a loop, but written declaratively.

```C#
// Model
var people = new List<Person>
{
    new Person { Name = "Alice", Age = 25 },
    new Person { Name = "Bob", Age = 17 },
    new Person { Name = "Charlie", Age = 32 }
};

// Query syntax example
var adults = from p in people
             where p.Age >= 18
             select p;

// Fluent Syntax
var adults = people
    .Where(p => p.Age >= 18)
    .ToList();
```

If we need to use multiple where clauses we can do so like this:

```C#
// Query based
var result = from p in people
             where p.Age >= 18 && p.Name.StartsWith("A")
             select p;

// We can also use multiple where conditions instead of using ampersands
var result = from p in people
             where p.Age >= 18 
             where p.Name.StartsWith("A")
             select p;

// Fluent syntax
var result = people
    .Where(p => p.Age >= 18 && p.Name.StartsWith("A"));

// Multiple where examples
var result = people
    .Where(p => p.Age >= 18)
    .Where(p => p.Name.StartsWith("A"))
```

### Ordering Data

To order data, we can use `orderby/OrderBy()`.

```C#
// Model
var songs = new List<Song>
{
    new Song { Title = "Electric Feel", Artist = "MGMT", Year = 2007, Plays = 5200000 },
    new Song { Title = "Yellow Submarine", Artist = "The Beatles", Year = 1966, Plays = 8800000 },
    new Song { Title = "Lose Yourself", Artist = "Eminem", Year = 2002, Plays = 15000000 },
    new Song { Title = "Bad Guy", Artist = "Billie Eilish", Year = 2019, Plays = 12000000 },
    new Song { Title = "Clocks", Artist = "Coldplay", Year = 2002, Plays = 7800000 }
};

// Order by with query syntax
var orderedByYear = from s in songs
                    orderby s.Year
                    select s;

// Order by with fluent syntax
var orderedByYear = songs.OrderBy(s => s.Year);

// Grouping multiple group by query syntax
var sortedSongs = from s in songs
                  orderby s.Artist, s.Title
                  select s;

// Grouping multiple group bys with fluent syntax
var sortedSongs = songs
    .OrderBy(s => s.Artist)
    .ThenBy(s => s.Title);

// Order by descending query syntax
var popularSongs = from s in songs
                   orderby s.Plays descending
                   select s;

// Order by descending fluent syntax
var popularSongs = songs
    .OrderByDescending(s => s.Plays);
```

### Custom Comparer

A custom comparer in LINQ (or in general .NET collections) is a powerful way to control how items are sorted or compared when the default behavior isn't enough. This does only work in the fluent syntax.

You do this by implementing one of these interfaces:

- `IComparer<T>` - used for sorting (e.g. `OrderBy`, `Sort`, etc.)
- `IEqualityComparer<T>` - used for equality checks (e.g. `Distinct`, `GroupBy`, `Except`)

```C#
// Model
var songs = new List<Song>
{
    new Song { Title = "Electric Feel", Artist = "MGMT", Plays = 5200000 },
    new Song { Title = "Bad Guy", Artist = "Billie Eilish", Plays = 12000000 },
    new Song { Title = "Yellow Submarine", Artist = "The Beatles", Plays = 8800000 },
    new Song { Title = "Clocks", Artist = "Coldplay", Plays = 7800000 },
    new Song { Title = "Another One Bites The Dust", Artist = "Queen", Plays = 15000000 }
};

// Custom comparer
public class SongTitleLengthComparer : IComparer<Song>
{
    public int Compare(Song? x, Song? y)
    {
        if (x == null || y == null)
            return 0;

        // Compare by title length
        int lengthComparison = x.Title.Length.CompareTo(y.Title.Length);

        // If same length, fallback to alphabetical order
        if (lengthComparison == 0)
            return string.Compare(x.Title, y.Title, StringComparison.OrdinalIgnoreCase);

        return lengthComparison;
    }
}

// Using the custom comparer in LINQ
var orderedSongs = songs.OrderBy(s => s, new SongTitleLengthComparer());
```  

### Deferred Execution

Deferred execution means that a LINQ query is not executed immediately when it's defined.
It's only executed later, when you actually iterate over the results.

A LINQ query executes when you enumerate it. That is, when you:

- Use a foreach loop

- Call methods like:
    - `.ToList()`
    - `.ToArray()`
    - `.Count()`
    - `.First()`
    - `.Sum()`
    - `.Any()`

```C#
var numbers = new List<int> { 1, 2, 3, 4, 5 };

// Define query (not executed yet)
var evens = numbers.Where(n => n % 2 == 0);

// Change the source before executing
numbers.Add(6);

// Execute query (now it runs)
foreach (var n in evens)
{
    Console.WriteLine(n);
}
```

Use deferred execution when you want a query that always reflects the current state of the data.

Use immediate execution when you need a fixed snapshot of results (e.g., for logging or caching).

### Fetching Results

To fetch all results when using LINQ we can use the `select` syntax or method.

```C#
// Fetching all results using query syntax
var allSongs = from s in songs
               select s;

// Fetching all results using fluent syntax
var allSongs = songs.Select(s => s);

// Fetching all filtered results
var coldplaySongs = songs.Where(s => s.Artist == "Coldplay");

foreach (var s in coldplaySongs)
    Console.WriteLine(s.Title);

// Fetching all results as a dictionary
var result = songs.ToDictionary(
    song => song.id,
    song => song.Title
);

foreach (var songId in result.Keys) {
    Console.WriteLine(result[songId]);
}
```

To fetch a single result, we can use methods like `First()`, `Single()`, `Last()` and others.

```C#
// Example fetching the first result
var firstColdplaySong = songs.First(s => s.Artist == "Coldplay");
Console.WriteLine(firstColdplaySong.Title);

// Example fetching the first result and avoiding exceptions
var firstBeatlesSong = songs.FirstOrDefault(s => s.Artist == "The Beatles");

// Example when using single()
// Note if there is more than one result, it will throw an exception
var findSongById = songs.Single(s => s.Id == 1);
```

### Projecting Data To Another Shape

There is often times we don't need to return every column in a dataset and instead only want to select a few. We can do this by using the `SELECT/select()` syntax.

```C#
// If we want to select one field using query syntax
var results = from s in songs
              select s.Title

// If we want to select multiple fields using query syntax
var results = from s in songs
              select new { s.Title, s.Artist, s.Year };

// We can also do something similar using the fluent syntax
var results = songs.Select(s => new { s.Title, s.Artist, s.Year });

// Mapping to a tuple
var songTuples = songs.Select(s => (s.Title, s.Artist));

foreach (var (title, artist) in songTuples)
{
    Console.WriteLine($"{title} by {artist}");
}
```

We can also map it to a model, DTO or ViewModel

```C#
// Create a model
public class SongInfo
{
    public string Title { get; set; }
    public string Artist { get; set; }
}

// Map our results to this model structure
var songInfos = songs.Select(s => new SongInfo
{
    Title = s.Title,
    Artist = s.Artist
});
```

### Partial Results

Partial results simply means retrieving a subset of the data rather than the entire collection or query result.

This is extremely common in:

- Pagination (e.g. showing only 10 songs per page)
- Early termination (e.g. stop when you find what you need)
- Streaming (deferred execution means you can process as you go)

These are the most common ways to fetch partial results.

```C#
// Using the Take() method to get the first two results
var firstTwo = songs.Take(2);

// Using TakeLast() to take the last 2 results
var lastTwo = songs.TakeLast(2);

foreach (var s in firstTwo)
    Console.WriteLine(s.Title);

// Using the skip then take methods
var nextTwo = songs.Skip(2).Take(2);

foreach (var s in nextTwo)
    Console.WriteLine(s.Title);

// Using the TakeWhile() method to get results which meet the condition
// There is also a SkipWhile() which does the opposite
var popularThreshold = songs.TakeWhile(s => s.Plays < 10_000_000);

foreach (var s in popularThreshold)
    Console.WriteLine(s.Title);
```

We can also chunk data which will fetch back our results as an array.

```C#
var sourceMovies = Repository.GetAllMovies();

var query = 
    from movie in sourceMovies
    where movie.Producers.Count > 1
    select movie;

var chunks = query.Chunk(5);

foreach (var chunk in chunks) {
    Console.WriteLine("Chunk:");

    foreach (var movie in chunk) {
        Console.WriteLine(movie);
    }
}
```

Grouping in LINQ is used to organize elements that share a common key (like an artist, category, or year).

```C#
// Grouping with the query syntax
var groupedByArtist =
    from s in songs
    group s by s.Artist into artistGroup
    select artistGroup;

// Grouping with fluent syntax
var groupedByYear = songs.GroupBy(s => s.Year);

foreach (var yearGroup in groupedByYear)
{
    Console.WriteLine($"Year: {yearGroup.Key}");
    foreach (var s in yearGroup)
        Console.WriteLine($"  {s.Title} by {s.Artist}");
}
```

### Deduplicating Data

We can use Linq to deduplicate data from our data collections easily rather than looping through it all and doing it manually ourselves.

Lets start with a simple example using an array of numbers.

```C#
int[] sourceItems = [1, 3, 5, 3, 7, 7, 1, 6, 20, 25, 25, 30];

// To see every unique item in this collection
var result = sourceItems.Distinct();
```

Another example using a List:

```C#
var songs = new List<Song>
{
    new Song { Title = "Yellow", Artist = "Coldplay" },
    new Song { Title = "Clocks", Artist = "Coldplay" },
    new Song { Title = "Levitating", Artist = "Dua Lipa" },
    new Song { Title = "Don't Stop Me Now", Artist = "Queen" }
};

// Deduplicate by Artist
var uniqueArtists = songs.DistinctBy(s => s.Artist);

foreach (var s in uniqueArtists)
    Console.WriteLine($"{s.Artist} - {s.Title}");

// We can also deduplicate by multiple keys
var uniqueArtistTitles = songs
    .DistinctBy(s => new { s.Artist, s.Title });
```

### Aggregate Functions

Aggregate functions are a core part of LINQ, used to perform summary operations over a collection, like counting, summing, averaging, finding minimums or maximums, and combining values.

```C#
// Example of counting results
int totalSongs = songs.Count();
int coldplaySongs = songs.Count(s => s.Artist == "Coldplay");

// Getting the total number of a certain column
int totalPlays = songs.Sum(s => s.Plays);

// Getting the average
double avgPlays = songs.Average(s => s.Plays);

// Min & Max (return a scalar value with the min or max value)
int maxPlays = songs.Max(s => s.Plays);
int minPlays = songs.Min(s => s.Plays);

// Min & Max (return the entire object related to the mix of max value)
int maxPlaySong = songs.MaxBy(s => s.Plays);
int minPlaySong = songs.MinBy(s => s.Plays);

// Aggregate() is a custom reduction function. It lets you combine elements manually.
string titles = songs
    .Select(s => s.Title)
    .Aggregate((a, b) => a + ", " + b);

// Group & Aggregate
var avgByArtist = songs
    .GroupBy(s => s.Artist)
    .Select(g => new
    {
        Artist = g.Key,
        AveragePlays = g.Average(s => s.Plays)
    });
```

### Set Operations

Set operations in LINQ are one of the most useful features when comparing or combining collections.

These operations are modeled after mathematical set theory and are designed to work with distinct elements (duplicates are automatically removed unless otherwise stated).

Set operations in LINQ let you:

- Combine sequences
- Find differences between them
- Identify common or unique elements

`Distinct()` - Removes duplicates
`Union()` - Combines two sequences, removing duplicates
`Intersect()` - Returns common elements from both sequences
`Except()` - Returns elements in one sequence but not the other
`Concat()` - Combines two sequences without removing duplicates

```C#
// Model to work with
var rockArtists = new List<string> { "Queen", "Coldplay", "Muse", "Foo Fighters" };
var popArtists = new List<string> { "Coldplay", "Dua Lipa", "Ed Sheeran", "Adele" };

// Union example
var allArtists = rockArtists.Union(popArtists);

Console.WriteLine("All Artists (Union):");
foreach (var artist in allArtists)
    Console.WriteLine(artist);

// Intersect example
var crossoverArtists = rockArtists.Intersect(popArtists);

Console.WriteLine("Crossover Artists (Intersect):");
foreach (var artist in crossoverArtists)
    Console.WriteLine(artist);

// Except
var onlyRock = rockArtists.Except(popArtists);

Console.WriteLine("Rock Artists Only (Except):");
foreach (var artist in onlyRock)
    Console.WriteLine(artist);

// Concat
var allArtistsWithDuplicates = rockArtists.Concat(popArtists);

Console.WriteLine("All Artists (Concat):");
foreach (var artist in allArtistsWithDuplicates)
    Console.WriteLine(artist);


```

### Select Many

`Select()` projects each element of a collection into one new value.

`SelectMany()` projects each element into a collection, and then flattens those collections into a single sequence.

```C#
// Model
public class Artist
{
    public string Name { get; set; }
    public List<string> Songs { get; set; }
}

var artists = new List<Artist>
{
    new Artist { Name = "Coldplay", Songs = new List<string> { "Yellow", "Clocks" } },
    new Artist { Name = "Dua Lipa", Songs = new List<string> { "Levitating", "Physical" } },
    new Artist { Name = "Queen", Songs = new List<string> { "Bohemian Rhapsody", "Don't Stop Me Now" } }
};

// Using a normal select then iterating through the data
var songLists = artists.Select(a => a.Songs);

foreach (var list in songLists)
{
    Console.WriteLine(string.Join(", ", list));
}

// Using SelectMany()
var allSongs = artists.SelectMany(a => a.Songs);

foreach (var song in allSongs)
{
    Console.WriteLine(song);
}

// SelectMany() with projection
var artistSongs = artists.SelectMany(
    artist => artist.Songs,
    (artist, song) => new { Artist = artist.Name, Song = song }
);

foreach (var item in artistSongs)
    Console.WriteLine($"{item.Artist} - {item.Song}");

// Using query syntax
var artistSongs =
    from artist in artists
    from song in artist.Songs
    select new { artist.Name, Song = song };

foreach (var item in artistSongs)
    Console.WriteLine($"{item.Name} - {item.Song}");
```

### Joins

A join combines data from two (or more) collections based on matching keys, just like in SQL.

Lets use this data set for our examples

```C#
public class Artist
{
    public int Id { get; set; }
    public string Name { get; set; }
}

public class Song
{
    public string Title { get; set; }
    public int ArtistId { get; set; }
}

var artists = new List<Artist>
{
    new Artist { Id = 1, Name = "Coldplay" },
    new Artist { Id = 2, Name = "Dua Lipa" },
    new Artist { Id = 3, Name = "Queen" }
};

var songs = new List<Song>
{
    new Song { Title = "Yellow", ArtistId = 1 },
    new Song { Title = "Clocks", ArtistId = 1 },
    new Song { Title = "Levitating", ArtistId = 2 },
    new Song { Title = "Bohemian Rhapsody", ArtistId = 3 }
};
```

Inner Joins

```C#
// Query syntax
var query =
    from artist in artists
    join song in songs
    on artist.Id equals song.ArtistId
    select new
    {
        Artist = artist.Name,
        Song = song.Title
    };

foreach (var item in query)
    Console.WriteLine($"{item.Artist} - {item.Song}");

// Fluent syntax
var result = artists.Join(
    songs,                   // Inner collection
    artist => artist.Id,     // Outer key selector
    song => song.ArtistId,   // Inner key selector
    (artist, song) => new    // Result selector
    {
        Artist = artist.Name,
        Song = song.Title
    });

foreach (var item in result)
    Console.WriteLine($"{item.Artist} - {item.Song}");
```

Group Join (Left Join Pattern)

```C#
// Query syntax
var groupJoin =
    from artist in artists
    join song in songs
    on artist.Id equals song.ArtistId into songGroup
    select new
    {
        Artist = artist.Name,
        Songs = songGroup
    };

foreach (var item in groupJoin)
{
    Console.WriteLine(item.Artist);
    foreach (var song in item.Songs)
        Console.WriteLine($"  - {song.Title}");
}

// Fluent syntax
var leftJoin = artists
    .GroupJoin(
        songs,                     // Inner collection
        artist => artist.Id,        // Outer key selector
        song => song.ArtistId,      // Inner key selector
        (artist, songGroup) => new  // Result selector
        {
            Artist = artist,
            Songs = songGroup
        })
    .SelectMany(
        x => x.Songs.DefaultIfEmpty(),   // Ensures left join behavior
        (x, song) => new
        {
            Artist = x.Artist.Name,
            Song = song?.Title ?? "(No Songs)"
        });

foreach (var item in leftJoin)
    Console.WriteLine($"{item.Artist} - {item.Song}");
```

Left Outer Join (Include Artists with No Songs)

```C#
// Query syntax
var leftJoin =
    from artist in artists
    join song in songs
    on artist.Id equals song.ArtistId into songGroup
    from subSong in songGroup.DefaultIfEmpty()
    select new
    {
        Artist = artist.Name,
        Song = subSong?.Title ?? "(No Songs)"
    };

foreach (var item in leftJoin)
    Console.WriteLine($"{item.Artist} - {item.Song}");

// Fluent syntax example (doesn't have the function)
var leftJoin = artists
    .GroupJoin(
        songs,                     // Inner collection
        artist => artist.Id,        // Outer key selector
        song => song.ArtistId,      // Inner key selector
        (artist, songGroup) => new  // Result selector
        {
            Artist = artist,
            Songs = songGroup
        })
    .SelectMany(
        x => x.Songs.DefaultIfEmpty(),   // Ensures left join
        (x, song) => new
        {
            Artist = x.Artist.Name,
            Song = song?.Title ?? "(No Songs)"
        });

foreach (var item in leftJoin)
    Console.WriteLine($"{item.Artist} - {item.Song}");
```

### Creating Our Own IEnumerable Methods

Let's create our own methods to use with LINQ with IEnumberables.

Lets start with this class. The `MyWhere` & `MyFirstOrDefault` methods don't yet exist so we will write our own.

```C#
public class EnumerableExample : QueryRunner
{
    public override void Run()
    {
        HomeLinqMethods();
    }

    void HomeLinqMethods()
    {
        var allMovies = Repository.GetAllMovies();

        var result = allMovies
            .MyWhere(movie => movie.Phase == 4)
            .MyFirstOrDefault();
    }
}
```

Linq Methods are basically extension methods, so we can implement them like this.

```C#
public static class MyLinqMethods
{
    public static IEnumerable<T> MyWhere<T>(this IEnumerable<T> source, Predicate<T> condition)
    {
        foreach (var sourceItem in source) {
            if (condition(sourceItem)) {
                yield return sourceItem;
            }
        }
    }

    public static T? MyFirstOrDefault(this IEnumerable<T> source)
    {
        foreach (var sourceItem in source) {
            return sourceItem;
        }

        return default;
    }
}
```

### PLINQ

PLINQ stands for Parallel LINQ. It's an extension of LINQ that runs queries in parallel, taking advantage of multiple CPU cores to speed up operations on large datasets.

PLINQ is part of the `System.Linq` and `System.Linq.Parallel` namespaces and is built on top of the Task Parallel Library (TPL).

When working with large collections, regular LINQ runs sequentially iterating one element at a time.

PLINQ splits the data source into multiple partitions, processes each one in parallel threads, and then merges the results.

Good use cases:

- CPU-bound operations
- Expensive calculations or transformations
- Large data sets that can be processed independently

Not good for:

- Small collections (parallel overhead may slow it down)
- Queries with lots of shared state or side effects (thread safety issues)
- Database queries (EF Core's LINQ is translated to SQL. PLINQ works only on in-memory data)

```C#
using System;
using System.Linq;

class Program
{
    static void Main()
    {
        var numbers = Enumerable.Range(1, 20);

        var squares = numbers
            .AsParallel()
            .Select(n =>
            {
                Console.WriteLine($"Processing {n} on thread {Environment.CurrentManagedThreadId}");
                return n * n;
            })
            .ToList();

        foreach (var s in squares)
            Console.WriteLine(s);
    }
}
```

You may notice the results do appear out of order because of how fast some are processed compared to others. This can be things like Intel's Big/Little design architecture with P-Cores and E-Cores etc.

To keep the order, we can sacrifice a little bit of time and use `AsOrdered()`

```C#
var orderedSquares = numbers
    .AsParallel()
    .AsOrdered()
    .Select(n => n * n)
    .ToList();
```

To limit how much processing cores we want to use, we can use `WithDegreeOfParallelism`

```C#
var result = numbers
    .AsParallel()
    .WithDegreeOfParallelism(2)
    .Select(n => n * n)
    .ToList();
```

PLINQ wraps exceptions inside an AggregateException, because multiple threads may fail simultaneously.

```C#
try
{
    var result = numbers.AsParallel().Select(n =>
    {
        if (n == 10) throw new Exception("Bad number!");
        return n;
    }).ToList();
}
catch (AggregateException ex)
{
    foreach (var e in ex.InnerExceptions) {
        Console.WriteLine(e.Message);
    }
}
```

If we want to keep the parallelism going instead of looping through each item at the end, we can use the `ForAll()` method which will execute an action on each element as soon as it's produced.

```C#
var result = numbers
    .AsParallel()
    .Select(number => number * number)
    .ForAll(number => Console.WriteLine(number));
```

When you run a PLINQ query, results from different threads need to be merged back into a single sequence. The merge options control when and how those results are made available to your program.

```C#
using System;
using System.Linq;
using System.Threading;
using System.Threading.Tasks;

class Program
{
    static void Main()
    {
        var songs = Enumerable.Range(1, 10).Select(i => $"Song {i}");

        Console.WriteLine("=== FullyBuffered ===");
        RunWithMergeOption(songs, ParallelMergeOptions.FullyBuffered);

        Console.WriteLine("\n=== AutoBuffered ===");
        RunWithMergeOption(songs, ParallelMergeOptions.AutoBuffered);

        Console.WriteLine("\n=== NotBuffered ===");
        RunWithMergeOption(songs, ParallelMergeOptions.NotBuffered);
    }

    static void RunWithMergeOption(IEnumerable<string> songs, ParallelMergeOptions option)
    {
        var results = songs
            .AsParallel()
            .WithMergeOptions(option)
            .Select(song =>
            {
                // Simulate CPU-heavy work
                Thread.Sleep(500);
                Console.WriteLine($"Processed {song} on thread {Environment.CurrentManagedThreadId}");
                return $"{song} - done";
            });

        foreach (var result in results)
        {
            Console.WriteLine($"Result available: {result}");
        }
    }
}
```

## Reflection

### What Is Reflection

Reflection in C# is the ability for a program to inspect and interact with its own metadata at runtime.

That means your program can:

- Discover types (classes, structs, interfaces, etc.)
- Examine methods, properties, fields, attributes, and constructors
- Invoke methods or access members dynamically
- Create instances of types even if you don't know their names until runtime

It's part of the `System.Reflection` namespace.

Reflection is powerful but should be used carefully. It's slower and less safe than regular code.

However, it's essential for dynamic, flexible, or meta-programming scenarios.

An example of reflection

```C#
// Lets create a Playable Attribute
[AttributeUsage(AttributeTargets.Method)]
public class PlayableAttribute : Attribute { }

// Create a class to work with assigning our playable to one of our methods
public class MusicLibrary
{
    [Playable]
    public void PlaySong() => Console.WriteLine("Playing song...");

    public void SkipSong() => Console.WriteLine("Skipping...");
}

// Use reflection to find all methods in our MusicLibrary class with the Playable attribute
var methods = typeof(MusicLibrary)
    .GetMethods()
    .Where(m => m.GetCustomAttribute<PlayableAttribute>() != null);

// Print out what we find, but normally you would use this in better ways
foreach (var m in methods)
    Console.WriteLine($"Playable method: {m.Name}");

```

### Looking Up Types

In C#, looking up types using reflection means finding information about a type like a class, struct, or interface, at runtime, even if you didn't hard-code it.

You can look up types in several ways:

- From a known type: typeof(MyClass)
- From an object instance: obj.GetType()
- From a type name (string): Type.GetType("Namespace.MyClass")
- From an assembly: Assembly.GetExecutingAssembly().GetTypes()

Once you have the Type object, you can inspect:

- Properties (GetProperties())
- Methods (GetMethods())
- Fields (GetFields())
- Constructors (GetConstructors())

```C#
public class Song
{
    public string Title { get; set; }
    public string Artist { get; set; }

    public void Play() => Console.WriteLine($"Playing {Title} by {Artist}");
}

using System;
using System.Reflection;

class Program
{
    static void Main()
    {
        // Get the Type object for the Song class
        // Note: typeof only works at compile time so it will not work 
        // with things like dynamically loading .dll libraries
        Type songType = typeof(Song);

        // Print its name and namespace
        Console.WriteLine($"Type Name: {songType.Name}");
        Console.WriteLine($"Namespace: {songType.Namespace}");

        // List all public properties
        Console.WriteLine("\nProperties:");
        foreach (var prop in songType.GetProperties())
            Console.WriteLine($" - {prop.Name} ({prop.PropertyType.Name})");

        // List all methods declared in this class
        Console.WriteLine("\nMethods:");
        foreach (var method in songType.GetMethods(BindingFlags.Public | BindingFlags.Instance | BindingFlags.DeclaredOnly))
            Console.WriteLine($" - {method.Name}");
    }
}
```

In the example above, we mention `typeof()` only works at compile time. If we need to run something dynamically we can use something like `Type.GetType()`

```C#
// Getting types by name
var typeByName = Type.GetType("MyDynamicClass");

// If we have nested classes inside our class we can access them like this
var nestedType = Type.GetType("MyDynamicClass+MyDynamicSubClass");

// We can also find by namespace
var typeFromNamespace = Type.GetType("ExampleNamespace.MyDynamicClass");

// We can also get types from the current executing assembly
var typeFromAssembly = Assembly.GetExecutingAssembly().GetType("MyDynamicClass");

// We can also get all types from an assembly
var allTypesFromAssembly = Assembly.GetExecutingAssembly().GetTypes();
```

### Filtering Type Information

When you use reflection to get type information, you often get all members including every property, method, field, etc.

Filtering type information means using reflection to find only the members you care about.

For example:

- Only public methods
- Only properties of a certain type
- Only members with a specific attribute
- Only methods that match a naming pattern

This is very common in frameworks like `ASP.NET`, `Entity Framework`, or testing libraries (they use reflection to find things like `[Controller]`, `[Key]`, `[Test]`, etc.).

```C#
using System;
using System.Linq;
using System.Reflection;

[AttributeUsage(AttributeTargets.Method)]
public class CommandAttribute : Attribute { }

public class MusicPlayer
{
    [Command]
    public void Play() { }

    public void Pause() { }

    [Command]
    public void Stop() { }

    private void Reset() { }

    public string Version => "1.0";
}

class Program
{
    static void Main()
    {
        Type type = typeof(MusicPlayer);

        // Get all instance methods declared on this type
        var publicMethods = type.GetMethods(BindingFlags.Public | BindingFlags.Instance | BindingFlags.DeclaredOnly);

        Console.WriteLine("Public Methods:");
        foreach (var method in publicMethods) {
            Console.WriteLine($" - {method.Name}");
        }

        // Get all methods which return void
        var voidMethods = type
            .GetMethods()
            .Where(m => m.ReturnType == typeof(void));

        // Get all functions with a Command attribute
        var commandMethods = type
            .GetMethods(BindingFlags.Public | BindingFlags.Instance)
            .Where(m => m.GetCustomAttribute<CommandAttribute>() != null);
    }
}
```

### Assembly Scanning

Assembly scanning is using reflection to look through all the types (classes, interfaces, etc.) in one or more assemblies, usually to automatically find types that meet some criteria.

Example:

```C#
// Let's say we have these classes
public interface IAudioEffect
{
    void Process();
}

public class Reverb : IAudioEffect
{
    public void Process() => Console.WriteLine("Applying reverb...");
}

public class Echo : IAudioEffect
{
    public void Process() => Console.WriteLine("Applying echo...");
}

public class Compressor
{
    public void Process() => Console.WriteLine("Compressing...");
}

// We can use assembly scanning to find all classes that implement the IAudioEffect within this assembly
using System;
using System.Linq;
using System.Reflection;

class Program
{
    static void Main()
    {
        // Get the currently running assembly
        Assembly assembly = Assembly.GetExecutingAssembly();

        // Find all types that implement IAudioEffect
        var effectTypes = assembly
            .GetTypes()
            .Where(t => typeof(IAudioEffect).IsAssignableFrom(t)
                        && t.IsClass                               
                        && !t.IsAbstract);                          

        Console.WriteLine("Discovered Effects:");
        foreach (var type in effectTypes)
        {
            Console.WriteLine($" - {type.Name}");

            // Create an instance dynamically
            var effect = (IAudioEffect)Activator.CreateInstance(type)!;
            effect.Process();
        }
    }
}

// Searching dynamically through a dll file
Assembly pluginAssembly = Assembly.LoadFrom("Plugins/AudioEffects.dll");

var pluginTypes = pluginAssembly
    .GetTypes()
    .Where(t => typeof(IAudioEffect).IsAssignableFrom(t));

// Loading from a directory of assemblies
static IReadOnlyList<Assembly> LoadAssembliesFromDirectory(string directoryPath)
{
    var assemblies = new List<Assembly>();
    
    foreach (var file in Directory.EnumerateFiles(directoryPath, '*.dll')) {
        var assembly Assembly.LoadFrom(file);
        assemblies.Add(assembly);
    }

    return assemblies;
}
```

### Binding Flags

BindingFlags are an enum in System.Reflection that control which members are returned or accessed when using reflection.

By default, many reflection methods only return public instance members.
BindingFlags allow you to fine-tune what you want to retrieve: public vs. non-public, static vs. instance, inherited vs. declared-only, etc.

Flags can be combined using the bitwise OR operator (|).

```C#
type.GetMethods(BindingFlags.Public | BindingFlags.Instance | BindingFlags.DeclaredOnly);
```

Example

```C#
// Example class
public class ExampleClass
{
    public string Name;
    private int secret;

    public static void Info() { }
    public void Play() { }
    private void Reset() { }
}

Type type = typeof(ExampleClass);

// Get all public instance members (fields, methods, properties)
var publicInstanceMethods = type.GetMethods(BindingFlags.Public | BindingFlags.Instance);

// Get all private members
var privateMembers = type.GetMembers(BindingFlags.NonPublic | BindingFlags.Instance | BindingFlags.Static);

// Get all declared members (exclude inherited)
var declaredMembers = type.GetMembers(BindingFlags.Public | BindingFlags.NonPublic | BindingFlags.Instance | BindingFlags.DeclaredOnly);

// Get static members
var staticMembers = type.GetMembers(BindingFlags.Static | BindingFlags.Public | BindingFlags.NonPublic);
```

### Fetching Values

`GetValue()` retrieves the current value of a field or property at runtime. For instance members, you pass the object instance and for static members, you pass `null`.

```C#
using System;
using System.Reflection;

public class ExampleClass
{
    // Instance field
    public string Name = "DefaultName";

    // Static field
    public static int Counter = 42;

    // Instance property
    public int Age { get; set; } = 25;

    // Static property
    public static string Version { get; set; } = "1.0";
}

// Accessing instances
class Program
{
    static void Main()
    {
        var example = new ExampleClass();

        Type type = typeof(ExampleClass);

        // Instance Field
        FieldInfo nameField = type.GetField("Name");
        Console.WriteLine("Instance Field Name: " + nameField.GetValue(example));

        // Instance Property
        PropertyInfo ageProp = type.GetProperty("Age");
        Console.WriteLine("Instance Property Age: " + ageProp.GetValue(example));

        // Accessing static members
        // Static Field
        FieldInfo counterField = type.GetField("Counter", BindingFlags.Static | BindingFlags.Public);
        Console.WriteLine("Static Field Counter: " + counterField.GetValue(null));

        // Static Property
        PropertyInfo versionProp = type.GetProperty("Version", BindingFlags.Static | BindingFlags.Public);
        Console.WriteLine("Static Property Version: " + versionProp.GetValue(null));
    }
}
```

### Calling Methods

We can find methods in our types and `Invoke` them using reflection.

```C#
using System;
using System.Reflection;

public class MusicPlayer
{
    public string Name { get; set; }

    public MusicPlayer(string name)
    {
        Name = name;
    }

    public void Play(string song)
    {
        Console.WriteLine($"{Name} is playing {song}");
    }

    public static void Info()
    {
        Console.WriteLine("MusicPlayer v1.0");
    }
}

class Program
{
    static void Main()
    {
        Type type = typeof(MusicPlayer);

        // Call an instance of a method dynamically
        object player = Activator.CreateInstance(type, "MyPlayer")!;
        MethodInfo playMethod = type.GetMethod("Play")!;

        // The second argument when calling Invoke() is the method parameters.
        // Pass null for no arguments and an object array listing each argument.
        playMethod.Invoke(player, ["Bohemian Rhapsody"]);

        // Call a static method dynamically
        MethodInfo infoMethod = type.GetMethod("Info", BindingFlags.Public | BindingFlags.Static)!;

        infoMethod.Invoke(null, null);
    }
}
```

### Activator Class

The Activator class (in the System namespace) provides methods to create objects at runtime when you don’t know the type at compile time.

It’s part of reflection because it works with Type objects.

There is two common ways to create instances:

- `Activator.CreateInstance(Type type)` - Creates an instance using a Type object (useful when type known only at runtime)
- Activator.CreateInstance<T>() - Generic version – creates a new instance of type T (known at compile time)


```C#
using System;

public class MusicPlayer
{
    public string Name { get; set; }

    public MusicPlayer()
    {
        Name = "Default Player";
    }

    public MusicPlayer(string name)
    {
        Name = name;
    }

    public void Play()
    {
        Console.WriteLine($"{Name} is playing music...");
    }
}

class Program
{
    static void Main()
    {
        // Create a new instance using the generic form
        var player = Activator.CreateInstance<MusicPlayer>();

        Console.WriteLine(player.Name);
        player.Play();

        // -------------------------------------------------------

        // Get the type dynamically
        Type type = typeof(MusicPlayer);

        // Create instance using the non-generic Activator method
        object instance = Activator.CreateInstance(type)!;

        // Cast to correct type if you need to access members
        MusicPlayer player = (MusicPlayer)instance;
        player.Play();
    }
}

```

### Source Generators

A Source Generator is a special kind of compiler extension that runs at compile time.
It can analyze your code and generate new C# code that’s added to your project automatically before compilation finishes.

They’re used for:

- Eliminating boilerplate (e.g. auto-generating DTO mappers, serializers, DI registrations)
- Improving runtime performance by moving work to compile-time
- Enabling “meta-programming” safely (without reflection at runtime)

Examples in the wild:

- System.Text.Json uses generators for fast serialization.
- Entity Framework Core uses them for optimized query models.
- MediatR, AutoMapper, and Dapper can be extended with them.

Very basic example

```bash
dotnet new classlib -n HelloSourceGenerator
```

Add a reference to the Roslyn SDK:

```bash
dotnet add package Microsoft.CodeAnalysis.CSharp
dotnet add package Microsoft.CodeAnalysis.Analyzers
```

Create the source generation class

```C#
using Microsoft.CodeAnalysis;
using Microsoft.CodeAnalysis.Text;
using System.Text;

namespace HelloSourceGenerator
{
    [Generator]
    public class HelloGenerator : ISourceGenerator
    {
        public void Initialize(GeneratorInitializationContext context)
        {
            // Optional: hook into compilation events or register syntax receivers
        }

        public void Execute(GeneratorExecutionContext context)
        {
            // Generate simple code
            string source = @"
namespace Generated
{
    public static class HelloWorld
    {
        public static void SayHello()
        {
            System.Console.WriteLine(""Hello from Source Generator!"");
        }
    }
}";

            // Add generated code to the compilation
            context.AddSource("HelloWorld.g.cs", SourceText.From(source, Encoding.UTF8));
        }
    }
}
```


Create a console app and reference the generator project as an analyzer:

```bash
dotnet new console -n GeneratorDemo
dotnet add GeneratorDemo.csproj reference ../HelloSourceGenerator/HelloSourceGenerator.csproj
```

Then edit your `.csproj` file so the reference is treated as an analyzer:

```xml
<ItemGroup>
  <ProjectReference Include="..\HelloSourceGenerator\HelloSourceGenerator.csproj"
                    OutputItemType="Analyzer"
                    ReferenceOutputAssembly="false" />
</ItemGroup>
```

In `Program.cs`:

```C#
using Generated;

HelloWorld.SayHello();
```

You can make much more advanced generators:

- Use a ISyntaxReceiver to detect specific syntax patterns (e.g. [GenerateSomething] attributes)
- Inspect existing code using the Roslyn Semantic Model
- Generate files conditionally or from external data sources (like JSON or templates)

```C#
context.SyntaxReceiver = new MySyntaxReceiver();
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

## Async & Await

### Intro To Async Await

`async` and `await` are keywords introduced in C# version 5 to simplify asynchronous programming. They let you write asynchronous code that looks like normal sequential code, instead of dealing with callbacks or complex threading. The compiler transforms it behind the scenes into a state machine that runs tasks without blocking the calling thread.

An example using Async / Await

```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main()
    {
        Console.WriteLine("Fetching data...");

        string data = await GetDataAsync();

        Console.WriteLine("Data length: " + data.Length);
    }

    static async Task<string> GetDataAsync()
    {
        using var httpClient = new HttpClient();
        return await httpClient.GetStringAsync("https://example.com");
    }
}
```

The await keyword makes sure the method pauses until the Task finishes, without blocking the main thread.

### What We Used Before

Before `async`/`await`, we often used:
- Threads (Thread class)
- ThreadPool (ThreadPool.QueueUserWorkItem)
- Tasks (Task.Run)
- Parallel.For / Parallel.ForEach (for CPU-bound work)

These worked well but could get messy with callbacks or manual synchronization.

Here's a simple parallel loop example:

```C#
using System;
using System.Threading.Tasks;

class Program
{
    static void Main()
    {
        Console.WriteLine("Starting parallel work...");

        Parallel.For(0, 5, i =>
        {
            Console.WriteLine($"Task {i} running on thread {Task.CurrentId}");
            Task.Delay(1000).Wait();
        });

        Console.WriteLine("All parallel work finished.");
    }
}
```

Parallel.For runs tasks concurrently, good for CPU-bound work. But it blocks threads (see Wait()), unlike async/await which frees them until the result is ready.

Use async/await for I/O-bound tasks (web requests, database calls, file access).

Use Parallel / Task.Run for CPU-bound tasks (math, processing, image manipulation).

This is another example using nested callbacks which can get very messy.

```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static void Main()
    {
        Console.WriteLine("Fetching data...");

        var httpClient = new HttpClient();

        Task<string> task = httpClient.GetStringAsync("https://example.com");

        task.ContinueWith(t =>
        {
            if (t.Exception == null)
            {
                Console.WriteLine("Data length: " + t.Result.Length);
            }
            else
            {
                Console.WriteLine("Error: " + t.Exception.Message);
            }
        });

        Console.WriteLine("Main method continues while request runs...");

        Console.ReadLine();
    }
}
```

### Parallel Programming

`Task.WhenAll()` is handy when you want to run multiple asynchronous operations in parallel and wait for all of them to finish. If any task throws, the exception is aggregated into a single `AggregateException`. Something to keep in mind that if one object is dependent on another which is also being called in `WhenAll()` then we could run into `deadlocks`.

```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main()
    {
        var httpClient = new HttpClient();

        Task<string> task1 = httpClient.GetStringAsync("https://example.com");
        Task<string> task2 = httpClient.GetStringAsync("https://www.bing.com");
        Task<string> task3 = httpClient.GetStringAsync("https://www.google.com");

        string[] results = await Task.WhenAll(task1, task2, task3);

        Console.WriteLine($"Example.com length: {results[0].Length}");
        Console.WriteLine($"Bing.com length: {results[1].Length}");
        Console.WriteLine($"Google.com length: {results[2].Length}");
    }
}
```

### Compiled Code Example

This is a quick example showing how our async code is output when we compile it. A great tool for looking into this is https://sharplab.io/ 

Lets take our example from the intro and see what it outputs

```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main()
    {
        Console.WriteLine("Fetching data...");

        string data = await GetDataAsync();

        Console.WriteLine("Data length: " + data.Length);
    }

    static async Task<string> GetDataAsync()
    {
        using var httpClient = new HttpClient();
        return await httpClient.GetStringAsync("https://example.com");
    }
}
```

We then compile this which turns it into the Common Intermediate Language which is then taken a step further into assembly with the JIT compiler. Use the link to Sharp Lab to look further into what this outputs if you're interested.

When we decompile that output back into C#, we get something like this.

```C#
using System;
using System.Diagnostics;
using System.Net.Http;
using System.Reflection;
using System.Runtime.CompilerServices;
using System.Runtime.InteropServices;
using System.Security;
using System.Security.Permissions;
using System.Threading.Tasks;

[assembly: CompilationRelaxations(8)]
[assembly: RuntimeCompatibility(WrapNonExceptionThrows = true)]
[assembly: Debuggable(DebuggableAttribute.DebuggingModes.IgnoreSymbolStoreSequencePoints)]
[assembly: SecurityPermission(SecurityAction.RequestMinimum, SkipVerification = true)]
[assembly: AssemblyVersion("0.0.0.0")]
[module: UnverifiableCode]
[module: RefSafetyRules(11)]

[NullableContext(1)]
[Nullable(0)]
internal class Program
{
    [StructLayout(LayoutKind.Auto)]
    [CompilerGenerated]
    private struct <GetDataAsync>d__1 : IAsyncStateMachine
    {
        public int <>1__state;

        [Nullable(0)]
        public AsyncTaskMethodBuilder<string> <>t__builder;

        [Nullable(0)]
        private HttpClient <httpClient>5__2;

        [Nullable(new byte[] { 0, 1 })]
        private TaskAwaiter<string> <>u__1;

        private void MoveNext()
        {
            int num = <>1__state;
            string result;
            try
            {
                if (num != 0)
                {
                    <httpClient>5__2 = new HttpClient();
                }
                try
                {
                    TaskAwaiter<string> awaiter;
                    if (num != 0)
                    {
                        awaiter = <httpClient>5__2.GetStringAsync("https://example.com").GetAwaiter();
                        if (!awaiter.IsCompleted)
                        {
                            num = (<>1__state = 0);
                            <>u__1 = awaiter;
                            <>t__builder.AwaitUnsafeOnCompleted(ref awaiter, ref this);
                            return;
                        }
                    }
                    else
                    {
                        awaiter = <>u__1;
                        <>u__1 = default(TaskAwaiter<string>);
                        num = (<>1__state = -1);
                    }
                    result = awaiter.GetResult();
                }
                finally
                {
                    if (num < 0 && <httpClient>5__2 != null)
                    {
                        ((IDisposable)<httpClient>5__2).Dispose();
                    }
                }
            }
            catch (Exception exception)
            {
                <>1__state = -2;
                <httpClient>5__2 = null;
                <>t__builder.SetException(exception);
                return;
            }
            <>1__state = -2;
            <httpClient>5__2 = null;
            <>t__builder.SetResult(result);
        }

        void IAsyncStateMachine.MoveNext()
        {
            //ILSpy generated this explicit interface implementation from .override directive in MoveNext
            this.MoveNext();
        }

        [DebuggerHidden]
        private void SetStateMachine(IAsyncStateMachine stateMachine)
        {
            <>t__builder.SetStateMachine(stateMachine);
        }

        void IAsyncStateMachine.SetStateMachine(IAsyncStateMachine stateMachine)
        {
            //ILSpy generated this explicit interface implementation from .override directive in SetStateMachine
            this.SetStateMachine(stateMachine);
        }
    }


    [StructLayout(LayoutKind.Auto)]
    [CompilerGenerated]
    private struct <Main>d__0 : IAsyncStateMachine
    {
        public int <>1__state;

        public AsyncTaskMethodBuilder <>t__builder;

        [Nullable(new byte[] { 0, 1 })]
        private TaskAwaiter<string> <>u__1;

        private void MoveNext()
        {
            int num = <>1__state;
            try
            {
                TaskAwaiter<string> awaiter;
                if (num != 0)
                {
                    Console.WriteLine("Fetching data...");
                    awaiter = GetDataAsync().GetAwaiter();
                    if (!awaiter.IsCompleted)
                    {
                        num = (<>1__state = 0);
                        <>u__1 = awaiter;
                        <>t__builder.AwaitUnsafeOnCompleted(ref awaiter, ref this);
                        return;
                    }
                }
                else
                {
                    awaiter = <>u__1;
                    <>u__1 = default(TaskAwaiter<string>);
                    num = (<>1__state = -1);
                }
                string result = awaiter.GetResult();
                Console.WriteLine(string.Concat("Data length: ", result.Length.ToString()));
            }
            catch (Exception exception)
            {
                <>1__state = -2;
                <>t__builder.SetException(exception);
                return;
            }
            <>1__state = -2;
            <>t__builder.SetResult();
        }

        void IAsyncStateMachine.MoveNext()
        {
            //ILSpy generated this explicit interface implementation from .override directive in MoveNext
            this.MoveNext();
        }

        [DebuggerHidden]
        private void SetStateMachine(IAsyncStateMachine stateMachine)
        {
            <>t__builder.SetStateMachine(stateMachine);
        }

        void IAsyncStateMachine.SetStateMachine(IAsyncStateMachine stateMachine)
        {
            //ILSpy generated this explicit interface implementation from .override directive in SetStateMachine
            this.SetStateMachine(stateMachine);
        }
    }

    [AsyncStateMachine(typeof(<Main>d__0))]
    private static Task Main()
    {
        <Main>d__0 stateMachine = default(<Main>d__0);
        stateMachine.<>t__builder = AsyncTaskMethodBuilder.Create();
        stateMachine.<>1__state = -1;
        stateMachine.<>t__builder.Start(ref stateMachine);
        return stateMachine.<>t__builder.Task;
    }

    [AsyncStateMachine(typeof(<GetDataAsync>d__1))]
    private static Task<string> GetDataAsync()
    {
        <GetDataAsync>d__1 stateMachine = default(<GetDataAsync>d__1);
        stateMachine.<>t__builder = AsyncTaskMethodBuilder<string>.Create();
        stateMachine.<>1__state = -1;
        stateMachine.<>t__builder.Start(ref stateMachine);
        return stateMachine.<>t__builder.Task;
    }
}
```

The main part to look into here is the `GetDataAsync()` method which is now using a state machine. 

All our variables have been turned into props in the struct. The variables start with <> as it is illegal in C# code we write, but the compiler does this to further make sure it doesn't generate any naming conflicts.

Next the `MoveNext()` function may look familiar if you have pushed release code but had error logs with async code which references this method. This is generated from the compiler.

Inside the `MoveNext()` function, we see a try/catch block with an if/else statement inside containing the code in our initial method. In some scenarios, this can also be a switch statement with a `default` case with our code inside which is hit by the `stateMachine.<>1__state = -1;` set in our `GetDataAsync()` method.

`awaiter.IsCompleted` is a check to see if we have already completed the task then we don't need to switch threads and saves on heavy CPU cycles. In more complex samples with the switch statement, it will usually be followed by a `goto` keyword which jumps to a block of code getting our result like `string result = awaiter.GetResult();`.

If you are working on embedded devices, each time you use the Async keyword it adds `80 bytes` as every async method becomes a struct.

### Creating Our Own Instance

Just so we can get a better understanding of how Async/Await works, we will make our own version. There is no need to run something like this in a real app and is just for educational purposes. For instance, the real implementation doesn't use `locks` to avoid performance hits etc.

Lets start with making our own `Task` class.

```C#
using System.Runtime.CompilerServices;
using System.Runtime.ExceptionServices;

public class CustomTask
{
    private readonly Lock _lock = new();

    private bool _completed;

    private Exception? _exception;

    private Action? _action;

    private ExecutionContext? _context;

    public static CustomTask Run(Action action)
    {
        CustomTask task = new();

        ThreadPool.QueueUserWorkItem(_ => {
            try 
            {
                action();

                task.SetResult();
            } 
            catch(Exception e) 
            {
                task.SetException(e);
            }
        });

        return task;
    }

    public static CustomTask Delay(TimeSpan delay)
    {
        CustomTask task = new();

        new Timer(_ => task.SetResult())
            .Change(delay, Timeout.InfiniteTimeSpan);

        return task;
    }

    public CustomTask ContinueWith(Action action)
    {
        CustomTask task = new();

        lock (_lock)
        {
            if (_completed) {
                ThreadPool.QueueUserWorkItem(_ => {
                    try 
                    {
                        action();

                        task.SetResult();
                    } 
                    catch(Exception e) 
                    {
                        task.SetException(e);
                    }
                });
            }
            else 
            {
                _action = action;

                _context = ExecutionContext.Capture();
            }
        }

        return task;
    }

    // This method does block the main thread when called. Mainly here just to show 
    // as an example
    public void Wait()
    {
        ManualResetEventSlim? resetEventSlim = null;

        lock (_lock)
        {
            if (!_completed) {
                resetEventSlim = new();

                ContinueWith(() => resetEventSlim.Set());
            }
        }

        resetEventSlim?.Wait();

        if (_exception != null) {
            ExceptionDispatchInfo.throw(_exception);
        }
    }

    public bool IsCompleted
    {
        get
        {
            lock (_lock)
            {
                return _completed;
            }
        }
    }

    // This is the method which gives us access to use the await keyword with our 
    // implementation. It is called a duck type and the await keyword just looks for
    // a method caled GetAwaiter(). We also do need to implement the INotifyCompletion
    // interface on the type returned from this method. In this instance, a struct under
    // this class
    public CustomTaskAwaiter GetAwaiter() => new(this);

    public void SetResult() => CompleteTask(null);

    public void SetException(Exception exception) => CompleteTask(exception);

    private void CompleteTask(Exception? exception)
    {
        lock(_lock)
        {
            if (_completed) {
                throw new InvalidOperationException("Task already completed");
            }

            _completed = true;

            _exception = exception;

            if (_action != null) {
                if (_context == null) {
                    _action.Invoke();
                } else {
                    ExecutionContext.Run(_context, state => ((Action?)state)?.Invoke(), _action);
                }
            }
        }
    }
}

public readonly struct CustomTaskAwaiter : INotifyCompletion
{
    private readonly CustomTask _task;

    internal CustomTaskAwaiter(CustomTask task) => _task = task;

    public bool IsCompleted => _task.IsCompleted;

    public void OnCompleted(Action continuation) => _task.ContinueWith(continuation);

    public CustomTaskAwaiter GetAwait() => this;

    public void GetResult() => _task.Wait();
}
```

We can now run this like the usual await style instance doing something like this

```C#
await CustomTask.Run(() => Console.WriteLine($"Current thread id: {Environment.CurrentManagedThreadId}"));
```

### Do's and Dont's Of Async & Await

--- 
#### Async Void

Normally, an async method should return either:

`Task` if it has no result.

`Task<T>` if it produces a result.

But you can mark a method as async void. The problem is:
- No way to await it
- Exceptions are uncatchable
- Fire-and-forget behavior
- Can cause race conditions

```C#
// Bad: async void (cannot await, exceptions unhandled)
async void DoWork()
{
    await Task.Delay(1000);
    throw new Exception("Oops!");
}

// Good: async Task
async Task DoWorkAsync()
{
    await Task.Delay(1000);
    throw new Exception("Oops!");
}
```

We can also use the `AsyncAwaitBestPractices` library and call a `SafeFireAndForget()` if we know we want this kind of behaviour of just letting it run in the background, but can still catch exceptions.

--- 
#### Cancellation Tokens

When creating async functions, we should always give the option of passing in a `CancellationToken`.

If you come across an async method without a `CancellationToken` param, we can append the `WaitAsync(token)`.

```C#
// Even though the second argument in the delay method supports a cancellation token
// we are just doing this to show as an example.
Task.Delay(TimeSpan.FromSeconds(2)).WaitAsync(token);
```
---  
#### Wait And Result

The `.Wait()` and `.Result` methods should always be avoided when it comes to async programming as they are thread blocking calls. Just use `await` instead.

--- 
#### Avoid Return Await

If you have any functions which use `return await`, you can remove the await keyword and pass the task back up the stack. There are some exceptions with this.
- When your await is inside a try/catch block
- When you're inside a `using` block of code

--- 
#### Utilize ConfigureAwait(false)

Use `.ConfigureAwait(false)` when using C# apps with a SynchronizationContext (e.g A UI Layer). These can include
- WPF
- Winforms
- Xamarin
- .NET MAUI
- WinUI
- Blazor

This is not useful for `ASP.NET Core` and can be avoided.

### IAsyncEnumerable

`IAsyncEnumerable<T>` is the asynchronous version of `IEnumerable<T>`. Instead of pulling items synchronously (foreach), you can pull them asynchronously using `await foreach`. This is useful when you want to stream results gradually (e.g., database rows, API responses, file lines), without waiting for all data to be ready.

An example streaming lines in a file:

```C#
static async IAsyncEnumerable<string> ReadLinesAsync(string filePath)
{
    using var reader = new StreamReader(filePath);
    while (!reader.EndOfStream)
    {
        string line = await reader.ReadLineAsync();
        yield return line;
    }
}

static async Task Main()
{
    await foreach (var line in ReadLinesAsync("data.txt"))
    {
        Console.WriteLine(line);
    }
}
```

`Task.WhenEach()` is a newer API that works hand-in-hand with `IAsyncEnumerable<Task<T>>`. Where `Task.WhenAll` waits for all tasks to complete before giving you results,
`Task.WhenEach` gives you results as soon as each task finishes, in completion order.

```C#
using System;
using System.Linq;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main()
    {
        var httpClient = new HttpClient();

        var urls = new[]
        {
            "https://example.com",
            "https://www.microsoft.com",
            "https://www.github.com"
        };

        var tasks = urls.Select(url => httpClient.GetStringAsync(url));

        await foreach (var completed in Task.WhenEach(tasks))
        {
            try
            {
                string result = await completed;
                Console.WriteLine($"Downloaded {result.Length} characters");
            }
            catch (Exception ex)
            {
                Console.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

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

### Installing CLI Template

To make the set up a bit easier, we can use a template created by Steve Smith which can be found here: https://github.com/ardalis/CleanArchitecture

We can install the template using this command: 

```bash
dotnet new install Ardalis.CleanArchitecture.Template
```

We can then create a new project using a command like this

```bash
dotnet new clean-arch -o Tips.Website --aspire
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

### Setting Up A Project

This is a guide on how to set up a project using the Dotnet CLI. This can also be done with Visual Studio or Jetbrains Rider through the new project commands and adding the relevant references to each library.

With a bit of tweaking, you can add a project name variable and make this a script to make this easier in the future.

```bash
# Create a folder and change into it
mkdir CleanArchitecture && cd CleanArchitecture

# Create a src folder for all the code to live in
mkdir src

# Create the API/Presentation layer
dotnet new webapi -o ./src/CleanArchitecture.Api

# Create the Application layer
dotnet new classlib -o ./src/CleanArchitecture.Application

# Create the Infrastructure layer
dotnet new classlib -o ./src/CleanArchitecture.Infrastructure

# Create the Domain layer
dotnet new classlib -o ./src/CleanArchitecture.Domain

# Lets add our references for each layer
# First we will add the Api/Presentation layer to the Application layer
dotnet add ./src/CleanArchitecture.Api reference ./src/CleanArchitecture.Application

# We also need to map the Infrastructure layer to the Application layer
dotnet add ./src/CleanArchitecture.Infrastructure reference ./src/CleanArchitecture.Application

# Next we just need to add a reference from the Application layer to the Domain layer
dotnet add ./src/CleanArchitecture.Application reference ./src/CleanArchitecture.Domain

# Last, we will add a reference from Infrastrcture to ther Presentation Layer. 
# The main reason for this is to access the DependencyInjection.cs file we will create later.
dotnet add ./src/CleanArchitecture.Api reference ./src/CleanArchitecture.Infrastructure

# Now we add a solution and add all our projects
dotnet new sln --name "CleanArchitecture"

# For Linux Or Mac OS run this
dotnet sln add ./src/**/**.csproj

# Run this for Windows
dotnet sln add (ls -r ./src/**/**.csproj)

# Check it build successfully
dotnet build
```

To start the project using the dotnet tool, we can run the following

```bash
dotnet run --project src/CleanArchitecture.Api
```

### Presentation Layer

The presentation layer has the following responsibilities

- Handling interactions with the outside world
- Presenting or displaying data
- Translating data (e.g Json to a DTO or the other way around)
- Managing UI and framework related elements
- Manipulating the Application layer

### Application Layer

The Application layers main responsibility is to execute use cases. This can be fetching or manipulating domain objects.

Some examples could be:
    - Creating record
    - Deleting record
    - Updating record
    - List all records

There is two ways this can also be structured. One is using the Services pattern or we can use a library `Mediatr`. Normally everything is split out and following `CQRS` (Command Query Responsibility Segregation). It can be up to the developer to depend how deep they want to go into this.

A small example of using Services (all kept in one file here but split it out into it's own files).

```C#
namespace CleanArchitecture.Application.Services

public interface IRecordService
{
    public Guid CreateRecord(string recordName, Guid userId);
}

public class RecordService : IRecordService
{
    public Guid CreateRecord(string recordName, Guid userId)
    {
        return Guid.NewGuid();
    }
}
```

We can then inject this service into our Controller in the Presentation layer and call the `CreateRecord()` method passing in data.

### Infrastructure Layer

The infrastructure layer deals with any persistent solutions such as database, file storage etc as well as connecting with 3rd party APIs and Services.

Responsibilities include:
- Interacting with persistent solutions
- Interacting with other services (web clients, message brokers etc)
- Interacting with the underlying machine (system clock, files etc)
- Identity concerns (Authentication & Authorization)

### Domain Layer

The Domain Layer is the core of the application in Clean Architecture.
It contains the business rules and logic, expressed through entities, value objects, domain services, and events.

- It is independent of external concerns (databases, UI, frameworks).

- It defines what the system does, not how it is implemented.

- Other layers (Application, Infrastructure, Presentation) depend on the Domain, but the Domain depends on nothing.

Responsibilities include:
- Defining domain models
- Defining domain errors
- Executing business logic
- Enforcing business rules

An example of a Rich Domain Model:

```C#
namespace CleanArchitecture.Domain.Records;

public class Record
{
    public Guid Id { get; private set; }
    public string Title { get; private set; }
    public string Email { get; private set; }
    public DateTime CreatedAt { get; private set; }

    private Record() { } // Required for EF Core or serialization

    public Record(string title, string email)
    {
        Id = Guid.NewGuid();
        CreatedAt = DateTime.UtcNow;

        SetTitle(title);
        SetEmail(email);
    }

    public void SetTitle(string title)
    {
        if (string.IsNullOrWhiteSpace(title))
            throw new ArgumentException("Title cannot be empty.", nameof(title));

        Title = title.Trim();
    }

    public void SetEmail(string email)
    {
        if (string.IsNullOrWhiteSpace(email))
            throw new ArgumentException("Email cannot be empty.", nameof(email));

        if (!IsValidEmail(email))
            throw new ArgumentException("Email format is invalid.", nameof(email));

        Email = email.Trim();
    }

    private bool IsValidEmail(string email)
    {
        try
        {
            var addr = new System.Net.Mail.MailAddress(email);
            return addr.Address == email;
        }
        catch
        {
            return false;
        }
    }
}
```

### Setting Up Dependency Injection Per Project

When it comes to registering services in the Application or Infrastructure layers, we do not want to be placing them all individually in the `Program.cs` file as this will get very large, messy. It is easier to create a `DepencyInjection.cs` file in each of these layers then just register it once per project in the `Program.cs` file.

We will need to access the `IServicesCollection` which can be added through a `NuGet` package.

```bash
dotnet add ./src/CleanArchitecture/Application package Microsoft.Extensions.DependencyInjection.Abstractions
```

An example of the `DependencyInjection.cs` file.

```C#
using CleanArchitecture.Application.Services;
using Microsoft.Extensions.DepencyInjection;

namespace CleanArchitecture.Application;

public static class DependencyInjection
{
    public static IServicesCollection AddApplication(this IServicesCollection services)
    {
        services.AddScoped<IRecordService, RecordService>();

        return services;
    }
}
```

We then just need to add this line to our `Program.cs`

```C#
builder.Services.AddApplication();
```

Don't forget to rename the method to `AddInfrastructure()` when creating this in the Infrastructure layer.


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

### Implementing CQRS & Mediatr

CQRS stands for Command Query Responsibility Segregation which is basically splitting the read queries from the write queries. 

It is not the same as the CQS (Command Query Segregation) pattern, as it is more strict on returning void when writing data. 

A small example 

```C#
public class RecordService
{
    // Valid in CQRS but not CQS
    Record CreateRecord(string name);

    // To make it CQS compatible, don't return anything from the write command
    void CreateRecord(string name);
}
```

If we previously choose to take the Service pattern, the easiest way to implement CQRS would be to split your Service into Read & Write.

```C#
// Old service
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

// Can now be turned into this
public class OrderReadService
{
    private readonly IOrderRepository _orderRepository;

    public OrderReadService(IOrderRepository orderRepository)
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
}

public class OrderWriteService
{
    private readonly IOrderRepository _orderRepository;

    public OrderWriteService(IOrderRepository orderRepository)
    {
        _orderRepository = orderRepository;
    }

    public async Task<Order> GetOrderByIdAsync(Guid id)
    {
        return await _orderRepository.GetByIdAsync(id);
    }
}
```

Now if we want to implement the Mediatr pattern instead, we need to reduce the coupling between ther classes and use a Mediatr class instead which sits in between and handles the referencing and calls.

The simplest way of getting started with this is using the `MediatR` package, but this does require a paid license in a commercial setting. We can install this into our Application layer.

```bash
dotnet add src/CleanArchitecture.Application package MediatR
```

To get started, we can inject the `MediatR` library into the controller we want to use to access data.

```C#
using MediatR;
using Microsoft.AspNetCore.Mvc;

namespace CleanArchitecture.Api.Controllers;

[ApiController]
[Route("[controller]")]
public class RecordController(ISender mediatr) : ControllerBase
{
    [HttpPost]
    public async Task<IActionResult> CreateRecord(CreateRecordRequest request)
    {
        // First we need to make an instance of the relevant command
        // the named parameters are optional, just did it for ease of reading
        var command = new CreateRecordCommand(name: request.recordName, userId: request.userId);

        // Call the send method with the command we just created as an argument
        var recordId = await mediatr.Send(command);

        return Ok(recordId);
    }
}
```

Now in the Application layer, we need to make the relevant `Command|Query` and `CommandHandler|QueryHandler` depending on what we want to do.

This is the typical kind of layout to create our `Command|Query`

```C#
using Mediatr;

namespace CleanArchitecture.Application.Records.Commands.CreateRecordCommand;

// We need to add the IRequest<> interface and pass in the data type we want to 
// return. In this case, it is a Guid for our recordId
public record CreateRecordCommand(string name, Guid userId) : IRequest<Guid>;
```

Next, we need to implement the `CommandHandler|QueryHandler` and typically looks something like this.

```C#
using Mediatr;

namespace CleanArchitecture.Application.Records.Commands.CreateRecordCommandHandler;

// For this class, we implement the IRequestHandler interface which takes two 
// arguments, the first is the Query or Command we are implementing, the second
// is the return type
public class CreateRecordCommandHandler : IRequestHandler<CreateRecordCommand, Guid>
{
    // This method is required by the interface to call the logic we want to implement
    public Task<Guid> Handle(CreateRecordCommand request, CancellationToken token)
    {
        // Implement calls to the DB etc and return the data
    }
}
```

Finally, we need to wire this up with our DI container in the Application layer.

```C#
using CleanArchitecture.Application.Services;
using Microsoft.Extensions.DepencyInjection;

namespace CleanArchitecture.Application;

public static class DependencyInjection
{
    public static IServicesCollection AddApplication(this IServicesCollection services)
    {
        services.AddMediatR(options => {
            options.RegisterServicesFromAssemblyContaining(typeof(DependencyInjection));
        })

        return services;
    }
}
```

### Result Pattern

The Result Pattern is a design pattern where methods return a wrapper object (often called `Result`, `OperationResult`, or similar) that clearly indicates success or failure, along with any associated data or error messages.

Instead of throwing exceptions everywhere or just returning raw values, you explicitly return a Result object like:

**Success** - The operation worked, and you get the expected data back.

**Failure** - The operation failed, and you have structured information about why (error message, error code, validation issues, etc.).

To build this raw, you would do something like this:

```C#
public class Result<T>
{
    public bool IsSuccess { get; }
    public bool IsFailure => !IsSuccess;
    public string Error { get; }
    public T Value { get; }

    private Result(bool isSuccess, T value, string error)
    {
        IsSuccess = isSuccess;
        Value = value;
        Error = error;
    }

    public static Result<T> Success(T value) => new Result<T>(true, value, string.Empty);
    public static Result<T> Failure(string error) => new Result<T>(false, default!, error);
}
```

and then it can be used like this:

```C#
var result = userService.CreateUser("john@example.com");

if (result.IsSuccess)
{
    Console.WriteLine($"User created: {result.Value.Id}");
}
else
{
    Console.WriteLine($"Error: {result.Error}");
}
```

If you're feeling lazy and would rather just implement a package, an example is using something like `ErrorOr`

We can install it using the command

```bash
dotnet add CleanArchitecture/Application package ErrorOr
```

We then just implement it wrapped around our return type in our Commands/Queries and Handlers like

```C#
using Mediatr;
using ErrorOr;

namespace CleanArchitecture.Application.Records.Commands.CreateRecordCommand;

public record CreateRecordCommand(string name, Guid userId) : IRequest<ErrorOr<Guid>>;
```

In our `CommandHandler` here, we can also just add something like this

```C#
using Mediatr;
using ErrorOr;

namespace CleanArchitecture.Application.Records.Commands.CreateRecordCommandHandler;

public class CreateRecordCommandHandler : IRequestHandler<CreateRecordCommand, ErrorOr<Guid>>
{
    public async Task<ErrorOr<Guid>> Handle(CreateRecordCommand request, CancellationToken token)
    {
        // Implement calls to the DB etc and return the data

        if (result == null) {
            return Error.NotFound();
        }

        return result.userId;
    }
}
```

In our controller, we then just handle the response

```C#
using MediatR;
using Microsoft.AspNetCore.Mvc;

namespace CleanArchitecture.Api.Controllers;

[ApiController]
[Route("[controller]")]
public class RecordController(ISender mediatr) : ControllerBase
{
    [HttpPost]
    public async Task<IActionResult> CreateRecord(CreateRecordRequest request)
    {
        var command = new CreateRecordCommand(name: request.recordName, userId: request.userId);

        var recordResult = await mediatr.Send(command);

        if (recordResult.IsError) {
            return Problem();
        }

        return Ok(recordResult.Value);
    }
}
```

You can also make a quick one liner as a return.

```C#
return recordResult.MatchFirst(
    userId => Ok(userId),
    error => Problem
);
```

### Repository Pattern

We are now going to start implementing our Repositories. Because our Application or Domain layer cannot call upwards into the Infrastructure layer, we create our interface in either layer it needs access then use Dependency Inversion to fetch our concrete implementation through dependency injection.

To start, we can make a `Common` directory. We then make a `Interfaces` directory and make a `IRecordsRepository.cs`

```C#
using CleanArchitecture.Domain.Records;

namespace CleanArchitecture.Application.Common.Interfaces;

public interface IRecordsRepository
{
    void AddRecord(Record record);
}
```

Now in the `Infrastructure` layer, we need to add our concrete implementation.

Lets make a `Records` directory, then inside that make a `Persistence` directory then create our `RecordRepository.cs` file.

```C#
using CleanArchitecture.Application.Common.Interfaces;
using CleanArchitecture.Domain.Records;

namespace CleanArchitecture.Infrastructure.Records.Persistence;

public class RecordsRepository : IRecordsRepository
{
    public Task AddRecordsAsync(Record record)
    {
        // Logic of the database call goes here using Entity Framework Core or Dapper etc
    }
}
```

Then we can map it in our `DependencyInjection.cs` file in our `Infrastructure` layer

```C#
using Microsoft.Extensions.DependencyInjection;
using CleanArchitecture.Application.Common.Interfaces;

namespace CleanArchitecture.Infrastructure;

public static class DependencyInjection
{
    public static IServiceCollection AddInfrastructure(this IServiceCollection services)
    {
        services.AddScoped<IRecordsRepository, RecordsRepository>();

        return services;
    }
}
```

### Setting Up Entity Framework Core

In this section, we will set up Entity Framework Core in our Infrastructure layer.

To begin, lets add the package

```bash
dotnet add src/CleanArchitecture.Infrastructure package Microsoft.EntityFrameworkCore

# Lets also set this up with Sqlite in this example
dotnet add src/CleanArchitecture.Infrastructure package Microsoft.EntityFrameworkCore.Sqlite
```

Now we need to add our DbContext. (File structure same as namespace).

This can start as one context but be broken out into sections when the application grows.

```C#
using Microsoft.EntityFrameworkCore;
using CleanArchitecture.Domain.Records;

namespace CleanArchitecture.Infrastructure.Common.Persistence;

public class ApplicationDbContext : DbContext
{
    public DbSet<Record> Records { get; set; } = null!;

    public ApplicationDbContext(DbContextOptions options) : base(options)
    {
        //
    }
}
```

We also need to register this in our Dependency Injection.

```C#
using Microsoft.Extensions.DependencyInjection;
using CleanArchitecture.Application.Common.Interfaces;

namespace CleanArchitecture.Infrastructure;

public static class DependencyInjection
{
    public static IServiceCollection AddInfrastructure(this IServiceCollection services)
    {
        services.AddDbContext<ApplicationDbContext>(options => options.UseSqlite("Data Source = CleanArchitecture.db"));

        services.AddScoped<IRecordsRepository, RecordsRepository>();

        return services;
    }
}
```

Now we need to set up migrations. Lets add the Entity Framework Core Design package to our `Presentation` layer. We can then run the migrations once this is installed.

```bash
# Install the package
dotnet add src/CleanArchitecture.Api package Microsoft.EntityFrameworkCore.Design

# Create the migrations
# -p = Project our DbContext lives
# -s = Startup project
dotnet ef migrations add initialCreate -p src/CleanArchitecture.Infrastructure -s src/CleanArchitecture.Api

# Run the migrations
dotnet ef database update -p src/CleanArchitecture.Infrastructure -s src/CleanArchitecture.Api
```

Now we can just inject the context into any repositories and start calling our queries.

### Unit Of Work Pattern

The `Unit Of Work` pattern is a way of wrapping all our queries we want to call in a Command in a database transaction. This way, we call a commit method at the end and either all queries run successfully, or if something goes wrong everything is rolled back and an error is sent back to the user etc.

We can start with adding an interface in our Application or Domain layer (depending on preference) called `IUnitOfWork.cs`

```C#
namespace CleanArchitecture.Application.Common.Interfaces;

public interface IUnitOfWork
{
    Task CommitChangesAsync();
}
```

Now, if we have EntityFrameworkCore set up, we need to add the `IUnitOfWork` interface to our context.

```C#
using Microsoft.EntityFrameworkCore;
using CleanArchitecture.Domain.Records;

namespace CleanArchitecture.Infrastructure.Common.Persistence;

public class ApplicationDbContext : DbContext, IUnitOfWork
{
    public DbSet<Record> Records { get; set; } = null!;

    public ApplicationDbContext(DbContextOptions options) : base(options)
    {
        //
    }

    public async Task CommitChangesAsync()
    {
        await base.SaveChangesAsync();
    }
}
```

We just need to wire this up to Dependency Injection

```C#
using Microsoft.Extensions.DependencyInjection;
using CleanArchitecture.Application.Common.Interfaces;
using CleanArchitecture.Infrastructure.Common.Persistence;

namespace CleanArchitecture.Infrastructure;

public static class DependencyInjection
{
    public static IServiceCollection AddInfrastructure(this IServiceCollection services)
    {
        services.AddDbContext<ApplicationDbContext>(options => options.UseSqlite("Data Source = CleanArchitecture.db"));

        services.AddScoped<IRecordsRepository, RecordsRepository>();
        services.AddScoped<IUnitOfWork>(serviceProvider => serviceProvider.GetRequiredService<ApplicationDbContext>());

        return services;
    }
}
```

In our `Application` layer within our `CommandHandler`, we can then call this with these two commands. If you miss the unitOfWork line, the changes won't save to the database.

```C#
recordsRepository.AddRecordsAsync(record);

unitOfWork.SaveChangesAsync();
```

### Using Fluent Api With Domain Objects And EF Core

When working with entities in the Domain layer, we want them to represent pure business concepts and rules without being tied to technical concerns such as how the database stores or retrieves them. Persistence logic, mappings, and database-specific attributes should instead live in the Infrastructure layer, ensuring the Domain remains focused solely on business logic and remains independent from external frameworks or storage details.

We need to make sure we have a private blank constructor for EF Core to use with reflection as well as making sure our properties have a private set.

```C#
namespace CleanArchitecture.Domain.Records;

public class Record
{
    public Guid Id { get; private set; }
    public string Title { get; private set; }
    public string Email { get; private set; }
    public DateTime CreatedAt { get; private set; }

    private Record() { } // Required for EF Core or serialization

    public Record(string title, string email)
    {
        Id = Guid.NewGuid();
        CreatedAt = DateTime.UtcNow;

        SetTitle(title);
        SetEmail(email);
    }

    public void SetTitle(string title)
    {
        if (string.IsNullOrWhiteSpace(title))
            throw new ArgumentException("Title cannot be empty.", nameof(title));

        Title = title.Trim();
    }

    public void SetEmail(string email)
    {
        if (string.IsNullOrWhiteSpace(email))
            throw new ArgumentException("Email cannot be empty.", nameof(email));

        if (!IsValidEmail(email))
            throw new ArgumentException("Email format is invalid.", nameof(email));

        Email = email.Trim();
    }

    private bool IsValidEmail(string email)
    {
        try
        {
            var addr = new System.Net.Mail.MailAddress(email);
            return addr.Address == email;
        }
        catch
        {
            return false;
        }
    }
}
```

Next, we can go to our `Infrastructure` layer and add a `RecordConfiguration.cs` to our persistence directory.

```C#
using Microsoft.EntityFrameworkCore;
using CleanArchitecture.Domain.Records;
using Microsoft.EntityFrameworkCore.Metadata.Builders;

namespace CleanArchitecture.Infrastructure.Records.Persistence;

public class RecordConfiguration : IEntityTypeConfiguration<Record>
{
    public void Configure(EntityTypeBuilder<Record> builder)
    {
        // Sets the primary key
        builder.HasKey(s => s.Id);

        // Example of setting the Guid ourselves instead of the database handling it
        builder.Property(s => s.Id)
            .ValueGeneratedNever();

        // If we want to rename a column in the database
        builder.Property("Title")
            .HasColumnName("RecordName");

        // If we needed to convert a value in and out of the database, we would use
        // HasConversion() on a complex data type. Lets pretend we have a recordType
        // which is a Smart Enum using the package Ardalis.SmartEnum
        builder.Property(s => s.RecordType)
            .HasConversion(
                recordType => recordType.Value,
                value => RecordType.FromValue(value)
            );
    }
}
```

We now need to apply this configuration when persisting the Domain object.

```C#
using Microsoft.EntityFrameworkCore;
using CleanArchitecture.Domain.Records;

namespace CleanArchitecture.Infrastructure.Common.Persistence;

public class ApplicationDbContext : DbContext
{
    public DbSet<Record> Records { get; set; } = null!;

    public ApplicationDbContext(DbContextOptions options) : base(options)
    {
        //
    }

    // Lets override the OnModelCreating
    protected override void OnModelCreating(ModelBuilder modelBuilder)
    {
        modelBuilder.ApplyConfigurationsFromAssembly(Assembly.GetExecutingAssembly());

        base.onModelCreating(modelBuilder);
    }
}
```

### Domain Driven Design

In **Domain-Driven Design (DDD)**, the software is modeled around the **domain** - the problem space the business cares about.  
For example, when a user raises an issue in an application, they'll typically say *"The record isn't updating"* rather than *"The `X` class isn't saving my update."*  
DDD helps us structure code so it speaks the same language as the business domain.  

---

Domain Models
A **Domain Model** represents concepts, rules, and behaviors from the domain. It can take different forms:  

- **Anemic Domain Model**  
  - Exposes data directly, usually through `public` properties.  
  - Has little or no behavior - logic is pushed outside into services or other parts of the system.  
  - Common in CRUD-style apps, but considered an anti-pattern in strict DDD since it treats objects like data bags.  

- **Rich Domain Model**  
  - Encapsulates both **data and behavior**.  
  - Properties are typically `private` or `protected` and modified through methods.  
  - Ensures invariants (business rules that must always be true) are enforced inside the model.  
  - Only exposes what is necessary to the outside world.  

---

Validity of Domain Models
- **Always Valid Domain Models**  
  - The model enforces its rules so that once created, it is always in a valid state.  
  - Example: If an `Email` value object requires a valid email format, the constructor validates it up front. Once created, you can trust it's always valid.  

- **Not Always Valid Domain Models**  
  - Models may be created in an incomplete or invalid state. External checks are required to ensure validity.  
  - This can lead to fragile code and inconsistent states.  

**Best Practice**: Strive for **Always Valid Domain Models** so your system naturally prevents invalid states and reduces the need for repetitive external validation. 



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

### Validation

There are two types of validation. 

First is `Model Validation` which can sit in the presentation layer or beginning of the Application layer. This is normally validating user input against certain criteria before we process it. A good preference when using this type of validation is fail early so we are not using more CPU cycles than needed going through the application for it to fail at a later stage. We may also end up with the same validation appearing twice when it hits the business logic later on but this is ok.

A good library to use is `Fluent Validation` which is a validation Library for .NET that uses a fluent interface and lambda extresssions for building strongly-typed validation rules.

The library and examples can be found here: https://github.com/FluentValidation/FluentValidation

```bash
dotnet add package FluentValidation
```

```C#
using FluentValidation;

public class CustomerValidator: AbstractValidator<Customer> {
  public CustomerValidator() {
    RuleFor(x => x.Surname).NotEmpty();
    RuleFor(x => x.Forename).NotEmpty().WithMessage("Please specify a first name");
    RuleFor(x => x.Discount).NotEqual(0).When(x => x.HasDiscount);
    RuleFor(x => x.Address).Length(20, 250);
    RuleFor(x => x.Postcode).Must(BeAValidPostcode).WithMessage("Please specify a valid postcode");
  }

  private bool BeAValidPostcode(string postcode) {
    // custom postcode validating logic goes here
  }
}

// Example of handling the validation
var customer = new Customer();
var validator = new CustomerValidator();

// Execute the validator
ValidationResult results = await validator.ValidateAsync(customer);

// Inspect any validation failures.
bool success = results.IsValid;
List<ValidationFailure> failures = results.Errors;

// In our Command/Query Handler we can return something like this
if (!results.IsValid) {
    return results.Errors
        .Select(error => Error.Validation(code: error.PropertyName, description: error.ErrorMessage))
        .ToList();
} 
```

There is also `Domain Layer Validation Rules`. An example of this from what we have been working with could be a Record cannot contain the same email as an existing record.

```C#
// The Command in the Application layer
public record CreateRecordCommand(string Email) : IRequest<Guid>;


// The Command Handler also in the Application layer
public class CreateRecordCommandHandler : IRequestHandler<CreateRecordCommand, Guid>
{
    private readonly IRecordUniquenessChecker _uniquenessChecker;
    private readonly IRecordRepository _recordRepository;

    public CreateRecordCommandHandler(
        IRecordUniquenessChecker uniquenessChecker,
        IRecordRepository recordRepository)
    {
        _uniquenessChecker = uniquenessChecker;
        _recordRepository = recordRepository;
    }

    public async Task<Guid> Handle(CreateRecordCommand request, CancellationToken cancellationToken)
    {
        // Business rule: Email must be unique
        if (!await _uniquenessChecker.IsEmailUniqueAsync(request.Email))
            throw new InvalidOperationException("A record with this email already exists.");

        var record = new Record(request.Email);

        await _recordRepository.AddAsync(record);

        return record.Id;
    }
}

// The Entity in the Domain layer
public class Record
{
    public Guid Id { get; private set; }
    public string Email { get; private set; }

    private Record() { } // For EF Core

    public Record(string email)
    {
        if (string.IsNullOrWhiteSpace(email))
            throw new ArgumentException("Email cannot be empty.", nameof(email));

        Email = email;
        Id = Guid.NewGuid();
    }
}


// The Domain Service Interface
public interface IRecordUniquenessChecker
{
    Task<bool> IsEmailUniqueAsync(string email);
}

// Implementing logic from the database (infrastrcutre layer)
public class RecordRepository : IRecordRepository
{
    private readonly AppDbContext _db;

    public RecordRepository(AppDbContext db)
    {
        _db = db;
    }

    public async Task AddAsync(Record record)
    {
        _db.Records.Add(record);
        await _db.SaveChangesAsync();
    }
}

public class RecordUniquenessChecker : IRecordUniquenessChecker
{
    private readonly AppDbContext _db;

    public RecordUniquenessChecker(AppDbContext db)
    {
        _db = db;
    }

    public async Task<bool> IsEmailUniqueAsync(string email)
    {
        return !await _db.Records.AnyAsync(r => r.Email == email);
    }
}
```

### Validation & MediatR Pipelines

The normal structure when validating using `Fluent Assertions` is placing your validator in your Command or Query folder relevant to the request and then adding a check at the beginning of the Command or Query Handler.

Having it at the beginning of the Command/Query Handler can look a bit messy and break the Single Responsibility Principle. If we are using `Mediatr` we can move this logic into a `Pipeline`. 

First we can add a file like `CreateRecordCommandBehaviour.cs`.

```C#
using MediatR;
using ErrorOr;

namespace CleanArchitecture.Application.Records.Commands.CreateRecordCommandBehaviour;

public class CreateRecordCommandBehaviour : IPipelineBehaviour<CreateRecordCommand, ErrorOr<Record>>
{
    public async Task<ErrorOr<Record>> Handle(CreateRecordCommand request, RequestHandlerDelegate<ErrorOr<Record>> next, CancellationToken cancellationToken)
    {
        ValidationResult results = await validator.ValidateAsync(request);

        bool success = results.IsValid;

        if (!results.IsValid) {
            return results.Errors
                .Select(error => Error.Validation(code: error.PropertyName, description: error.ErrorMessage))
                .ToList();
        } 

        return await next();
    }
}
```

We then register this in our `DepencyInjection.cs` file in our `Application` layer. 

```C#
using CleanArchitecture.Application.Services;
using Microsoft.Extensions.DepencyInjection;

namespace CleanArchitecture.Application;

public static class DependencyInjection
{
    public static IServicesCollection AddApplication(this IServicesCollection services)
    {
        services.AddScoped<IRecordService, RecordService>();

        // Add this to implement our pipeline as Middleware 
        services.AddBehaviour<IPipelineBehaviour<CreateRecordCommand, ErrorOr<Record>>, CreateRecordCommandBehaviour>();

        return services;
    }
}
```

### Validation & MediatR Pipelines Using Generic Behaviours

In the last section, we implemented a `MediatR pipeline` to handle our validation. The problem with that approach is everytime a developer on your team wants to add a new feature, they have to add a file for our Command/Query, the Handler, the Validator and the Behaviour.

We can make this easier by implementing a Open Generic Pipeline Behaviour.

First we will next to add another package to our Application layer.

```bash
dotnet add src/CleanArchitecture.Application package FluentValidation.AspNetCore
```

We can get started by adding a new folder in our `Common` directory called `Behaviours` and create a file called `ValidationBehaviour.cs`.

```C#
using MediatR;
using ErrorOr;

namespace CleanArchitecture.application.Common.Behaviours;

public class ValidationBehaviour<TRequest, TResponse> : IPipelineBehaviour<TRequest, TResponse>
    where TRequest : IRequest<TResponse>
    where TResponse : IErrorOr
{
    private readonly IValidator<TRequest>? _validator;

    public ValidationBehaviour(IValidator<TRequest>? validator = null)
    {
        _validator = validator;
    }

    public async Task<TResponse> Handle(TRequest request, RequestHandlerDelegate<TResponse> next, CancellationToken token)
    {
        if (_validator == null) {
            return await next();
        }

        var validationResult = await _validator.ValidateAync(request, token);

        if (validationResult.IsValid) {
            return await next();
        }

        var errors = validationResult.Errors
            .ConvertAll(error => Error.Validation(code: error.PropertyName, description: error.ErrorMessage));

        return (dynamic)errors;
    }
}
```

In our `DepencyInjection.cs`, we can now add this

```C#
using CleanArchitecture.Application.Services;
using Microsoft.Extensions.DepencyInjection;

namespace CleanArchitecture.Application;

public static class DependencyInjection
{
    public static IServicesCollection AddApplication(this IServicesCollection services)
    {
        services.AddMediatR(options => {
            options.RegisterServicesFromAssemblyContaining(typeof(DependencyInjection));

            options.AddOpenBehaviour(typeof(ValidationBehaviour<,>));
        })

        services.AddValidatorsFromAssemblyContaining(typeof(DependencyInjection));

        return services;
    }
}
```

### Domain Events

A `domain event` is something interesting, from a business point of view, that happened within the system.

For this example, we will need to add the `MediatR` package to the Domain layer

```bash
dotnet add src/CleanArchitecture.Domain package MediatR
```

```C#
// First lets make an interface in a Common directory in the Domain layer
public interface IDomainEvent : INotification;

// We'll make a simple event that fires when a Record is created. We place these in the domain layer within an events folder.
public class RecordCreatedEvent : IDomainEvent
{
    public Guid RecordId { get; }
    public string Email { get; }

    public RecordCreatedEvent(Guid recordId, string email)
    {
        RecordId = recordId;
        Email = email;
    }
}

// Now we want to make a base class for our Domain Events. This can also live in the Common folder we just created. We can call it something like Entity.cs
public abstract class Entity
{
    public Guid Id { get; init; }

    protected readonly List<IDomainEvent> _domainEvents = [];

    protected IReadOnlyCollection<IDomainEvent> DomainEvents => _domainEvents.AsReadOnly();

    protected Entity(Guid id) => Id = id;

    protected Entity() {}

    private void AddDomainEvent(IDomainEvent domainEvent)
    {
        _domainEvents.Add(domainEvent);
    }

    public void ClearDomainEvents() => _domainEvents.Clear();
}

// Next we add an internal collection of events to the relevant entity
public class Record : Entity
{
    public string Email { get; private set; }

    private Record() { } // EF Core

    public Record(Guid userId, string email) : base(userId ?? Guid.NewGuid())
    {
        if (string.IsNullOrWhiteSpace(email))
            throw new ArgumentException("Email cannot be empty.", nameof(email));

        Email = email;

        AddDomainEvent(new RecordCreatedEvent(Id, Email));
    }
}

// After saving a Record, the application layer (command handler or repository decorator) is responsible for publishing domain events.
public class CreateRecordCommandHandler : IRequestHandler<CreateRecordCommand, Guid>
{
    private readonly IRecordRepository _recordRepository;
    private readonly IRecordUniquenessChecker _uniquenessChecker;
    private readonly IMediator _mediator;

    public CreateRecordCommandHandler(
        IRecordRepository recordRepository,
        IRecordUniquenessChecker uniquenessChecker,
        IMediator mediator)
    {
        _recordRepository = recordRepository;
        _uniquenessChecker = uniquenessChecker;
        _mediator = mediator;
    }

    public async Task<Guid> Handle(CreateRecordCommand request, CancellationToken cancellationToken)
    {
        if (!await _uniquenessChecker.IsEmailUniqueAsync(request.Email))
            throw new InvalidOperationException("A record with this email already exists.");

        var record = new Record(request.Email);

        await _recordRepository.AddAsync(record);

        // Publish domain events
        foreach (var domainEvent in record.DomainEvents)
        {
            await _mediator.Publish(domainEvent, cancellationToken);
        }

        record.ClearDomainEvents();

        return record.Id;
    }
}

// Handlers live in the Application Layer (or Infrastructure if they're purely technical).
public class RecordCreatedEventHandler : INotificationHandler<RecordCreatedEvent>
{
    public async Task Handle(RecordCreatedEvent notification, CancellationToken cancellationToken)
    {
        // Example: Send welcome email, log audit trail, etc.
        Console.WriteLine($"New record created: {notification.Email}");

        return Task.CompletedTask;
    }
}
```

### Transactional & Eventual Consistency

`Transactional Consistency` is when all operations within a unit of work (usually a database transaction) succeed or fail together. The system state is always consistent immediately after the transaction commits.

For example: When creating a Record, you also create a related UserProfile in the same transaction. If saving the UserProfile fails, the whole transaction rolls back, leaving no half-complete data.

Pros:
- Low congitive load
- Simplicity

Cons:
- Decreased performance
- Limited error handling
- Decreased scalability

`Eventual Consistency` is when changes are applied in one place first, then propagated to others asynchronously (via events or messaging). The system will become consistent over time, but not immediately. 

For example: RecordCreatedEvent is raised when a Record is saved. A handler later sends a "welcome email" or updates a reporting database. There may be a short delay where the Record exists but the email hasn't been sent yet.

Pros:
- High performance
- Flexible error handling
- Scalability
- Compose different side effects

Cons:
- High congitive load
- Complexity

An example of using Eventual Consistency looks something like this:

```C#
// In our Entity class, see above for the Entity base class version
public class Record
{
    public Guid Id { get; private set; }
    public string Email { get; private set; }

    private readonly List<IDomainEvent> _domainEvents = new();
    public IReadOnlyCollection<IDomainEvent> DomainEvents => _domainEvents.AsReadOnly();

    private Record() { }

    public Record(string email)
    {
        Id = Guid.NewGuid();
        Email = email;

        AddDomainEvent(new RecordCreatedEvent(Id, Email));
    }

    private void AddDomainEvent(IDomainEvent domainEvent) => _domainEvents.Add(domainEvent);

    public void ClearDomainEvents() => _domainEvents.Clear();
}

// Now create a middleware to process the Queue
public class DomainEventsMiddleware
{
    private readonly RequestDelegate _next;
    private static readonly Queue<IDomainEvent> _eventQueue = new();

    public DomainEventsMiddleware(RequestDelegate next)
    {
        _next = next;
    }

    public async Task InvokeAsync(HttpContext context, AppDbContext dbContext)
    {
        // Before request
        await _next(context);

        // After transaction completes successfully
        var entitiesWithEvents = dbContext.ChangeTracker
            .Entries<Record>()
            .Select(e => e.Entity)
            .Where(e => e.DomainEvents.Any())
            .ToList();

        foreach (var entity in entitiesWithEvents)
        {
            foreach (var domainEvent in entity.DomainEvents)
            {
                _eventQueue.Enqueue(domainEvent);
            }

            entity.ClearDomainEvents();
        }

        // Process events asynchronously (simulated eventual consistency)
        while (_eventQueue.Count > 0)
        {
            var domainEvent = _eventQueue.Dequeue();
            await HandleEventAsync(domainEvent);
        }
    }

    private Task HandleEventAsync(IDomainEvent domainEvent)
    {
        switch (domainEvent)
        {
            case RecordCreatedEvent e:
                Console.WriteLine($"[EVENT HANDLER] Record created: {e.RecordId}, {e.Email}");
                // e.g. send email, publish to external service, etc.
                break;
        }

        return Task.CompletedTask;
    }
}

// Register this middleware in Program.cs
var builder = WebApplication.CreateBuilder(args);
builder.Services.AddDbContext<AppDbContext>();
var app = builder.Build();

app.UseMiddleware<DomainEventsMiddleware>();
app.MapControllers();

app.Run();

// We can also add this to our infrastructure layer like this
public static class RequestPipeline
{
    public static IApplicationBuilder AddInfrastructureMiddleware(this IApplicationBuilder builder)
    {
        builder.UseMiddleware<DomainEventsMiddleware>();

        return builder;
    }
}

// We then just add this to Program.cs instead
app.AddInfrastructureMiddleware();
```

With the in-memory approach, if our application restarts, we lose any outstanding events because they only exist in memory. For a more consistent and reliable solution, we should persist events and use a message broker or durable queue (like RabbitMQ, Redis Streams, or Apache Kafka) so that events survive crashes and can be processed reliably. This is known as the `Outbox Pattern + Message Broker` strategy.

### Authentication & Authorization

Authentication and Authorization in a Clean Architecture app require some careful separation of concerns, because they cut across multiple layers.

Authentication is typically handled at the API / Infrastructure boundary (before entering your Application layer).

Example: ASP.NET Core Middleware validates a JWT and extracts claims. The result (e.g. UserId, Roles) is passed into the Application Layer via an abstraction (e.g. ICurrentUserService).

Authorization is typically business rules about what users can do belong in the Domain or Application layer.

Example: "Only the owner of a Record can delete it" is a Domain rule or "Only Admins can create new Records" is an Application rule.

An example of implementation:

```C#
// In the domain layer, create an IdentityUser
public class ApplicationUser : IdentityUser<Guid>
{
    // Add any custom props here
    public string? FirstName { get; set; }
    public string? LastName { get; set; }
}

// In the infrastructure layer, add the IdentityDbContext to our DbContext
public class ApplicationDbContext : IdentityDbContext<ApplicationUser, IdentityRole<Guid>, Guid>
{
    public ApplicationDbContext(DbContextOptions<ApplicationDbContext> options)
        : base(options)
    {
    }

    protected override void OnModelCreating(ModelBuilder builder)
    {
        base.OnModelCreating(builder);
        // You can add seeding or model customization here
    }
}

// Add something like this to our Program.cs or abstract it into our infrastructure layer
builder.Services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(builder.Configuration.GetConnectionString("DefaultConnection")));

builder.Services.AddDefaultIdentity<ApplicationUser>(options =>
    {
        options.SignIn.RequireConfirmedAccount = true;
        // Additional Identity options...
    })
    .AddRoles<IdentityRole<Guid>>()  // if role support needed
    .AddEntityFrameworkStores<ApplicationDbContext>();
```

If we want to seed a Admin and User role, we can modify the `OnModelCreating`

```C#
protected override void OnModelCreating(ModelBuilder builder)
{
    base.OnModelCreating(builder);

    var adminId = Guid.NewGuid();
    var roleId = Guid.NewGuid();
    var hasher = new PasswordHasher<ApplicationUser>();

    var adminUser = new ApplicationUser
    {
        Id = adminId,
        UserName = "admin",
        NormalizedUserName = "ADMIN",
        Email = "admin@example.com",
        NormalizedEmail = "ADMIN@EXAMPLE.COM",
        EmailConfirmed = true,
        SecurityStamp = Guid.NewGuid().ToString(),
        FirstName = "Super",
        LastName = "Admin"
    };
    adminUser.PasswordHash = hasher.HashPassword(adminUser, "Admin@123");

    var adminRole = new IdentityRole<Guid>
    {
        Id = roleId,
        Name = "Admin",
        NormalizedName = "ADMIN"
    };

    builder.Entity<ApplicationUser>().HasData(adminUser);
    builder.Entity<IdentityRole<Guid>>().HasData(adminRole);
    builder.Entity<IdentityUserRole<Guid>>().HasData(new IdentityUserRole<Guid>
    {
        RoleId = roleId,
        UserId = adminId
    });
}
```

Implement ICurrentUserService to abstract identity details into Application layer:

```C#
public interface ICurrentUserService
{
    Guid? UserId { get; }
    bool IsInRole(string role);
}
```

and add the logic to the Infrastructure layer

```C#
public class CurrentUserService : ICurrentUserService
{
    private readonly IHttpContextAccessor _httpContextAccessor;

    public CurrentUserService(IHttpContextAccessor httpContextAccessor)
    {
        _httpContextAccessor = httpContextAccessor;
    }

    public Guid? UserId =>
        Guid.TryParse(_httpContextAccessor.HttpContext?.User.FindFirstValue(ClaimTypes.NameIdentifier), out var id)
            ? id
            : (Guid?)null;

    public bool IsInRole(string role) =>
        _httpContextAccessor.HttpContext?.User.IsInRole(role) ?? false;
}
```

Add this to the DepencyInjection in the Application layer.

Finally we need to add some setup for the Authentication endpoints to register
In `Program.cs`, add the following

```C#
// Authorization
builder.Services.AddAuthorization();

// Configure identity database access via EF Core. Something like this should already 
// exist but make sure the Context here is the one we extended earlier
builder.Services.AddDbContext<ApplicationDbContext>(
    options => options.UseInMemoryDatabase("AppDb")
);

// Activate identity APIs. By default, both cookies and proprietary tokens
// are activated. Cookies will be issued based on the `useCookies` querystring
// parameter in the login endpoint.
builder.Services.AddIdentityApiEndpoints<IdentityUser>()
    .AddEntityFrameworkStores<ApplicationDbContext>();

// Built-in endpoints like /register, /login, /me
app.MapIdentityApi<IdentityUser>();
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


### Returning Problem Details

`ProblemDetails` is a built-in class in ASP.NET Core (Microsoft.AspNetCore.Mvc) that represents machine-readable error details for HTTP responses.

It provides a consistent format for error messages so that clients (like frontend apps or API consumers) can parse and handle errors predictably.

```json
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "Bad Request",
  "status": 400,
  "detail": "Email address is invalid.",
  "instance": "/customers"
}
```

Example using an `[ApiController]`

```C#
[ApiController]
[Route("api/[controller]")]
public class CustomersController : ControllerBase
{
    [HttpPost]
    public IActionResult CreateCustomer(Customer customer)
    {
        if (!ModelState.IsValid)
            return ValidationProblem(ModelState);

        return CreatedAtAction(nameof(GetCustomer), new { id = customer.Id }, customer);
    }

    [HttpGet("{id}")]
    public IActionResult GetCustomer(Guid id) => Ok(new { id });
}
```

If this fails, then the user recieves this

```json
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "errors": {
    "Email": [
      "The Email field is required."
    ]
  },
  "traceId": "00-2a13d6c5..."
}
```

You can configure global `ProblemDetails` behavior with middleware:

```C#
builder.Services.AddProblemDetails(options =>
{
    options.CustomizeProblemDetails = context =>
    {
        context.ProblemDetails.Extensions.Add("traceId", context.HttpContext.TraceIdentifier);
    };
});
```

### Model Binding

Model Binding in ASP.NET Core is the process that automatically maps HTTP request data (like form fields, JSON, query strings, route values, or headers) into .NET method parameters or object properties in your controller or Razor Page.

When a request hits your controller action:

- The model binding system looks at each action parameter.
- It determines where to get the data from (based on attributes, HTTP method, or content type).
- It reads and converts that data to the correct .NET type.
- It validates the model (if you use data annotations).
- It passes the populated object into your action method.

Common Data Sources:

- Route data - [FromRoute]
- Query string - [FromQuery]
- Form data - [FromForm]
- Request body (JSON/XML) - [FromBody]
- Header values - [FromHeader]
- Custom services - [FromServices]

Example:

```C#
[HttpPost("{orderId}")]
public IActionResult CreateOrder(
    [FromRoute] int orderId,
    [FromQuery] bool notify,
    [FromBody] OrderRequest request)
{
    // orderId = 123
    // notify = true
    // request.ProductId = 5, request.Quantity = 2
    ...
}
```

Model Validation Integration:  

```C#
// Create a model
public class RegisterModel
{
    [Required]
    public string Username { get; set; }

    [EmailAddress]
    public string Email { get; set; }

    [Range(18, 120)]
    public int Age { get; set; }
}

// In your controller
[HttpPost]
public IActionResult Register([FromBody] RegisterModel model)
{
    if (!ModelState.IsValid)
        return BadRequest(ModelState);

    // Valid model
    return Ok();
}
```

Implementing `IValidatableObject` is a great way to add custom validation logic to your models in ASP.NET Core beyond what you can do with `[DataAnnotation]` attributes like `[Required]` or `[Range]`.

```C#
using System;
using System.Collections.Generic;
using System.ComponentModel.DataAnnotations;

public class RegisterModel : IValidatableObject
{
    [Required]
    public string Name { get; set; }

    public int Age { get; set; }

    public bool SubscribeToNewsletter { get; set; }

    public string? Email { get; set; }

    public IEnumerable<ValidationResult> Validate(ValidationContext validationContext)
    {
        // Rule 1: Age must be >= 18
        if (Age < 18)
        {
            yield return new ValidationResult(
                "You must be at least 18 years old.",
                new[] { nameof(Age) }
            );
        }

        // Rule 2: Email required if subscribing
        if (SubscribeToNewsletter && string.IsNullOrWhiteSpace(Email))
        {
            yield return new ValidationResult(
                "Email is required when subscribing to the newsletter.",
                new[] { nameof(Email) }
            );
        }
    }
}
```

In your controller, model validation will automatically invoke Validate() after DataAnnotation validation.

A good library to use for Validation is FluentValidations.

### Configuration

The best way to set up application settings from `AppSettings.json` etc is to create a class or record with the parameters we want to introduice from the file and then instaniate them in our `Program.cs` or some configuration file to map from our json file to the class/record.

```C#
// Create a new class or record
public record MailSettings(string Server, int Port);

// In our Program.cs or abstraction
var mailSettings = builder.Configuration.GetSection(nameof(MailSettings)).Get<MailSettings>();
builder.Services.AddSingleton(mailSettings);
```

You may also see sometimes that some developers inject `IConfiguration` into the class then pick it out using `_config["MailSettings:Port"]` but this can be hard to mock when it comes to testing. It may also need extra checks to make sure a value is set.

This is the order in which different configuration providers take recedence from highest to lowest:

- Command-line args
- Environment variables
- User secrets (Development)
- appsettings.{Environment}.json
- appsettings.json

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

If you are using JetBrains Rider, you can install a plugin called `Entity Framework Core UI` which gives you this functionality through a nice UI.

### MSSQL Connection String Example

This is for connecting to a local instance of the database

```json
"ConnectionStrings": {
    "DefaultConnection": "Data Source=WinDev2401Eval\\SQLEXPRESS;Initial Catalog=financial-app;Integrated Security=True;Connect Timeout=30;Encrypt=False;TrustServerCertificate=False;ApplicationIntent=ReadWrite;MultiSubnetFailover=False"
},
```

### Example CRUD using Async Await

In the example above, we just used thread blocking calls to retrieve our data. In this example we will use async await to create non-blocking DB access.

```C#
using Microsoft.AspNetCore.Mvc;
using Microsoft.EntityFrameworkCore;
using AsyncCrudDemo.Data;
using AsyncCrudDemo.Models;

namespace AsyncCrudDemo.Controllers;

[ApiController]
[Route("api/[controller]")]
public class ProductsController(AppDbContext context) : ControllerBase
{
    // GET: api/products
    [HttpGet]
    public async Task<ActionResult<IEnumerable<Product>>> GetProducts()
    {
        return await context.Products.AsNoTracking().ToListAsync();
    }

    // GET: api/products/5
    [HttpGet("{id}")]
    public async Task<ActionResult<Product>> GetProduct(int id)
    {
        var product = await context.Products.FindAsync(id);

        if (product == null)
            return NotFound();

        return product;
    }

    // POST: api/products
    [HttpPost]
    public async Task<ActionResult<Product>> CreateProduct(Product product)
    {
        context.Products.Add(product);
        await context.SaveChangesAsync();

        return CreatedAtAction(nameof(GetProduct), new { id = product.Id }, product);
    }

    // PUT: api/products/5
    [HttpPut("{id:int}")]
    public async Task<IActionResult> UpdateProduct(int id, Product updatedProduct)
    {
        if (id != updatedProduct.Id)
            return BadRequest();

        var product = await context.Products.FindAsync(id);
        if (product == null)
            return NotFound();

        product.Name = updatedProduct.Name;
        product.Price = updatedProduct.Price;

        await context.SaveChangesAsync();
        return NoContent();
    }

    // DELETE: api/products/5
    [HttpDelete("{id:int}")]
    public async Task<IActionResult> DeleteProduct(int id)
    {
        var product = await context.Products.FindAsync(id);
        if (product == null)
            return NotFound();

        context.Products.Remove(product);
        await context.SaveChangesAsync();
        return NoContent();
    }
}
```

### Logging Queries Sent To The Database

If we need to log queries being sent to the database to see if there is anything wrong, we can enable `LogTo()` method in our context. This spits out a lot of extra data but is a quick way of seeing what is happening.

For more production based settings, we would use something like `Serilog` and use a file sink to dump out into. This does not need the `EnableDetailedErrors` or `LogTo` adding to our options and can be set up as normal.

```C#
using Microsoft.EntityFrameworkCore;
using AsyncCrudDemo.Models;
using Microsoft.Extensions.Logging;

namespace AsyncCrudDemo.Data;

public class AppDbContext : DbContext
{
    public DbSet<Product> Products => Set<Product>();

    public AppDbContext(DbContextOptions<AppDbContext> options)
        : base(options)
    {
    }

    // Optional constructor for cases where DI isn't used
    public AppDbContext()
    {
    }

    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        // Only configure if options not already provided by DI (to avoid conflicts)
        if (!optionsBuilder.IsConfigured)
        {
            optionsBuilder.UseSqlite("Data Source=products.db");
        }

        // Configure EF Core logging
        optionsBuilder
            .EnableSensitiveDataLogging() // logs parameter values (useful for debugging; avoid in production)
            .EnableDetailedErrors()       // provides more detailed EF Core exceptions
            .LogTo(
                message => Console.WriteLine($"[EF LOG] {message}"),
                new[] { DbLoggerCategory.Database.Command.Name },
                LogLevel.Information)
            .LogTo(
                message => Console.WriteLine($"[EF DEBUG] {message}"),
                new[] { DbLoggerCategory.ChangeTracking.Name },
                LogLevel.Debug);
    }

    protected override void OnModelCreating(ModelBuilder modelBuilder)
    {
        // Example: configure a table name and constraints
        modelBuilder.Entity<Product>(entity =>
        {
            entity.ToTable("Products");

            entity.HasKey(e => e.Id);

            entity.Property(e => e.Name)
                .HasMaxLength(200)
                .IsRequired();

            entity.Property(e => e.Price)
                .HasPrecision(10, 2);
        });
    }
}
```

### Database Annotations

Below is a comprehensive example of an entity class that uses many of the most common EF Core data annotations to demonstrate:

- Primary key & identity
- Required fields & string length constraints
- Indexes
- Relationships (foreign keys)
- Computed & ignored properties
- Column mapping and naming

```C#
using System.ComponentModel.DataAnnotations;
using System.ComponentModel.DataAnnotations.Schema;
using Microsoft.EntityFrameworkCore;

namespace AsyncCrudDemo.Models;

// Example of defining an index using attribute (EF Core 5+)
[Index(nameof(Email), IsUnique = true)]
public class Customer
{
    // Primary key
    [Key]
    [DatabaseGenerated(DatabaseGeneratedOption.Identity)]
    public int CustomerId { get; set; }

    // Required string with max length
    [Required]
    [StringLength(100)]
    public string FirstName { get; set; } = string.Empty;

    [Required]
    [StringLength(100)]
    public string LastName { get; set; } = string.Empty;

    // Unique index (via attribute above) + required + email format hint
    [Required]
    [StringLength(255)]
    [EmailAddress]
    public string Email { get; set; } = string.Empty;

    // Custom column name and type
    [Column("Phone_Number", TypeName = "varchar(20)")]
    public string? PhoneNumber { get; set; }

    // Date with database default value (set in OnModelCreating or migration)
    [Required]
    public DateTime CreatedAt { get; set; } = DateTime.UtcNow;

    // Decimal with precision and scale
    [Column(TypeName = "decimal(10,2)")]
    [Range(0, 1000000)]
    public decimal AccountBalance { get; set; }

    // Navigation property - one-to-many with Orders
    public ICollection<Order> Orders { get; set; } = new List<Order>();

    // Computed (not mapped to database)
    [NotMapped]
    public string FullName => $"{FirstName} {LastName}";
}

// Example of a related entity
public class Order
{
    [Key]
    public int OrderId { get; set; }

    [Required]
    public DateTime OrderDate { get; set; } = DateTime.UtcNow;

    [Required]
    [Column(TypeName = "decimal(10,2)")]
    public decimal TotalAmount { get; set; }

    // Foreign key
    [ForeignKey(nameof(Customer))]
    public int CustomerId { get; set; }

    // Navigation property
    public Customer? Customer { get; set; }
}
```

### Fluent API

Using the Fluent API is often preferred in larger projects because it keeps your entities clean (no attributes) and centralizes all mapping logic in `OnModelCreating`.

Lets start with these two models

```C#
namespace AsyncCrudDemo.Models;

public class Customer
{
    public int CustomerId { get; set; }
    public string FirstName { get; set; } = string.Empty;
    public string LastName { get; set; } = string.Empty;
    public string Email { get; set; } = string.Empty;
    public string? PhoneNumber { get; set; }
    public DateTime CreatedAt { get; set; } = DateTime.UtcNow;
    public decimal AccountBalance { get; set; }

    // Navigation property
    public ICollection<Order> Orders { get; set; } = new List<Order>();

    // Computed property (not mapped to DB)
    public string FullName => $"{FirstName} {LastName}";
}

public class Order
{
    public int OrderId { get; set; }
    public DateTime OrderDate { get; set; } = DateTime.UtcNow;
    public decimal TotalAmount { get; set; }

    public int CustomerId { get; set; }
    public Customer? Customer { get; set; }
}
```

Now in our Context file, we can use the `OnModelCreating` method to set up our schema definitions

```C#
using Microsoft.EntityFrameworkCore;
using AsyncCrudDemo.Models;

namespace AsyncCrudDemo.Data;

public class AppDbContext : DbContext
{
    public DbSet<Customer> Customers => Set<Customer>();
    public DbSet<Order> Orders => Set<Order>();

    public AppDbContext(DbContextOptions<AppDbContext> options) : base(options)
    {
    }

    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        if (!optionsBuilder.IsConfigured)
        {
            optionsBuilder.UseSqlite("Data Source=customers.db");
        }

        // Enable useful EF debugging
        optionsBuilder
            .EnableSensitiveDataLogging()
            .EnableDetailedErrors()
            .LogTo(Console.WriteLine, LogLevel.Information);
    }

    protected override void OnModelCreating(ModelBuilder modelBuilder)
    {
        // ============================
        // Customer Entity Configuration
        // ============================
        var customer = modelBuilder.Entity<Customer>();

        customer.ToTable("Customers");

        // Primary key
        customer.HasKey(c => c.CustomerId);

        // Properties
        customer.Property(c => c.FirstName)
            .IsRequired()
            .HasMaxLength(100);

        customer.Property(c => c.LastName)
            .IsRequired()
            .HasMaxLength(100);

        customer.Property(c => c.Email)
            .IsRequired()
            .HasMaxLength(255);

        // Index (unique)
        customer.HasIndex(c => c.Email)
            .IsUnique();

        customer.Property(c => c.PhoneNumber)
            .HasColumnName("Phone_Number")
            .HasColumnType("varchar(20)");

        customer.Property(c => c.CreatedAt)
            .IsRequired();

        customer.Property(c => c.AccountBalance)
            .HasPrecision(10, 2)
            .HasDefaultValue(0m);

        // Ignore computed property
        customer.Ignore(c => c.FullName);

        // ============================
        // Order Entity Configuration
        // ============================
        var order = modelBuilder.Entity<Order>();

        order.ToTable("Orders");

        order.HasKey(o => o.OrderId);

        order.Property(o => o.OrderDate)
            .IsRequired();

        order.Property(o => o.TotalAmount)
            .HasPrecision(10, 2)
            .IsRequired();

        // Relationships
        order.HasOne(o => o.Customer)
            .WithMany(c => c.Orders)
            .HasForeignKey(o => o.CustomerId)
            .OnDelete(DeleteBehavior.Cascade);
    }
}
```

Now, as your app grows this is going to get messy very fast. Lets split these out into configuration files instead. These classes need to implement the `IEntityTypeConfiguration<>` interface which wants us to implement a `Configure` method. We then use `ApplyConfiguration` if we want to add each configuration individually or `ApplyConfigurationsFromAssembly` to find all the classes using the interface.

```C#
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;
using AsyncCrudDemo.Models;

namespace AsyncCrudDemo.Data.Configurations;

public class CustomerConfiguration : IEntityTypeConfiguration<Customer>
{
    public void Configure(EntityTypeBuilder<Customer> builder)
    {
        builder.ToTable("Customers");

        builder.HasKey(c => c.CustomerId);

        builder.Property(c => c.FirstName)
            .IsRequired()
            .HasMaxLength(100);

        builder.Property(c => c.LastName)
            .IsRequired()
            .HasMaxLength(100);

        builder.Property(c => c.Email)
            .IsRequired()
            .HasMaxLength(255);

        builder.HasIndex(c => c.Email)
            .IsUnique();

        builder.Property(c => c.PhoneNumber)
            .HasColumnName("Phone_Number")
            .HasColumnType("varchar(20)");

        builder.Property(c => c.CreatedAt)
            .IsRequired();

        builder.Property(c => c.AccountBalance)
            .HasPrecision(10, 2)
            .HasDefaultValue(0m);

        builder.Ignore(c => c.FullName);
    }
}

public class OrderConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> builder)
    {
        builder.ToTable("Orders");

        builder.HasKey(o => o.OrderId);

        builder.Property(o => o.OrderDate)
            .IsRequired();

        builder.Property(o => o.TotalAmount)
            .HasPrecision(10, 2)
            .IsRequired();

        builder.HasOne(o => o.Customer)
            .WithMany(c => c.Orders)
            .HasForeignKey(o => o.CustomerId)
            .OnDelete(DeleteBehavior.Cascade);
    }
}
```

Now we can just change our `OnModelCreating` to this

```C#
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    // Applies all IEntityTypeConfiguration<T> classes automatically
    modelBuilder.ApplyConfigurationsFromAssembly(Assembly.GetExecutingAssembly());
}
```

### Relationships

EF Core supports several kinds of relationships between entities:

- One-to-Many
- One-to-One
- Many-to-Many
- Self-referencing

One To Many:

```C#
// Entities
public class Customer
{
    public int CustomerId { get; set; }
    public string Name { get; set; } = string.Empty;

    public ICollection<Order> Orders { get; set; } = new List<Order>();
}

public class Order
{
    public int OrderId { get; set; }
    public DateTime OrderDate { get; set; } = DateTime.UtcNow;

    public int CustomerId { get; set; }
    public Customer? Customer { get; set; }
}

// Configurations
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;

public class CustomerConfiguration : IEntityTypeConfiguration<Customer>
{
    public void Configure(EntityTypeBuilder<Customer> builder)
    {
        builder.ToTable("Customers");
        builder.HasKey(c => c.CustomerId);
        builder.Property(c => c.Name).IsRequired();
    }
}

public class OrderConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> builder)
    {
        builder.ToTable("Orders");
        builder.HasKey(o => o.OrderId);

        builder.HasOne(o => o.Customer)
               .WithMany(c => c.Orders)
               .HasForeignKey(o => o.CustomerId)
               .OnDelete(DeleteBehavior.Cascade);
    }
}
```

One To One:

```C#
// Entities
public class Customer
{
    public int CustomerId { get; set; }
    public string Name { get; set; } = string.Empty;
    public Address? Address { get; set; }

    public ICollection<Order> Orders { get; set; } = new List<Order>();
}

public class Address
{
    public int AddressId { get; set; }
    public string Street { get; set; } = string.Empty;
    public string City { get; set; } = string.Empty;

    public int CustomerId { get; set; }
    public Customer? Customer { get; set; }
}

// Configuration
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;

public class CustomerConfiguration : IEntityTypeConfiguration<Customer>
{
    public void Configure(EntityTypeBuilder<Customer> builder)
    {
        builder.ToTable("Customers");
        builder.HasKey(c => c.CustomerId);
        builder.Property(c => c.Name).IsRequired();
    }
}

public class AddressConfiguration : IEntityTypeConfiguration<Address>
{
    public void Configure(EntityTypeBuilder<Address> builder)
    {
        builder.ToTable("Addresses");
        builder.HasKey(a => a.AddressId);

        builder.HasOne(a => a.Customer)
               .WithOne(c => c.Address)
               .HasForeignKey<Address>(a => a.CustomerId)
               .OnDelete(DeleteBehavior.Cascade);
    }
}
```

Many-to-Many:

```C#
// Models
public class Student
{
    public int StudentId { get; set; }
    public string Name { get; set; } = string.Empty;

    public ICollection<Course> Courses { get; set; } = new List<Course>();
}

public class Course
{
    public int CourseId { get; set; }
    public string Title { get; set; } = string.Empty;

    public ICollection<Student> Students { get; set; } = new List<Student>();
}

// Configuration
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;

public class StudentConfiguration : IEntityTypeConfiguration<Student>
{
    public void Configure(EntityTypeBuilder<Student> builder)
    {
        builder.ToTable("Students");
        builder.HasKey(s => s.StudentId);
        builder.Property(s => s.Name).IsRequired();

        builder.HasMany(s => s.Courses)
               .WithMany(c => c.Students)
               // This part is optional if you want more control
               .UsingEntity<Dictionary<string, object>>(
                    "StudentCourse",  // Join table name
                    left => left.HasOne<Course>().WithMany().HasForeignKey("CourseId"),
                    right => right.HasOne<Student>().WithMany().HasForeignKey("StudentId"),
                    linkBuilder =>
                    {
                        linkBuilder.HasKey("StudentId", "CourseId");
                        linkBuilder.ToTable("StudentCourses");
                    });
    }
}
```

Self-referencing:

```C#
// Models
public class Employee
{
    public int EmployeeId { get; set; }
    public string Name { get; set; } = string.Empty;

    public int? ManagerId { get; set; }
    public Employee? Manager { get; set; }

    public ICollection<Employee> DirectReports { get; set; } = new List<Employee>();
}

// Configuration
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;

public class EmployeeConfiguration : IEntityTypeConfiguration<Employee>
{
    public void Configure(EntityTypeBuilder<Employee> builder)
    {
        builder.ToTable("Employees");
        builder.HasKey(e => e.EmployeeId);

        builder.Property(e => e.Name).IsRequired();

        builder.HasOne(e => e.Manager)
               .WithMany(m => m.DirectReports)
               .HasForeignKey(e => e.ManagerId)
               .OnDelete(DeleteBehavior.Restrict);
    }
}
```

By default, Entity Framework Core does not lazy load all relationships and needs to be defined when we call our query. For this we use the `Include` method.

```C#
var customersWithOrders = await context.Customers
    .Include(c => c.Orders) // Eagerly load Orders
    .ToListAsync();

// If we need to include nested relationships, we can also use ThenInclude
var customersWithOrders = await context.Customers
    .Include(c => c.Orders)
    .ThenInclude(o => o.OrderItems)
    .ThenInclude(i => i.Product);
```

If we get any errors about `A Possible object cycle was detected`, this is because we have a circular dependency which is fetching back the relationship but inside that is then linking back to our main model and repeating this loop.

To fix this, we can go into our model and apply the `[JsonIgnore]` attribute to the navigation property. We can also use a `DTO` and return the data we actually want.

```C#
[HttpGet("{id}")]
public async Task<ActionResult<CustomerDto>> GetCustomer(int id)
{
    var customer = await _context.Customers
        .Include(c => c.Orders)
        .FirstOrDefaultAsync(c => c.CustomerId == id);

    if (customer == null) return NotFound();

    var dto = new CustomerDto
    {
        CustomerId = customer.CustomerId,
        Name = customer.Name,
        Orders = customer.Orders
            .Select(o => new OrderDto
            {
                OrderId = o.OrderId,
                OrderDate = o.OrderDate
            }).ToList()
    };

    return dto;
}
```

### Value Converters

Value Converters are a very handy feature of Entity Framework Core.

They let you map between a property in your entity and a different representation in the database without changing your model.

For most scenarios we can use the built in Value Converters built into entity framework which can be found here https://learn.microsoft.com/en-us/ef/core/modeling/value-conversions?tabs=data-annotations  

```C#
builder.Property(movie => movie.ReleaseDate)
    .HasConversion<string>();
```

If we want to make our own, we can inherit from `ValueConverter` class like this

```C#
using Microsoft.EntityFrameworkCore.Storage.ValueConversion;
using System.Security.Cryptography;
using System.Text;

public class EncryptedStringConverter : ValueConverter<string, string>
{
    private static readonly byte[] Key = Encoding.UTF8.GetBytes("1234567890123456");
    private static readonly byte[] IV = Encoding.UTF8.GetBytes("abcdefghijklmnop");

    public EncryptedStringConverter()
        : base(
            v => Encrypt(v),
            v => Decrypt(v))
    {
    }

    private static string Encrypt(string plainText)
    {
        if (string.IsNullOrEmpty(plainText)) return plainText;

        using var aes = Aes.Create();
        aes.Key = Key;
        aes.IV = IV;

        using var encryptor = aes.CreateEncryptor();
        var bytes = Encoding.UTF8.GetBytes(plainText);
        var cipher = encryptor.TransformFinalBlock(bytes, 0, bytes.Length);

        return Convert.ToBase64String(cipher);
    }

    private static string Decrypt(string cipherText)
    {
        if (string.IsNullOrEmpty(cipherText)) return cipherText;

        using var aes = Aes.Create();
        aes.Key = Key;
        aes.IV = IV;

        using var decryptor = aes.CreateDecryptor();
        var bytes = Convert.FromBase64String(cipherText);
        var plain = decryptor.TransformFinalBlock(bytes, 0, bytes.Length);

        return Encoding.UTF8.GetString(plain);
    }
}
```

We can then use it like so

```C#
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;

public class CustomerConfiguration : IEntityTypeConfiguration<Customer>
{
    public void Configure(EntityTypeBuilder<Customer> builder)
    {
        builder.ToTable("Customers");

        builder.Property(c => c.SensitiveData)
               .HasConversion(new EncryptedStringConverter())
               .HasMaxLength(512);
    }
}
```

### Owned And Complex Types

Owned and complex types in Entity Framework Core are powerful patterns for value objects and aggregates. They allow you to group related properties into components inside an entity without creating separate tables (unless you want to).

An owned type is a class that:

- Has no identity of its own (no primary key).
- Is always owned by another entity.
- Gets stored in the same table by default as the owner.
- Can also be mapped to a separate table if needed.

This is ideal for Value Objects.

```C#
// Value Object
public class Address
{
    public string Street { get; set; } = string.Empty;
    public string City { get; set; } = string.Empty;
    public string Country { get; set; } = string.Empty;
}

// Entity
public class Customer
{
    public int CustomerId { get; set; }
    public string Name { get; set; } = string.Empty;

    public Address Address { get; set; } = new Address();
}

// Configuration
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;

public class CustomerConfiguration : IEntityTypeConfiguration<Customer>
{
    public void Configure(EntityTypeBuilder<Customer> builder)
    {
        builder.ToTable("Customers");
        builder.HasKey(c => c.CustomerId);

        // If we want the address in the customers table
        builder.OwnsOne(c => c.Address, address =>
        {
            address.Property(a => a.Street).HasColumnName("Street");
            address.Property(a => a.City).HasColumnName("City");
            address.Property(a => a.Country).HasColumnName("Country");
        });

        // If we want to split out the address into it's own table
        builder.OwnsOne(c => c.Address, address =>
        {
            address.ToTable("CustomerAddresses");
            address.WithOwner().HasForeignKey("CustomerId");
            address.Property(a => a.Street);
            address.Property(a => a.City);
            address.Property(a => a.Country);
        });
    }
}

// Querying the data
var customer = await context.Customers
    .Where(c => c.Address.City == "London")
    .FirstOrDefaultAsync();

```

Starting with EF Core 7, `complex types` are basically a more modern, cleaner way to define what used to be "owned entity types" but with:

- Simpler configuration (no OwnsOne required).
- More natural value object semantics.
- Reusable type definitions across multiple entities.

A complex type is similar to an owned type, but:

- It doesn't need explicit .OwnsOne configuration (you register the complex type once).
- It can be reused by multiple owners easily.
- It does not support separate-table mapping (always inline).

```C#
// Address class complex type
[ComplexType]
public class Address
{
    public string Street { get; set; } = string.Empty;
    public string City { get; set; } = string.Empty;
    public string Country { get; set; } = string.Empty;
}

// or register with fluent api
modelBuilder.ComplexType<Address>();

// Entity
public class Customer
{
    public int CustomerId { get; set; }
    public string Name { get; set; } = string.Empty;
    public Address Address { get; set; } = new Address();
}
```

### Default Values

If we want to do something like set a default value for a createdDate field, we can use the `HasDefaultValueSql` method. If we want a static string or int, we can use `HasDefaultSql`.

```C#
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;

public class OrderConfiguration : IEntityTypeConfiguration<Order>
{
    public void Configure(EntityTypeBuilder<Order> builder)
    {
        builder.ToTable("Orders");
        builder.HasKey(o => o.OrderId);

        builder.Property(o => o.CreatedAt)
               .HasDefaultValueSql("GETUTCDATE()"); // SQL Server
               
        builder.Property(o => o.Status)
               .HasDefaultValue("Pending");
    }
}
```

Sometimes, we may want to generate a value in the code and we can use Value Generators for this.

```C#
// Create our value generator
using Microsoft.EntityFrameworkCore.ChangeTracking;
using Microsoft.EntityFrameworkCore.ValueGeneration;

public class CustomerIdValueGenerator : ValueGenerator<string>
{
    public override bool GeneratesTemporaryValues => false;

    public override string Next(EntityEntry entry)
    {
        // Example: simple timestamp + random number
        return $"CUST-{DateTime.UtcNow:yyyyMMddHHmmss}-{Random.Shared.Next(1000, 9999)}";
    }
}

// Apply this in Fluent API
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;

public class Customer
{
    public string CustomerId { get; set; } = string.Empty; // key
    public string Name { get; set; } = string.Empty;
}

public class CustomerConfiguration : IEntityTypeConfiguration<Customer>
{
    public void Configure(EntityTypeBuilder<Customer> builder)
    {
        builder.HasKey(c => c.CustomerId);

        builder.Property(c => c.CustomerId)
               .HasValueGenerator<CustomerIdValueGenerator>();
    }
}
```

### Global Query Filters

Global query filters in EF Core let you define a filter that automatically applies to all queries for a given entity type. This is super useful for things like:

- Soft deletes (IsDeleted = true)
- Multi-tenancy (TenantId = currentTenantId)
- Filtering active users (IsActive = true)

```C#
using Microsoft.EntityFrameworkCore;

public class AppDbContext : DbContext
{
    public DbSet<Customer> Customers => Set<Customer>();

    protected override void OnModelCreating(ModelBuilder modelBuilder)
    {
        base.OnModelCreating(modelBuilder);

        // Global filter: only include non-deleted customers
        modelBuilder.Entity<Customer>().HasQueryFilter(c => !c.IsDeleted);
    }
}

// If we need to override this filter in our query
var allCustomers = await context.Customers
    .IgnoreQueryFilters() // bypass the global filter
    .ToListAsync();
```

### Migrations

This part is a more in depth guide to migrations than the other migrations section.

In Entity Framework Core (EF Core), migrations are a way to incrementally evolve your database schema as your application's data model changes over time.

They allow you to keep your code (model classes) and your database schema in sync and they can even generate SQL scripts to apply those schema changes automatically.

To get started, we will need to install a nuget package

```bash
dotnet add package Microsoft.EntityFrameworkCore.Tools
```

We will also need to install the Entity Framework Core Tools globally on our machine.

```bash
dotnet tool install -g dotnet-ef

# confirm it installed
dotnet-ef
```

To add a migration, we can run the following. The final argument is the name of the migration. Each time we update the models, we can run the add migrations command again to create a new migration file.  

```bash
dotnet-ef migrations add AddProductsTable

# If you make a mistake, you can roll it back
dotnet-ef migrations remove
```

This should now create a migrations folder with the database changes. It generates a set of files like this:  

```bash
Migrations/
    20251011123045_AddProductsTable.cs
    20251011123045_AddProductsTable.Designer.cs
    MyDbContextModelSnapshot.cs
```

- `20251011123045_AddProductsTable.cs` - Contains a `Up` and `Down` method which apply the changes or reverts back depending on which command is run.
- `20251011123045_AddProductsTable.Designer.cs` - This file is auto-generated and usually not edited by hand. It contains a snapshot of the model at the time of the migration, some EF Core metadata & used internally to know what changed between migrations.
- `MyDbContextModelSnapshot.cs` - This file is crucial. It represents the latest state of your model. It is updated every time you add a migration. EF Core uses it to compare your current model with the last migration and determine what changed. If you delete this file, EF Core will lose its reference point (you can regenerate it, but it's best to keep it intact).


When renaming fields or types, be careful with what the migration generates. It may drop a column and recreate it which can cause data loss in production. If you need to modify a column, you may need to modify the migration to use the `AlterColumn<>` & `RenameColumn`.  

```C#
// In the Up() method

// Change the type
migrationBuilder.AlterColumn<int>(
    name: "OldColumnName",
    table: "TestTable",
    type: "decimal(18,2)" // The type we want to change it to
    nullable: false,
    defaultValue: 0m
);

// Change the name
migrationBuilder.RenameColumn(
    name: "OldColumnName",
    table: "TestTable",
    newName: "NewColumnName"
);

// Don't forget to the the opposite in the down() method
```

If we want to make sure our application is always running the latest migrations, we can add a check into our `Program.cs` file to see if any migrations are pending.

```C#
// We don't want the context to stay running once we have finished this check
using (var scope = app.Services.CreateScope())
{
    var context = scope.ServiceProvider.GetRequiredService<AppDbContext>();
    var pendingMigrations = await context.Database.GetPendingMigrationsAsync();

    if (pendingMigrations.Count() > 0) {
        throw new Exception("There are pending migrations to the database.");
    }
}
```

To run the migrations we can use the following command

```bash
# Use the default database connection string
dotnet-ef database update

# If we want to target a database (e.g. CI/CD pipeline)
dotnet-ef database update --connection "SOME_CONNECTION_STRING_HERE"

# If we want to dump out a script to run manually or check changes
dotnet-ef migrations script > script.sql

# If we want to generate an executable to run all our migrations
dotnet-ef migrations bundle
```

### Testing Entity Framework

There are several ways of testing Entity Frameworks and how our application is working with our database.

To begin, we could use a `test database`. This is normally a replication of a production database with a limited data set. We then set a connection string to point at our context and run tests as normal. This works great because we are using the same tech stack, doesn't require mocking in our tests and testing a lot. The downsides include that we could be testing too much, handling our setup and teardown to make sure we are not leaving around a lot of data slowing down testing over time and possible table locks and concurrency if multiple users are running tests at the same time.

Another way we can run our tests is with using an `In Memory Database` instead. Two ways we can implement this is using Microsofts `In Memory DB` and `SQLite` (SQLite is the recommended version). This is useful as our tests can run a lot faster than using a test database. Usually, because we switch our database for a different engine such as SQLite, this can run into issues like missing features (like stored procedures and functions from MS-SQL), incompatible data types and any raw sql statements if they are being used as the syntax likely won't match.

An example of using an In Memory Database in a test:

We will need to add a package to our Test Project

```C#
dotnet add package Microsoft.EntityFrameworkCore.Sqlite
```

```C#
public class SqlLiteTest : IDisposible
{
    private readonly SqliteConnection _connection;

    public SqlLiteTest()
    {
        _connection = new SqliteConnection("Filename=:memory:");
        _connection.Open();

        var context = CreateInMomoryContext();

        context.Database.EnsureCreated();

        context.Genres.AddRange(
            new Genre { name = "Drama" },
            new Genre { name = "Action" },
            new Genre { name = "Comedy" },
        );

        context.SaveChanges();
    }

    public void Dispose()
    {
        _connection.Dispose();
    }

    [Fact]
    public async Task IfGenreExists_ReturnsGenre()
    {
        var context = CreateInMemoryContext();
        var controller = new GenresController(context);

        var response = await controller.Get(2);
        var okResult = response as OkObjectResult;

        Assert.NotNull(okResult);
        Assert.Equal(200, okResult.StatusCode);
        Assert.Equal("Action", (okResult.Value as Genre)?.Name);
    }

    private MoviesContext CreateInMemoryContext()
    {
        var contextOptions = new DbContextOptionsBuilder<MoviesContext>()
            .UseSqlite(_connection)
            .Options;

        var context = new MoviesContext(contextOptions);

        return context;
    }
}
```

Another way we can test is using `Fake Db Sets`. This is good for keeping logic in isolation and very fast. The downsides include a lot of mocking our DbContext, Db Sets etc. We may also be using Linq which will make the mocking even more difficult. It will also be problematic if we start using async also.

Example of using a Fake Db Set  

```C#
using Microsoft.EntityFrameworkCore;
using System.Collections;
using System.Linq.Expressions;

public class FakeDbSet<T> : DbSet<T>, IQueryable<T>, IAsyncEnumerable<T> where T : class
{
    private readonly List<T> _data;
    private readonly IQueryable<T> _query;

    public FakeDbSet()
    {
        _data = new List<T>();
        _query = _data.AsQueryable();
    }

    public override EntityEntry<T> Add(T entity)
    {
        _data.Add(entity);
        return null; // Not tracking entities here, just faking
    }

    public override EntityEntry<T> Remove(T entity)
    {
        _data.Remove(entity);
        return null;
    }

    public override EntityEntry<T> Update(T entity)
    {
        return null; // no-op for fake
    }

    public override IEnumerator<T> GetEnumerator() => _data.GetEnumerator();

    Type IQueryable.ElementType => _query.ElementType;
    Expression IQueryable.Expression => _query.Expression;
    IQueryProvider IQueryable.Provider => _query.Provider;

    public IAsyncEnumerator<T> GetAsyncEnumerator(CancellationToken cancellationToken = default)
        => new AsyncEnumeratorWrapper<T>(_data.GetEnumerator());

    private class AsyncEnumeratorWrapper<TItem> : IAsyncEnumerator<TItem>
    {
        private readonly IEnumerator<TItem> _inner;
        public AsyncEnumeratorWrapper(IEnumerator<TItem> inner) => _inner = inner;
        public TItem Current => _inner.Current;
        public ValueTask DisposeAsync() { _inner.Dispose(); return ValueTask.CompletedTask; }
        public ValueTask<bool> MoveNextAsync() => new ValueTask<bool>(_inner.MoveNext());
    }
}
```

Then we can use it like this:

```C#
using Xunit;

public class ProductServiceTests
{
    [Fact]
    public void GetAll_ReturnsAllProducts()
    {
        // Arrange
        var fakeDbSet = new FakeDbSet<Product>();
        fakeDbSet.Add(new Product { Id = 1, Name = "Keyboard" });
        fakeDbSet.Add(new Product { Id = 2, Name = "Mouse" });

        var mockContext = new Mock<AppDbContext>(new DbContextOptions<AppDbContext>());
        mockContext.Setup(c => c.Products).Returns(fakeDbSet);

        var service = new ProductService(mockContext.Object);

        // Act
        var result = service.GetAll().ToList();

        // Assert
        Assert.Equal(2, result.Count);
        Assert.Contains(result, p => p.Name == "Keyboard");
    }

    [Fact]
    public void Add_AddsProductToDbSet()
    {
        // Arrange
        var fakeDbSet = new FakeDbSet<Product>();
        var mockContext = new Mock<AppDbContext>(new DbContextOptions<AppDbContext>());
        mockContext.Setup(c => c.Products).Returns(fakeDbSet);

        var service = new ProductService(mockContext.Object);
        var product = new Product { Id = 3, Name = "Monitor" };

        // Act
        service.Add(product);

        // Assert
        Assert.Single(fakeDbSet);
        Assert.Equal("Monitor", fakeDbSet.First().Name);
    }
}
```

The last method to run tests for our database dependent logic is the `Repositories`. These classes make it easy to mock, run fast and shields Entity Framework from the logic. There is an in detail example of using this in the Clewan Architecture & DDD section.

With the database, we are likely going to be testing it more with integration tests.

If we need to connect to a test database for this, we can do something like this:

```C#
var options = new DbContextOptionsBuilder<DbContext>()
    .UseSqlServer("Data Source=localhost;Initial Catalog=TestDatabase;User Id=sa;Password=SomeStrongPassword123!;TrustServerCertificate=True;").Options;

_testContext = new DbContext(options);
```  

### Multi Tenancy

Multi-tenancy with Entity Framework Core (EF Core) typically means running one application for multiple customers ('tenants'), while ensuring their data stays isolated. There are a few architectural strategies to achieve this, and EF Core supports them all in different ways.

There are multiple approaches to multi-tenancy in EF Core:

- Single Database & Desciminator: 
    - Description: All tenants share the same DB, rows have a TenantId column.
    - Pros: Simple to manage. One schema.
    - Cons: Security depends on filters. DB can get large.
- Single Database, Separate Schemas: 
    - Description: One DB, but each tenant has its own schema.
    - Pros: Better isolation.
    - Cons: More complex migrations and management.
- Separate Databases Per Tenant: 
    - Description: Each tenant gets its own connection string/database.
    - Pros: Strong isolation. Easy to scale out.
    - Cons: Harder to manage migrations and connections.  

Example of the descriminator:

```C#
// Entity Example
public class TenantEntity
{
    public Guid Id { get; set; }
    public Guid TenantId { get; set; } 
    public string Name { get; set; }
}

// Applying a Global Query Filter
public class AppDbContext : DbContext
{
    private readonly Guid _tenantId;

    public AppDbContext(DbContextOptions<AppDbContext> options, ITenantProvider tenantProvider)
        : base(options)
    {
        _tenantId = tenantProvider.GetTenantId();
    }

    public DbSet<TenantEntity> TenantEntities { get; set; }

    protected override void OnModelCreating(ModelBuilder modelBuilder)
    {
        modelBuilder.Entity<TenantEntity>()
            .HasQueryFilter(e => e.TenantId == _tenantId); 
    }
}

// Inserting Tenant Data Automatically
public override int SaveChanges()
{
    foreach (var entry in ChangeTracker.Entries<TenantEntity>())
    {
        if (entry.State == EntityState.Added)
        {
            entry.Entity.TenantId = _tenantId;
        }
    }
    return base.SaveChanges();
}
```

Separate Schemas Per Tenant:

```C#
// EF Core allows schema mapping dynamically
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    var schema = _tenantProvider.GetSchema(); // e.g. "tenant1"
    modelBuilder.Entity<Product>().ToTable("Products", schema);
}
```

Separate Database Per Tenant:

```C#
// Dynamic connection string per tenant
public class TenantDbContextFactory
{
    private readonly ITenantProvider _tenantProvider;

    public TenantDbContextFactory(ITenantProvider tenantProvider)
    {
        _tenantProvider = tenantProvider;
    }

    public AppDbContext CreateDbContext()
    {
        var optionsBuilder = new DbContextOptionsBuilder<AppDbContext>();
        optionsBuilder.UseSqlServer(_tenantProvider.GetConnectionString());
        return new AppDbContext(optionsBuilder.Options, _tenantProvider);
    }
}
```

### Inheritence In Models

Entity Framework Core (EF Core) has built-in support for inheritance mapping, which lets you model an object-oriented class hierarchy and map it to one or more database tables.

This is super useful in scenarios like:

- Common base class with shared properties (e.g. Id, CreatedAt)
- Different derived classes representing specialized entities (e.g. Employee vs Manager)
- Polymorphic queries (context.People.ToList() returns all subclasses)

There are three primary inheritance strategies in EF Core:

- Table-per-Hierarchy (TPH) - single table, discriminator column (default in EF Core)
- Table-per-Type (TPT) - separate table per class
- Table-per-Concrete-Type (TPC) - separate table per class, no base table

Class Hierarchy Example:

```C#
public abstract class Person
{
    public int Id { get; set; }
    public string Name { get; set; }
}

public class Student : Person
{
    public string Grade { get; set; }
}

public class Teacher : Person
{
    public string Subject { get; set; }
}
```

Table-per-Hierarchy (TPH) Example:

```C#
public class SchoolContext : DbContext
{
    public DbSet<Person> People { get; set; }

    protected override void OnModelCreating(ModelBuilder modelBuilder)
    {
        modelBuilder.Entity<Person>()
            .HasDiscriminator<string>("PersonType")
            .HasValue<Student>("Student")
            .HasValue<Teacher>("Teacher");
    }
}
```

Table-per-Type (TPT) - One table per class example:

```C#
public class SchoolContext : DbContext
{
    public DbSet<Person> People { get; set; }

    protected override void OnModelCreating(ModelBuilder modelBuilder)
    {
        modelBuilder.Entity<Person>().ToTable("People");
        modelBuilder.Entity<Student>().ToTable("Students");
        modelBuilder.Entity<Teacher>().ToTable("Teachers");
    }
}
```

Table-per-Concrete-Type (TPC) Example:

```C#
public class SchoolContext : DbContext
{
    public DbSet<Person> People { get; set; }

    protected override void OnModelCreating(ModelBuilder modelBuilder)
    {
        modelBuilder.Entity<Student>().ToTable("Students");
        modelBuilder.Entity<Teacher>().ToTable("Teachers");

        modelBuilder.Entity<Person>().UseTpcMappingStrategy(); // 👈 key line
    }
}
```

All strategies let you query the base class and get derived objects automatically:

```C#
// returns Student and Teacher instances in one list
var allPeople = context.People.ToList();

// Query by derived type
var students = context.Set<Student>().ToList();

// Using LINQ filters
var onlyTeachers = context.People.OfType<Teacher>().ToList();
```  

### Compound Keys

Compound keys (also called composite primary keys) are when you use more than one property together as the primary key for an entity. This is common in scenarios like join tables in many-to-many relationships, lookup tables with natural keys and domain models where a single property isn't unique.

Example:

```C#
// Models
public class Order
{
    public int OrderId { get; set; }
    public DateTime CreatedAt { get; set; }

    public ICollection<OrderItem> Items { get; set; }
}

public class OrderItem
{
    public int OrderId { get; set; }       // Part of composite key
    public int ProductId { get; set; }     // Part of composite key

    public int Quantity { get; set; }

    public Order Order { get; set; }
}

// Configuring Composite Keys with Fluent API (required way)
public class AppDbContext : DbContext
{
    public DbSet<Order> Orders { get; set; }
    public DbSet<OrderItem> OrderItems { get; set; }

    protected override void OnModelCreating(ModelBuilder modelBuilder)
    {
        modelBuilder.Entity<OrderItem>()
            .HasKey(oi => new { oi.OrderId, oi.ProductId }); // Composite Key

        modelBuilder.Entity<OrderItem>()
            .HasOne(oi => oi.Order)
            .WithMany(o => o.Items)
            .HasForeignKey(oi => oi.OrderId);
    }
}
```

### Using Raw Queries

Entity Framework Core (EF Core) lets you run raw SQL queries when LINQ isn't flexible enough or you need specific database features.

```C#
// hard coded parameters example with sql injection protection
var products = await context.Products
    .FromSql("SELECT * FROM Products WHERE Price > 50")
    .ToListAsync();

// With parameters on a raw query
decimal minPrice = 50;
var products = await context.Products
    .FromSqlRaw("SELECT * FROM Products WHERE Price > {0}", minPrice)
    .ToListAsync();

// Using string interpolation
var products = await context.Products
    .FromSqlInterpolated($"SELECT * FROM Products WHERE Price > {minPrice}")
    .ToListAsync();

// For Non-Query Commands
int affected = await context.Database.ExecuteSqlRawAsync(
    "UPDATE Products SET Price = Price * 0.9 WHERE Category = {0}", "Electronics"
);

Console.WriteLine($"{affected} rows updated.");

```


### Keyless Entities

Keyless entities (previously called query types) are used when there's no primary key on the data source (e.g., a view, raw SQL, or denormalized table), you want to map results from a raw SQL query to a .NET class that isn't tracked like a normal entity or you want read-only data (no inserts/updates/deletes).

Say your database has a view or query like:

```sql
SELECT Category, COUNT(*) AS ProductCount
FROM Products
GROUP BY Category
```

You can map this to a class:

```C#
public class ProductCategorySummary
{
    public string Category { get; set; }
    public int ProductCount { get; set; }
}
```

Configure It in `OnModelCreating`

```C#
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    modelBuilder.Entity<ProductCategorySummary>()
        .HasNoKey();
}
```

Once configured, you can query it like a DbSet:

```C#
var summaries = await context.Set<ProductCategorySummary>()
    .FromSqlRaw("SELECT Category, COUNT(*) AS ProductCount FROM Products GROUP BY Category")
    .ToListAsync();

foreach (var s in summaries)
{
    Console.WriteLine($"{s.Category}: {s.ProductCount}");
}
```

You can map a keyless entity directly to a view:

```C#
modelBuilder.Entity<ProductCategorySummary>()
    .HasNoKey()
    .ToView("ProductCategorySummaryView");
```

An easier way of doing this also is using `context.Database.SqlQuery` and mapping the results to a model class. This is also useful if we are executing `Stored Procedures` sometimes seen in some businesses who handle all their queries using this method. 

```C#
public class SalesSummary
{
    public string Category { get; set; }
    public decimal TotalSales { get; set; }
}

public class AppDbContext : DbContext
{
    public AppDbContext(DbContextOptions<AppDbContext> options) : base(options) { }
}

// Usage
var results = await context.Database
    .SqlQuery<SalesSummary>(
        "SELECT Category, SUM(Price) AS TotalSales FROM Products GROUP BY Category"
    )
    .ToListAsync();

foreach (var item in results)
{
    Console.WriteLine($"{item.Category}: {item.TotalSales}");
}
```

### Interceptors

Interceptors in Entity Framework Core (EF Core) are a powerful feature that let you hook into EF's execution pipeline and modify or observe behavior globally.

They're great for things like:

- Logging or auditing queries
- Adding multi-tenancy filters
- Automatically setting timestamps or user info
- Blocking or modifying SQL commands before they hit the DB
- Tracing performance of queries

```C#
// Creating the interceptor
using Microsoft.EntityFrameworkCore.Diagnostics;
using System.Data.Common;

public class SqlLoggingInterceptor : DbCommandInterceptor
{
    public override InterceptionResult<DbDataReader> ReaderExecuting(
        DbCommand command,
        CommandEventData eventData,
        InterceptionResult<DbDataReader> result)
    {
        Console.WriteLine($"SQL: {command.CommandText}");
        return base.ReaderExecuting(command, eventData, result);
    }

    public override async ValueTask<InterceptionResult<DbDataReader>> ReaderExecutingAsync(
        DbCommand command,
        CommandEventData eventData,
        InterceptionResult<DbDataReader> result,
        CancellationToken cancellationToken = default)
    {
        Console.WriteLine($"SQL (async): {command.CommandText}");
        return await base.ReaderExecutingAsync(command, eventData, result, cancellationToken);
    }
}

// Registering the interceptor
public class AppDbContext : DbContext
{
    public AppDbContext(DbContextOptions<AppDbContext> options) : base(options) {}

    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        optionsBuilder
            .AddInterceptors(new SqlLoggingInterceptor()); 
    }

    public DbSet<Product> Products { get; set; }
}

// Or

builder.Services.AddDbContext<AppDbContext>(options =>
{
    options.UseSqlServer(connectionString);
    options.AddInterceptors(new SqlLoggingInterceptor());
});
```

The different interceptors include:

- `IDbCommandInterceptor` - Intercepts low-level ADO.NET commands (e.g., SELECT, INSERT, etc.). Useful for logging SQL, modifying commands, multi-tenancy filters, performance tracing.
- `IDbConnectionInterceptor` - Intercepts when EF opens and closes database connections. Useful for connection pooling diagnostics, monitoring, or enforcing policies.
- `IDbTransactionInterceptor` - Intercepts transaction lifecycle events like BEGIN, COMMIT, ROLLBACK. Useful for logging or enforcing transaction behavior.
- `ISaveChangesInterceptor` - Intercepts the SaveChanges / SaveChangesAsync process. Great for auditing, timestamps, validation, soft deletes, etc.
- `IMaterializationInterceptor` - Intercepts when EF constructs entities from database rows. Useful for post-processing objects, injecting dependencies, or caching.
- `IQueryExpressionInterceptor` - Intercepts EF LINQ query expressions before they're translated to SQL. Useful for query rewriting or injecting global filters. (advanced scenario)


### Types Of Performance Issues

Entity Framework Core (EF Core) is powerful and developer-friendly, but if used incorrectly it can easily become a performance bottleneck in real-world apps.

--- 
N+1 Query Problem:

When loading related entities, EF may issue 1 query for the parent and N separate queries for each related record, instead of one optimized join.

```C#
// Problem 
var blogs = await context.Blogs.ToListAsync(); 
foreach (var blog in blogs)
{
    var posts = blog.Posts; // triggers a query per blog!
}

// Fix
// Use Include and ThenInclude to eager load related data in one query
var blogs = await context.Blogs
    .Include(b => b.Posts)
    .ToListAsync();

// Or use projection to avoid loading unneeded entities:
var blogDtos = await context.Blogs
    .Select(b => new { b.Name, PostCount = b.Posts.Count })
    .ToListAsync();

```
--- 
Loading Too Much Data (Unfiltered Queries):

Loading entire tables or wide objects unnecessarily.

```C#
// Problem
var users = await context.Users.ToListAsync(); // thousands of rows

// Fix:
// Always filter and page:
var users = await context.Users
    .Where(u => u.IsActive)
    .Take(50)
    .ToListAsync();

// Or project to a DTO:
var userDtos = await context.Users
    .Select(u => new UserDto { u.Id, u.Name })
    .ToListAsync();
```
--- 
Inefficient Change Tracking:

EF tracks all entities by default, which adds overhead if you don't need to modify them.

```C#
// Problem
var products = await context.Products.ToListAsync(); 

// Fix
// Use No Tracking for read-only scenarios:
var products = await context.Products
    .AsNoTracking()
    .ToListAsync();
```
--- 
Inefficient Compiled Queries:

EF Core compiles your LINQ to SQL each time it's run (costly), especially in high-throughput systems.

```C#
// Problem
var orders = await context.Orders
    .Where(o => o.Status == status)
    .ToListAsync(); // repeated many times

// Fix
// Use compiled queries
private static readonly Func<AppDbContext, string, Task<List<Order>>> _ordersQuery =
    EF.CompileAsyncQuery((AppDbContext ctx, string s) =>
        ctx.Orders.Where(o => o.Status == s));

var orders = await _ordersQuery(context, "Shipped");
```
--- 
Inefficient LINQ Queries / Client Evaluation:

Some LINQ expressions can't be translated to SQL and are evaluated in memory, leading to:

- Pulling the entire table into memory
- Slow performance
- High memory usage

```C#
// Problem
var users = await context.Users
    .Where(u => MyCustomFunc(u.Name)) // can't translate
    .ToListAsync(); // client evaluation!

// Fixes:
// Keep queries translatable to SQL:
// Move non-translatable logic after fetching a minimal set of data.
// Use EF-supported functions (EF.Functions.Like, etc.).
```
--- 
Missing Indexes / Poor Database Schema:

EF Core generates queries, but performance depends on DB design:

- No indexes on foreign keys or search columns
- Poor normalization
- Large tables with no partitioning

```C#
// Fix
modelBuilder.Entity<User>()
    .HasIndex(u => u.Email);
```
--- 
Repeated Context Instantiation or Mismanagement:

- Creating and disposing DbContext too often
- Or keeping one context alive too long leading to bloated change tracker

Fixes:

- Use short-lived contexts per unit of work
- In web apps, typically one per request.
- Avoid keeping the same context for background loops or caching.
--- 
Inefficient SaveChanges (Bulk Inserts/Updates)

`SaveChanges()` sends one command per entity, which can be slow for thousands of records. The default sizing for batching is 42 records.

```C#
// Problem
foreach (var entity in bigList)
    context.Entities.Add(entity);

await context.SaveChangesAsync(); // 1000+ inserts individually

// Fix:
// Use batching Or use specialized bulk libraries (e.g. EFCore.BulkExtensions)
await context.BulkInsertAsync(bigList);

// If we want to increase the batch size we can do something like this where we initialise our database
optionsBuilder.UseSqlServer(connectionString, sqlBuilder => sqlBuilder.MaxBatchSize(100));
```
--- 
More include 

- Projection of Entire Graphs
- Lack of Caching / Repeated Queries
- Poor Transaction Management
- Too Many Interceptors / Logging Overhead

When using SQL Server, one way to help improve queries is using the tooling included. First we can connect the `Profiler` to the database and dump out some trace files. We can then feed this into the `Tuning Advisor` and do some processing on it and will tell us what kind of changes we can make to improve performance.

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

**Purpose:** Ensures your email content hasn't been altered and really came from your domain.

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

**Why it matters:** DKIM confirms that the message wasn't forged or tampered with in transit.

---

### 3. DMARC (Domain-based Message Authentication, Reporting, and Conformance)

**Purpose:** Tells recipients' mail servers what to do if SPF and/or DKIM checks fail, and provides reports.

**How it works:**
- DMARC is another **DNS TXT record**.
- It sets a policy for handling failed checks: accept, quarantine, or reject.
- It can send **daily reports** showing who's sending mail using your domain.

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
- **DKIM** → Confirms their ID matches and hasn't been altered.
- **DMARC** → Decides to let them in, send them to security, or deny entry and logs the event.

---


### Using Thread Channels To Send Emails In The Background

When we want to make our application more responsive, we can use `System.Threading.Channels` to run a process in the background and push emails to the queue to send.

An example of how to get this up and running:

```C#
using System;
using System.Net;
using System.Net.Mail;
using System.Threading;
using System.Threading.Channels;
using System.Threading.Tasks;

public record EmailMessage(string To, string Subject, string Body);

public class BackgroundEmailSender : IDisposable
{
    private readonly Channel<EmailMessage> _channel;
    private readonly CancellationTokenSource _cts;
    private readonly Task _processingTask;

    public BackgroundEmailSender()
    {
        _channel = Channel.CreateUnbounded<EmailMessage>();
        _cts = new CancellationTokenSource();
        _processingTask = Task.Run(ProcessEmailsAsync);
    }

    public async Task QueueEmailAsync(EmailMessage message)
    {
        await _channel.Writer.WriteAsync(message);
    }

    private async Task ProcessEmailsAsync()
    {
        try
        {
            await foreach (var email in _channel.Reader.ReadAllAsync(_cts.Token))
            {
                try
                {
                    using var smtp = new SmtpClient("smtp.example.com", 587)
                    {
                        Credentials = new NetworkCredential("username", "password"),
                        EnableSsl = true
                    };

                    var mail = new MailMessage("sender@example.com", email.To, email.Subject, email.Body)
                    {
                        IsBodyHtml = true
                    };

                    await smtp.SendMailAsync(mail);
                    Console.WriteLine($"Sent email to {email.To}");
                }
                catch (Exception ex)
                {
                    Console.WriteLine($"Failed to send email to {email.To}: {ex.Message}");
                }
            }
        }
        catch (OperationCanceledException)
        {
            // Normal when shutting down
        }
    }

    public void Dispose()
    {
        _cts.Cancel();
        _processingTask.Wait();
        _cts.Dispose();
    }
}

class Program
{
    static async Task Main()
    {
        using var emailSender = new BackgroundEmailSender();

        Console.WriteLine("Queueing emails...");
        await emailSender.QueueEmailAsync(new EmailMessage(
            "recipient1@example.com",
            "Test Email 1",
            "Hello from Thread Channels!"
        ));

        await emailSender.QueueEmailAsync(new EmailMessage(
            "recipient2@example.com",
            "Test Email 2",
            "This is queued and sent in the background."
        ));

        Console.WriteLine("Main thread doing other work...");
        
        // This is not required, but if you're testing in a console app, we need to keep alive the application while it processes the queue
        await Task.Delay(5000);
    }
}
```

### Example Of Keeping The SMTP Client Alive For Multiple Messages

This is an example version of how to keep the SMTP Client alive when sending multiple emails so the code doesn't keep connecting and disconnecting and slowing down each message sent.

```C#
using MailKit.Net.Smtp;
using MailKit.Security;
using MimeKit;

namespace Rockaway.WebApp.Services.Mail;

public class SmtpMailSender(
	SmtpSettings smtpSettings,
	ILogger<SmtpMailSender> logger
) : IMailSender, IDisposable {

	public async Task<string> SendAsync(MimeMessage message) {
		using var smtp = new SmtpClient();

		await smtp.ConnectAsync(smtpSettings.Host, smtpSettings.Port,
			SecureSocketOptions.StartTlsWhenAvailable);

		if (smtpSettings.Authenticate)
			await smtp.AuthenticateAsync(smtpSettings.Username, smtpSettings.Password);

		var result = await smtp.SendAsync(message);

		await smtp.DisconnectAsync(true);

		return result;
	}

	public async Task<string> SendAsync(MimeMessage message, CancellationToken token) {
		await semaphore.WaitAsync(token);

		var result = "ERROR";

		try {
			await ConnectAsync(token);

			result = await smtpClient.SendAsync(message, token);
		} catch (Exception ex) {
			logger.LogError(ex, "SendAsync");

			throw;
		} finally {
			semaphore.Release();
		}

		return result;
	}

	private readonly SmtpClient smtpClient = new();

	private static readonly TimeSpan smtpClientTimeout = TimeSpan.FromSeconds(10);

	private DateTimeOffset disconnectAfter = DateTimeOffset.MinValue;

	private readonly SemaphoreSlim semaphore = new(1, 1);

	private void ScheduleDisconnect(CancellationToken token) {
		disconnectAfter = DateTimeOffset.UtcNow.Add(smtpClientTimeout);

		Task.Run(async () => {
			await Task.Delay(smtpClientTimeout.Add(TimeSpan.FromSeconds(1)), token);

			if (DateTimeOffset.UtcNow > disconnectAfter) await DisconnectAsync(token);

		}, token);
	}

	private async Task ConnectAsync(CancellationToken token) {
		if (smtpClient.IsConnected) {
			await smtpClient.NoOpAsync(token);
		} else {
			await smtpClient.ConnectAsync(smtpSettings.Host, smtpSettings.Port,
				SecureSocketOptions.StartTlsWhenAvailable, token);

			if (smtpSettings.Authenticate)
				await smtpClient.AuthenticateAsync(smtpSettings.Username, smtpSettings.Password, token);
		}

		ScheduleDisconnect(token);
	}

	private async Task DisconnectAsync(CancellationToken token) {
		await semaphore.WaitAsync(token);

		try {
			if (!smtpClient.IsConnected) return;

			await smtpClient.DisconnectAsync(true, token);

			disconnectAfter = DateTimeOffset.MinValue;
		} catch (Exception ex) {
			logger.LogError(ex, "DisconnectAsync");

			throw;
		} finally {
			semaphore.Release();
		}
	}

	public void Dispose() {
		smtpClient.DisconnectAsync(true);

		smtpClient.Dispose();

		semaphore.Dispose();

		GC.SuppressFinalize(this);
	}
}
```

## Dotnet MAUI

Documentation - https://learn.microsoft.com/en-us/dotnet/maui/get-started/installation?view=net-maui-9.0&tabs=visual-studio

### Installing Dotnet MAUI

First we need to make sure we have the .NET SDK installed.

For MacOS:

We need to make sure we have XCode installed. This can be downloaded in the App Store.

```bash
sudo dotnet workload install maui
```

For Windows:

We will need to download Visual Studio. On the workloads screen in the installer, we need to add the .NET MAUI option.

Note: on multiple machines for me, I could not get the Android emulator to work through visual studio. If this happens, download Android Studio and set up a virtual device. Run it and Visual Studio should detect it in the device dropdown.

If we use VS Code to develop, there is a .NET MAUI extension that can be downloaded from the extensions tab.

### Setting Up A Maui Project

In our IDE, we want to create a new MAUI solution. This is similar to creating any other solution where we give it a Solution Name, Project name and where we want to keep this project.

### Community ToolKit

The community toolkit is a dotnet MAUI add on for extra features which can be dropped into your application to help build certain parts of your application faster.

More information can be found here.

https://learn.microsoft.com/en-gb/dotnet/communitytoolkit/maui/

Some of the most common ones which can be installed on NuGet through your IDE or the command line with the `dotnet package add` command

- communitytoolkit.maui
- communitytoolkit.mvvm
- communitytoolkit.maui.markup

We can now add these in our `MauiProgram.cs`

```C#
// Add these into our builder
builder
    .UseMauiCommunityToolkit()
    .UseMauiCommunityToolkitMarkup()
```

### MauiProgram.cs

This file is the entry point to our Application. it is Similar to `Program.cs` in a .NET Core application. It handles setup of libraries, dependency injection and other bits.

This line tells MAUI where to launch our Application from

```C#
builder.UseMauiApp<App>()
```

The App inside the generic points at our `App.xaml.cs` file. Inside this file, we see this line

```C#
MainPage = new AppShell();
```

If we want to change this, we can delete the old page and create a new file like `MainPage.cs` and will look like this

```C#
namespace HelloMaui;

public class MainPage : ContentPage
{

}
```

### Creating A Content Page

For this example, we will use our `MainPage.cs` file from the last section and add some text.

```C#
namespace HelloMaui;

public class MainPage : ContentPage
{
    public MainPage()
    {
        Content = new Label()
            .Text("This is a label")
            .Center()
            .TextCenter();
    }
}
```

This should now show some text in the center of the screen.

### Layouts

In .NET MAUI, layouts are containers that organize child controls (buttons, labels, etc.) on the screen. They define how elements are positioned and sized.

Main Layouts:

`StackLayout`:

- Arranges elements vertically (default) or horizontally.
- Good for simple forms and lists.

```C#
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="HelloMaui.MainPage">

    <VerticalStackLayout Spacing="12">

        <Image Source="appicon"
               WidthRequest="500"
               HeightRequest="250"
               Aspect="AspectFit" />

        <Label Text="Hello"
               TextColor="Black"
               HorizontalOptions="Center"
               HorizontalTextAlignment="Center" />

        <!-- Entry is a textarea where a user can input text -->
        <Entry Placeholder="Notes"
               PlaceholderColor="DarkGray"
               TextColor="Black" />

        <!-- Nested layout -->
        <HorizontalStackLayout Spacing="12"
                               HorizontalOptions="Center">

            <Entry Placeholder="First"
                   PlaceholderColor="DarkGray"
                   TextColor="Black" />

            <Entry Placeholder="Second"
                   PlaceholderColor="DarkGray"
                   TextColor="Black" />
        </HorizontalStackLayout>

    </VerticalStackLayout>
</ContentPage>
```  

```C#
using CommunityToolkit.Maui.Markup;

namespace HelloMaui;

public class MainPage : ContentPage
{
    public MainPage()
    {
        Content = new VerticalStackLayout()
        {
            Spacing = 12,

            Children = 
            {
                new Image()
                    .Size(500, 250)
                    .Aspect(Aspect.AspectFit)
                    .Source("appicon"),

                new Label()
                    .Text("Hello", Colors.Black)
                    .Center()
                    .TextCenter(),

                // Entry is a textarea where a user can input text
                new Entry()
                    .Placeholder("Notes", Colors.DarkGray)
                    .TextColor(Colors.Black)

                // We can also nest layouts 
                new HorizontalStackLayout()
                {
                    Spacing = 12,

                    Children =
                    {
                        new Entry()
                            .Placeholder("First", Colors.DarkGray)
                            .TextColor(Colors.Black)

                        new Entry()
                            .Placeholder("Second", Colors.DarkGray)
                            .TextColor(Colors.Black)
                    }
                }.Center();
            }
        };
    }
}
```

`Grid`:

- Organizes content in rows and columns (like an HTML table).
- Most powerful layout for complex UIs.

```C#
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="HelloMaui.MainPage"
             BackgroundColor="DarkViolet">

    <ScrollView>
        <Grid BackgroundColor="LightSteelBlue"
              RowSpacing="12"
              HorizontalOptions="Center"
              VerticalOptions="Start">

            <Grid.RowDefinitions>
                <RowDefinition Height="*" />
                <RowDefinition Height="32" />
                <RowDefinition Height="40" />
                <RowDefinition Height="500" />
            </Grid.RowDefinitions>

            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="*" />
                <ColumnDefinition Width="*" />
                <ColumnDefinition Width="*" />
            </Grid.ColumnDefinitions>

            <Image Source="dotnet_bot.png"
                   Aspect="AspectFit"
                   WidthRequest="500"
                   HeightRequest="250"
                   HorizontalOptions="Center"
                   VerticalOptions="Center"
                   Grid.Row="0"
                   Grid.ColumnSpan="3" />

            <Label Text="Hello MAUI"
                   TextColor="Black"
                   HorizontalOptions="Center"
                   HorizontalTextAlignment="Center"
                   Grid.Row="1"
                   Grid.ColumnSpan="3" />

            <Entry Placeholder="First Entry"
                   PlaceholderColor="DarkGray"
                   TextColor="Black"
                   HorizontalOptions="End"
                   Grid.Row="2"
                   Grid.Column="0" />

            <Entry Placeholder="Second Entry"
                   PlaceholderColor="DarkGray"
                   TextColor="Black"
                   HorizontalOptions="Center"
                   Grid.Row="2"
                   Grid.Column="1" />

            <Entry Placeholder="Third Entry"
                   PlaceholderColor="DarkGray"
                   TextColor="Black"
                   HorizontalOptions="Start"
                   Grid.Row="2"
                   Grid.Column="2" />

            <Label Text="LARGE TEXT"
                   LineBreakMode="WordWrap"
                   FontSize="100"
                   HorizontalOptions="Center"
                   HorizontalTextAlignment="Center"
                   Grid.Row="3"
                   Grid.ColumnSpan="3" />

        </Grid>
    </ScrollView>
</ContentPage>
```

```C#
using static CommunityToolkit.Maui.Markup.GridRowsColumns;

namespace HelloMaui;

class MainPage : BaseContentPage
{
    public MainPage()
    {
        BackgroundColor = Colors.DarkViolet;

        Content = new ScrollView
        {
            Content = new Grid
            {
                BackgroundColor = Colors.LightSteelBlue,

                RowSpacing = 12,

                RowDefinitions = Rows.Define(
                    (Row.Image, Star),
                    (Row.Label, 32),
                    (Row.Entry, 40),
                    (Row.LargeText, 500)),

                ColumnDefinitions = Columns.Define(
                    (Column.Entry1, Star),
                    (Column.Entry2, Star),
                    (Column.Entry3, Star)),

                Children =
                {
                    new Image()
                        .Center()
                        .Size(500, 250)
                        .Aspect(Aspect.AspectFit)
                        .Source("dotnet_bot.png")
                        .Row(Row.Image).ColumnSpan(All<Column>()),

                    new Label()
                        .Text("Hello MAUI", Colors.Black)
                        .Center()
                        .TextCenter()
                        .Row(Row.Label).ColumnSpan(All<Column>()),

                     new Entry()
                        .End()
                        .Placeholder("First Entry", Colors.DarkGray)
                        .TextColor(Colors.Black)
                        .Row(Row.Entry).Column(Column.Entry1),

                     new Entry()
                        .CenterHorizontal()
                        .Placeholder("Second Entry", Colors.DarkGray)
                        .TextColor(Colors.Black)
                        .Row(Row.Entry).Column(Column.Entry2),

                     new Entry()
                        .Start()
                        .Placeholder("Third Entry", Colors.DarkGray)
                        .TextColor(Colors.Black)
                        .Row(Row.Entry).Column(Column.Entry3),

                     new Label { LineBreakMode = LineBreakMode.WordWrap }
                        .Text("LARGE TEXT")
                        .TextCenter()
                        .Font(size: 100)
                        .Row(Row.LargeText).ColumnSpan(All<Column>())
                }
            }.Top().CenterHorizontal()
        };
    }

    enum Row { Image, Label, Entry, LargeText }
    enum Column { Entry1, Entry2, Entry3 }
}
```

`AbsoluteLayout`:

- Places elements at specific coordinates.
- Great for overlays or custom positioning.

```C#
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="HelloMaui.MainPage">

    <AbsoluteLayout>
        <Image 
            Source="appicon"
            Aspect="AspectFit"
            AbsoluteLayout.LayoutFlags="PositionProportional"
            AbsoluteLayout.LayoutBounds="0.5,0,500,250" />
    </AbsoluteLayout>

</ContentPage>
```

```C#
using CommunityToolkit.Maui.Markup;

namespace HelloMaui;

public class MainPage : ContentPage
{
    public MainPage()
    {
        Content = new AbsoluteLayout()
        {
            Children =
            {
                new Image()
                    .Size(500, 250)
                    .Aspect(Aspect.AspectFit)
                    .Source("appicon")
                    .LayoutFlags(AbsoluteLayoutFlags.PositionProportional)
                    .LayoutBounds(0.5, 0)
            }
        }
    }
}
```

`FlexLayout`:

- Works like CSS Flexbox.
- Items can wrap, align, and justify dynamically.

```C#
<FlexLayout Direction="Row" Wrap="Wrap" JustifyContent="SpaceBetween">
    <Button Text="1" />
    <Button Text="2" />
    <Button Text="3" />
</FlexLayout>
```

```C#
using CommunityToolkit.Maui.Markup;

namespace HelloMaui;

public class MainPage : ContentPage
{
    public MainPage()
    {
        Content = new FlexLayout
        {
            Direction = FlexDirection.Row,
            Wrap = FlexWrap.Wrap,
            JustifyContent = FlexJustify.SpaceBetween,

            Children =
            {
                new Button().Text("1"),
                new Button().Text("2"),
                new Button().Text("3")
            }
        };
    }
}
```

There is also `ContentView` which is what we discussed in the last section which is a simple container for one child and `ScrollView` which adds scrolling to the content.

### BaseContentPage & Global Page Config

This is not required but helpful when it comes to adding settings like Safe Area to iOS devices.

```C#
public abstract class BaseContentPage : ContentPage
{
    public BaseContentPage()
    {
        On<iOS>.SetUseSafeArea(true);
    }
}
```

We can now just inherit this on our pages.

### Margin & Padding

Margin is space outside a control. It pushes the control away from surrounding elements or the edges of its container.

Padding is space inside a control. It pushes the content away from the control's border.

The methods we can add are `Paddings()` and `Margins()`.

```C#
using CommunityToolkit.Maui.Markup;

namespace HelloMaui;

public class MainPage : ContentPage
{
    public MainPage()
    {
        Content = new FlexLayout
        {
            Direction = FlexDirection.Row,
            Wrap = FlexWrap.Wrap,
            JustifyContent = FlexJustify.SpaceBetween,

            Children =
            {
                new Button()
                    .Text("1")
                    .Paddings(5, 10, 5, 10),

                new Button()
                    .Text("2")
                    .Margins(5, 10, 5, 10)
            }
        };
    }
}
```

### XAML

This is going to be a few tips on what can be done in XAML

To start, if we want to use our BaseContentPage we created before, we need to decalre a namespace and then change our ContentPage tag to this

```c#
<helloMaui:BaseContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
            xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
            xmlns:helloMaui="clr-namespace:HelloMaui"
            x:Class="HelloMaui.MainPage"
>

    <AbsoluteLayout>
        <Image 
            Source="appicon"
            Aspect="AspectFit"
            AbsoluteLayout.LayoutFlags="PositionProportional"
            AbsoluteLayout.LayoutBounds="0.5,0,500,250" />
    </AbsoluteLayout>

</helloMaui:BaseContentPage>
```

### Collection Views

A CollectionView is a flexible and efficient control for displaying a list of data in .NET MAUI. It's used when you need to show scrollable lists of items (like contacts, messages, or products). It supports vertical and horizontal layouts, grid layouts, and item templates for customizing how each item looks. It is the preferred replacement for `ListView` because it's faster, more flexible, and supports modern features.

```C#
namespace HelloMaui;

public class MainPage : BaseContentPage
{
    public MainPage()
    {
        Content = new CollectionView()
        {
            Header = new Label()
                .Text("Sample Header For View")
                .Paddings(bottom: 8)
                .Font(size: 32)
                .Center()
                .TextCenter(),

            Footer = new Label()
                .Text("Sample Footer For View")
                .Paddings(left: 8)
                .Font(size: 10)
                .Center()
                .TextCenter(),

            SelectionMode = SelectionMode.Single,
            
            ItemsSource = SampleModels,

            ItemTemplate = 
        }
        .ItemsSource(SampleModels)
        .ItemTemplate(new SampleDataTemplate())
        .Invoke(collectionView => collectionView.SelectionChanged += HandleSelectionChanged)
    }

    // We are using an ObservableCollection here so when we Add or Delete
    // elements from this list it will Automatically re-render in the app.
    ObservableCollection<SampleModel> SampleModels { get; } = new()
    {
        new()
        {
            Title = "Sample Entry 1",
            Description = "Sample Description 1",
            ImageSource = "someImage.jpg"
        },
        new()
        {
            Title = "Sample Entry 2",
            Description = "Sample Description 2",
            ImageSource = "someImage.jpg"
        },
        new()
        {
            Title = "Sample Entry 2",
            Description = "Sample Description 2",
            ImageSource = "someImage.jpg"
        }
    };

    // This is called every time a user clicks on a row or if the collectionView is progrmatically changed
    async void HandleSelectionChanged(object? sender, SelectionChangedEventArgs e)
    {
        ArgumentNullException.ThrowIfNull(sender);

        var collectionView = (CollectionView) sender;

        if (e.CurrentSelection.FirstOrDefault() is LibraryModel model) {
            await Toast.Make($"{model.Title} tapped").Show();
        }

        // This removes the row highlighting which can remain stuck. This does cause
        // this method to fire again
        collectionView.SelectedItem = null;
    }
}

public class SampleModel
{
    public required string Title { get; init; }

    public required string Description { get; init; }

    public required ImageSource ImageSource { get; init; }
}

// ----
using CommunityToolkit.Maui.Markup;
using static CommunityToolkit.Maui.Markup.GridRowColumns;

public class SampleDataTemplate : DataTemplate
{
    const int imageRadius = 25;
    const int imagePadding = 8;

    public SampleDataTemplate() : base(() => CreateGridTemplate())
    {

    }

    static Grid CreateGridTemplate() => new()
    {
        RowDefinitions = Rows.Define(
            (Row.Title, 22),
            (Row.Description, 44),
            (Row.BottomPadding, 8)
        ),

        ColumnDefinitions = Columns.Define(
            (Column.Icon, (imageRadius * 2) + (imagePadding * 2)),
            (ColumnText, Star),
        ),

        RowSpacing = 4,

        Children = 
        {
            new Image()
                .Row(Row.Title)
                .RowSpan(2)
                .Column(Column.Icon)
                .Center()
                .Aspect(Aspect.AspectFit)
                .Size(imageRadius * 2)
                .Bind(Image.SourceProperty,
                    getter: (SampleModel model) => model.ImageSource,
                    mode: BindingMode.OneWay
                ),

            new Label()
                .Row(Row.Title)
                .Column(Column.Text)
                .Font(size: 18, bold: true)
                .TextTop()
                .TextStart()
                .Bind(Label.TextProperty,
                    getter: (SampleModel model) => model.Title,
                    mode: BindingMode.OneWay
                ),

            new Label()
                .Row(Row.Description)
                .Column(Column.Text)
                .Font(size: 12)
                .TextTop()
                .TextStart()
                .Bind(Label.TextProperty,
                    getter: (SampleModel model) => model.Description,
                    mode: BindingMode.OneWay
                ),
        }
    };

    enum Column { Icon, Text }
    enum Row { Title, Description, BottomPadding }
}
```

### Refresh Views

This is a very popular view you see on most (if not all) apps. When the user pulls down the page, an event is sent and a loading icon is displayed while it reloads or fetchesd new data etc.

This example is using the same code as the previous section but truncating some of the extra
bits.

```C#
namespace HelloMaui;

public class MainPage : BaseContentPage
{
    public MainPage()
    {
        Content = new RefreshView
        {
            Content = new CollectionView()
            {
                Header = new Label()
                    .Text("Sample Header For View")
                    .Paddings(bottom: 8)
                    .Font(size: 32)
                    .Center()
                    .TextCenter(),

                Footer = new Label()
                    .Text("Sample Footer For View")
                    .Paddings(left: 8)
                    .Font(size: 10)
                    .Center()
                    .TextCenter(),

                SelectionMode = SelectionMode.Single,
                
                ItemsSource = SampleModels,

                ItemTemplate = 
            }
            .ItemsSource(SampleModels)
            .ItemTemplate(new SampleDataTemplate())
            .Invoke(collectionView => collectionView.SelectionChanged += HandleSelectionChanged)
        }
        .Invoke(refreshView => refreshView.Refreshing += HandleRefreshing)
        .Margin(12, 24, 12, 0);
    }

    // ... Truncated code

    async void HandleRefreshing(object? sender, SelectionChangedEventArgs e)
    {
        ArgumentNullException.ThrowIfNull(sender);

        var refreshView = (RefreshView) sender;

        // This would normally be logic to fetch from an external API
        await task.Delay(TimeSpan.FromSeconds(2));

        // Removes the loading icon
        refreshView.IsRefreshing = false;
    }
}
```

### Colors

In .NET MAUI, colors can be used in different ways named colors, system colors, hex values, RGB/ARGB, HSL, and from resources.

```C#
// Named colors
BackgroundColor = Colors.Red;
TextColor = Colors.Blue;

// Hex Values
BackgroundColor = Color.FromArgb("#FF5733");

// RGB / ARGB
BackgroundColor = Color.FromRgb(255, 87, 51);
BackgroundColor = Color.FromRgba(255, 87, 51, 128);

// HSL (Hue, Saturation, Luminosity)
BackgroundColor = Color.FromHsla(0.05, 0.9, 0.5, 1.0); 

//System Colors (Platform-specific)
BackgroundColor = Application.Current!.Resources["WindowBackgroundColor"] as Color;

// Resource-based Colors (XAML)
// Setup
<Application.Resources>
    <Color x:Key="PrimaryColor">#512BD4</Color>
</Application.Resources>

//Usage
<Label Text="Hello MAUI" TextColor="{StaticResource PrimaryColor}" />

// Or
TextColor = (Color)Application.Current.Resources["PrimaryColor"];

```

### Resources

The Resources folder in a .NET MAUI app is a special place where you put platform-agnostic assets (images, fonts, styles, etc.). At build time, MAUI processes this folder and generates optimized resources for each platform (Android, iOS, Windows, MacCatalyst).

`Resources/Fonts/`

Place your custom fonts here (.ttf or .otf).

Register them in MauiProgram.cs:

```C#
builder.ConfigureFonts(fonts =>
{
    fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
});
```

`Resources/Images/`

All images (e.g., .png, .jpg, .svg) go here.

MAUI automatically resizes and optimizes them for each platform (different DPI/density).

`Resources/Raw/`

For raw files (like JSON, MP3, video, text) that you want copied as-is.

Access them using `FileSystem.OpenAppPackageFileAsync`.

```C#
using var stream = await FileSystem.OpenAppPackageFileAsync("sample.json");
```

`Resources/Styles/`

Contains `Styles.xaml` where you define app-wide styles, themes, and resource dictionaries.
Good place for colors, brushes, typography, and reusable UI definitions.

```xml
<Application.Resources>
    <ResourceDictionary>
        <Color x:Key="PrimaryColor">#512BD4</Color>
        <Style TargetType="Label">
            <Setter Property="TextColor" Value="{StaticResource PrimaryColor}" />
        </Style>
    </ResourceDictionary>
</Application.Resources>
```

`AppIcon` & `Splash`

These need to be `svg` format images to make it easily resizeable for MAUI.

### Styles & Theming

We can customise our component styles. This is mainly done in XAML and can find examples in the `Resources/Styles` directory. In this example, we can just make a new Component inheriting from what we want to customise and use that in our code.

```C#
// Create our customised component
class LargeFontLabel : Label
{
    public LargeFontLabel()
    {
        FontSize = 20;
    }
}

// Then just use it in our C# code
new LargeFontLabel()
    .TextTop()
    .TextStart() //...
```

Now, say we want to control our App for Light mode and Dark mode, we can use `AppThemeBinding`.

```C#
// Component example
new LargeFontLabel()
    .AppThemeColorBinding(Label.TextColorProperty, Color.Black, Color.White)

// Background example
this.AppThemeColorBinding(BackgroundColorProperty, Colors.White, Colors.Black);
```

### Behaviours

Behaviors in .NET MAUI let you attach extra functionality to controls without subclassing them.

```C#
// Implementing a previous defined behaviour
readonly SearchBar _searchBar;

new SearchBar()
    .Placeholder("Search...")
    .Behaviours(new UserStoppedTypingBehaviour()
    {
        StoppedTypingTimeThreshold = 1000,
        ShouldDismissKeyboardAutomatically = true,
        Command = new Command(() => UserStoppedTyping())
    })
    .Assign(out _searchBar)

// Method implementation
void UserStoppedTyping()
{
    // Example of getting access to the search bar we made
    var searchbarText = _searchBar.Text;

    if (string.IsNullOrWhitespace(searchbarText)) {
        // initial state
    }

    // Filter list logic
}
```

We can also create our own behaviours

```C#
// Implement a behaviour
using Microsoft.Maui.Controls;

namespace HelloMaui.Behaviors;

public class SearchDelayBehavior : Behavior<SearchBar>
{
    private CancellationTokenSource _cts;

    protected override void OnAttachedTo(SearchBar bindable)
    {
        base.OnAttachedTo(bindable);
        bindable.TextChanged += OnTextChanged;
    }

    protected override void OnDetachingFrom(SearchBar bindable)
    {
        base.OnDetachingFrom(bindable);
        bindable.TextChanged -= OnTextChanged;
    }

    private async void OnTextChanged(object sender, TextChangedEventArgs e)
    {
        _cts?.Cancel();
        _cts = new CancellationTokenSource();

        try
        {
            // Wait 500ms after last key press
            await Task.Delay(500, _cts.Token);

            var searchBar = (SearchBar)sender;

            await Application.Current.MainPage.DisplayAlert("Search Triggered", $"Searching for: {searchBar.Text}", "OK");
        }
        catch (TaskCanceledException)
        {
            // Ignore if user keeps typing
        }
    }
}


// Use our behaviour
new SearchBar
{
    Placeholder = "Type to search...",
    Behaviors = { new SearchDelayBehavior() }
};
```

### Gestures

We can control gestures and respond as expected in MAUI. The types of Gestures include

- Tap
- Pan
- Pinch
- Swipe
- Drag
- Pointer (Desktop only)

There is also a Library to extend this fnuctionality here - https://github.com/vapolia/MauiGestures

Example (Silly example but just for demonstration)

```C#
new SearchBar()
    .TapGesture(async () => {
        await Toast.Make("Double Tapped").Show();
    }, 2)
```

### Application Lifecycles

In .NET MAUI, the application lifecycle is about how your app starts, runs, pauses, resumes, and stops and it changes depending on the platform.

These can be found in any class that inherits from `Application` e.g `App.xaml.cs`

We can override the lifecycle methods and below is a few of the main ones.

```C#
protected override void OnStart()
{
    // Called when the app first starts
}

protected override void OnSleep()
{
    // Called when the app is backgrounded (e.g., user switches apps)
}

protected override void OnResume()
{
    // Called when the app comes back from background
}
```

There is also methods like `CreateWindow()` where we can make multi-window apps for desktop applications.

Each page (like `ContentPage`) also has lifecycle events called `Page Lifecycles`

```C#
protected override void OnAppearing()
{
    base.OnAppearing();
    // Runs when the page is visible
}

protected override void OnDisappearing()
{
    base.OnDisappearing();
    // Runs when the page is navigated away from
}

protected override void OnNavigatedTo()
{
    // Runs when the page is navigated to 
}

protected override void OnNavigatedFrom()
{
    // Runs when the page is navigated away from
}
```

### Shell & Navigation

.NET MAUI Shell gives you a simple way to structure navigation in your app (tabs, flyouts, hierarchical navigation) without writing all the boilerplate.

The types of Navigation we have include

- Flyout (like a side drawer)
- Tabs
- Hierarchical (stack based)

In this example, we will implement the AppShell in pure C#

```C#
namespace HelloMaui;

public class AppShell : Shell
{
    public AppShell(MainPage mainPage)
    {
        Items.Add(mainPage);
    }
}

// In our App.xaml.cs, inject our AppShell and set it to MainPage Property
public partial class App : Application
{
    public App(AppShell shell)
    {
        InitializeComponent();

        MainPage = shell; 
    }
}

// Then set up our dependency injection in MauiProgram.cs
builder.Services.AddSingleton<AppShell>();
builder.Services.AddSingleton<App>();

builder.Services.AddTransient<MainPage>();
```

To navigate from from page to another, we need to set up some routes in `AppShell.cs`

```C#
public partial class AppShell : Shell
{
    public AppShell()
    {
        InitializeComponent();
        RegisterRoutes();
    }

    private void RegisterRoutes()
    {
        RegisterRoute<MainPage>();
        RegisterRoute<DetailsPage>();
        // Add more pages as needed
    }

    private static void RegisterRoute<TPage>() where TPage : BaseContentPage
    {
        string route = typeof(TPage).Name;
        Routing.RegisterRoute(route, typeof(TPage));
    }
}
```

Then we can add something like this to a Gesture or Event Handler

```C#
// Data to pass into the route
var pageData = new Dictionary<string, object>
{
    { "TestData": modelData }
};

// Second param is optional just to pass data
await Shell.Current.GoToAsync(Routes.Details, pageData);
```

When navigating, if we do want to pass data we need to implement the `IQueryAttributable` interface and the required method.

```C#
public class DetailsPage : BaseContentPage, IQueryAttributable
{
    private readonly Label _labelText;

    public DetailsPage()
    {

    }

    // From the interface
    public void ApplyQueryAttributes(IDictionary<string, object> query)
    {
        // This gets all the data we pass. We can also cast query to the type
        // of object passed in.
        var passedData = query["TestData"];

        // We can just assign any data we need from this object and attach it to our components
        // using the Assign() passing in our _labelText
        _labelText = passedData.SomeLabelData;
    }
}
```

In our content pages, we can also modify the behaviour of the back button. Each page also has a prop caled `Title` which can be set to display a title in the bar across the top  next to the back icon or text.

```C#
// Changes the back icon to the word
Shell.SetBackButtonBehaviour(this, new() {
    TextOverride = "Back"
})
```

If we need to make a custom back button, we can do something like this

```C#
new Button()
    .Text("Back")
    .Invoke(async () => await Shell.Current.GoToAsync(".."))
```

### MVVM

`MVVM` is an acronym for `Model View View-Model`. The `View` handles the UI, the `View Model` handles the business logic and the `Model` handles the data structure.

In .NET MAUI, MVVM works by using the `INotifyPropertyChanged` interface. This updates a property name between the `View` and `View-Model` when the value changes. When a property is updated, MAUI redraws the UI using the new value. The name for this is called `Bindings`.

We use this pattern for future maintenence when our Application grows. It also helps with keeping our data loosely coupled so our view and view-model know nothing about each other and helps with separation of concerns so it is easy to replace or modify our UI or business logic in the future.

Our folder structure would normally end up something like this:

```bash
MyMauiApp/
│
├── App.xaml
├── App.xaml.cs
│
├── Models/                  # Business/domain objects
│   └── User.cs
│   └── Product.cs
│
├── ViewModels/              # ViewModels (logic & state for each page)
│   └── MainPageViewModel.cs
│   └── DetailsPageViewModel.cs
│
├── Pages/                   # Full content pages
│   └── MainPage.xaml
│   └── MainPage.xaml.cs
│   └── DetailsPage.xaml
│   └── DetailsPage.xaml.cs
│   └── AppShell.xaml
│   └── AppShell.xaml.cs
│
├── Views/                   # Reusable components (partial UI)
│   └── HeaderView.xaml
│   └── HeaderView.xaml.cs
│   └── ProductCard.xaml
│   └── ProductCard.xaml.cs
│
├── Services/                # App services (API calls, auth, persistence, etc.)
│   └── ApiService.cs
│   └── AuthService.cs
│
├── Helpers/                 # Utilities, converters, constants
│   └── BoolToVisibilityConverter.cs
│   └── SettingsHelper.cs
│
├── Resources/               # Static app resources (MAUI-specific)
│   ├── Fonts/
│   ├── Images/
│   ├── Raw/
│   ├── Styles/              # Centralised styles/themes
│   │   └── Styles.xaml
│
└── Platforms/               # Platform-specific code
    ├── Android/
    ├── iOS/
    ├── MacCatalyst/
    └── Windows/
```

This is not a concrete example of what we need to do to implement `MVVM` but it makes binding a little easier. We can create a base class for all our `View-Models` to inherit from `INotifyPropertyChanged` like this.

```C#
using System.ComponentModel;
using SystemRuntime.CompilerServices;

namespace HelloMaui.ViewModels;

public abstract class BaseViewModel : INotifyPropertyChanged
{
    public event PropertyChangedEventHandler? PropertyChanged;

    protected virtual void OnPropertyChanged([CallerMemberName] string? propertyName = null)
    {
        PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
    }

    // CallerMemberName attribute automatically calls the nameof() and handles this so we don't have to
    // write it each time.
    protected bool SetProperty<T>(ref T field, T value, [CallerMemberName] string? propertyName = null)
    {
        if (EqualityComparer<T>.Default.Equals(field, value)) {
            return false;
        }

        field = value;

        OnPropertyChanged(propertyName);

        return true;
    }
}
```

When naming our `View-Models` it is normally named the same as our View page but with ViewModel appended on the end. e.g. `HomePage` will get a View-Model called `HomeViewModel`.

```C#
using System.Windows.Input;

namespace HelloMaui.ViewModels;

public class MainPageViewModel : BaseViewModel
{
    private string _username;
    private int _count;

    public string Username
    {
        get => _username;
        set => SetProperty(ref _username, value);
    }

    public int Count
    {
        get => _count;
        set => SetProperty(ref _count, value);
    }

    public ICommand IncrementCommand { get; }

    public MainPageViewModel()
    {
        _username = "Guest";
        _count = 0;

        IncrementCommand = new Command(OnIncrement);

        // If we have an async function returning a Task, use this
        // IncrementCommand = new AsyncRelayCommand(OnIncrement);
    }

    private void OnIncrement()
    {
        Count++;
    }
}
```

We then initialise this in our View and bind the properties to our components

```C#
using CommunityToolkit.Maui.Markup;
using HelloMaui.ViewModels;
using static CommunityToolkit.Maui.Markup.GridRowsColumns;

namespace HelloMaui.Pages;

public class MainPage : ContentPage
{
    public MainPage()
    {
        // This is how we can bind to our Page Properties
        // We will just set our title to the username as an example
        this.Bind(MainPage.TitleProperty,
            getter: (MainPageViewModel vm) => vm.Username
        )

        Content = new VerticalStackLayout
        {
            Spacing = 12,
            Padding = 20,

            Children =
            {
                new Entry()
                    .Placeholder("Enter your name")
                    .Bind(Entry.TextProperty, 
                        getter: (MainPageViewModel vm) => vm.Username
                    ),

                new Label()
                    .Font(size: 20)
                    .Bind(Label.TextProperty, 
                        getter: (MainPageViewModel vm) => vm.Username
                    ),

                new Label()
                    .Font(size: 20)
                    .Bind(Label.TextProperty, 
                        getter: (MainPageViewModel vm) => vm.Count
                    ),

                new Button()
                    .Text("Increment")
                    .BindCommand(Button.CommandProperty,
                        getter: (MainPageViewModel vm) => vm.IncrementCommand
                    )
            }
        };
    }
}
```

We also have `BindingContexts` which is essentially the data source for your UI controls.

It works like this
- Your Page or Layout has a `BindingContext`.
- Any child controls inside that page automatically inherit the same `BindingContext` (unless you override it).
- When you write a binding (e.g., `Label.Text = "{Binding Username}"`), MAUI looks for a property called Username on the current `BindingContext`.

```C#
using CommunityToolkit.Maui.Markup;
using HelloMaui.ViewModels;
using static CommunityToolkit.Maui.Markup.GridRowsColumns;

namespace HelloMaui.Pages;

public class MainPage : ContentPage
{
    public MainPage()
    {
        // Tell the binding context what ViewModel we are using
        BindingContext = new MainPageViewModel();

        Content = new VerticalStackLayout
        {
            Spacing = 12,
            Padding = 20,

            Children =
            {
                new Entry()
                    .Placeholder("Enter your name")
                    .Bind(Entry.TextProperty, 
                        getter: (MainPageViewModel vm) => vm.Username,
                        setter: (MainPageViewModel vm, string value) => vm.Username = value,
                        mode: BindingMode.TwoWay //optional
                    ),

                new Label()
                    .Font(size: 20)
                    .Bind(Label.TextProperty, 
                        getter: (MainPageViewModel vm) => vm.Username
                    ),

                new Label()
                    .Font(size: 20)
                    .Bind(Label.TextProperty, 
                        getter: (MainPageViewModel vm) => vm.Count
                    ),

                new Button()
                    .Text("Increment")
                    .BindCommand(Button.CommandProperty,
                        getter: (MainPageViewModel vm) => vm.IncrementCommand
                    )
            }
        };
    }
}
```

We can update our `BaseContentPage` like this to make things a little easier also.

```C#
public abstract class BaseContentPage<TViewModel> : ContentPage
    where TViewModel : BaseViewModel
{
    public BaseContentPage(TViewModel viewModel)
    {
        On<iOS>.SetUseSafeArea(true);

        BindingContent = viewModel;
    }
}

// We then update our pages like this
public class HomePage : BaseContentPage<HomeViewModel>
{
    public HomePage(HomeViewModel viewModel) : base(viewModel)
    {
        //
    }
}
```

Don't forget to also register your ViewModels in the dependency injection container.

```C#
builder.Services.AddTransient<HomeViewModel>();
```

.NET MAUI does not set the BindingContext of a behavior, because behaviors can be shared and applied to multiple controls through styles.

To fix this we can just set the bindingCOntext in the behaviour.

```C#
.Behaviours(new UserStoppedTypingBehaviour()
{
    BindingContext = viewModel,
    // Rest of the props....
})
```

More information here - https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/behaviors?view=net-maui-9.0

### MVVM Community Toolkit

https://learn.microsoft.com/en-gb/dotnet/communitytoolkit/mvvm/

In the previous section, we went through setting up `MVVM` ourselves. There is a package called `CommunityToolkit.Mvvm` which can make our lives easier.

```bash
dotnet add package CommunityToolkit.Mvvm
```

The CommunityToolkit.Mvvm package is a huge productivity booster for MVVM in .NET MAUI. It provides source generators and attributes so you don't have to write all the boilerplate `INotifyPropertyChanged`, commands, etc. yourself.

In this library, we use Attributes to simplify the code.
- [RelayCommand]
- [ObservableProperty]
- [AlsoNotifyChangeFor]
- [AlsoNotifyCanExecuteFor]

If we are using a `BaseViewModel` class, we can easily implement the functionality by inheriting from the `ObervableObject` class.

```C#
public abstract class BaseViewModel : ObservableObject
{

}
```

Instead of writing your own BaseViewModel, you can inherit from ObservableObject and use [ObservableProperty].

(Note: in the examples, we are now using partial classes. This is required by the MVVM Community Toolkit library).

```C#
using CommunityToolkit.Mvvm.ComponentModel;

namespace HelloMaui.ViewModels;

public partial class MainPageViewModel : ObservableObject
{
    // Generates a property with change notification:
    [ObservableProperty]
    private string username;

    [ObservableProperty]
    private int counter;
}
```

Instead of writing `ICommand` manually, you can use [RelayCommand].

```C#
using CommunityToolkit.Mvvm.ComponentModel;
using CommunityToolkit.Mvvm.Input;

namespace HelloMaui.ViewModels;

public partial class MainPageViewModel : ObservableObject
{
    [ObservableProperty]
    private int counter;

    [RelayCommand]
    private void IncrementCounter()
    {
        Counter++;
    }
}
```

We can now bind like this

```C#
Content = new VerticalStackLayout
{
    Spacing = 12,
    Padding = 20,

    Children =
    {
        new Entry()
            .Placeholder("Enter your name")
            .Bind(
                Entry.TextProperty,
                getter: (MainPageViewModel vm) => vm.Username,
                setter: (MainPageViewModel vm, string value) => vm.Username = value,
                mode: BindingMode.TwoWay
            ),

        new Label()
            .Bind(
                Label.TextProperty,
                getter: (MainPageViewModel vm) => vm.Username
            ),

        new Button()
            .Text("Click Me")
            .BindCommand((MainPageViewModel vm) => vm.IncrementCounterCommand),

        new Label()
            .Bind(
                Label.TextProperty,
                getter: (MainPageViewModel vm) => vm.Counter
            )
    }
};

```

We can also use `AlsoNotifyChangeFor` to tell the source generator to change the value of another property.

```C#
using CommunityToolkit.Mvvm.ComponentModel;

namespace HelloMaui.ViewModels;

public partial class PersonViewModel : ObservableObject
{
    [ObservableProperty]
    [AlsoNotifyChangeFor(nameof(FullName))]
    private string firstName;

    [ObservableProperty]
    [AlsoNotifyChangeFor(nameof(FullName))]
    private string lastName;

    public string FullName => $"{FirstName} {LastName}";
}
```

`AlsoNotifyCanExecuteFor` tells the source generator that when a property changes, check if this command can execute. The below example does not allow the user to login until a username and password are both set.

```C#
using CommunityToolkit.Mvvm.ComponentModel;
using CommunityToolkit.Mvvm.Input;

namespace HelloMaui.ViewModels;

public partial class LoginViewModel : ObservableObject
{
    [ObservableProperty]
    [AlsoNotifyCanExecuteFor(nameof(LoginCommand))]
    private string username;

    [ObservableProperty]
    [AlsoNotifyCanExecuteFor(nameof(LoginCommand))]
    private string password;

    [RelayCommand(CanExecute = nameof(CanLogin))]
    private void Login()
    {
        // Perform login logic
    }

    private bool CanLogin()
    {
        return !string.IsNullOrWhiteSpace(Username) && 
               !string.IsNullOrWhiteSpace(Password);
    }
}
```

```C#
using CommunityToolkit.Maui.Markup;
using HelloMaui.ViewModels;

namespace HelloMaui.Pages;

public class LoginPage : ContentPage
{
    public LoginPage()
    {
        var viewModel = new LoginViewModel();
        BindingContext = viewModel;

        Content = new VerticalStackLayout
        {
            Spacing = 12,
            Padding = 20,

            Children =
            {
                new Entry()
                    .Placeholder("Username")
                    .Bind(Entry.TextProperty, 
                        getter: (LoginViewModel vm) => vm.Username
                    ),

                new Entry()
                    .Placeholder("Password")
                    .IsPassword(true)
                    .Bind(Entry.TextProperty, 
                        getter: (LoginViewModel vm) => vm.Password
                    ),

                new Button()
                    .Text("Login")
                    .BindCommand((LoginViewModel vm) => vm.LoginCommand)
            }
        };
    }
}
```

### iOS Issue

If we have an obvervable property in our view model which is updated in a loop (e.g adding new rows to a Observable List) then this can cause an OutOfRangeException to be thrown as iOS cannot write the values fast enough. We can work around this by making sure we keep everything on the main UI thread.

We can do this by injecting the `IDispatcher` through our View Model constructor and setting a field.

We then just need to change our method causing the issue to an async method with a Task return type.

```C#
public partial class ExampleFix(IDispatcher dispatcher)
{
    [ObservableProperty]
    private List<string> users;

    [RelayCommand]
    async Task UserStoppedTyping()
    {
        // Imagine having some list we are going to loop over
        foreach (var user in newUsers) {
            // Everytime we want to update our list, we use DispatchAsync
            // to keep it on the main thread
            await dispatcher.DispatchAsync(() => users.Add(user));
        }
    }
}
```

### MAUI Libraries

Some libraries to help with styling and themeing etc

Uranium UI - https://uraniumui.gh.enisn-projects.io/en/Getting-Started.html  
Reactor UI Maui - https://github.com/adospace/reactorui-maui

### Creating A Calendar View

Let's create our own calendar view. This will give us an insight in to how the MAUI architecture works from making the `UI Framework` element, implementing the `interface` layer then adding the specific `handlers` to our implementation (iOS, Android, Windows, Mac etc).

Lets start with making an interface. In this instance we are just goping to put it in our Views directory but you can place it somewhere like it's own folder in a real project. We need to inherit from `IView`.

```C#
namespace MauiApp;

public interface ICalendarView : IView
{
    DayOfWeek FirstDayOfWeek { get; }
    DateTimeOffset MinDate { get; }
    DateTimeOffset MaxDate { get; }
    DateTimeOffset? SelectedDate { get; set; }

    void OnSelectedDateChanged(DateTimeOffset? selectedDate);
}
```

Now we need to create our actual implementation. We will make a concrete class called `CalendarView` and inherit from the `View` class. This will help when we also implement the `ICalendarView` interface so we don't need to implement every method and can just implement and override any we need to change later on along with the ones we defined above.

```C#
namespace MauiApp;

public class CalendarView : View, ICalendarView
{
    // This secWtion creates our bindings to our properties
    // Take note of the name, we need it to be the same name as what we want to bind to with Property appended
    public static readonly BindableProperty FirstDayOfWeekProperty = BindableProperty.Create(
        nameof(FirstDayOfWeek), 
        returnType: typeof(DayOfWeek), 
        declaringType: typeof(CalendarView), 
        defaultValue: default(DayOfWeek)
    );
    public static readonly BindableProperty MinDateProperty = BindableProperty.Create(
        nameof(MinDate),
        returnType: typeof(DateTimeOffset), 
        declaringType: typeof(CalendarView), 
        defaultValue: DateTimeOffset.MinValue
    );
    public static readonly BindableProperty MaxDateProperty = BindableProperty.Create(
        nameof(MaxDate),
        returnType: typeof(DateTimeOffset), 
        declaringType: typeof(CalendarView), 
        defaultValue: DateTimeOffset.MaxValue
    );
    public static readonly BindableProperty SelectedDateProperty = BindableProperty.Create(
        nameof(SelectedDate),
        returnType: typeof(DateTimeOffset?), 
        declaringType: typeof(CalendarView), 
    );

    // Create an event args (class at the bottom)
    public event EventHandler<SelectedDateChangedEventArgs>? SelectedDateChanged;

    // Now we implement our properties and set the getter to get the value of the binding property above
    DayOfWeek FirstDayOfWeek 
    {
        get => (DayOfWeek)GetValue(FirstDayOfWeekProperty);
        set => SetValue(FirstDayOfWeekProperty, value);
    }

    DateTimeOffset MinDate
    {
        get => (DateTimeOffset)GetValue(MinDateProperty);
        set => SetValue(MinDateProperty, value);
    }

    DateTimeOffset MaxDate
    {
        get => (DateTimeOffset)GetValue(MaxDateProperty);
        set => SetValue(MaxDateProperty, value);
    }

    DateTimeOffset? SelectedDate
    {
        get => (DateTimeOffset?)GetValue(SelectedDateProperty);
        set => SetValue(SelectedDateProperty, value);
    }

    // Implementing the method like this hides it from people initializing the class
    // but we can still attach it to handlers later on.
    void ICalendarView.OnSelectedDateChanged(DateTimeOffset? selectedDate)
    {
        SelectedDateChanged?.Invoke(this, new SelectedDateChangedEventArgs(selectedDate));
    }
}

public class SelectedDateChangedEventArgs(DateTimeOffset? selectedDate) : EventArgs
{
    public DateTimeOffset? SelectedDate { get; } = selectedDate;
}
```

Now lets start the `handlers` by creating a base handler for our Calendar. We can put these in a Handlers directory and call it `CalendarHandler.cs`

```C#
namespace MauiApp.Handlers;

// We need to make sure this is a partial class as this is how maui uses the different 
// implementations
public partial class CalendarHandler
{
    // We need two constructors, first one to allow other devs to pass their own PropertyMappers and commandHandlers and a default one for our property and command mappers
    public CalendarHandler(IPropertyMapper mapper, CommandMapper? commandMapper = null) : base(mapper, commandMapper)
    {

    }

    public CalendarHandler() : this(PropertyMapper, CommandMapper)
    {

    }

    // This will throw errors to begin with until we implement the Map... methods
    public static PropertyMapper<ICalendarView, CalendarHandler> PropertyMapper = new PropertyMapper<ICalendarView, CalendarHandler>(ViewMapper)
    {
        [nameof(ICalendarView.FirstDayOfWeek)] = MapFirstDayOfWeek,
        [nameof(ICalendarView.MinDate)] = MapMinDate,
        [nameof(ICalendarView.MaxDate)] = MapMaxDate,
        [nameof(ICalendarView.SelectedDate)] = MapSelectedDate,
    };

    // This is for mapping commands but we don't have any
    public static CommandMapper<ICalendarView, CalendarMapper> commandMapper = new(ViewCommandMapper);
}
```

Now before we start adding our `.ios.cs` or `.android.cs` files, we need to implement a `Directory.Build.targets` file to be able to handle these different naming conventions. The file looks like this and can be saved as `Directory.Build.targets` in your project.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Project>
  <ItemGroup Condition="$(TargetFramework.StartsWith('Xamarin.iOS')) != true AND $(TargetFramework.EndsWith('-ios')) != true">
    <Compile Remove="**\**\*.ios.cs" />
    <None Include="**\**\*.ios.cs" Exclude="$(DefaultItemExcludes);$(DefaultExcludesInProjectFolder)" />
    <Compile Remove="**\ios\**\*.cs" />
    <None Include="**\ios\**\*.cs" Exclude="$(DefaultItemExcludes);$(DefaultExcludesInProjectFolder)" />
  </ItemGroup>
  <ItemGroup Condition="$(TargetFramework.StartsWith('Xamarin.Mac')) != true AND $(TargetFramework.EndsWith('-maccatalyst')) != true">
    <Compile Remove="**\*.macos.cs" />
    <None Include="**\*.macos.cs" Exclude="$(DefaultItemExcludes);$(DefaultExcludesInProjectFolder)" />
    <Compile Remove="**\macos\**\*.cs" />
    <None Include="**\macos\**\*.cs" Exclude="$(DefaultItemExcludes);$(DefaultExcludesInProjectFolder)" />
  </ItemGroup>
  <ItemGroup Condition="$(TargetFramework.StartsWith('Xamarin.Mac')) != true AND $(TargetFramework.StartsWith('Xamarin.iOS')) != true AND $(TargetFramework.EndsWith('-ios')) != true AND $(TargetFramework.EndsWith('-maccatalyst')) != true">
    <Compile Remove="**\*.macios.cs" />
    <None Include="**\*.macios.cs" Exclude="$(DefaultItemExcludes);$(DefaultExcludesInProjectFolder)" />
    <Compile Remove="**\macios\**\*.cs" />
    <None Include="**\macios\**\*.cs" Exclude="$(DefaultItemExcludes);$(DefaultExcludesInProjectFolder)" />
  </ItemGroup>
  <ItemGroup Condition="$(TargetFramework.StartsWith('MonoAndroid')) != true AND $(TargetFramework.EndsWith('-android')) != true ">
    <Compile Remove="**\**\*.android.cs" />
    <None Include="**\**\*.android.cs" Exclude="$(DefaultItemExcludes);$(DefaultExcludesInProjectFolder)" />
    <Compile Remove="**\android\**\*.cs" />
    <None Include="**\android\**\*.cs" Exclude="$(DefaultItemExcludes);$(DefaultExcludesInProjectFolder)" />
  </ItemGroup>
  <ItemGroup Condition="$(TargetFramework.Contains('-windows')) != true ">
    <Compile Remove="**\*.windows.cs" />
    <None Include="**\*.windows.cs" Exclude="$(DefaultItemExcludes);$(DefaultExcludesInProjectFolder)" />
    <Compile Remove="**\windows\**\*.cs" />
    <None Include="**\windows\**\*.cs" Exclude="$(DefaultItemExcludes);$(DefaultExcludesInProjectFolder)" />
  </ItemGroup>
  <ItemGroup Condition="$(TargetFramework.Contains('-tizen')) != true ">
    <Compile Remove="**\*.tizen.cs" />
    <None Include="**\*.tizen.cs" Exclude="$(DefaultItemExcludes);$(DefaultExcludesInProjectFolder)" />
    <Compile Remove="**\tizen\**\*.cs" />
    <None Include="**\tizen\**\*.cs" Exclude="$(DefaultItemExcludes);$(DefaultExcludesInProjectFolder)" />
  </ItemGroup> 
  <ItemGroup Condition="!($(TargetFramework.StartsWith('net')) == true AND $(TargetFramework.EndsWith('.0')) == true AND $(TargetFramework.Contains('-')) != true)"> <!-- e.g net6.0 or net8.0 -->
    <Compile Remove="**\*.net.cs" />
    <None Include="**\*.net.cs" Exclude="$(DefaultItemExcludes);$(DefaultExcludesInProjectFolder)" />
    <Compile Remove="**\net\**\*.cs" />
    <None Include="**\net\**\*.cs" Exclude="$(DefaultItemExcludes);$(DefaultExcludesInProjectFolder)" />
  </ItemGroup>
</Project>
```

Now we can start adding our Handlers. Lets start with `iOS`. Create a file called `CalendarHandler.ios.cs` in the Handlers directory. 
Note: Most of the time, we can name our file `CalendarHandler.macios.cs` and it will work for both Mac and iOS. If we get any errors then we will need to split them out into separate versions.

```C#
using Foundation;
using Microsoft.Maui.Handlers;
using Microsoft.Maui.Platform;
using ObjCRuntime;
using UIKit;

namespace MauiApp.Handlers;

public partial class CalendarHandler : ViewHandler<ICalendarView, UICalendarView>, IDisposable
{
	UICalendarSelection? _calendarSelection;
	
	~CalendarHandler()
	{
		Dispose(false);
	}

	public void Dispose()
	{
		Dispose(true);
		GC.SuppressFinalize(this);
	}
	
	protected override UICalendarView CreatePlatformView()
	{
		return new UICalendarView();
	}

	protected override void ConnectHandler(UICalendarView platformView)
	{
		base.ConnectHandler(platformView);

		_calendarSelection = new UICalendarSelectionSingleDate(new CalendarSelectionSingleDateDelegate(VirtualView));
	}
	
	protected virtual void Dispose(bool disposing)
	{
		ReleaseUnmanagedResources();
		
		if (disposing)
		{
			_calendarSelection?.Dispose();
			_calendarSelection = null;
		}
	}

	static void MapSelectedDate(CalendarHandler handler, ICalendarView virtualView)
	{
		if (handler._calendarSelection is UICalendarSelectionSingleDate calendarSelection)
		{
			MapSingleDateSelection(calendarSelection, virtualView);
		}
	}
	
	static void MapSingleDateSelection(UICalendarSelectionSingleDate calendarSelection, ICalendarView virtualView)
	{
		if (virtualView.SelectedDate is null)
		{
			calendarSelection.SetSelectedDate(null, true);
			return;
		}

		calendarSelection.SetSelectedDate(new NSDateComponents
		{
			Day = virtualView.SelectedDate.Value.Day,
			Month = virtualView.SelectedDate.Value.Month,
			Year = virtualView.SelectedDate.Value.Year
		}, true);
	}


    // Whenever the FirstDayOfWeek property changes in your MAUI control (or during initial setup), this mapper runs and:
    // Reads the .NET property (virtualView.FirstDayOfWeek).
    // Converts it to the numeric value expected by iOS.
    // Updates the native iOS calendar's FirstWeekDay so the displayed calendar starts the week on the correct day.
	static void MapFirstDayOfWeek(CalendarHandler handler, ICalendarView virtualView)
	{
		handler.PlatformView.Calendar.FirstWeekDay = (nuint)virtualView.FirstDayOfWeek;
	}
	
	static void MapMinDate(CalendarHandler handler, ICalendarView virtualView)
	{
		SetDateRange(handler, virtualView);
	}
	
	static void MapMaxDate(CalendarHandler handler, ICalendarView virtualView)
	{
		SetDateRange(handler, virtualView);
	}
	
	static void SetDateRange(CalendarHandler handler, ICalendarView virtualView)
	{
		var fromDateComponents = virtualView.MinDate.Date.ToNSDate();
		var toDateComponents = virtualView.MaxDate.Date.ToNSDate();

		var calendarViewDateRange = new NSDateInterval(fromDateComponents, toDateComponents);
		handler.PlatformView.AvailableDateRange = calendarViewDateRange;
	}

	void ReleaseUnmanagedResources()
	{
		// Release unmanaged resources here
	}
	
	sealed class CalendarSelectionSingleDateDelegate(ICalendarView calendarView) : IUICalendarSelectionSingleDateDelegate
	{
		public NativeHandle Handle { get; }
		
		public void Dispose()
		{
			
		}

		public void DidSelectDate(UICalendarSelectionSingleDate calendarSelection, NSDateComponents? date)
		{
			calendarSelection.SelectedDate = date;
			calendarView.SelectedDate = date?.Date.ToDateTime();
			calendarView.OnSelectedDateChanged(date?.Date.ToDateTime());
		}
	}
}
```

After this, we can now implement the Android Handler. Create a new file called `CalendarHandler.android.cs`.

```C#
using Microsoft.Maui.Handlers;
using Calendar = Android.Widget.CalendarView;

namespace MauiApp.Handlers;

public partial class CalendarHandler : ViewHandler<ICalendarView, Calendar>
{
	protected override Calendar CreatePlatformView()
	{
		return new Calendar(Context);
	}

	protected override void ConnectHandler(Calendar platformView)
	{
		base.ConnectHandler(platformView);
		platformView.DateChange += HandleDateChanged;
	}

	protected override void DisconnectHandler(Calendar platformView)
	{
		base.DisconnectHandler(platformView);
		platformView.DateChange -= HandleDateChanged;
	}

	static void MapFirstDayOfWeek(CalendarHandler handler, ICalendarView virtualView)
	{
		handler.PlatformView.FirstDayOfWeek = (int)virtualView.FirstDayOfWeek;
	}
	
	static void MapMinDate(CalendarHandler handler, ICalendarView virtualView)
	{
		handler.PlatformView.MinDate = virtualView.MinDate.ToUnixTimeMilliseconds();
	}

	static void MapMaxDate(CalendarHandler handler, ICalendarView virtualView)
	{
		handler.PlatformView.MaxDate = virtualView.MaxDate.ToUnixTimeMilliseconds();
	}
	
	static void MapSelectedDate(CalendarHandler handler, ICalendarView virtualView)
	{
		if (virtualView.SelectedDate is null)
		{
			return;
		}

		handler.PlatformView.SetDate(virtualView.SelectedDate.Value.ToUnixTimeMilliseconds(), true, true);
	}
	
	void HandleDateChanged(object? sender, Calendar.DateChangeEventArgs e)
	{
		PlatformView.DateChange -= HandleDateChanged;
		
		VirtualView.SelectedDate = new DateTime(e.Year, e.Month + 1, e.DayOfMonth, 0, 0, 0);
		VirtualView.OnSelectedDateChanged(VirtualView.SelectedDate);
		
		PlatformView.DateChange += HandleDateChanged;
	}
}
```

We can also add another for windows. Add another file called `CalendarHandler.windows.cs`.

```C#
using Microsoft.Maui.Handlers;
using Microsoft.UI.Xaml.Controls;
using Windows.Globalization;
using Calendar = Microsoft.UI.Xaml.Controls.CalendarView;

namespace MauiApp.Handlers;

public partial class CalendarHandler : ViewHandler<ICalendarView, Calendar>
{
	protected override Calendar CreatePlatformView()
	{
		return new Calendar();
	}
	
	protected override void ConnectHandler(Calendar platformView)
	{
		base.ConnectHandler(platformView);
		platformView.SelectedDatesChanged += SelectedDatesChanged;
	}
	
	protected override void DisconnectHandler(Calendar platformView)
	{
		platformView.SelectedDatesChanged -= SelectedDatesChanged;
		base.DisconnectHandler(platformView);
	}
	
	static void MapFirstDayOfWeek(CalendarHandler handler, ICalendarView virtualView)
	{
		handler.PlatformView.FirstDayOfWeek = (DayOfWeek)virtualView.FirstDayOfWeek;
	}
	
	static void MapMinDate(CalendarHandler handler, ICalendarView virtualView)
	{
		handler.PlatformView.MinDate = virtualView.MinDate;
	}
	
	static void MapMaxDate(CalendarHandler handler, ICalendarView virtualView)
	{
		handler.PlatformView.MaxDate = virtualView.MaxDate;
	}
	
	static void MapSelectedDate(CalendarHandler handler, ICalendarView virtualView)
	{
		handler.PlatformView.SelectedDates.Clear();
		if (virtualView.SelectedDate is not null)
		{
			handler.PlatformView.SelectedDates.Add(virtualView.SelectedDate.Value);
			handler.PlatformView.SetDisplayDate(virtualView.SelectedDate.Value);
		}
	}
	
	void SelectedDatesChanged(Calendar sender, CalendarViewSelectedDatesChangedEventArgs args)
	{
		PlatformView.SelectedDatesChanged -= SelectedDatesChanged;
		
		if (args.AddedDates.Count == 0)
		{
			VirtualView.SelectedDate = null;
		}

		if (args.AddedDates.Count > 0)
		{
			VirtualView.SelectedDate = args.AddedDates[0];
		}

		VirtualView.OnSelectedDateChanged(VirtualView.SelectedDate);
		
		PlatformView.SelectedDatesChanged += SelectedDatesChanged;
	}
}
```

now we have added all our `Handlers`, we now need to connect them to DotNet Maui. We need to go into our `MauiProgram.cs` and configure maui handlers by adding this.

```C#
// Usually add this under UseMauiApp()
builder.ConfigureMauiHandlers(handlers => {
    handlers.AddHandler<CalendarView, CalendarHandler>();
})
```

### Memory Management

Memory management is important in any long-running app, but it's especially critical for .NET MAUI because MAUI apps run on mobile devices and desktops where resources are limited. Phones and tablets have less RAM than a typical server, and the OS will aggressively kill an app that grows too large or leaks memory. More allocations and frequent garbage collections (GC) mean more CPU cycles and power use. MAUI apps host a .NET runtime while also using native iOS/Android/Windows/macOS UI objects. Both managed and native memory must stay in sync.

There are two types of memory referred to in Dotnet Maui and Mobile Development. We have `Managed Memory` and `Native/Unmanaged Memory`.

Managed memory is handled by the .NET GC. It automatically reclaims unreachable objects, so you don't call free() or delete.

Native memory (platform controls, images, file handles, etc.) is not collected by the GC until the managed wrapper is disposed and the finalizer runs.

If you keep references alive (e.g., static fields, event handlers, closures) the GC can't collect them, leading to managed leaks.

If you forget to call `Dispose()` on things like `Stream`, `ImageSource`, or `Handler` objects, the underlying native resources stay allocated.

When it comes to memory leaks in MAUI applications, these tend to be the most common ones:

- Forgetting to unsubscribe from events. Can be prevented using `WeakEventManager`
- Circular References e.g Referencing a parent view from a child view.
- Forgetting to `Dispose`. `IDisposible` & `IAsyncDisposable` type classes.
- Incorrectly scoping anonymous/lambda methods. This causes every variable in an anonymous method to be kept alive.


The `WeakEventManager` in .NET MAUI is a handy way to avoid "event subscription leaks."
It wraps an event so that the subscriber is held by a weak reference.
Because the publisher does not hold a strong reference, the GC can collect the subscriber when it's no longer used, even if you never manually unsubscribe.

```C#
// Example of a strong reference which causes a memory leak
public partial class LeakPage : ContentPage
{
    public LeakPage()
    {
        InitializeComponent();
        SomeService.SomeEvent += OnSomeEvent;   // <- strong reference
    }

    void OnSomeEvent(object sender, EventArgs e)
    {
        // ...
    }
}

// Using weak event manager on the publisher
// Service or view model that raises the event
public class SomeService
{
    readonly WeakEventManager _eventManager = new();

    public event EventHandler SomeEvent
    {
        add    => _eventManager.AddEventHandler(value);
        remove => _eventManager.RemoveEventHandler(value);
    }

    public void Trigger() => _eventManager.HandleEvent(this, EventArgs.Empty, nameof(SomeEvent));
}


// Subscribing from the Page
public partial class SafePage : ContentPage
{
    public SafePage()
    {
        InitializeComponent();

        // Normal += syntax works, but it goes through the WeakEventManager internally
        SomeServiceInstance.SomeEvent += OnSomeEvent;
    }

    void OnSomeEvent(object sender, EventArgs e)
    {
        // Handle event
    }
}
```

Another isseu we may come across is the anonymous lambda methods accessing long living classes which will cause memory leaks. The most simple way of preventing this is to mark our anonymous lambdas as static.

```C#
// Example code using the static keyword with a lambda. 
// Now we cannot reference classes outside the method.
// We can still do crazy things like subscribing to events etc but we should avoid this.

new SearchBar()
    .Bind(SearchBar.TextProperty,
        getter: static (ListViewModel vm) => vm.SearchBarText,
        // ...
    )
```


### Connecting To Backend Services

A .NET MAUI app is usually the front-end of a larger system. Connecting it to backend services lets you retrieve and update shared data e.g., user profiles, orders, chat messages, or sensor readings stored in a central database. We can also enforce business logic such as complex rules, validation, and workflows which can run on secure servers instead of on every device. We can also syncronise across devices and leverage Authentication, Payments, Push Notifications etc.

Some good libraries to help with this:
- Refit.HttpClientFactory (Helps with handling JSON encoding and decoding) - https://www.nuget.org/packages/refit.httpclientfactory
- Microsoft.Extensions.Http.Resilience (Handles network failures) - https://www.nuget.org/packages/Microsoft.Extensions.Http.Resilience


When using `Refit.HttpClientFactory`, the best structure layout is to place our API logic in a services directory. We can then call these methods from our ViewModels. (There is some good example code on the nuget link above about setting it up).

`Microsoft.Extensions.Http.Resilience` is very simple to implement if we are using `Refit.HttpClientFactory`. It is a library which retries calling your backend when the first attempt fails and tries again depending on what settings we pass it.

```C#
// Make a separate class for the options to pass into AddStandardResilienceHandler
internal sealed class MobileHttpRetryStrategyOptions : HttpRetryStrategyOptions
{
    public MobileHttpRetryStrategyOptions()
    {
        BackoffType = DelayBackoffType.Exponential;
        MaxRetryAttempts = 3;
        UseJitter = true;
        Delay = TimeSpan.FromSeconds(2);
    }
}

builder.Services.AddRefitClient<IApiData>()
    .ConfigureHttpClient(client => client.BaseAddress = new Uri("https://fakeurlserver.com"))
    .AddStandardResilienceHandler(options => options.Retry = new MobileHttpRetryStrategyOptions());
```


### Local Storage

A MAUI app often needs to persist small bits of data such as user settings, tokens, flags, or the last screen a user visited. For simple key/value data, `Preferences` (exposed through the `IPreferences` interface) are the easiest option as is it cross platform and is sandboxed to the application which survives restarts.

We can begin by adding `IPreferences` as a singleton in our `MauiProgram.cs`

```C#
builder.services.AddSingleton<IPreferences>(Preferences.Default);
```

We can then make a Preference in our servies layer.

```C#
namespace MauiApp.Services;

public class WelcomePreferences(IPreferences preferences)
{
    public bool IsFirstRun
    {
        get => preferences.Get(nameof(IsFirstRun), true);
        set => preferences.Set(nameof(IsFirstRun), value);
    }
}
```

We then add `WelcomePreferences` to our Dependency Injection container and inject it into the page we wish to use it.

We can access it like any other Property in C#.

```C#
// welcomePreferences being an instance of our injected service
if (welcomePreferences.IsFirstRun) {
    // Show some agree terms or something...

    // Set the value to false so this code doesn't show again
    welcomePreferences.IsFirstRun = false;
}
```

### SqLite

We may want to use a local database to store data instead of having everything hosted in the cloud. For this we can use SqLite. To get started, we can install a couple of packages.

Links: 
- https://www.nuget.org/packages/sqlite-net-pcl/
- https://www.nuget.org/packages/SQLitePCLRaw.bundle_green


```bash
dotnet add package sqlite-net-pcl
dotnet add package SQLitePCLRaw.bundle_green
```

Next, we can make a `Database` directory and create an abstract class called `BaseDatabase`.

```C#
namespace MauiApp.Database;

abstract class BaseDatabase
{
    private readonly Lazy<SQLiteAsyncConnection> _sqliteDatabaseHolder;

    protected BaseDatabase(IFileSystem fileSystem)
    {
        var databasePath = Path.Combine(fileSystem.AppDataDirectory, "Database.db3");

        _sqliteDatabaseHolder = new(() => new SQLiteAsyncConnection(databasePath, SQLiteOpenFlags.Create | SQLiteOpenFlags.ReadWrite | SQLiteOpenFlags.SharedCache ));
    }

    SQLiteAsyncConnection DatabaseConnection => _sqliteDatabaseHolder.Value;

    protected async Task<TReturn> Execute<TReturn, TDatabase>(Func<SQLiteAsyncConnection, Task<TReturn>> action, CancellationToken token, int maxRetries = 10)
	{
		var databaseConnection = await GetDatabaseConnection<TDatabase>().ConfigureAwait(false);

		var resiliencePipeline = new ResiliencePipelineBuilder<TReturn>()
			.AddRetry(new RetryStrategyOptions<TReturn>
			{
				MaxRetryAttempts = maxRetries,
				Delay = TimeSpan.FromMilliseconds(2),
				BackoffType = DelayBackoffType.Exponential
			}).Build();

		return await resiliencePipeline.ExecuteAsync(async _ => await action(databaseConnection), token);
	}

    private async ValueTask<SQLiteAsyncConnection> GetDatabaseConnection<T>()
    {
        if (DatabaseConnection.TableMappings.All(static x => x.MappedType == typeof(T))) {
            await DatabaseConnection.EnableWriteAheadLoggingAsync().ConfigureAwait(false);
            await DatabaseConnection.CreateTableAsync(typeof(T)).ConfigureAwait(false);
        }

        return DatabaseConnetion;
    }

}

// Add the IFileSystem to the dependency injection container in MauiProgram.cs
builder.Services.AddSingleton<IFileSystem>(FileSystem.Current);
```

We can then implement it with something like this:

```C#
namespace MauiApp.Database;

class LibraryModelDatabase(IFileSystem fileSystem) : BaseDatabase(fileSystem)
{
	public Task<List<LibraryModel>> GetLibraries(CancellationToken token) => 
		Execute<List<LibraryModel>, LibraryModel>(databaseConnection => databaseConnection.Table<LibraryModel>().ToListAsync(), token);

	public Task InsertAllLibraries(IEnumerable<LibraryModel> libraryModels, CancellationToken token) =>
		Execute<int, LibraryModel>(databaseConnection => databaseConnection.InsertAllAsync(libraryModels), token);
}
```

### GraphQL

GraphQL is a query language for APIs and a runtime for executing those queries on your server.
Instead of having many REST endpoints, you expose a single endpoint that lets the client ask exactly for the data it needs. No more, no less.

GraphQL is also self documenting. Most tools will provide a docs section of what data is available. Any data with a `!` is non nullable. All GraphQL url's are `POST` requests.

When using a tool like Postman, we can set the query or mutation in the body section as raw json.

Example of schema on the server side:

```graphql
type Book {
  id: ID!
  title: String!
  author: Author!
}

type Author {
  id: ID!
  name: String!
}

type Query {
  book(id: ID!): Book
  books: [Book]
}
```

Example of a query to fetch data

```graphql
query GetBook {
  book(id: "1") {
    title
    author {
      name
    }
  }
}
```

In GraphQL, a `mutation` is how the client requests to change data (create, update, delete).
It looks like a query but is defined under a Mutation root type.

Extending the schema on the server:

```graphql
type Mutation {
  addBook(title: String!, authorId: ID!): Book
}
```

Updating the data through a mutation:

```graphql
mutation AddBook {
  addBook(title: "The Silmarillion", authorId: "2") {
    id
    title
    author {
      name
    }
  }
}
```

### GraphQL in MAUI

To get started with GraphQL in Dotnet MAUI, we need to install the folowing package.

StrawberryShake.Maui - https://www.nuget.org/packages/StrawberryShake.Maui/   

```bash
dotnet add package StrawberryShake.Maui
```

We can then follow the docs here - https://chillicream.com/docs/strawberryshake/v15/get-started/console  

Once it is set up, we should have some new files appear in our Maui app.

- `.graphqlrc.json` - Settings file for StrawberryShake
- `schema.graphql` - The schema from our GraphQL backend.
- `schema.extentions.graphql` - Additional information about the schema.

Now we can make our GraphQL file like `GraphQL/GetBook.graphql`:

```graphql
query GetBook($id: ID!) {
  book(id: $id) {
    id
    title
    author {
      name
    }
  }
}
```

We now just need to run the following in our terminal 

```bash
dotnet graphql generate
```  

We then need to register this in our `MauiProgram.cs`

```c#
builder.Services
    .AddBookClient()
    .ConfigureHttpClient(static client => client.BaseAddress = new Uri("https://your-graphql-endpoint.com/graphql"));

// If we want to add resilience 
builder.Services
    .AddBookClient()
    .ConfigureHttpClient(
        static client => client.BaseAddress = new Uri("https://your-graphql-endpoint.com/graphql"),
        static builder => builder.AddStandardResilienceHandler(options => options.Retry = new MobileHttpRetryStrategyOptions())
    );
```

We can now use our GraphQL endpoint like this:

```C#
using StrawberryShake;
using System.Threading.Tasks;

public interface IBookService
{
    Task<BookDto?> GetBookAsync(string id);
}

public class BookService : IBookService
{
    private readonly IGetBookClient _client;

    public BookService(IGetBookClient client)
    {
        _client = client;
    }

    public async Task<BookDto?> GetBookAsync(string id)
    {
        var result = await _client.GetBook.ExecuteAsync(id).ConfigureAwait(false);

        result.EnsureNoErrors();

        if (!result.IsSuccessResult() || result.Data?.Book is null)
            return null;

        // Map generated GraphQL type to your own DTO
        var book = result.Data.Book;

        return new BookDto(
            book.Id,
            book.Title,
            book.Author.Name
        );
    }

    public async IAsyncEnumerable<BookDto> GetAllBooksAsync(
        [EnumeratorCancellation] CancellationToken cancellationToken = default)
    {
        var result = await _client.GetBooks.ExecuteAsync(cancellationToken).ConfigureAwait(false);

        if (!result.IsSuccessResult() || result.Data?.Books is null)
            yield break;

        foreach (var book in result.Data.Books)
        {
            yield return new BookDto(
                book.Id,
                book.Title,
                book.Author.Name);
        }
    }
}

// Simple data transfer object for the app's domain
public record BookDto(string Id, string Title, string AuthorName);
```

Don't forget to register this service in your dependency injection container.

In the example of getting all the books, we need to use an await foreach like this:

```C#
public class BooksViewModel
{
    private readonly IBookService _bookService;

    public BooksViewModel(IBookService bookService)
    {
        _bookService = bookService;
    }

    public async Task LoadBooksAsync()
    {
        await foreach (var book in _bookService.GetAllBooksAsync().ConfigureAwait(false))
        {
            Console.WriteLine($"{book.Title} by {book.AuthorName}");
        }
    }
}
```

### Cross Platform Services

one of the big benefits of .NET MAUI Essentials is that it gives you a set of cross-platform APIs (services) that abstract away platform differences, so you write code once and it runs on Android, iOS, macOS, and Windows.

Sometimes we need to add additional code to access some of these so check the docs to make sure they are implemented correctly.

Here's a rundown of the most commonly used ones:

Device & App Info:

- DeviceInfo - device model, manufacturer, OS version, idiom (phone, tablet, desktop).
- AppInfo - app name, package identifier, version, build number, open app settings.
- VersionTracking - track app version/first run, check if upgraded/downgraded.

Connectivity & Communication:

- Connectivity - check internet/network access type.
- NetworkAccess / ConnectionProfiles - details about Wi-Fi, cellular, etc.
- Browser - open system browser or in-app web view.
- PhoneDialer - start a phone call.
- Sms - compose and send SMS.
- Email - compose and send email.

Storage & Preferences:

- Preferences / IPreferences - simple key/value storage for settings.
- SecureStorage - encrypted storage for sensitive data (tokens, passwords).
- FileSystem - access app cache/data folders.
- Launcher - open another app or file with default handler.
- Clipboard - copy/paste text.

Sensors & Device Features:

- Geolocation - get current location (lat/lon).
- Geocoding - convert addresses <-> coordinates.
- Map - open maps at a location.
- Accelerometer - detect acceleration (tilt, shake).
- Compass - get magnetic heading.
- Gyroscope - detect device rotation.
- Magnetometer - raw magnetic field values.
- OrientationSensor - 3D orientation of device.
- Barometer - air pressure.
- Battery - charge level, state, and power source.
- Flashlight - toggle torch on/off.
- Vibration - vibrate the device.
- HapticFeedback - trigger platform haptics.

UI & Display: 

- MainThread - ensure code runs on UI thread.
- DeviceDisplay - screen metrics, keep screen awake.
- Screenshot - capture a screenshot.
- Share - share text/files to other apps.
- TextToSpeech - speak text with system TTS engine.
- SpeechRecognizer (preview/3rd party) - convert speech to text.

Security & Permissions:

- Permissions - request/check runtime permissions (location, camera, etc.).
- SecureStorage - mentioned above, secure key/value store.

Miscellaneous:

- Dispatcher / IDispatcher - scheduling work on UI/background thread.
- Launcher - launch URIs or apps.
- Connectivity - check online/offline state.

Example usage:

```C#
// Get device info
var model = DeviceInfo.Model;
var version = DeviceInfo.VersionString;

// Save and read a preference
Preferences.Set("theme", "dark");
var theme = Preferences.Get("theme", "light");

// Get location
var location = await Geolocation.GetLastKnownLocationAsync();

// Copy to clipboard
await Clipboard.SetTextAsync("Hello MAUI!");

// Open browser
await Browser.OpenAsync("https://dotnet.microsoft.com");
```

### Unit Testing In Maui

Unit testing is pretty similar to how we do it in most Dotnet projects. The unit tests will mainly cover logic in our `ViewModels` and Services.

After creating a new unit test project, you may have an issue trying to reference the Maui application in the testing project. This is because by default, there is no `net9.0;` target framework set up in our Maui's .csproj file. We can open this file and add it to our `<TargetFrameworks>` tag, separating each one with a semi colon.

If we have made any of our own `Handlers` which target different frameworks which normally look like `MyFeature.ios.cs` then we will get build errors when adding the target framework above. We will also need to create an implementation under the name `MyFeature.net.cs`. We can then add any methods like `createPlatformView()` and throw a `NotSupportedException()`. This will only happen if we have a condition inside our `Directory.Build.targets` file mentioned in the Creating A Calendar View section.

If we get any issues about the program not containing a static Main method, we can add a `Program.net.cs` file and add the standard Main method to it.

```C#
namespace MauiApp;

public class Program
{
    public static void Main(string[] args)
    {

    }
}
```

A good place to start when setting up our unit tests is creating a `BaseTest` abstract class which all our tests will inherit from.

A basic starting example using NUnit:

```C#
namespace MauiApp.UnitTests.Tests;

abstract class BaseTest
{
    [TearDown]
    public virtual Task TearDown()
    {
        return Task.CompletedTask;
    }

    [SetUp]
    public virtual Task SetUp()
    {
        return Task.CompletedTask;
    }
}
```

This is an example of mocking the `IPreferences` which stores data locally through Key/Value pairs. We can implement the interface into our mock then use a dictionary to set, get, clear etc.

```C#
using Newtonsoft.Json;

namespace MauiApp.UnitTests.Mocks;

class MockPreferences : IPreferences
{
	readonly Dictionary<string, string> _dictionary = new();
	
	public bool ContainsKey(string key, string? sharedName = null)
	{
		return _dictionary.ContainsKey(key);
	}

	public void Remove(string key, string? sharedName = null)
	{
		_dictionary.Remove(key);
	}

	public void Clear(string? sharedName = null)
	{
		_dictionary.Clear();
	}

	public void Set<T>(string key, T value, string? sharedName = null)
	{
		var serializedValue = JsonConvert.SerializeObject(value);
		
		if (ContainsKey(key))
		{
			_dictionary[key] = serializedValue;
		}
		else
		{
			_dictionary.Add(key, serializedValue);	
		}
	}

	public T Get<T>(string key, T defaultValue, string? sharedName = null)
	{
		if (ContainsKey(key))
		{
			var serializedValue = _dictionary[key];
			return JsonConvert.DeserializeObject<T>(serializedValue) ?? throw new InvalidOperationException("Key does not exist");
		}

		return defaultValue;
	}
}
```

We can also create our own `ServiceCollection` to have dependency injection in our testing project.

```C#
using MauiApp.Database;
using MauiApp.Services;
using MauiApp.UnitTests.Mocks;

namespace MauiApp.UnitTests;

class Services
{
	static readonly Lazy<IServiceProvider> _serviceProviderHolder = new(CreateCollection);

	public static IServiceProvider Provider => _serviceProviderHolder.Value;
	
	static IServiceProvider CreateCollection()
	{
		var container = new ServiceCollection();
		
		// Services
		container.AddSingleton<IPreferences, MockPreferences>();
		container.AddSingleton<MauiGraphQLService>();
		
		// ViewModels
		container.AddTransient<ListViewModel>();

		return container.BuildServiceProvider();
	}
}
```

When we now need to implement something, we can initialize it like this in our test.

```C#
var preferences = Services.Provider.GetRequiredService<IPreferences>();
```


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


## Unit Testing

To setup, right click the solution and Add -> New Project

Select the test suite to use. Recommend XUnit as it's cross platform. It was also built by the same people who made NUnit but wuilt with the knowledge learnt from that library.

When naming the project, a standard way is to call it your `ProjectName.Tests.Unit`.

When naming the class, a good way of naming these is `ClassTest`.

When naming each test, a good way of naming these is following method name -> should -> when approach. E.g. `Add_ShouldAddTwoNumbers_WhenTwoNumbersAreIntegers()`

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

### Test Class Lifecycle

xUnit's design goal is test isolation. Each new instance is created per test method. This means the constructor and any initialised variables are run before every test. This means we do not need a `Setup` and `TearDown` method like in most testing suites such as NUnit.

For each discovered test method:

- Create the test class instance.
- Run the constructor.
- Run any async initializers if using `IAsyncLifetime.InitializeAsync()`.
- Invoke the test method (await if async).
- Call `Dispose` or `IAsyncLifetime.DisposeAsync()` if implemented.
- Dispose the instance.

This happens independently for every test method.

Because we don't have the Setup and Teardown methods, we can use the Constructor and Dispose methods.

```C#
// Normal example
public class ExampleTests : IDisposable
{
    private readonly ITestOutputHelper _outputHelper;

    // Example of Setup in xUnit
    public ExampleTests(ITestOutputHelper outputHelper)
    {
        _outputHelper = outputHelper;
        _outputHelper.WriteLine("Hello from the constructor");
    }

    // Example of teardown in xUnit
    public void Dispose()
    {
        _outputHelper.WriteLine("Hello from the dispose method");
    }
}

// Async example
public class ExampleTests : IAsyncLifetime
{
    private readonly ITestOutputHelper _outputHelper;

    
    public ExampleTests(ITestOutputHelper outputHelper)
    {
        _outputHelper = outputHelper;
    }

    public async Task InitializeAsync()
    {
        _outputHelper.WriteLine("Hello from the initialize method");
    }

    
    public async Task DisposeAsync()
    {
        _outputHelper.WriteLine("Hello from the dispose method");
    }
}
```

### Parameterization

`Parameterization` in xUnit lets you run the same test method multiple times with different input values. This is great for avoiding copy-paste tests. it works by using the `[Theory]` attribute instead of `[Fact]`. We then provide the data with attributes like `[InlineData]`, `[MemberData]`, or `[ClassData]`. xUnit creates a new instance of the test class for each data row and runs the method with those parameters.

```C#
using Xunit;

public class MathTests
{
    [Theory]
    [InlineData(2, 4)]
    [InlineData(3, 9)]
    [InlineData(4, 16)]
    public void Squares_ShouldReturnExpectedResult(int input, int expected)
    {
        int result = input * input;

        Assert.Equal(expected, result);
    }
}
```  


### Exposing Internals To Tests

If you need to test internal based classes, methods or properties then we can change the csproj file to make internals visible to our test project. Open the projects `.csproj` file and add the following.

```xml
<ItemGroup>
    <InternalsVisibleTo Include="TestingProject.Tests.Unit">
</ItemGroup>
```

### Fakes

When we are using interfaces and need to fake a class being injected into a Service class etc, we can create a fake instance of a class implementing the interface we need to inject with and then return any expected output. This only works when we need to fake small bits of code and doesn't scale well so you would usually use Mocking.

We can make a fake User Repository instance something like this

```C#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using UnderstandingDependencies.Api.Models;
using UnderstandingDependencies.Api.Repositories;

namespace UnderstandingDependencies.Api.Tests.Unit;

public class FakeUserRepository : IUserRepository
{
    public Task<IEnumerable<User>> GetAllAsync()
    {
        return Task.FromResult(Enumerable.Empty<User>());
    }
}

public class FakeUserRepositoryWithUsers : IUserRepository
{
    public Task<IEnumerable<User>> GetAllAsync()
    {
        return Task.FromResult<IEnumerable<User>>(new []
        {
            new User
            {
                Id = Guid.NewGuid(),
                FullName = "Test User"
            }
        });
    }
}
```

We can now use these classes like this

```C#
using System;
using System.Threading.Tasks;
using FluentAssertions;
using NSubstitute;
using UnderstandingDependencies.Api.Models;
using UnderstandingDependencies.Api.Repositories;
using UnderstandingDependencies.Api.Services;
using Xunit;

namespace UnderstandingDependencies.Api.Tests.Unit;

public class UserServiceTests
{
    private readonly UserService _sut;
    private readonly FakeUserRepository _userRepository = new();

    public UserServiceTests()
    {
        _sut = new UserService(_userRepository);
    }

    [Fact]
    public async Task GetAllAsync_ShouldReturnEmptyList_WhenNoUsersExist()
    {
        // Arrange
        _userRepository.GetAllAsync().Returns(Array.Empty<User>());

        // Act
        var users = await _sut.GetAllAsync();

        // Assert
        users.Should().BeEmpty();
    }
}
```

### Mocking

Mocking is a testing technique used to isolate the code under test by replacing its real dependencies with lightweight, controllable stand-ins. In C# unit tests, this is common when your class depends on external services such as databases, HTTP calls, file I/O, that you don't want to hit during a fast, repeatable test run.

two libraries we can use are `Moq` and `NSubstitute`.  

Example using a User Repository

```C#
public interface IUserRepository
{
    Task<User> GetUserAsync(int id);
}

public class UserService
{
    private readonly IUserRepository _repository;
    public UserService(IUserRepository repository) => _repository = repository;

    public async Task<string> GetUserNameAsync(int id)
    {
        var user = await _repository.GetUserAsync(id);
        return user?.Name ?? "Unknown";
    }
}

public record User(int Id, string Name);
```

Now we can mock this and test what we need to in the service.

```C#
using System.Threading.Tasks;
using NSubstitute;
using Xunit;

public class UserServiceTests
{
    [Fact]
    public async Task GetUserNameAsync_ReturnsName_WhenUserExists()
    {
        // Arrange: create a substitute for the repository
        var repo = Substitute.For<IUserRepository>();

        // Configure the fake's behavior
        repo.GetUserAsync(42).Returns(new User(42, "Alice"));

        var service = new UserService(repo);

        // Act
        var result = await service.GetUserNameAsync(42);

        // Assert: check the return value
        Assert.Equal("Alice", result);

        // Verify the method was called exactly once with argument 42
        await repo.Received(1).GetUserAsync(42);
    }

    [Fact]
    public async Task GetUserNameAsync_ReturnsUnknown_WhenUserMissing()
    {
        var repo = Substitute.For<IUserRepository>();
        // No setup means it returns default (null) for User

        var service = new UserService(repo);

        var result = await service.GetUserNameAsync(99);

        Assert.Equal("Unknown", result);
        await repo.Received(1).GetUserAsync(99);
    }
}
```

### Testing Static And Extension Methods

Sometimes, we may want to cover testing certain functionality like logging, but may use extension or static implementations. This makes it very hard to test. One way we can get around this is using the adapter pattern.

Let's say we are using the `ILogger`. Lets make an interface and adapter and use them in a test instead.

```C#
namespace Users.Api.Logging;

public interface ILoggerAdapter<TType>
{
    void LogInformation(string? message, params object?[] args);

    void LogError(Exception? exception, string? message, params object?[] args);
}
```

```C#
namespace Users.Api.Logging;

public class LoggerAdapter<TType> : ILoggerAdapter<TType>
{
    private readonly ILogger<TType> _logger;

    public LoggerAdapter(ILogger<TType> logger)
    {
        _logger = logger;
    }

    public void LogInformation(string? message, params object?[] args)
    {
        _logger.LogInformation(message, args);
    }

    public void LogError(Exception? exception, string? message, params object?[] args)
    {
        _logger.LogError(exception, message, args);
    }
}
```

Now we can test it using our adapter class instead

```C#
using System;
using System.Linq;
using System.Threading.Tasks;
using Castle.Core.Logging;
using FluentAssertions;
using Microsoft.Data.Sqlite;
using Microsoft.Extensions.Logging;
using NSubstitute;
using NSubstitute.ExceptionExtensions;
using NSubstitute.ReturnsExtensions;
using Users.Api.Logging;
using Users.Api.Models;
using Users.Api.Repositories;
using Users.Api.Services;
using Xunit;

namespace Users.Api.Tests.Unit;

public class UserServiceTests
{
    private readonly UserService _sut;
    private readonly IUserRepository _userRepository = Substitute.For<IUserRepository>();
    private readonly ILoggerAdapter<UserService> _logger = Substitute.For<ILoggerAdapter<UserService>>();

    public UserServiceTests()
    {
        _sut = new UserService(_userRepository, _logger);
    }

    [Fact]
    public async Task GetAllAsync_ShouldLogMessages_WhenInvoked()
    {
        // Arrange
        _userRepository.GetAllAsync().Returns(Enumerable.Empty<User>());

        // Act
        await _sut.GetAllAsync();

        // Assert
        _logger.Received(1).LogInformation(Arg.Is("Retrieving all users"));
        _logger.Received(1).LogInformation(Arg.Is("All users retrieved in {0}ms"), Arg.Any<long>());
    }

    [Fact]
    public async Task GetAllAsync_ShouldLogMessageAndException_WhenExceptionIsThrown()
    {
        // Arrange
        var sqliteException = new SqliteException("Something went wrong", 500);
        _userRepository.GetAllAsync()
            .Throws(sqliteException);

        // Act
        var requestAction = async () => await _sut.GetAllAsync();

        // Assert
        await requestAction.Should()
            .ThrowAsync<SqliteException>().WithMessage("Something went wrong");
        _logger.Received(1).LogError(Arg.Is(sqliteException), Arg.Is("Something went wrong while retrieving all users"));
    }

    [Fact]
    public async Task GetByIdAsync_ShouldLogMessages_WhenInvoked()
    {
        // Arrange
        var userId = Guid.NewGuid();
        _userRepository.GetByIdAsync(userId).ReturnsNull();

        // Act
        await _sut.GetByIdAsync(userId);

        // Assert
        _logger.Received(1).LogInformation(Arg.Is("Retrieving user with id: {0}"),
            Arg.Is(userId));
        _logger.Received(1).LogInformation(Arg.Is("User with id {0} retrieved in {1}ms"),
            Arg.Is(userId), Arg.Any<long>());
    }

    [Fact]
    public async Task GetByIdAsync_ShouldLogMessageAndException_WhenExceptionIsThrown()
    {
        // Arrange
        var userId = Guid.NewGuid();
        var sqliteException = new SqliteException("Something went wrong", 500);
        _userRepository.GetByIdAsync(userId)
            .Throws(sqliteException);

        // Act
        var requestAction = async () => await _sut.GetByIdAsync(userId);

        // Assert
        await requestAction.Should()
            .ThrowAsync<SqliteException>().WithMessage("Something went wrong");
        _logger.Received(1).LogError(Arg.Is(sqliteException),
            Arg.Is("Something went wrong while retrieving user with id {0}"),
            Arg.Is(userId));
    }
}
```

### Class Fixtures

Fixtures let you share setup and cleanup code across multiple tests in the same class. Instead of re-creating expensive resources (e.g., a database connection, HTTP client, service) for every test, you build them once and reuse them. In unit tests, ther could be a scenario where you have a service that depends on some expensive setup (like configuration or a fake in-memory database). Instead of setting that up for every test, you put it in a fixture.

First we need to make a fixture class

```C#
using System;

public class CalculatorFixture : IDisposable
{
    public Calculator Calculator { get; private set; }

    public CalculatorFixture()
    {
        // Setup: runs ONCE for the whole test class
        Calculator = new Calculator();
        Console.WriteLine("Calculator created!");
    }

    public void Dispose()
    {
        // Cleanup: runs ONCE after all tests finish
        Console.WriteLine("Calculator disposed!");
    }
}
```

We now implement this using the `IClassFixture` interface using our fixture as the type in the generic then injecting it through our constructor.

```C#
using Xunit;

public class CalculatorTests : IClassFixture<CalculatorFixture>
{
    private readonly CalculatorFixture _fixture;

    public CalculatorTests(CalculatorFixture fixture)
    {
        _fixture = fixture; // shared across all tests
    }

    [Fact]
    public void Add_WorksCorrectly()
    {
        var result = _fixture.Calculator.Add(2, 3);
        Assert.Equal(5, result);
    }

    [Fact]
    public void Multiply_WorksCorrectly()
    {
        var result = _fixture.Calculator.Multiply(4, 5);
        Assert.Equal(20, result);
    }
}
```

### Collection Fixtures

Collection fixtures are the next step up from class fixtures. They let you share the same fixture across multiple test classes.

First lets make the fixture (will pretend to use a database in this example).

```C#
using System;

public class DatabaseFixture : IDisposable
{
    public string ConnectionString { get; private set; }

    public DatabaseFixture()
    {
        ConnectionString = "Server=localhost;Database=TestDb;User=sa;Password=Pass@word1;";
        Console.WriteLine("Database initialized!");
    }

    public void Dispose()
    {
        Console.WriteLine("Database cleaned up!");
    }
}
```

We now make a collection implementing the `ICollectionFixture` interface

```C#
using Xunit;

[CollectionDefinition("Database collection")]
public class DatabaseCollection : ICollectionFixture<DatabaseFixture>
{
    // This class has no code.
    // Its purpose is simply to be the anchor for the [CollectionDefinition].
}
```

We can now apply `[Collection("Name")]` to any test classes that need the shared fixture.

```C#
using Xunit;

[Collection("Database collection")]
public class UserRepositoryTests
{
    private readonly DatabaseFixture _fixture;

    public UserRepositoryTests(DatabaseFixture fixture)
    {
        _fixture = fixture;
    }

    [Fact]
    public void CanUseDatabaseConnection()
    {
        Assert.Contains("Database=TestDb", _fixture.ConnectionString);
    }
}
```

### Parallelization

By default, tests run in Parallel but grouped by Class collections. For most scenarios this is fine.

This is not recommended but if you want every single test to run at the same time in evry class then you can create a new file like `TestParallelism.cs` and add the following to change the behaviour.

```C#
using Xunit;

[assembly: CollectionBehaviour(CollectionBehaviour.CollectionPerAssembly)]
```

Another setting which may be more useful is disabling tests running in Parallel. If you need to enable this, it could be a sign you are doing something wrong in your tests.

```C#
using Xunit;

[assembly: CollectionBehaviour(DisableTestParallelization = true)]
```

We can also change the amount of threads which can run tests.

```C#
using Xunit;

[assembly: CollectionBehaviour(MaxParallelThreads = 24)]
```

### Advanced Parameterization

When we wanted to pass multiple data sets into our tests earlier, we used the `[Theory]` attribute then passed in our data through `[InlineData]`. We can also use member parameterization to make this easier if the data sets get too big.

We can either use a static object or a method to pass the data into our tests. We can pick either one but this example shows how to use both.

```C#
using System.Collections.Generic;
using Xunit;

public class CalculatorTests
{
    private readonly Calculator _calculator = new Calculator();

    // Static property that returns IEnumerable<object[]>
    public static IEnumerable<object[]> AddTestData =>
        new List<object[]>
        {
            new object[] { 1, 2, 3 },
            new object[] { -1, -1, -2 },
            new object[] { 100, 200, 300 }
        };

    // Static method that returns IEnumerable<object[]>
    public static IEnumerable<object[]> GetAddTestData()
    {
        yield return new object[] { 2, 3, 5 };
        yield return new object[] { -5, 5, 0 };
    }

    [Theory]
    [MemberData(nameof(AddTestData))]  // using property
    [MemberData(nameof(GetAddTestData))] // using method
    public void Add_WorksCorrectly(int a, int b, int expected)
    {
        var result = _calculator.Add(a, b);
        Assert.Equal(expected, result);
    }
}

```

If the test data gets very large, we can use Class Parameterization.

Lets make our Test Parameterization class.

```C#
using System.Collections;
using System.Collections.Generic;

// Must implement IEnumerable<object[]>
public class MultiplyTestData : IEnumerable<object[]>
{
    public IEnumerator<object[]> GetEnumerator()
    {
        yield return new object[] { 2, 3, 6 };
        yield return new object[] { -1, 5, -5 };
        yield return new object[] { 0, 10, 0 };
        yield return new object[] { 7, 7, 49 };
    }

    IEnumerator IEnumerable.GetEnumerator() => GetEnumerator();
}
```

We can now implement it like this

```C#
using Xunit;

public class CalculatorTests
{
    private readonly Calculator _calculator = new Calculator();

    [Theory]
    [ClassData(typeof(MultiplyTestData))]
    public void Multiply_WorksCorrectly(int a, int b, int expected)
    {
        var result = _calculator.Multiply(a, b);
        Assert.Equal(expected, result);
    }
}
```

### Testing DateTime

Unit testing methods that call `DateTime.Now` (or `DateTime.UtcNow`) can be tricky because they introduce non-determinism. Every time you run the test, the current time is different, so your tests become unreliable.

Lets take this example. We cannot test it because two of the conditions will always fail depending what time the tests are run through the day.

```C#
public class GreetingService
{
    public string GetGreeting()
    {
        var hour = DateTime.Now.Hour;
        if (hour < 12) return "Good morning!";
        if (hour < 18) return "Good afternoon!";
        return "Good evening!";
    }
}
```

To fix this, lets abstract the DateTime Provider.

```C#
// Make an interface
public interface IDateTimeProvider
{
    DateTime Now { get; }
}

// Implement it into an instance
public class SystemDateTimeProvider : IDateTimeProvider
{
    public DateTime Now => DateTime.Now;
}

// Use this in our service code
public class GreetingService
{
    private readonly IDateTimeProvider _dateTimeProvider;

    public GreetingService(IDateTimeProvider dateTimeProvider)
    {
        _dateTimeProvider = dateTimeProvider;
    }

    public string GetGreeting()
    {
        var hour = _dateTimeProvider.Now.Hour;
        if (hour < 12) return "Good morning!";
        if (hour < 18) return "Good afternoon!";
        return "Good evening!";
    }
}
```

We can now write a test and use a `Mock` to generate the hours.

```C#
using Xunit;
using NSubstitute;

public class GreetingServiceTests
{
    [Theory]
    [InlineData(9, "Good morning!")]
    [InlineData(15, "Good afternoon!")]
    [InlineData(20, "Good evening!")]
    public void GetGreeting_ReturnsExpectedGreeting(int hour, string expected)
    {
        // Arrange: substitute a fake time provider
        var fakeDateTime = Substitute.For<IDateTimeProvider>();
        fakeDateTime.Now.Returns(new DateTime(2025, 1, 1, hour, 0, 0));

        var service = new GreetingService(fakeDateTime);

        // Act
        var result = service.GetGreeting();

        // Assert
        Assert.Equal(expected, result);
    }
}
```

### Code Coverage

When testing in our IDE we may want to see how much of our code is covered by the tests we have been writing. For JetBrains Rider, this is built in by default. For Visual Studio, this is in the paid version.

If we want, we can also use a third party dependency to generate code coverage reports in case the want to implement checks into our CI/CD pipeline called `coverlet.console`.

First lets begin by installing the package.

```bash
dotnet tool install -g coverlet.console
```

We then build the project using `dotnet build` and get the name of the Test .dll that was generated.

We then run coverlet with the path to that dll file.

```bash
coverlet ./bin/Debug/net9.0/Users.Api.Tests.Unit.dll --target "dotnet" --targetargs "test --no-build"
```

Now if we have certain parts of code we don't wanrt to include in our code coverage e.g Repositories in unit tests we can add an attribute to our classes.

```C#
[ExcludeFromCodeCoverage]
public class UserRepository : IUserRepository
{
    //
}
```

Putting attributes on all our classes can be tedious. With coverlet, we can add the exclude argument to our command instead adding namespaces we don't want to cover.

```bash
coverlet ./bin/Debug/net9.0/Users.Api.Tests.Unit.dll --target "dotnet" --targetargs "test --no-build" --exclude "[*]Users.Api.Repositories*"
```

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

- Ardalis.SmartEnum - https://github.com/ardalis/SmartEnum

