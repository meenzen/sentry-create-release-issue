# SentryCreateRelease Issue Reproduction

See https://github.com/getsentry/sentry-dotnet/issues/3536

## Reproduction Steps

Run the following command:

```bash
dotnet build -c Release Bazinga.ConsoleApp -p:SentryProject=foo
```

Output:

```
  Getting Sentry Release...
  Sentry Release: Bazinga.ConsoleApp@2.2.0.0
  Creating Sentry Release: Bazinga.ConsoleApp@2.2.0.0
```

Remove the `Microsoft.Identity.Web` package from the project, then run the command again. Output:

```
  Getting Sentry Release...
  Sentry Release: Bazinga.ConsoleApp@2.2.0-alpha.0+2828578da4
  Creating Sentry Release: Bazinga.ConsoleApp@2.2.0-alpha.0+2828578da4
```


