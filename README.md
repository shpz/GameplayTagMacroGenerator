# GameplayTagMacroGenerator

![Icon256](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Icon256.png "LOGO")

Unreal Engine based plugin for generate GameplayTag macro code.

[**中文文档点这里**](https://gitee.com/shpoz/gameplay-tag-macro-generator-doc/blob/master/README.md)

---------

## Feature
1. Generate GameplayTag macro code with one click. The generated code includes macros, macro checks, and comments
2. Check if the GameplayTag is duplicate to ensure security. Duplicate GamePlaytags are printed in the console as warnings
3. Script frameworks such as Unlua and PuerTS will be supported soon
4. Continuous improvement of documentation, convenient secondary development and learning

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

7. After saved, open Main Menu - Project Settings - GameplayTag Macro Generator - Settings, fill in settings.

    ![Screenshot6](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Screenshot6.png)

8. Click ![LOGO](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Icon20.png "LOGO") generate macro file, then you can obtain the target GameplayTag through a macro in code.

    ![Screenshot7](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Screenshot7.png)