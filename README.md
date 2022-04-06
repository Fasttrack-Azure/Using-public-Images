## Initial Users
The database creation logic above will create the following users:
* rr@acme.com / `l00neyTunes!`
* wile@acme.com / `l00neyTunes!`
* kim@mars.com / `to1nfinity!`
* stanley@mars.com / `to1nfinity!`

## Setup Notes
* [SQL Server Express](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)

## Preparing Your Workstation for Containers
* [Docker Desktop](https://www.docker.com/products/docker-desktop)
* [Install and Configure Windows Terminal](https://gist.github.com/dahlsailrunner/ec99e195b2a4903748a74df64a1f1a94)
* [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

## Pull Smtp4Dev image from Docker Hub
```
docker pull rnwood/smtp4dev
```

## Run Smtp4Dev container locally
```
docker run --rm -it -p 3000:80 -p 2525:25 rnwood/smtp4dev
```


## Clone the Globomantics source code in Visual Studio IDE
```
https://github.com/Fasttrack-Azure/Using-public-Images.git
```

## Ensure the correct SMTP port number on localhost
```
"Email": {
    "SmtpServer": "localhost",
    "SmtpPort": 2525,
    "SenderAddress": "donotreply@globomantics.com"
  }
```

## Run and test the application 
* Set all projects to run on startup
* https://localhost:44320/


## Pull Seq image from Docker Hub
```
docker pull datalust/seq
```

## Run Seq container locally
```
docker run --name seq -d --restart unless-stopped -e ACCEPT_EULA=Y -p 5341:80 datalust/seq:latest
```

## Update the program.cs files in all projects of the solution as below
```
{
    loggerConfiguration
        .ReadFrom.Configuration(context.Configuration)
        .Enrich.FromLogContext()
        .WriteTo.Console()
        .WriteTo.Seq("http://localhost:5341"); ;
})
```
## Run and test the application to visualize logs
* Navigate to "Weather" to trigger an API call
* http://localhost:5341/#/events 
