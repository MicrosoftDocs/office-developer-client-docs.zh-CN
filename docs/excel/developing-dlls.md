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
# <a name="developing-dlls"></a><span data-ttu-id="4f677-104">开发 Dll</span><span class="sxs-lookup"><span data-stu-id="4f677-104">Developing DLLs</span></span>

<span data-ttu-id="4f677-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4f677-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="4f677-106">库是提供了一些功能和数据到可执行应用程序的已编译代码的正文。</span><span class="sxs-lookup"><span data-stu-id="4f677-106">A library is a body of compiled code that provides some functionality and data to an executable application.</span></span> <span data-ttu-id="4f677-107">库可为静态链接或动态链接，并且其逆文件名称扩展名.lib 和.dll 分别。</span><span class="sxs-lookup"><span data-stu-id="4f677-107">Libraries can be either statically linked or dynamically linked, and they conventionally have the file name extensions .lib and .dll respectively.</span></span> <span data-ttu-id="4f677-108">静态库 （如 C 运行时库） 链接到应用程序在编译和因此成为生成可执行文件的一部分。</span><span class="sxs-lookup"><span data-stu-id="4f677-108">Static libraries (such as the C run-time library) are linked to the application at compilation and so become part of the resulting executable.</span></span> <span data-ttu-id="4f677-109">应用程序需要时，通常在应用程序启动时加载 DLL。</span><span class="sxs-lookup"><span data-stu-id="4f677-109">The application loads a DLL when it is needed, usually when the application starts up.</span></span> <span data-ttu-id="4f677-110">一个 DLL 可以加载并动态链接到另一个 DLL。</span><span class="sxs-lookup"><span data-stu-id="4f677-110">One DLL can load and dynamically link to another DLL.</span></span>
  
## <a name="benefits-of-using-dlls"></a><span data-ttu-id="4f677-111">使用 Dll 的好处</span><span class="sxs-lookup"><span data-stu-id="4f677-111">Benefits of using DLLs</span></span>

<span data-ttu-id="4f677-112">Dll 的主要优点如下所示：</span><span class="sxs-lookup"><span data-stu-id="4f677-112">The main benefits of DLLs are as follows:</span></span>
  
- <span data-ttu-id="4f677-113">所有应用程序可以共享在磁盘上的一个副本。</span><span class="sxs-lookup"><span data-stu-id="4f677-113">All applications can share a single copy on disk.</span></span>
    
- <span data-ttu-id="4f677-114">应用程序的可执行文件保持在较小。</span><span class="sxs-lookup"><span data-stu-id="4f677-114">Applications' executable files are kept smaller.</span></span>
    
- <span data-ttu-id="4f677-115">它们使大型开发项目细分。</span><span class="sxs-lookup"><span data-stu-id="4f677-115">They enable large development projects to be broken down.</span></span> <span data-ttu-id="4f677-116">应用程序和 DLL 开发人员只需同意及其各自的部件之间的接口。</span><span class="sxs-lookup"><span data-stu-id="4f677-116">Application and DLL developers only need agree an interface between their respective parts.</span></span> <span data-ttu-id="4f677-117">此接口将导出 dll。</span><span class="sxs-lookup"><span data-stu-id="4f677-117">This interface is exported by the DLL.</span></span>
    
- <span data-ttu-id="4f677-118">DLL 开发人员可以更新 Dll — 可能是为了使其更高效或修复 bug — 无需更新的所有应用程序使用它，前提是 DLL 的导出的接口不会更改。</span><span class="sxs-lookup"><span data-stu-id="4f677-118">DLL developers can update DLLs—perhaps to make them more efficient or to fix a bug—without having to update all the applications that use it, provided that the exported interface of the DLL does not change.</span></span>
    
<span data-ttu-id="4f677-119">您可以使用 Dll Microsoft Excel 中添加工作表函数和命令。</span><span class="sxs-lookup"><span data-stu-id="4f677-119">You can use DLLs to add worksheet functions and commands in Microsoft Excel.</span></span>
  
