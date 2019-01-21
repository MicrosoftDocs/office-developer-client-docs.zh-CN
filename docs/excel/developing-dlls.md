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
# <a name="developing-dlls"></a><span data-ttu-id="ebfb5-104">开发 DLL</span><span class="sxs-lookup"><span data-stu-id="ebfb5-104">Developing DLLs</span></span>

<span data-ttu-id="ebfb5-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ebfb5-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="ebfb5-106">一个库表示一组经过编译的代码，为可执行应用程序提供一些功能和数据。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-106">A library is a body of compiled code that provides some functionality and data to an executable application.</span></span> <span data-ttu-id="ebfb5-107">库可以是静态链接的，也可以是动态链接的，两种情况下通常分别具有文件扩展名 .lib 和 .dll。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-107">Libraries can be either statically linked or dynamically linked, and they conventionally have the file name extensions .lib and .dll respectively.</span></span> <span data-ttu-id="ebfb5-108">静态库（例如 C 运行时库）在编译时链接到应用程序，因此成为生成的可执行文件的一部分。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-108">Static libraries (such as the C run-time library) are linked to the application at compilation and so become part of the resulting executable.</span></span> <span data-ttu-id="ebfb5-109">应用程序在需要 DLL 时（通常是在应用程序启动时）加载 DLL。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-109">The application loads a DLL when it is needed, usually when the application starts up.</span></span> <span data-ttu-id="ebfb5-110">一个 DLL 可以加载并动态链接到另一个 DLL。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-110">One DLL can load and dynamically link to another DLL.</span></span>
  
## <a name="benefits-of-using-dlls"></a><span data-ttu-id="ebfb5-111">使用 DLL 的好处</span><span class="sxs-lookup"><span data-stu-id="ebfb5-111">Benefits of using MDS</span></span>

<span data-ttu-id="ebfb5-112">DLL 的主要好处如下：</span><span class="sxs-lookup"><span data-stu-id="ebfb5-112">The main benefits of DLLs are as follows:</span></span>
  
- <span data-ttu-id="ebfb5-113">所有应用程序可以共享磁盘上的单个副本。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-113">All applications can share a single copy on disk.</span></span>
    
- <span data-ttu-id="ebfb5-114">应用程序的可执行文件保持较小。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-114">Applications' executable files are kept smaller.</span></span>
    
- <span data-ttu-id="ebfb5-115">它们使大型开发项目得以细分。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-115">They enable large development projects to be broken down.</span></span> <span data-ttu-id="ebfb5-116">应用程序和 DLL 开发人员只需要就各自部分之间的接口达成一致。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-116">Application and DLL developers only need agree an interface between their respective parts.</span></span> <span data-ttu-id="ebfb5-117">此接口由 DLL 导出。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-117">This interface is exported by the DLL.</span></span>
    
- <span data-ttu-id="ebfb5-118">DLL 开发人员可以更新 DLL（可能是为了提高它们的效率或修复 bug），而不必更新所有使用它的应用程序，但前提是 DLL 的导出接口不会改变。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-118">DLL developers can update DLLs—perhaps to make them more efficient or to fix a bug—without having to update all the applications that use it, provided that the exported interface of the DLL does not change.</span></span>
    
<span data-ttu-id="ebfb5-119">可以使用 DLL 在 Microsoft Excel 中添加工作表函数和命令。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-119">You can use DLLs to add worksheet functions and commands in Microsoft Excel.</span></span>
  
## <a name="resources-for-creating-dlls"></a><span data-ttu-id="ebfb5-120">用于创建 DLL 的资源</span><span class="sxs-lookup"><span data-stu-id="ebfb5-120">Resources for creating DLLs</span></span>

<span data-ttu-id="ebfb5-121">若要创建 DLL，你需要：</span><span class="sxs-lookup"><span data-stu-id="ebfb5-121">To create a DLL, you need the following:</span></span>
  
- <span data-ttu-id="ebfb5-122">源代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-122">A source code editor.</span></span>
    
- <span data-ttu-id="ebfb5-123">一个编译器，用于将源代码转换为与硬件兼容的目标代码。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-123">A compiler to turn source code into object code that is compatible with your hardware.</span></span>
    
