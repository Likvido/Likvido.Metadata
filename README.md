# Likvido.Metadata

[![NuGet](https://img.shields.io/nuget/v/Likvido.Metadata.svg)](https://www.nuget.org/packages/Likvido.Metadata)

A lightweight library providing application metadata for Likvido robots and web applications.

## Overview

This library contains the `AppMetadata` class, which provides a simple way to access application information throughout your application via dependency injection.

## Usage

The `AppMetadata` class currently contains:
- `AppName`: The name of the application

### Example

```csharp
// Register in your DI container
services.AddSingleton(new AppMetadata { AppName = "MyApp" });

// Inject anywhere in your application
public class MyService
{
    private readonly AppMetadata _appMetadata;

    public MyService(AppMetadata appMetadata)
    {
        _appMetadata = appMetadata;
    }

    public void DoWork()
    {
        Console.WriteLine($"Running in: {_appMetadata.AppName}");
    }
}
```

## Installation

```bash
dotnet add package Likvido.Metadata
```