---
title: 开发 Dll
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- dll [excel 2007]，创建、 创建 Dll [Excel 2007]
localization_priority: Normal
ms.assetid: 5d69d06d-a126-4c47-82ad-17112674c8a3
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 030cdd4358d9a71841eca6acfcef6e71839e02a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773661"
---
# <a name="developing-dlls"></a>开发 Dll

**适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
库是提供了一些功能和数据到可执行应用程序的已编译代码的正文。 库可为静态链接或动态链接，并且其逆文件名称扩展名.lib 和.dll 分别。 静态库 （如 C 运行时库） 链接到应用程序在编译和因此成为生成可执行文件的一部分。 应用程序需要时，通常在应用程序启动时加载 DLL。 一个 DLL 可以加载并动态链接到另一个 DLL。
  
## <a name="benefits-of-using-dlls"></a>使用 Dll 的好处

Dll 的主要优点如下所示：
  
- 所有应用程序可以共享在磁盘上的一个副本。
    
- 应用程序的可执行文件保持在较小。
    
- 它们使大型开发项目细分。 应用程序和 DLL 开发人员只需同意及其各自的部件之间的接口。 此接口将导出 dll。
    
- DLL 开发人员可以更新 Dll — 可能是为了使其更高效或修复 bug — 无需更新的所有应用程序使用它，前提是 DLL 的导出的接口不会更改。
    
您可以使用 Dll Microsoft Excel 中添加工作表函数和命令。
  
## <a name="resources-for-creating-dlls"></a>有关创建 Dll 资源

若要创建一个 DLL，您需要以下各项：
  
- 源代码编辑器。
    
- 编译器将变成对象代码与您的硬件兼容的源代码。
    
- 链接器从静态库添加代码，其中使用，以及创建可执行的 DLL 文件。
    
现代集成的开发环境 (Ide)，如 Microsoft Visual Studio 中，提供所有这些操作。 他们还提供了大量的详细信息： 智能编辑器、 工具来调试代码、 工具来管理多个项目、 新项目向导和很多其他重要的工具。
  
您可以在多个语言版本，例如，C/c + +、 Pascal 和 Visual Basic 中创建 Dll。 假定 Excel 提供的 API 源代码，C 和 c + + 仅这两种语言视为本文档中。
  
## <a name="exporting-functions-and-commands"></a>导出函数和命令

在编译的 DLL 项目时，编译器和链接器需要知道什么函数是要导出，以便他们可以使其可用于应用程序。 本节介绍进行这种方式。
  
编译器编译源代码，一般情况下，这些函数的名称从更改其源代码中的外观。 他们通常执行此操作通过将添加到的开始和/或结束的名称，在进程中称为名称修饰。 您需要确保该函数导出到加载 DLL 时出错的应用程序可识别的名称。 这可能意味着告知链接器简单的导出名称相关联的修饰的名。 导出名称可以名称，如它最初出现在源代码，或其他内容。
  
修饰名称的方式取决于语言和编译器将指示以使函数可用，即，调用约定。 标准进程间 windows 使用 Dll 调用约定称为选择约定。 它被指在 Windows 头文件**选择**，其中使用 Win32 声明符 **__stdcall**反过来定义。
  
用于 Excel （无论是工作表函数、 宏表等效函数或用户定义的命令） DLL 导出函数应该始终使用**选择** / **__stdcall**调用约定。 它是必要 Win32 编译器中的默认设置是使用 **__cdecl**调用约定，如果未指定还定义为**WINAPIV**，如显式包含该函数的定义中的**选择**说明符。
  
您可以判断函数是要导出链接器和名称会能够由外部在几种方式之一：
  
- **导出**关键字之后, 将该函数放入 DEF 文件并将设置您的 DLL 项目设置，以在链接时引用此文件。 
    
- 该函数的定义中使用 **__declspec(dllexport)** 声明符。 
    
- 使用 **#pragma**预处理器指令链接器发送一条消息。 
    
虽然您编译器和链接器支持这些项目可以使用所有三种方法，您应尝试导出中多个下列方法之一一个函数。 例如，假设 DLL 包含两个源代码模块、 一个 C 和一个 c + +，其中包含要导出的两个函数，**我\_C\_导出**和**我\_Cpp\_导出**分别。 为了简单起见，假设每个函数采用单个双精度数字参数，并返回同一字段数据类型。 以下各节概述了用于将每个函数导出使用每种方法的替代方法。 
  
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