- <span data-ttu-id="ebfb5-124">一个链接器，用于从静态库（如果使用）中添加代码以及创建可执行的 DLL 文件。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-124">A linker to add code from static libraries, where used, and to create the executable DLL file.</span></span>
    
<span data-ttu-id="ebfb5-125">诸如 Microsoft Visual Studio 之类的现代集成开发环境 (IDE) 可提供所有这些功能。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-125">Modern integrated development environments (IDEs), such as Microsoft Visual Studio, provide all of these things.</span></span> <span data-ttu-id="ebfb5-126">它们还提供了大量更多功能：智能编辑器、用于调试代码的工具、用于管理多个项目的工具、新项目向导以及许多其他重要工具。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-126">They also provide a great deal more: smart editors, tools to debug your code, tools to manage multiple projects, new project wizards, and many other important tools.</span></span>
  
<span data-ttu-id="ebfb5-127">可以使用多种语言（例如，C/C++、Pascal 和 Visual Basic）创建 DLL。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-127">You can create DLLs in several languages, for example, C/C++, Pascal and Visual Basic.</span></span> <span data-ttu-id="ebfb5-128">鉴于 Excel 附带的 API 源代码是 C 和 C++，本文档中仅考虑这两种语言。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-128">Given that the API source code provided with Excel is C and C++, only these two languages are considered in this documentation.</span></span>
  
## <a name="exporting-functions-and-commands"></a><span data-ttu-id="ebfb5-129">导出函数和命令</span><span class="sxs-lookup"><span data-stu-id="ebfb5-129">Exporting functions and commands</span></span>

<span data-ttu-id="ebfb5-130">在编译 DLL 项目时，编译器和链接器需要知道要导出哪些函数，以便使这些函数可用于应用程序。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-130">When compiling a DLL project, the compiler and linker need to know what functions are to be exported so that they can make them available to the application.</span></span> <span data-ttu-id="ebfb5-131">本部分将介绍如何实现此目的。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-131">This section describes the ways this can be done.</span></span>
  
<span data-ttu-id="ebfb5-132">编译器编译源代码时，通常会根据函数在源代码中的外观更改函数的名称。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-132">When compilers compile source code, in general, they change the names of the functions from their appearance in the source code.</span></span> <span data-ttu-id="ebfb5-133">编译器通常在所谓的“名称修饰”过程中通过在名称的开头和/或结尾添加内容来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-133">They usually do this by adding to the beginning and/or end of the name, in a process known as name decoration.</span></span> <span data-ttu-id="ebfb5-134">务必使用可由加载 DLL 的应用程序识别的名称导出函数。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-134">You need to make sure that the function is exported with a name that is recognizable to the application loading the DLL.</span></span> <span data-ttu-id="ebfb5-135">这可能意味着告诉链接器将修饰的名称与更简单的导出名称相关联。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-135">This can mean telling the linker to associate the decorated name with a simpler export name.</span></span> <span data-ttu-id="ebfb5-136">导出名称可以是最初出现在源代码中的名称，也可以是其他名称。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-136">The export name can be the name as it originally appeared in the source code, or something else.</span></span>
  
<span data-ttu-id="ebfb5-137">名称的修饰方式取决于语言以及如何指示编译器使函数可用（即调用约定）。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-137">The way the name is decorated depends on the language and how the compiler is instructed to make the function available, that is, the calling convention.</span></span> <span data-ttu-id="ebfb5-138">DLL 使用的 Windows 标准进程间调用约定称为 WinAPI 约定。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-138">The standard inter-process calling convention for Windows used by DLLs is known as the WinAPI convention.</span></span> <span data-ttu-id="ebfb5-139">此约定在 Windows 头文件中定义为 **WINAPI**，后者则是用 Win32 声明符 **__stdcall** 定义的。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-139">It is defined in Windows header files as **WINAPI**, which is in turn defined using the Win32 declarator **__stdcall**.</span></span>
  