## <a name="resources-for-creating-dlls"></a><span data-ttu-id="4f677-120">有关创建 Dll 资源</span><span class="sxs-lookup"><span data-stu-id="4f677-120">Resources for creating DLLs</span></span>

<span data-ttu-id="4f677-121">若要创建一个 DLL，您需要以下各项：</span><span class="sxs-lookup"><span data-stu-id="4f677-121">To create a DLL, you need the following:</span></span>
  
- <span data-ttu-id="4f677-122">源代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="4f677-122">A source code editor.</span></span>
    
- <span data-ttu-id="4f677-123">编译器将变成对象代码与您的硬件兼容的源代码。</span><span class="sxs-lookup"><span data-stu-id="4f677-123">A compiler to turn source code into object code that is compatible with your hardware.</span></span>
    
- <span data-ttu-id="4f677-124">链接器从静态库添加代码，其中使用，以及创建可执行的 DLL 文件。</span><span class="sxs-lookup"><span data-stu-id="4f677-124">A linker to add code from static libraries, where used, and to create the executable DLL file.</span></span>
    
<span data-ttu-id="4f677-125">现代集成的开发环境 (Ide)，如 Microsoft Visual Studio 中，提供所有这些操作。</span><span class="sxs-lookup"><span data-stu-id="4f677-125">Modern integrated development environments (IDEs), such as Microsoft Visual Studio, provide all of these things.</span></span> <span data-ttu-id="4f677-126">他们还提供了大量的详细信息： 智能编辑器、 工具来调试代码、 工具来管理多个项目、 新项目向导和很多其他重要的工具。</span><span class="sxs-lookup"><span data-stu-id="4f677-126">They also provide a great deal more: smart editors, tools to debug your code, tools to manage multiple projects, new project wizards, and many other important tools.</span></span>
  
<span data-ttu-id="4f677-127">您可以在多个语言版本，例如，C/c + +、 Pascal 和 Visual Basic 中创建 Dll。</span><span class="sxs-lookup"><span data-stu-id="4f677-127">You can create DLLs in several languages, for example, C/C++, Pascal and Visual Basic.</span></span> <span data-ttu-id="4f677-128">假定 Excel 提供的 API 源代码，C 和 c + + 仅这两种语言视为本文档中。</span><span class="sxs-lookup"><span data-stu-id="4f677-128">Given that the API source code provided with Excel is C and C++, only these two languages are considered in this documentation.</span></span>
  
## <a name="exporting-functions-and-commands"></a><span data-ttu-id="4f677-129">导出函数和命令</span><span class="sxs-lookup"><span data-stu-id="4f677-129">Exporting functions and commands</span></span>

<span data-ttu-id="4f677-130">在编译的 DLL 项目时，编译器和链接器需要知道什么函数是要导出，以便他们可以使其可用于应用程序。</span><span class="sxs-lookup"><span data-stu-id="4f677-130">When compiling a DLL project, the compiler and linker need to know what functions are to be exported so that they can make them available to the application.</span></span> <span data-ttu-id="4f677-131">本节介绍进行这种方式。</span><span class="sxs-lookup"><span data-stu-id="4f677-131">This section describes the ways this can be done.</span></span>
  
