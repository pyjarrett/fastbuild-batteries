# fastbuild-batteries

## Goal

Improve initial FASTBuild setup by providing a base set of compiler, linker, and
archiver definitions.

Focus on developing appropriate conventions for names, especially for my own
projects.

```
OutputBase
    $Flavor$/
	    objects/
	
                         Test output
```
|                                    |                              |                                       |
|------------------------------------|------------------------------|---------------------------------------|
| Global Configurations              |                              |                                       |
|                                    | Output location              | `OutputBase`                          |
|                                    | Preprocessed configs         | `InputConfigs`                        |
|                                    | Build configs to use         | `BuildConfigs`                        |
|                                    |                              |                                       |
| Standardized Configs               |                              |                                       |
|                                    | Operating system             | `OS_{Name}`                           |
|                                    | Compiler                     | `Compiler_{Name}`                     |
|                                    | Configuration                | `Config_{Name}`                       |
|                                    |                              |                                       |
| OS (`.OS_`)                        |                              |                                       |
|                                    |                              | `ExeExtension`                        |
|                                    |                              | `LibPrefix`                           |
|                                    |                              | `LibStaticSuffix`                     |
|                                    |                              | `LibSharedSuffix`                     |
|                                    |                              |                                       |
| Compiler (`.Compiler_{Name}`)      |                              |                                       |
|                                    | Compiler Specific Type Flags | `CFl{Type}`                           |
|                                    | Linker Specific Type Flags   | `LFl{Type}`                           |
|                                    |                              |                                       |
| Configuration (`.Config_{Name}`)   |                              |                                       |
|                                    |                              | `ConfigName`                          |
|                                    |                              | `ConfigCompilerOptions`               |
|                                    |                              | `ConfigLinkerOptions`                 |
|                                    |                              | `OS`                                  |
|                                    |                              |                                       |
| Build (`.BuildConfigs`)            |                              |                                       |
|                                    |                              | `Compiler`                            |
|                                    |                              | `CompilerOptions`                     |
|                                    |                              | `Linker`                              |
|                                    |                              | `LinkerOptions`                       |
|                                    |                              | `Flavor`                              |
|                                    | Output location              | `OutputBase`                          |
|                                    |                              |                                       |
| Standardized Targets               |                              |                                       |
|                                    | Object                       | `{ProjectName}_{Name}_Obj_$Flavor$`   |
|                                    | Library                      | `{ProjectName}_{Name}_Lib_$Flavor$`   |
|                                    | Executable                   | `{ProjectName}_{Name}_Exe_$Flavor$`   |
|                                    | Test                         | `{ProjectName}_{Name}_Test_$Flavor$`  |
|                                    | Flavor                       | `Targets_$Flavor$`                    |
|                                    | Config                       | `Targets_$Config$`                    |
|                                    |                              |                                       |
|                                    |                              |                                       |
| All Targets                        |                              |                                       |
|                                    | Flavor                       | `All_$Flavor$`                        |
|                                    | Config                       | `All_$ConfigName$`                    |
|                                    |                              |                                       |
| Project                            |                              |                                       |
|                                    |                              | `ProjectName`                         |
|                                    |                              | `ProjectPath`                         |
|                                    |                              |                                       |
| Visual Studio                      |                              |                                       |
|                                    | Visual Studio Projects       | `Project_{Project}_{Name}`            |
|                                    | Visual Studio Solutions      | `Sln_{Name}`                          |
|                                    | All Visual Studio Projects   | `All_Projects`                        |
|                                    |                              |                                       |
|                                    |                              | `VS{Year}BasePath`                    |
|                                    |                              | `VS{Year}Version`                     |
|                                    |                              |                                       |
|                                    |                              |                                       |


| Variable                     | Meaning                                                              |
|------------------------------|----------------------------------------------------------------------|
| `CFlSysInc`                  | compiler system include flag                                         |
| `Flavor`                     | Build Flavor `{OS}_{Compiler}_{Config}`                              |
| `Config`                     | Build Configuration (Debug, Release)                                 |
|------------------------------|----------------------------------------------------------------------|

