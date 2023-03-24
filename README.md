# GameplayTag 宏生成器
# GameplayTag Macro Generator

基于虚幻引擎制作的，用于生成 GameplayTag 宏的插件。
A plugin based on an UnrealEngine for generating GameplayTag macros.

## 使用 Usage

1. 在虚幻商城找到 GameplayTagMacroGenerator 插件并下载，选择安装到项目。

    Find and download the GameplayTagMacroGenerator plugin in the UnrealEngine Marketplace, and choose to install it to the project.

2. 打开项目，主工具栏多了个按钮[image]，在菜单栏-窗口中也能找到。

    Open the project, there is an additional button on the Main Toolbar [image], which can also be found in the Main Menu - Window.

3. 新建一个合成数据表格命名为 CDT_GameplayTags，行结构体选择 GameplayTagTableRow。

    Create a new CompositeDataTable named CDT_GameplayTags, select GameplayTagTableRow for the row structure.

4. 新建一个数据表格命名为 DT_CharacterGameplayTag，行结构体选择 GameplayTagTableRow。

    Create a new DataTable named DT_CharacterGameplayTag, select GameplayTagTableRow for the row structure.

5. 向 DT_CharacterGameplayTag 中添加几条数据，例如：

    Add several pieces of data to the DT_CharacterGameplayTag, such as: [image]

6. 打开 CDT_GameplayTags，在父表格中添加 DT_CharacterGameplayTag。这里可以添加很多 GameplayTagDataTable。

    Open CDT_GameplayTags, add DT_CharacterGameplayTag to Parent Tables. here can add many GameplayTagDataTable.

7. 保存后，打开主菜单- 项目设置 - GameplayTag Macro Generator - Settings 中填写对应设置。
    
    After saved, open Main Menu - Project Settings - GameplayTag Macro Generator - Settings, fill in settings.

8. 点击 [image]，就会自动生成宏文件。

    Click [image], will generate macro file。