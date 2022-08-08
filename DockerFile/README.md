# Extending the DockerFile

Visual Studio provides an easy Dockerfile for simple applications.

## Installing Software

Where possible you'll always want to add software installations to your applications Dockerfile. It keeps all of the dependencies together and won't mean maintaining your own container image that has all of the software dependencicies installed.

### The Azure  CLI

If we take the Azure CLI as a typical example. It uses an msi to install the application, but it can be launched silently by passing the correct arguements.

Silent installs are necessary.

```powershell
$ProgressPreference = 'SilentlyContinue'; Invoke-WebRequest -Uri https://aka.ms/installazurecliwindows -OutFile .\AzureCLI.msi; Start-Process msiexec.exe -Wait -ArgumentList '/I AzureCLI.msi /quiet'; rm .\AzureCLI.msi
```

## Configuration

