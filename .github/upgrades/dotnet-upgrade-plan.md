# .NET 9.0 Upgrade Plan

## Execution Steps

1. Validate that an .NET 9.0 SDK required for this upgrade is installed on the machine and if not, help to get it installed.
2. Ensure that the SDK version specified in global.json files is compatible with the .NET 9.0 upgrade.
3. Upgrade projects to .NET 9.0.
  - 3.1. Upgrade Blazored.Typeahead.csproj
  - 3.2. Upgrade Sample.Shared.csproj
  - 3.3. Upgrade BlazorServer.csproj
  - 3.4. Upgrade BlazorWebAssembly.csproj

## Settings

This section contains settings and data used by execution steps.

### Excluded projects

Table below contains projects that do belong to the dependency graph for selected projects and should not be included in the upgrade.

| Project name                                   | Description                 |
|:-----------------------------------------------|:---------------------------:|

### Aggregate NuGet packages modifications across all projects

NuGet packages used across all selected projects or their dependencies that need version update in projects that reference them.

| Package Name                        | Current Version | New Version | Description                         |
|:------------------------------------|:---------------:|:-----------:|:------------------------------------|
| Microsoft.AspNetCore.Components     |   6.0.3         |  9.0.5      | Recommended for .NET 9.0            |
| Microsoft.AspNetCore.Components.Web |   6.0.3         |  9.0.5      | Recommended for .NET 9.0            |
| Microsoft.AspNetCore.Components.WebAssembly |   6.0.3         |  9.0.5      | Recommended for .NET 9.0            |
| Microsoft.AspNetCore.Components.WebAssembly.DevServer |   6.0.3         |  9.0.5      | Recommended for .NET 9.0            |

### Project upgrade details

#### Blazored.Typeahead modifications

Project properties changes:
  - Target framework should be changed from `net6.0` to `net9.0`

NuGet packages changes:
  - Microsoft.AspNetCore.Components should be updated from `6.0.3` to `9.0.5` (*recommended for .NET 9.0*)
  - Microsoft.AspNetCore.Components.Web should be updated from `6.0.3` to `9.0.5` (*recommended for .NET 9.0*)

#### Sample.Shared modifications

Project properties changes:
  - Target framework should be changed from `net6.0` to `net9.0`

NuGet packages changes:
  - System.ComponentModel.Annotations should be removed (*functionality included with new framework reference*)

#### BlazorServer modifications

Project properties changes:
  - Target framework should be changed from `net6.0` to `net9.0`

#### BlazorWebAssembly modifications

Project properties changes:
  - Target framework should be changed from `net6.0` to `net9.0`

NuGet packages changes:
  - Microsoft.AspNetCore.Components.WebAssembly should be updated from `6.0.3` to `9.0.5` (*recommended for .NET 9.0*)
  - Microsoft.AspNetCore.Components.WebAssembly.DevServer should be updated from `6.0.3` to `9.0.5` (*recommended for .NET 9.0*)