# GameplayTagMacroGenerator

![Icon256](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/Icon256.png "LOGO")

Unreal Engine based plugin for generate GameplayTag macro code. Safe, elegant, simple, convenient, and fast.

[**中文文档点这里**](https://zhuanlan.zhihu.com/p/617792556)

---------

> TypeScript macro generator has been supported.

## introduce
GameplayTag is heavily used in the project through Blueprints and C++. The following are the ways that everyone adds GameplayTags:

Add a DataTable with TableRow set to FGameplayTagTableRow in the settings.

Add it in the GameplayTag editor.

Write it directly in .ini files (yes, I do this -.-).

Clearly, we need order and rules!

1. We have decided to manage GameplayTags using DataTable in the following way:

2. Use a CompositeDataTable as a container and add multiple child GameplayTagDataTables.

3. Each child GameplayTagDataTable only contains one type of GameplayTag, for example, the UI DataTable is named DT_UIGameplayTags.

4. Each child GameplayTagDataTable has a fixed prefix. For example, the UI-related GameplayTags are named http://UI.XXX.XXX.

5. We created an EditorBlueprintUtility in Blueprint to check for duplicate GameplayTags in the DataTables and generate code like this:
``` C++
#ifndef UI_XXX_XXX
/**
 *	GameplayTagTableRow DevComment
 */
#define UI_XXX_XXX FGameplayTag::RequestGameplayTag(FName("UI.XXX.XXX"))
#endif
```

This saves us from the tedious work of copying, pasting, and checking for duplicates.

It's very smooth and elegant. I'm truly amazed by it.

## GameplayTagMacroGenerator plugin
Later, I rewrote the EditorBlueprintUtility in C++ at home and added editor support to improve the user experience.

I named it GameplayTagMacroGenerator (GTMG for short).

I am preparing to release it on the Unreal Marketplace. If it is successful, I will write a post to share my experience with submitting products to the marketplace.![Screenshot1](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/images/chidai.jpg)

## Features

1. One-click generation of GameplayTag macro code. The generated code includes macros, macro checks, and comments.
``` C++
#ifndef UI_XXX_XXX
/**
 *	GameplayTagTableRow DevComment
 */
#define UI_XXX_XXX FGameplayTag::RequestGameplayTag(FName("UI.XXX.XXX"))
#endif
```
The GameplayTag collection source includes the GameplayTagTableList in settings and the DefaultGameplayTags.ini configuration file.
2. Check if the GameplayTag is duplicated. Duplicated GameplayTags will be printed as warnings in the console.
3. In addition to support for C++ macros, it also supports popular script language frameworks such as Unlua and Puerts.
4. Full code comments are provided for easy secondary development and learning.
5. Sure, here is the translation of my previous response:
``` C++
// Line comments
```

AND

```
/**
 *	Documention comments
 */
```

6. Aligning C++ code makes compulsive disorders feel comfortable.

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
