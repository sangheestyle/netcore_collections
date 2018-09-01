# Newbie's practice: Logging and Configuration

## Remarks

### Environment

* `ASPNETCORE_ENVIRONMENT` is used for environment varialble for ASP.net core. It is convention. Instead of that, I use similar one because it is console app.
* [`??`](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/operators/null-coalescing-operator) operator can be used for default env variable.

### Configuration

* A file can be a placeholder for [Configuration](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/configuration/?view=aspnetcore-2.1).
* `appsettings.json` is just conventional setting name on .net core.
* Section can be selected by `Configuration.GetSection("SectionName")`.

### ServiceCollection and serviceProvider

* .net core provides default dependency injection container. So, we can utilize it.
* In this session, we can't say it is useful but just stick to it for next session.
* [Dependency injection in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1) should be useful resource.

### Logging

* `ServiceCollection` helps us to add logging.
* Lambda expressions for logging builder can be used.
* Please check `LogLevel` on `appsettings.Development.json`.
* You can create logger from loggerFactory.
* In `CreateLogger<Program>()`, `Program` is category name. Usually class name is used.
* Understanding [log level](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/logging/?view=aspnetcore-2.1#log-level) is important.
* Without `((IDisposable) serviceProvider)?.Dispose();`, you can't see output at this moment. Please check [here](https://github.com/aspnet/Logging/issues/631).

## Reference

* https://andrewlock.net/creating-a-rolling-file-logging-provider-for-asp-net-core-2-0/
* https://andrewlock.net/using-dependency-injection-in-a-net-core-console-application/