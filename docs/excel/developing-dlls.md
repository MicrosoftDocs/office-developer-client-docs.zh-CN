---
title: 开发 DLL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- dll [excel 2007], 创建, 创建 DLL [Excel 2007]
ms.assetid: 5d69d06d-a126-4c47-82ad-17112674c8a3
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
localization_priority: Priority
ms.openlocfilehash: 89dd7b65ad94ba2fc7e1cf3f99ee163d3003d0fe
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704747"
---
# <a name="developing-dlls"></a>开发 DLL

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
一个库表示一组经过编译的代码，为可执行应用程序提供一些功能和数据。 库可以是静态链接的，也可以是动态链接的，两种情况下通常分别具有文件扩展名 .lib 和 .dll。 静态库（例如 C 运行时库）在编译时链接到应用程序，因此成为生成的可执行文件的一部分。 应用程序在需要 DLL 时（通常是在应用程序启动时）加载 DLL。 一个 DLL 可以加载并动态链接到另一个 DLL。
  
## <a name="benefits-of-using-dlls"></a>使用 DLL 的好处

DLL 的主要好处如下：
  
- 所有应用程序可以共享磁盘上的单个副本。
    
- 应用程序的可执行文件保持较小。
    
- 它们使大型开发项目得以细分。 应用程序和 DLL 开发人员只需要就各自部分的接口达成一致。 此接口由 DLL 导出。
    
- DLL 开发人员可以更新 DLL（可能是为了提高它们的效率或修复 bug），而不必更新所有使用它的应用程序，但前提是 DLL 的导出接口不会改变。
    
可以使用 DLL 在 Microsoft Excel 中添加工作表函数和命令。
  
## <a name="resources-for-creating-dlls"></a>用于创建 DLL 的资源

若要创建 DLL，你需要：
  
- 源代码编辑器。
    
- 一个编译器，用于将源代码转换为与硬件兼容的目标代码。
    
- 一个链接器，用于从静态库（如果使用）中添加代码以及创建可执行的 DLL 文件。
    
诸如 Microsoft Visual Studio 之类的现代化集成开发环境 (IDE) 可提供所有这些功能。 它们还提供了大量额外功能：智能编辑器、用于调试代码的工具、用于管理多个项目的工具、新项目向导以及许多其他重要工具。
  
可以使用多种语言（例如，C/C++、Pascal 和 Visual Basic）创建 DLL。 鉴于 Excel 附带的 API 源代码是 C 和 C++，本文档中仅考虑这两种语言。
  
## <a name="exporting-functions-and-commands"></a>导出函数和命令

在编译 DLL 项目时，编译器和链接器需要知道要导出哪些函数，以便使这些函数可用于应用程序。 本部分将介绍如何实现此目的。
  
编译器编译源代码时，通常会根据函数在源代码中的外观更改函数的名称。 编译器通常在所谓的“名称修饰”过程中通过在名称的开头和/或结尾添加内容来实现此目的。 务必使用可由加载 DLL 的应用程序识别的名称导出函数。 这可能意味着告诉链接器将修饰的名称与更简单的导出名称相关联。 导出名称可以是最初出现在源代码中的名称，也可以是其他名称。
  
名称的修饰方式取决于语言以及如何指示编译器使函数可用（即调用约定）。 DLL 使用的 Windows 标准进程间调用约定称为 WinAPI 约定。 此约定在 Windows 头文件中定义为 **WINAPI**，后者则是用 Win32 声明符 **__stdcall** 定义的。
  
用于 Excel 的 DLL 导出函数（无论是工作表函数、宏表等效函数还是用户定义的命令）应始终使用 **WINAPI** / **__stdcall** 调用约定。 有必要在函数的定义中显式包含 **WINAPI** 说明符，因为 Win32 编译器中的默认设置是使用 **__cdecl** 调用约定（如果没有指定，则也可定义为 **WINAPIV**）。
  
你可以告诉链接器要导出一个函数，并通过以下几种方式之一从外部获知函数名称：
  
- 将函数放在 DEF 文件中的 **EXPORTS** 关键字后，并设定 DLL 项目设置以便在链接时引用此文件。 
    
- 在函数定义中使用 **__declspec(dllexport)** 声明符。 
    
- 使用 **#pragma** 预处理器指令向链接器发送消息。 
    
虽然项目可以使用所有这三种方法，并且编译器和链接器支持这些方法，但不应尝试以多种方式导出同一个函数。 例如，假设一个 DLL 包含两个源代码模块：一个 C 和一个 C++，它们分别包含两个要导出的函数 **my\_C\_export** 和 **my\_Cpp\_export**。 为简单起见，假设每个函数都采用单个双精度数值参数并返回相同的数据类型。 以下部分将说明如何分别使用这些方法导出每个函数。 
  
### <a name="using-a-def-file"></a>使用 DEF 文件