<span data-ttu-id="ebfb5-140">用于 Excel 的 DLL 导出函数（无论是工作表函数、宏表等效函数还是用户定义的命令）应始终使用 **WINAPI** / **__stdcall** 调用约定。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-140">A DLL-export function for use with Excel (whether it is a worksheet function, macro-sheet equivalent function, or user-defined command) should always use the **WINAPI** / **__stdcall** calling convention.</span></span> <span data-ttu-id="ebfb5-141">有必要在函数的定义中显式包含 **WINAPI** 说明符，因为 Win32 编译器中的默认设置是使用 **__cdecl** 调用约定（如果没有指定，则也定义为 **WINAPIV**）。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-141">It is necessary to include the **WINAPI** specifier explicitly in the function's definition as the default in Win32 compilers is to use the **__cdecl** calling convention, also defined as **WINAPIV**, if none is specified.</span></span>
  
<span data-ttu-id="ebfb5-142">你可以告诉链接器要导出一个函数，并通过以下几种方式之一从外部获知函数名称：</span><span class="sxs-lookup"><span data-stu-id="ebfb5-142">You can tell the linker that a function is to be exported, and the name it is to be known by externally in one of several ways:</span></span>
  
- <span data-ttu-id="ebfb5-143">将函数放在 DEF 文件中的 **EXPORTS** 关键字后，并设定 DLL 项目设置以便在链接时引用此文件。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-143">Place the function in a DEF file after the **EXPORTS** keyword, and set your DLL project setting to reference this file when linking.</span></span> 
    
- <span data-ttu-id="ebfb5-144">在函数定义中使用 **__declspec(dllexport)** 声明符。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-144">Use the **__declspec(dllexport)** declarator in the function's definition.</span></span> 
    
- <span data-ttu-id="ebfb5-145">使用 **#pragma** 预处理器指令向链接器发送消息。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-145">Use a **#pragma** preprocessor directive to send a message to the linker.</span></span> 
    
<span data-ttu-id="ebfb5-146">虽然项目可以使用所有这三种方法，并且编译器和链接器支持这些方法，但不应尝试以多种方式导出同一个函数。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-146">Although your project can use all three methods and your compiler and linker support them, you should not try to export one function in more than one of these ways.</span></span> <span data-ttu-id="ebfb5-147">例如，假设一个 DLL 包含两个源代码模块：一个 C 和一个 C++，它们分别包含两个要导出的函数 **my\_C\_export** 和 **my\_Cpp\_export**。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-147">For example, suppose that a DLL contains two source code modules, one C and one C++, which contain two functions to be exported, **my\_C\_export** and **my\_Cpp\_export** respectively.</span></span> <span data-ttu-id="ebfb5-148">为简单起见，假设每个函数都采用单个双精度数值参数并返回相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-148">For simplicity, suppose that each function takes a single double-precision numerical argument and returns the same data type.</span></span> <span data-ttu-id="ebfb5-149">以下部分将说明如何分别使用这些方法导出每个函数。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-149">The alternatives for exporting each function by using each of these methods are outlined in the following sections.</span></span> 
  
### <a name="using-a-def-file"></a><span data-ttu-id="ebfb5-150">使用 DEF 文件</span><span class="sxs-lookup"><span data-stu-id="ebfb5-150">Using a DEF file</span></span>

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

<span data-ttu-id="ebfb5-151">DEF 文件需要包含以下行。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-151">The DEF file would then need to contain these lines.</span></span>
  
`EXPORTS my_C_export = _my_C_export@8  my_Cpp_export`

<br/>

<span data-ttu-id="ebfb5-152">**EXPORTS** 语句后面一行的一般语法如下所示。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-152">The general syntax of a line that follows an **EXPORTS** statement is as follows.</span></span> 
  
`entryname[=internalname] [@ordinal[NONAME]] [DATA] [PRIVATE]`

<span data-ttu-id="ebfb5-153">请注意，C 函数已经过修饰，但 DEF 文件显式强制链接器使用原始源代码名称公开该函数（在本示例中）。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-153">Note that the C function has been decorated, but the DEF file explicitly forces the linker to expose the function using the original source code name (in this example).</span></span> <span data-ttu-id="ebfb5-154">链接器使用原始代码名称隐式导出 C++ 函数，因此不必在 DEF 文件中包含修饰的名称。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-154">The linker implicitly exports the C++ function using the original code name, so that it is not necessary to include the decorated name in the DEF file.</span></span>
  
