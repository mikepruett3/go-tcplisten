# go-tcplisten: A simple TCP Listener written in go

This simple program was created to be used as a system service. The service starts and listens on a specified TCP port number, and echos back any raw data sent.

Designed as a tiny executable to be used as a service monitor with VMware NSX Load Balancers

## Configuration

No configuration required. Build to be executed from either **command line** or **crontab** (or **Services** for Windows).

```bash
> ./go-tcplisten 1234
```

```powershell
> .\go-tcplisten 1234
```

Where **1234** is the TCP Port number you want the service to listen to.

### Windows Service

Add to Services using the following...

```batch
sc create "GoLang TCP Listener" binpath="c:\go-tcplisten\go-tcplisten.exe 1234" type=own start=auto
```

## Testing

To test the application, run the following

```bash
go run *.go
```

## Building

When ready to compile, run the following

```bash
go build
```

The resulting executable & config.yml file can be placed in your system or user path.

## References

- Using the [Type Listener](https://golang.org/pkg/net/#example_Listener) Example from the [Package net](https://golang.org/pkg/net/) Documentation

- Using [service](https://github.com/kardianos/service) go package, by [kardianos](https://github.com/kardianos)

- Following steps from [How to create a windows service by using sc.exe](https://support.microsoft.com/en-us/help/251192/how-to-create-a-windows-service-by-using-sc-exe)