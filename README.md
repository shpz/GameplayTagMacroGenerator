# GameplayTagMacroGenerator

![Icon256](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Icon256.png "LOGO")

Unreal Engine based plugin for generate GameplayTag macro code. Safe, elegant, simple, convenient, and fast.

[**中文文档点这里**](https://zhuanlan.zhihu.com/p/617792556)

---------

## Features

1. Generate GameplayTag macro code with one click. Generating code includes macros, macro checks, and comments. The GameplayTag collection source includes the GameplayTagTableList in the settings, as well as the defaultGameplayTags.ini configuration file
2. Check if GameplayTag is duplicated. Duplicate GameplayTag will be printed in the form of a warning on the console
3. In addition to supporting C++macros, it also supports popular scripting language frameworks such as Unlua and Purchases
4. Complete code annotations for easy secondary development and learning
5. The annotation style can be changed, and there are now two types: line annotations and document annotations
6. C++ Code Force Alignment

## Usage

1. In the Unreal Engine Marketplace search GameplayTagMacroGenerator code plugin, download and install.

2. Open the project, there is an additional button ![Icon20](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Icon20.png "LOGO") on the Main Toolbar, which can also be found in the Main Menu - Window.

    ![Screenshot1](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Screenshot1.png)

3. Create a new CompositeDataTable named CDT_GameplayTags, select GameplayTagTableRow for the row structure.

    ![Screenshot2](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Screenshot2.png)

4. Create a new DataTable named DT_CharacterGameplayTag, select GameplayTagTableRow for the row structure.

    ![Screenshot3](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Screenshot3.png)

5. Add several pieces of data to the DT_CharacterGameplayTag, such as:

    ![Screenshot4](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Screenshot4.png)

    **Row Name** will be used as the macro name. 

    **Tag** will be the target GameplayTag. 

    **Dev Comment** will be annotated above the macro.

6. Open CDT_GameplayTags, add DT_CharacterGameplayTag to Parent Tables. here can add many GameplayTagDataTable. 

    ![Screenshot5](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Screenshot5.png)

    After, add CDT_GameplayTags to Project Settings - Project - GameplayTags - GameplayTagTableList

7. After saved, open Main Menu - Project Settings - Project - GameplayTag Macro Generator, fill in settings.

    ![Screenshot6](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Screenshot6.png)

    There are three settings here:

    **CppMacroFileOutputPath**: file output path, select the path for the header file in a project

    **CppMacroFileOutputName**: file name, default to MyGameplayTags, can be modified at will

    **CommentStyle**: Comment style, default to document comment, with two options: document comment and line comment

8. Click ![LOGO](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Icon20.png "LOGO") generate macro file, then you can obtain the target GameplayTag through a macro in code.

    ![Screenshot7](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Screenshot7.png)
