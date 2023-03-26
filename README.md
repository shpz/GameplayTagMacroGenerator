# GameplayTag 宏生成器  GameplayTagMacroGenerator

![LOGO](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/Icon256.png "LOGO")

基于虚幻引擎制作的，用于生成 GameplayTag 宏的插件。

A plugin based on an UnrealEngine for generating GameplayTag macros.

## 使用  Usage

1. 在虚幻商城找到 GameplayTagMacroGenerator 插件，下载并安装。

    Find the GameplayTagMacroGenerator plugin at the UnrealEngine Marketplace, download and install it.

2. 打开项目，主工具栏多了个按钮 ![LOGO](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/Icon20.png "LOGO")，在菜单栏-窗口中也能找到。

    Open the project, there is an additional button ![LOGO](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/Icon20.png "LOGO") on the Main Toolbar, which can also be found in the Main Menu - Window.

    ![Screenshot1](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/Screenshot1.png)

3. 新建一个合成数据表格命名为 CDT_GameplayTags，行结构体选择 GameplayTagTableRow。

    Create a new CompositeDataTable named CDT_GameplayTags, select GameplayTagTableRow for the row structure.

    ![Screenshot2](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/Screenshot2.png)

4. 新建一个数据表格命名为 DT_CharacterGameplayTag，行结构体选择 GameplayTagTableRow。

    Create a new DataTable named DT_CharacterGameplayTag, select GameplayTagTableRow for the row structure.

    ![Screenshot3](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/Screenshot3.png)

5. 向 DT_CharacterGameplayTag 中添加几条数据，例如：

    Add several pieces of data to the DT_CharacterGameplayTag, such as:     

    ![Screenshot4](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/Screenshot4.png)

    行名会将作为宏名，Tag 为目标 GameplayTag，开发评论将注释在宏上方。

    The Row Name will be used as the macro name, and the Tag will be the target GameplayTag. Dev Comment will be annotated above the macro.

6. 打开 CDT_GameplayTags，在父表格中添加 DT_CharacterGameplayTag。这里可以添加很多 GameplayTagDataTable。

    Open CDT_GameplayTags, add DT_CharacterGameplayTag to Parent Tables. here can add many GameplayTagDataTable.

    ![Screenshot5](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/Screenshot5.png)

7. 保存后，打开主菜单- 项目设置 - GameplayTag Macro Generator - Settings 中填写对应设置。
    
    After saved, open Main Menu - Project Settings - GameplayTag Macro Generator - Settings, fill in settings.

    ![Screenshot6](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/Screenshot6.png)

8. 点击 ![LOGO](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/Icon20.png "LOGO")生成宏文件，然后就可以在C++代码里通过宏拿到目标GameplayTag。

    Click ![LOGO](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/Icon20.png "LOGO") generate macro file, then you can obtain the target GameplayTag through a macro in C++ code.

    ![Screenshot7](https://raw.githubusercontent.com/shpz/GameplayTagMacroGenerator/master/Screenshot7.png)