<span data-ttu-id="ebfb5-155">对于 32 位 Windows API 函数调用，C 编译函数的修饰约定如下：**function_name** 变为 _ **function_name@** _n_，其中 _n_ 是所有参数占用的字节数（以十进制数表示）以及每个四舍五入到最接近的四的倍数的字节数。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-155">For 32-bit Windows API function calls, the convention for the decoration of C-compiled functions is as follows: **function_name** becomes _ **function_name@** _n_ where  _n_ is the number of bytes expressed as a decimal taken up by all the arguments, with the bytes for each rounded up to the nearest multiple of four.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ebfb5-156">在 Win32 中，所有指针的宽度都是四个字节。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-156">All pointers are four bytes wide in Win32.</span></span> <span data-ttu-id="ebfb5-157">返回类型对名称修饰没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-157">The return type has no impact on name decoration.</span></span> 
  
<span data-ttu-id="ebfb5-158">通过在 extern "C" {…} 代码块中包含函数和所有函数原型，可以强制 C++ 编译器公开 C++ 函数的未修饰名称，</span><span class="sxs-lookup"><span data-stu-id="ebfb5-158">It is possible to force the C++ compiler to expose undecorated names for C++ functions by enclosing the function, and any function prototypes, within an extern "C" {…}</span></span> <span data-ttu-id="ebfb5-159">如本例中所示。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-159">block, as shown in this example.</span></span> <span data-ttu-id="ebfb5-160">（此处省略了大括号 **{}**，因为该声明仅引用紧跟在后面的函数代码块）。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-160">(The braces **{}** are omitted here because the declaration only refers to the function code block that immediately follows it).</span></span> 
  
```cpp
extern "C"
double WINAPI my_undecorated_Cpp_export(double x)
{
// Modify x and return it.
    return x * 2.0;
}

```

<span data-ttu-id="ebfb5-161">将 C 函数原型放在可包含在 C 或 C++ 源文件中的头文件内时，应包含以下预处理器指令。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-161">When you are placing C function prototypes in header files that could be included in C or C++ source files, you should include the following pre-processor directive.</span></span>
  
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

### <a name="using-the-declspecdllexport-declarator"></a><span data-ttu-id="ebfb5-162">使用 __declspec(dllexport) 声明符</span><span class="sxs-lookup"><span data-stu-id="ebfb5-162">Using the __declspec(dllexport) declarator</span></span>

<span data-ttu-id="ebfb5-163">可在如下所示的函数声明中使用 **__Declspec(dllexport)** 关键字。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-163">The **__declspec(dllexport)** keyword can be used in the declaration of the function as follows.</span></span> 
  
```cpp
__declspec(dllexport) double WINAPI my_C_export(double x)
{
/* Modify x and return it. */
    return x * 2.0;
}
```

<span data-ttu-id="ebfb5-164">必须在声明的最左侧添加 **__declspec(dllexport)** 关键字。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-164">The **__declspec(dllexport)** keyword must be added at the extreme left of the declaration.</span></span> <span data-ttu-id="ebfb5-165">这种方法的优点是该函数不需要在 DEF 文件中列出，并且导出状态与定义一致。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-165">The advantages of this approach are that the function does not need to be listed in a DEF file, and that the export status is right with the definition.</span></span> 
  
<span data-ttu-id="ebfb5-166">如果要避免使用 C++ 名称修饰来提供 C++ 函数，必须按如下方式声明函数。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-166">If you want to avoid a C++ function being made available with the C++ name decoration, you must declare the function as follows.</span></span>
  
```cpp
extern "C"
__declspec(dllexport) double WINAPI my_undecorated_Cpp_export(double x)
{
// Modify x and return it.
    return x * 2.0;
}
```

<span data-ttu-id="ebfb5-167">链接器将使该函数显示为 my_undecorated_Cpp_export，即源代码中显示的名称，没有任何修饰。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-167">The linker will make the function available as my_undecorated_Cpp_export, that is, the name as it appears in the source code with no decoration.</span></span>
  
