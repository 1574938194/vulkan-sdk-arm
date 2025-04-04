1. Clone repo (or sync with `git pull` if already cloned):

```
git clone https://github.com/EpicGames/UnrealEngine
```

2. Run setup script:

```
./Setup.sh
```

ii. Edit 
UnrealEngine/Engine/Build/BatchFiles/Linux/
SetupDotnet.sh    =>ARCH=arm64
GitDependencies.sh   =>linux-arm64


3. Run project file generation script:

```
./GenerateProjectFiles.sh
```

If you get the error

```
Setting up bundled DotNet SDK
Process terminated. Couldn't find a valid ICU package installed on the system. Set the configuration flag System.Globalization.Invariant to true if you want to run with no globalization support.
...
GenerateProjectFiles ERROR: Failed to build UnrealBuildTool
```

try setting environment variable `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT=1`, or installing [ICU v50](https://icu.unicode.org/download/50) (courtesy of @debian-user-france1).

4. Finally, run the build:

```
make
```
