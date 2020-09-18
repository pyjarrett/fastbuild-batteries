# fb-batteries

## Goal

Improve initial FASTBuild setup by providing a base set of compiler, linker, and
archiver definitions.

Focus on developing appropriate conventions for names, especially for my own
projects.

```
OutputBase
	objects/
	
                         Test output
```

|                              |                              |                                       |
|------------------------------|------------------------------|---------------------------------------|
| Global Configurations        |                              |                                       |
|                              | Output location              | `OutputBase`                          |
|                              |                              | `ConfigName`                          |
|                              |                              | `InputConfigs`                        |
|                              |                              | `BuildConfigs`                        |
|                              |                              |                                       |
| Standardized Configs         |                              |                                       |
|                              | Operating system             | `OS_{Name}`                           |
|                              | Compiler                     | `Compiler_{Name}`                     |  
|                              | Configuration                | `Config_{Name}`                       |
|                              |                              |                                       |
| Compiler                     |                              |                                       |
|                              | Compiler Specific Type Flags | `CFl{Type}`                           |  
|                              | Linker Specific Type Flags   | `LFl{Type}`                           |  
|                              |                              |                                       |
| Configuration                |                              |                                       |
|                              |                              | `ConfigName`                          |
|                              |                              | `ConfigCompilerOptions`               |
|                              |                              | `ConfigLinkerOptions`                 |
|                              |                              | `OS`                                  |
|                              |                              |                                       |
| Project                      |                              |                                       |
|                              |                              | `ProjectName`                         |
|                              |                              | `ProjectPath`                         |
|                              |                              |                                       |
| Standardized Targets         |                              |                                       |
|                              | Object                       | `{ProjectName}_{Name}_Obj_$Flavor$`   |
|                              | Library                      | `{ProjectName}_{Name}_Lib_$Flavor$`   |
|                              | Executable                   | `{ProjectName}_{Name}_Exe_$Flavor$`   |
|                              | Test                         | `{ProjectName}_{Name}_Test_$Flavor$`  |  
|                              |                              |                                       |  
|                              |                              |                                       |  
|                              | Visual Studio Projects       | `Project_{Project}_{Name}`            |  
|                              | Visual Studio Solutions      | `Sln_{Name}`                          |  
|                              |                              |                                       |  
|                              |                              |                                       |   
|                              |                              |                                       |   
|                              | Flavor                       | `Targets_$Flavor$`                    |   
|                              | Config                       | `Targets_$Config$`                    |   
|                              |                              |                                       |   
|                              |                              |                                       |   
| All Targets                  |                              |                                       |   
|                              | Flavor                       | `All_$Flavor$`                        |   
|                              | Config                       | `All_$ConfigName$`                    |   
|                              | All Visual Studio Projects   | `All_Projects`                        |   
|                              |                              |                                       |   
|                              |                              | `CommonCompilerOptions`               |   
|------------------------------|------------------------------|---------------------------------------|   



| Variable                     | Meaning                                                              |
|------------------------------|----------------------------------------------------------------------|   
| `CFlSysInc`                  | compiler system include flag                                         |
| `Flavor`                     | Build Flavor `{OS}_{Compiler}_{Arch}_{Config}`                       |
|                              |                                                                      |
|                              |                                                                      |
|------------------------------|----------------------------------------------------------------------|   