```C
double WINAPI my_C_export(double x)
{
/* Modify x and return it. */
    return x * 2.0;
}
```

```cpp
double WINAPI my_Cpp_export(double x)
{
// Modify x and return it.
    return x * 2.0;
}
```

<br/>

DEF 文件需要包含以下行。
  
`EXPORTS my_C_export = _my_C_export@8  my_Cpp_export`

<br/>

**EXPORTS** 语句后面一行的一般语法如下所示。 
  
`entryname[=internalname] [@ordinal[NONAME]] [DATA] [PRIVATE]`

请注意，C 函数已经过修饰，但 DEF 文件显式强制链接器使用原始源代码名称公开该函数（在本示例中）。 链接器使用原始代码名称隐式导出 C++ 函数，因此不必在 DEF 文件中包含修饰的名称。
  
对于 32 位 Windows API 函数调用，C 编译函数的修饰约定如下：**function_name** 变为 _ **function_name@** _n_，其中 _n_ 是所有参数占用的字节数（以十进制数表示）以及每个四舍五入到最接近四的倍数的字节数。 
  
> [!NOTE]
> 在 Win32 中，所有指针的宽度都是四个字节。 返回类型对名称修饰没有任何影响。 
  
通过包含函数和所有函数原型，可以强制 C++ 编译器在 extern "C" {…} 代码块中公开 C++ 函数的未修饰名称， 如本例中所示。 （此处省略了大括号 **{}**，因为该声明仅引用紧跟在后面的函数代码块）。 
  
```cpp
extern "C"
double WINAPI my_undecorated_Cpp_export(double x)
{
// Modify x and return it.
    return x * 2.0;
}

```

将 C 函数原型放在可包含在 C 或 C++ 源文件中的头文件内时，应包含以下预处理器指令。
  
```cpp
#ifdef __cplusplus
extern "C" {
#endif
double WINAPI my_C_export(double x);
double WINAPI my_Cdecorated_Cpp_export(double x);
#ifdef __cplusplus
}
#endif
```

### <a name="using-the-declspecdllexport-declarator"></a>使用 __declspec(dllexport) 声明符

可在如下所示的函数声明中使用 **__declspec(dllexport)** 关键字。 
  
```cpp
__declspec(dllexport) double WINAPI my_C_export(double x)
{
/* Modify x and return it. */
    return x * 2.0;
}
```

必须在声明的最左侧添加 **__declspec(dllexport)** 关键字。 这种方法的优点是该函数不需要在 DEF 文件中列出，并且导出状态与定义一致。 
  
如果要避免使用 C++ 名称修饰来提供 C++ 函数，必须按如下方式声明函数。
  
```cpp
extern "C"
__declspec(dllexport) double WINAPI my_undecorated_Cpp_export(double x)
{
// Modify x and return it.
    return x * 2.0;
}
```

链接器将使该函数显示为 my_undecorated_Cpp_export，即源代码中显示的名称，没有任何修饰。
  
### <a name="using-a-pragma-preprocessor-linker-directive"></a>使用 #pragma 预处理器链接器指令

最新版本的 Microsoft Visual Studio 支持两个预定义的宏，当这些宏与 **#pragma** 指令结合使用时，可以指示链接器直接从函数代码中导出函数。 这些宏为 __FUNCTION__ 和 __FUNCDNAME__（注意两端的双下划线），它们分别扩展为未修饰的和已修饰的函数名称。 
  
例如，使用 Microsoft Visual Studio 时，这些行可以合并到一个公共头文件中，如下所示。
  
```cpp
#if _MSC_VER > 1200 // Later than Visual Studio 6.0
#define EXPORT comment(linker, "/EXPORT:"__FUNCTION__"="__FUNCDNAME__)
#else // Cannot use this way of exporting functions.
#define EXPORT
#endif // else need to use DEF file or __declspec(dllexport)

```

如果此头文件包含在源文件中，则可以按如下方式导出这两个示例函数。
  
C 代码：
  
```C
double WINAPI my_C_export(double x)
{
#pragma EXPORT
/* Modify x and return it. */
    return x * 2.0;
}
```

C++ 代码：
  
```cpp
double WINAPI my_Cpp_export(double x)
{
#pragma EXPORT
// Modify x and return it.
    return x * 2.0;
}
```

请注意，该指令必须放在函数的正文中，并且仅在编译器选项 **/EP** 和 **/P** 均未设置时才会扩展。 此方法不需要 DEF 文件或 **__declspec(dllexport)** 声明，并且使用函数代码保持指定其导出状态。 
  
## <a name="see-also"></a>另请参阅

- [在 Excel 中访问 DLL](how-to-access-dlls-in-excel.md)
- [从 DLL 或 XLL 调用 Excel](calling-into-excel-from-the-dll-or-xll.md)
- [Excel 编程概念](excel-programming-concepts.md)
- [开发 Excel XLL](developing-excel-xlls.md)