<span data-ttu-id="4f677-132">编译器编译源代码，一般情况下，这些函数的名称从更改其源代码中的外观。</span><span class="sxs-lookup"><span data-stu-id="4f677-132">When compilers compile source code, in general, they change the names of the functions from their appearance in the source code.</span></span> <span data-ttu-id="4f677-133">他们通常执行此操作通过将添加到的开始和/或结束的名称，在进程中称为名称修饰。</span><span class="sxs-lookup"><span data-stu-id="4f677-133">They usually do this by adding to the beginning and/or end of the name, in a process known as name decoration.</span></span> <span data-ttu-id="4f677-134">您需要确保该函数导出到加载 DLL 时出错的应用程序可识别的名称。</span><span class="sxs-lookup"><span data-stu-id="4f677-134">You need to make sure that the function is exported with a name that is recognizable to the application loading the DLL.</span></span> <span data-ttu-id="4f677-135">这可能意味着告知链接器简单的导出名称相关联的修饰的名。</span><span class="sxs-lookup"><span data-stu-id="4f677-135">This can mean telling the linker to associate the decorated name with a simpler export name.</span></span> <span data-ttu-id="4f677-136">导出名称可以名称，如它最初出现在源代码，或其他内容。</span><span class="sxs-lookup"><span data-stu-id="4f677-136">The export name can be the name as it originally appeared in the source code, or something else.</span></span>
  
<span data-ttu-id="4f677-137">修饰名称的方式取决于语言和编译器将指示以使函数可用，即，调用约定。</span><span class="sxs-lookup"><span data-stu-id="4f677-137">The way the name is decorated depends on the language and how the compiler is instructed to make the function available, that is, the calling convention.</span></span> <span data-ttu-id="4f677-138">标准进程间 windows 使用 Dll 调用约定称为选择约定。</span><span class="sxs-lookup"><span data-stu-id="4f677-138">The standard inter-process calling convention for Windows used by DLLs is known as the WinAPI convention.</span></span> <span data-ttu-id="4f677-139">它被指在 Windows 头文件**选择**，其中使用 Win32 声明符 **__stdcall**反过来定义。</span><span class="sxs-lookup"><span data-stu-id="4f677-139">It is defined in Windows header files as **WINAPI**, which is in turn defined using the Win32 declarator **__stdcall**.</span></span>
  
<span data-ttu-id="4f677-140">用于 Excel （无论是工作表函数、 宏表等效函数或用户定义的命令） DLL 导出函数应该始终使用**选择** / **__stdcall**调用约定。</span><span class="sxs-lookup"><span data-stu-id="4f677-140">A DLL-export function for use with Excel (whether it is a worksheet function, macro-sheet equivalent function, or user-defined command) should always use the **WINAPI** / **__stdcall** calling convention.</span></span> <span data-ttu-id="4f677-141">它是必要 Win32 编译器中的默认设置是使用 **__cdecl**调用约定，如果未指定还定义为**WINAPIV**，如显式包含该函数的定义中的**选择**说明符。</span><span class="sxs-lookup"><span data-stu-id="4f677-141">It is necessary to include the **WINAPI** specifier explicitly in the function's definition as the default in Win32 compilers is to use the **__cdecl** calling convention, also defined as **WINAPIV**, if none is specified.</span></span>
  
<span data-ttu-id="4f677-142">您可以判断函数是要导出链接器和名称会能够由外部在几种方式之一：</span><span class="sxs-lookup"><span data-stu-id="4f677-142">You can tell the linker that a function is to be exported, and the name it is to be known by externally in one of several ways:</span></span>
  
- <span data-ttu-id="4f677-143">**导出**关键字之后, 将该函数放入 DEF 文件并将设置您的 DLL 项目设置，以在链接时引用此文件。</span><span class="sxs-lookup"><span data-stu-id="4f677-143">Place the function in a DEF file after the **EXPORTS** keyword, and set your DLL project setting to reference this file when linking.</span></span> 
    
- <span data-ttu-id="4f677-144">该函数的定义中使用 **__declspec(dllexport)** 声明符。</span><span class="sxs-lookup"><span data-stu-id="4f677-144">Use the **__declspec(dllexport)** declarator in the function's definition.</span></span> 
    
- <span data-ttu-id="4f677-145">使用 **#pragma**预处理器指令链接器发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="4f677-145">Use a **#pragma** preprocessor directive to send a message to the linker.</span></span> 
    
