# Extensions and guides for .NET SDK

guides for .net core 3.1 and above.


This repo contains extensions to use with .NET applications, using .net core 3.1 and higher, as well as extensions for unit and [integration tests](https://docs.microsoft.com/en-us/aspnet/core/test/integration-tests?#introduction-to-integration-tests).

It also contains guides on scenarios around building apps using .NET SDK. These guides are for situations where an extension is not merited but some documentation on how to accomplish the task is.

## Documentation and Guides

For documentation about the available extensions go [here](/docs/docs-main.md).

For the .NET SDK guides available go [here](/docs/guides-main.md).

## GitHub Workflows

| Worflow                   |      Status and link      |
|---------------------------|:-------------------------:|
| [build-demos](https://github.com/edumserrano/dot-net-sdk-extensions/blob/master/.github/workflows/build-demos.yml)             |  ![Build Status](https://github.com/edumserrano/dot-net-sdk-extensions/workflows/Build%20demos/badge.svg) |
| [nuget-publish](https://github.com/edumserrano/dot-net-sdk-extensions/blob/master/.github/workflows/nuget-publish.yml)             |  ![Build Status](https://github.com/edumserrano/dot-net-sdk-extensions/workflows/Publish%20Nuget%20packages/badge.svg) |

For more information about the GitHub actions go [here](/docs/github-workflows/github-workflows.md).

## Installing

This repo provides two NuGet packages:

- [DotNet-Sdk-Extensions](https://www.nuget.org/packages/DotNet-Sdk-Extensions)
- [DotNet-Sdk-Extensions-Testing](https://www.nuget.org/packages/DotNet-Sdk-Extensions-Testing)

Installation is performed via NuGet and you can do it using the following commands:

```
dotnet add package DotNet-Sdk-Extensions
dotnet add package DotNet-Sdk-Extensions-Testing
```

## Building

### Using Visual Studio

1) Clone the repo and open one of the solution files:
   - **DotNet.Sdk.Extensions.sln:** source for the extensions.
   - **DotNet.Sdk.Extensions.Demos.sln:** demo projects for the extensions and the guides.

2) Press build on Visual Studio.

### Using dotnet CLI

1) Clone the repo and browse to the directory using your favorite shell.

2) Run:
   - **`dotnet build DotNet.Sdk.Extensions.sln`:** to build the source for the extensions.
   - **`dotnet build DotNet.Sdk.Extensions.Demos.sln`:** to build the demos for the extensions and the guides.

## Debugging

The NuGet packages published include symbols generated with [sourcelink](https://github.com/dotnet/sourcelink).

For more information on how to debug the NuGet packages code from your application see:

- [Exploring .NET Core's SourceLink - Stepping into the Source Code of NuGet packages you don't own](https://www.hanselman.com/blog/exploring-net-cores-sourcelink-stepping-into-the-source-code-of-nuget-packages-you-dont-own)
- [How to Configure Visual Studio to Use SourceLink to Step into NuGet Package Source](https://aaronstannard.com/visual-studio-sourcelink-setup/)
- [Source Link - microsoft docs](https://docs.microsoft.com/en-us/dotnet/standard/library-guidance/sourcelink)

## License

This project is licensed under the [MIT license](https://licenses.nuget.org/MIT).

## TODO

* where to save info about how to use splunk + docker + asp.net core app (+ serilog?). If on guides then maybe the curren title .net sdk guides is not the best.

* investigate how to test using Ilogger
* investigate serilog logging test extensions for integration tests
  * investigate test sink (search github) and look at how the test is done for the enricher https://github.com/serilog/serilog-enrichers-environment/commit/24c1c874ed4044ec488a5119130c869d328f9fbd 
* useful serilog related guides/extensions/enrichers/attributes? What common things I do when logging?

* Polly http extrnsions: addcircuitbreaker addregistry options etc. explain app settings Add fallbalback as optional but have a add default resilience that adds all if u want but if you need to add separate ones then have the several resilience as separate

* what about learnings about custom swagger stuff for health checks?
* swagger ui healtchecks learnings? and k8s related?

* move packages from alpha to stable and update it on demo sln
* any readme missing?
* create an issue on the repo to allow testing https. need to figure out how to configure a cert. Look for TODO on the codebase

* rename repo to something that reflects that this is not only extensions but also guides and examples of working with the sdk?
* on the dot net sdk extensions repo: add also example projects, so rename the repo to something else? dotnet-sdk-extensions-guides-examples or break up the repo into 3
* what do I need to do so that everything works on vscode?
* guide/examples/demos -> learn about identity asp.net core and probably identity server (how to authenticate with external providers like facebook and how to deal with custom providers like an internal old system)
* demos on orleans
  
## Notes

If you have problems with SSL certificates when running the demos or tests then make sure you have trusted dev certificates by executing the following command

```
dotnet dev-certs https --trust
```

For more info see [Generate self-signed certificates with the .NET CLI](https://docs.microsoft.com/en-us/dotnet/core/additional-tools/self-signed-certificates-guide).
