# axal-dotnet-static

This is the public available release of the binary distributables for the Axal .NET static analysis tool. To start, download the binary corresponding to your given operating system:

#### Windows
```
axal-csharp-static-win64.exe
```

#### Linux
```
axal-csharp-static-linux
```

#### MacOS
```
axal-csharp-static-macos
```

## Running the binary
To run the static analysis tool on a given .NET application, you need to have first compiled the target application into IL or `.dll` files. Building the target application into a single `.dll` file is ideal, but otherwise, you can simply provide the main entry point `.dll` file into the program. 

The Axal static analysis tool has the following options:
```
  -a, --assembly <path>    Path to the assembly (.dll or .exe) to analyze [required]
  -g, --graph <path>       Path to save the dependency graph (.dot format) [default: dependency-graph.dot]
  -m, --metrics <path>     Path to save the class metrics (.json format) [default: class-metrics.json]
  -n, --namespace <prefix> Only include types in the specified namespace prefix
  -h, --help               Display a help message
```

So for example, you can run the static analyzer on linux using:
```
./axal-csharp-static-linux -a /path/to/your/Target.dll -n MyCompany.MyNamespace
```
For successful run conditions, make sure to specify both the path to the target assembly as well as the application's namespace. This will generate two output files (which will have the default names of `dependency-graph.dot` and `class-metrics.json`), which the Axal web app can use in conjunction with dynamic traces in order to provide architectural visibility.