<span data-ttu-id="4f677-146">虽然您编译器和链接器支持这些项目可以使用所有三种方法，您应尝试导出中多个下列方法之一一个函数。</span><span class="sxs-lookup"><span data-stu-id="4f677-146">Although your project can use all three methods and your compiler and linker support them, you should not try to export one function in more than one of these ways.</span></span> <span data-ttu-id="4f677-147">例如，假设 DLL 包含两个源代码模块、 一个 C 和一个 c + +，其中包含要导出的两个函数，**我\_C\_导出**和**我\_Cpp\_导出**分别。</span><span class="sxs-lookup"><span data-stu-id="4f677-147">For example, suppose that a DLL contains two source code modules, one C and one C++, which contain two functions to be exported, **my\_C\_export** and **my\_Cpp\_export** respectively.</span></span> <span data-ttu-id="4f677-148">为了简单起见，假设每个函数采用单个双精度数字参数，并返回同一字段数据类型。</span><span class="sxs-lookup"><span data-stu-id="4f677-148">For simplicity, suppose that each function takes a single double-precision numerical argument and returns the same data type.</span></span> <span data-ttu-id="4f677-149">以下各节概述了用于将每个函数导出使用每种方法的替代方法。</span><span class="sxs-lookup"><span data-stu-id="4f677-149">The alternatives for exporting each function by using each of these methods are outlined in the following sections.</span></span> 
  
### <a name="using-a-def-file"></a><span data-ttu-id="4f677-150">使用 DEF 文件</span><span class="sxs-lookup"><span data-stu-id="4f677-150">Using a DEF file</span></span>

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

<span data-ttu-id="4f677-151">然后，DEF 文件需要包含这些行。</span><span class="sxs-lookup"><span data-stu-id="4f677-151">The DEF file would then need to contain these lines.</span></span>
  
`EXPORTS my_C_export = _my_C_export@8  my_Cpp_export`

<br/>

<span data-ttu-id="4f677-152">下面的**导出**语句的行的常规语法如下所示。</span><span class="sxs-lookup"><span data-stu-id="4f677-152">The general syntax of a line that follows an **EXPORTS** statement is as follows.</span></span> 
  
`entryname[=internalname] [@ordinal[NONAME]] [DATA] [PRIVATE]`

<span data-ttu-id="4f677-153">请注意，已修饰 C 函数，但 DEF 文件显式强制链接器公开使用原始源代码名称 （在本例中） 的函数。</span><span class="sxs-lookup"><span data-stu-id="4f677-153">Note that the C function has been decorated, but the DEF file explicitly forces the linker to expose the function using the original source code name (in this example).</span></span> <span data-ttu-id="4f677-154">链接器隐式导出使用原始代码名称，该 c + + 函数，以便不需要在 DEF 文件中包含的修饰的名。</span><span class="sxs-lookup"><span data-stu-id="4f677-154">The linker implicitly exports the C++ function using the original code name, so that it is not necessary to include the decorated name in the DEF file.</span></span>
  
<span data-ttu-id="4f677-155">对于 32 位 Windows API 函数调用，C 编译函数的修饰的约定是，如下所示：**兼容**成为 _ **@ 兼容** _n_其中_n_是由所有占用小数形式表示的字节数参数，每个字节会向上舍入到最接近的四个倍数。</span><span class="sxs-lookup"><span data-stu-id="4f677-155">For 32-bit Windows API function calls, the convention for the decoration of C-compiled functions is as follows: **function_name** becomes _ **function_name@** _n_ where  _n_ is the number of bytes expressed as a decimal taken up by all the arguments, with the bytes for each rounded up to the nearest multiple of four.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4f677-156">所有指针都是范围在 Win32 四个字节。</span><span class="sxs-lookup"><span data-stu-id="4f677-156">All pointers are four bytes wide in Win32.</span></span> <span data-ttu-id="4f677-157">返回类型名称修饰时不会影响。</span><span class="sxs-lookup"><span data-stu-id="4f677-157">The return type has no impact on name decoration.</span></span> 
  
