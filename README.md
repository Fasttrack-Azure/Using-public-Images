# Using-public-Images

### Pull the public image for Smtp4Dev from Docker Hub
```sh
docker pull rnwood/smtp4dev
```
Refer: https://hub.docker.com/r/rnwood/smtp4dev


### How to run smtp4dev in Docker
Docker images for both Windows and Linux are available. To run with the web interface on port 3000 and SMTP on port 2525:

```
docker run --rm -it -p 3000:80 -p 2525:25 rnwood/smtp4dev
```
Remove `--rm -it` if you want to leave smtp4dev running in the backg




#### Clone the source code for Globomantics project and open the solution in your Visual Studio IDE
Verify the SQL connection strings in appsettings.json files for all projects in the solution
```
Ensure the correct port number on localhost:
"Email": {
    "SmtpServer": "localhost",
    "SmtpPort": 2525,
    "SenderAddress": "donotreply@globomantics.com"
  }
  ```
  
Set all projects to run on startup
Navigate to https://localhost:44320/




#### Navigate to Sign-in -> Forgot Password
The database creation logic above will create the following users:
* rr@acme.com / `l00neyTunes!`
* wile@acme.com / `l00neyTunes!`
* kim@mars.com / `to1nfinity!`
* stanley@mars.com / `to1nfinity!`




#### Pull the public image for Seq from Docker Hub
```sh
docker pull datalust/seq
```
Refer: https://hub.docker.com/r/datalust/seq/




#### How to run Seq in Docker
Run an initially-unsecured Seq instance with container-local storage and all services on port 5341:

```
docker run --name seq -d --restart unless-stopped -e ACCEPT_EULA=Y -p 5341:80 datalust/seq:latest
```
Refer: https://hub.docker.com/r/datalust/seq/



#### Write application logs to Seq for all projects in the solution
```
{
  loggerConfig
      .ReadFrom.Configuration(ctx.Configuration) // minimum levels defined per project in json files 
      .Enrich.FromLogContext()
      .WriteTo.Console()
      .WriteTo.Seq("http://localhost:5341");
})
```


#### Use the application and visualize logs
```
http://localhost:5341/#/events
```