### <a name="using-a-pragma-preprocessor-linker-directive"></a><span data-ttu-id="ebfb5-168">使用 #pragma 预处理器链接器指令</span><span class="sxs-lookup"><span data-stu-id="ebfb5-168">Using a #pragma preprocessor linker directive</span></span>

<span data-ttu-id="ebfb5-169">最新版本的 Microsoft Visual Studio 支持两个预定义的宏，当这些宏与 **#pragma** 指令结合使用时，可以指示链接器直接从函数代码中导出函数。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-169">Recent versions of Microsoft Visual Studio support two predefined macros that, when used in conjunction with a **#pragma** directive, enable you to instruct the linker to export the function directly from within the function code.</span></span> <span data-ttu-id="ebfb5-170">这些宏为 __FUNCTION__ 和 __FUNCDNAME__（注意两端的双下划线），它们分别扩展为未修饰和修饰的函数名称。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-170">The macros are __FUNCTION__ and __FUNCDNAME__ (note the double underline at each end) which are expanded to the undecorated and decorated function names respectively.</span></span> 
  
<span data-ttu-id="ebfb5-171">例如，使用 Microsoft Visual Studio 时，这些行可以合并到一个公共头文件中，如下所示。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-171">For example, when you are using Microsoft Visual Studio, these lines can be incorporated into a common header file as follows.</span></span>
  
```cpp
#if _MSC_VER > 1200 // Later than Visual Studio 6.0
#define EXPORT comment(linker, "/EXPORT:"__FUNCTION__"="__FUNCDNAME__)
#else // Cannot use this way of exporting functions.
#define EXPORT
#endif // else need to use DEF file or __declspec(dllexport)

```

<span data-ttu-id="ebfb5-172">如果此标头包含在源文件中，则可以按如下方式导出这两个示例函数。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-172">If this header is included in the source files, the two example functions can then be exported as follows.</span></span>
  
<span data-ttu-id="ebfb5-173">C 代码：</span><span class="sxs-lookup"><span data-stu-id="ebfb5-173">C code:</span></span>
  
```C
double WINAPI my_C_export(double x)
{
#pragma EXPORT
/* Modify x and return it. */
    return x * 2.0;
}
```

<span data-ttu-id="ebfb5-174">C++ 代码：</span><span class="sxs-lookup"><span data-stu-id="ebfb5-174">C++ code:</span></span>
  
```cpp
double WINAPI my_Cpp_export(double x)
{
#pragma EXPORT
// Modify x and return it.
    return x * 2.0;
}
```

<span data-ttu-id="ebfb5-175">请注意，该指令必须放在函数体内，并且只有在编译器选项 **/EP** 和 **/P** 均未设置时才会扩展。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-175">Note that the directive must be placed within the body of the function and is only expanded when neither of the compiler options **/EP** or **/P** is set.</span></span> <span data-ttu-id="ebfb5-176">此方法不需要 DEF 文件和 **__declspec(dllexport)** 声明，并使用函数代码保持其导出状态的指定。</span><span class="sxs-lookup"><span data-stu-id="ebfb5-176">This technique removes the need for a DEF file, or **__declspec(dllexport)** declaration, and keeps the specification of its export status with the function code.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ebfb5-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebfb5-177">See also</span></span>

- [<span data-ttu-id="ebfb5-178">在 Excel 中访问 DLL</span><span class="sxs-lookup"><span data-stu-id="ebfb5-178">Access DLLs in Excel</span></span>](how-to-access-dlls-in-excel.md)
- [<span data-ttu-id="ebfb5-179">从 DLL 或 XLL 调用 Excel</span><span class="sxs-lookup"><span data-stu-id="ebfb5-179">Calling into Excel from the DLL or XLL</span></span>](calling-into-excel-from-the-dll-or-xll.md)
- [<span data-ttu-id="ebfb5-180">Excel 编程概念</span><span class="sxs-lookup"><span data-stu-id="ebfb5-180">Excel Programming Concepts</span></span>](excel-programming-concepts.md)
- [<span data-ttu-id="ebfb5-181">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="ebfb5-181">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