<span data-ttu-id="4f677-158">可以强制 c + + 编译器公开未修饰 c + + 函数名称括函数和任何函数原型内外部"C"{...}</span><span class="sxs-lookup"><span data-stu-id="4f677-158">It is possible to force the C++ compiler to expose undecorated names for C++ functions by enclosing the function, and any function prototypes, within an extern "C" {…}</span></span> <span data-ttu-id="4f677-159">阻止，此例中所示。</span><span class="sxs-lookup"><span data-stu-id="4f677-159">block, as shown in this example.</span></span> <span data-ttu-id="4f677-160">(在大括号**{}** 因为声明仅涉及到紧跟在它后面的函数代码块此处省略)。</span><span class="sxs-lookup"><span data-stu-id="4f677-160">(The braces **{}** are omitted here because the declaration only refers to the function code block that immediately follows it).</span></span> 
  
```cpp
extern "C"
double WINAPI my_undecorated_Cpp_export(double x)
{
// Modify x and return it.
    return x * 2.0;
}

```

<span data-ttu-id="4f677-161">当您将无法 C 或 c + + 源文件中包含的头文件中放置 C 函数原型时，应该包括以下预处理器指令。</span><span class="sxs-lookup"><span data-stu-id="4f677-161">When you are placing C function prototypes in header files that could be included in C or C++ source files, you should include the following pre-processor directive.</span></span>
  
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

### <a name="using-the-declspecdllexport-declarator"></a><span data-ttu-id="4f677-162">使用 __declspec(dllexport) 声明符</span><span class="sxs-lookup"><span data-stu-id="4f677-162">Using the __declspec(dllexport) declarator</span></span>

<span data-ttu-id="4f677-163">**__Declspec(dllexport)** 关键字可在函数的声明，如下所示。</span><span class="sxs-lookup"><span data-stu-id="4f677-163">The **__declspec(dllexport)** keyword can be used in the declaration of the function as follows.</span></span> 
  
```cpp
__declspec(dllexport) double WINAPI my_C_export(double x)
{
/* Modify x and return it. */
    return x * 2.0;
}
```

<span data-ttu-id="4f677-164">必须在声明的最左侧添加 **__declspec(dllexport)** 关键字。</span><span class="sxs-lookup"><span data-stu-id="4f677-164">The **__declspec(dllexport)** keyword must be added at the extreme left of the declaration.</span></span> <span data-ttu-id="4f677-165">此方法的优点是函数不需要在 DEF 文件中，列出和导出状态适合进行定义。</span><span class="sxs-lookup"><span data-stu-id="4f677-165">The advantages of this approach are that the function does not need to be listed in a DEF file, and that the export status is right with the definition.</span></span> 
  
<span data-ttu-id="4f677-166">如果您想要避免进行提供 c + + 名称修饰 c + + 函数，您必须按如下方式声明函数。</span><span class="sxs-lookup"><span data-stu-id="4f677-166">If you want to avoid a C++ function being made available with the C++ name decoration, you must declare the function as follows.</span></span>
  
```cpp
extern "C"
__declspec(dllexport) double WINAPI my_undecorated_Cpp_export(double x)
{
// Modify x and return it.
    return x * 2.0;
}
```

<span data-ttu-id="4f677-167">链接器将使该函数可用作 my_undecorated_Cpp_export，即，名称与无修饰源代码中所示。</span><span class="sxs-lookup"><span data-stu-id="4f677-167">The linker will make the function available as my_undecorated_Cpp_export, that is, the name as it appears in the source code with no decoration.</span></span>
  
### <a name="using-a-pragma-preprocessor-linker-directive"></a><span data-ttu-id="4f677-168">使用 #pragma 预处理器链接器指令</span><span class="sxs-lookup"><span data-stu-id="4f677-168">Using a #pragma preprocessor linker directive</span></span>