然后，DEF 文件需要包含这些行。
  
`EXPORTS my_C_export = _my_C_export@8  my_Cpp_export`

<br/>

下面的**导出**语句的行的常规语法如下所示。 
  
`entryname[=internalname] [@ordinal[NONAME]] [DATA] [PRIVATE]`

请注意，已修饰 C 函数，但 DEF 文件显式强制链接器公开使用原始源代码名称 （在本例中） 的函数。 链接器隐式导出使用原始代码名称，该 c + + 函数，以便不需要在 DEF 文件中包含的修饰的名。
  
对于 32 位 Windows API 函数调用，C 编译函数的修饰的约定是，如下所示：**兼容**成为 _ **@ 兼容** _n_其中_n_是由所有占用小数形式表示的字节数参数，每个字节会向上舍入到最接近的四个倍数。 
  
> [!NOTE]
> 所有指针都是范围在 Win32 四个字节。 返回类型名称修饰时不会影响。 
  
可以强制 c + + 编译器公开未修饰 c + + 函数名称括函数和任何函数原型内外部"C"{...} 阻止，此例中所示。 (在大括号**{}** 因为声明仅涉及到紧跟在它后面的函数代码块此处省略)。 
  
```cpp
extern "C"
double WINAPI my_undecorated_Cpp_export(double x)
{
// Modify x and return it.
    return x * 2.0;
}

```

当您将无法 C 或 c + + 源文件中包含的头文件中放置 C 函数原型时，应该包括以下预处理器指令。
  
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

**__Declspec(dllexport)** 关键字可在函数的声明，如下所示。 
  
```cpp
__declspec(dllexport) double WINAPI my_C_export(double x)
{
/* Modify x and return it. */
    return x * 2.0;
}
```

必须在声明的最左侧添加 **__declspec(dllexport)** 关键字。 此方法的优点是函数不需要在 DEF 文件中，列出和导出状态适合进行定义。 
  
如果您想要避免进行提供 c + + 名称修饰 c + + 函数，您必须按如下方式声明函数。
  
```cpp
extern "C"
__declspec(dllexport) double WINAPI my_undecorated_Cpp_export(double x)
{
// Modify x and return it.
    return x * 2.0;
}
```

链接器将使该函数可用作 my_undecorated_Cpp_export，即，名称与无修饰源代码中所示。
  
### <a name="using-a-pragma-preprocessor-linker-directive"></a>使用 #pragma 预处理器链接器指令

最新版本的 Microsoft Visual Studio 支持两个预定义的宏，在与 **#pragma**指令一起使用时，使您能够让链接器导出函数代码中的直接从函数。 宏是__函数__和__FUNCDNAME__ （请注意两端双下划线） 它们分别扩展到未修饰和修饰函数名称。 
  
例如，当您使用 Microsoft Visual Studio，这些行可以合并到常见的头文件，如下所示。
  
```cpp
#if _MSC_VER > 1200 // Later than Visual Studio 6.0
#define EXPORT comment(linker, "/EXPORT:"__FUNCTION__"="__FUNCDNAME__)
#else // Cannot use this way of exporting functions.
#define EXPORT
#endif // else need to use DEF file or __declspec(dllexport)

```

如果源文件中包含此标头，两个示例函数可将其导出，如下所示。
  
C 代码：
  
```C
double WINAPI my_C_export(double x)
{
#pragma EXPORT
/* Modify x and return it. */
    return x * 2.0;
}
```

C + + 代码：
  
```cpp
double WINAPI my_Cpp_export(double x)
{
#pragma EXPORT
// Modify x and return it.
    return x * 2.0;
}
```

请注意，指令必须放置在函数的正文和仅展开时都不 **/EP**或 **/P**设置的编译器选项。 此方法删除需要 DEF 文件或 **__declspec(dllexport)** 声明，并保留功能代码其导出状态的规范。 
  
## <a name="see-also"></a>另请参阅

- [在 Excel 中访问 Dll](how-to-access-dlls-in-excel.md)
- [从 DLL 或 XLL 调用 Excel](calling-into-excel-from-the-dll-or-xll.md)
- [Excel Programming Concepts](excel-programming-concepts.md)
- [Developing Excel XLLs](developing-excel-xlls.md)

