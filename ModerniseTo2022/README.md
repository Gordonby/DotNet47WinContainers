# Modernising to Windows Server 2022

## Step 1 - Getting the app running

Before modernising starts, it's best to see the app running and working properly.

### Compilation Error

If you find you receive a compilation error then it can be resolved with 
'Could not find file ... bin\roslyn\csc.exe' [duplicate]

```powershell
Update-Package Microsoft.CodeDom.Providers.DotNetCompilerPlatform -r
```

### Running the app

![working legacy app](legacyAppScreenshot.png)

## Step 2 - Publishing to an Azure VM

## Step 3 - Connecting to SQL

## Step 4 - Modernising to Windows Containers

## Step 5 - Deploying to Azure App Service

## Step 6 - Deploying to Azure Kubernetes Service
