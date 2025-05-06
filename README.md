# GSD Solution Template

## Install the template

1. Clone the solution template.

```
git clone https://github.com/gsdlogic/GSD.SolutionTemplate.git
```

2. Remove the `.git` folder from within the template source directory.

```
rm -Recurse -Force GSD.SolutionTemplate\.git
```

3. Install the template.

```
dotnet new install GSD.SolutionTemplate
```

## Create a solution

1. Create the solution.

```
dotnet new gsdsolution -n YourSolutionName
```

2. Create a strong name file. Run this in the solution directory.

```
sn -k YourSolutionName.snk
```

3. Edit `Directory.Build.Props` and update `<Company>` and `<Copyright>` properties accordingly.

4. Edit `stylecop.json` and update `companyName` and `copyrightText` accordingly.

5. Replace the `README.md` with a more appropriate template for the solution.

6. A good practice is to create a new Git repository with an initial commit at this point before adding any projects.

```
git init
git add .
git commit -m 'Initial commit.'
```

7. All projects must be at the same level relative to the solution directory.

Example directory structure:

```
<root>
├── YourSolutionName.sln
├── Project1\Project1.csproj
└── Project2\Project2.csproj.
```

To group similar projects by type, edit `Directory.Build.Props` and replace `../` with `../../` in the path to the `.snk` and `stylecop.jon` files.

Example directory structure:

```
<root>
├── YourSolutionName.sln
├── Source
│   ├── Project1\Project1.csproj
│   └── Project2\Project2.csproj.
└── Tests
    ├── Project1Tests\Project1Tests.csproj
    └── Project2Tests\Project2Tests.csproj
```

## Uninstall the template

Ensure a relative path to `GSD.SolutionTemplate`, or specify an absolute path to the directory.

```
dotnet new uninstall GSD.SolutionTemplate
```