<span data-ttu-id="4f677-169">最新版本的 Microsoft Visual Studio 支持两个预定义的宏，在与 **#pragma**指令一起使用时，使您能够让链接器导出函数代码中的直接从函数。</span><span class="sxs-lookup"><span data-stu-id="4f677-169">Recent versions of Microsoft Visual Studio support two predefined macros that, when used in conjunction with a **#pragma** directive, enable you to instruct the linker to export the function directly from within the function code.</span></span> <span data-ttu-id="4f677-170">宏是__函数__和__FUNCDNAME__ （请注意两端双下划线） 它们分别扩展到未修饰和修饰函数名称。</span><span class="sxs-lookup"><span data-stu-id="4f677-170">The macros are __FUNCTION__ and __FUNCDNAME__ (note the double underline at each end) which are expanded to the undecorated and decorated function names respectively.</span></span> 
  
<span data-ttu-id="4f677-171">例如，当您使用 Microsoft Visual Studio，这些行可以合并到常见的头文件，如下所示。</span><span class="sxs-lookup"><span data-stu-id="4f677-171">For example, when you are using Microsoft Visual Studio, these lines can be incorporated into a common header file as follows.</span></span>
  
```cpp
#if _MSC_VER > 1200 // Later than Visual Studio 6.0
#define EXPORT comment(linker, "/EXPORT:"__FUNCTION__"="__FUNCDNAME__)
#else // Cannot use this way of exporting functions.
#define EXPORT
#endif // else need to use DEF file or __declspec(dllexport)

```

<span data-ttu-id="4f677-172">如果源文件中包含此标头，两个示例函数可将其导出，如下所示。</span><span class="sxs-lookup"><span data-stu-id="4f677-172">If this header is included in the source files, the two example functions can then be exported as follows.</span></span>
  
<span data-ttu-id="4f677-173">C 代码：</span><span class="sxs-lookup"><span data-stu-id="4f677-173">C code:</span></span>
  
```C
double WINAPI my_C_export(double x)
{
#pragma EXPORT
/* Modify x and return it. */
    return x * 2.0;
}
```

<span data-ttu-id="4f677-174">C + + 代码：</span><span class="sxs-lookup"><span data-stu-id="4f677-174">C++ code:</span></span>
  
```cpp
double WINAPI my_Cpp_export(double x)
{
#pragma EXPORT
// Modify x and return it.
    return x * 2.0;
}
```

<span data-ttu-id="4f677-175">请注意，指令必须放置在函数的正文和仅展开时都不 **/EP**或 **/P**设置的编译器选项。</span><span class="sxs-lookup"><span data-stu-id="4f677-175">Note that the directive must be placed within the body of the function and is only expanded when neither of the compiler options **/EP** or **/P** is set.</span></span> <span data-ttu-id="4f677-176">此方法删除需要 DEF 文件或 **__declspec(dllexport)** 声明，并保留功能代码其导出状态的规范。</span><span class="sxs-lookup"><span data-stu-id="4f677-176">This technique removes the need for a DEF file, or **__declspec(dllexport)** declaration, and keeps the specification of its export status with the function code.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4f677-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f677-177">See also</span></span>

- [<span data-ttu-id="4f677-178">在 Excel 中访问 Dll</span><span class="sxs-lookup"><span data-stu-id="4f677-178">Access DLLs in Excel</span></span>](how-to-access-dlls-in-excel.md)
- [<span data-ttu-id="4f677-179">从 DLL 或 XLL 调用 Excel</span><span class="sxs-lookup"><span data-stu-id="4f677-179">Calling into Excel from the DLL or XLL</span></span>](calling-into-excel-from-the-dll-or-xll.md)
- [<span data-ttu-id="4f677-180">Excel Programming Concepts</span><span class="sxs-lookup"><span data-stu-id="4f677-180">Excel Programming Concepts</span></span>](excel-programming-concepts.md)
- [<span data-ttu-id="4f677-181">Developing Excel XLLs</span><span class="sxs-lookup"><span data-stu-id="4f677-181">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

