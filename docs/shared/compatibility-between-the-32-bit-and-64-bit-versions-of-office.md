---
title: 32 位和 64 位版本的 Office 之间的兼容性
ms.date: 04/27/2016
ms.audience: ITPro
localization_priority: Normal
ms.assetid: ff49dc9e-daf8-43cf-8802-51c2537ed561
description: 找出与 64 位版本的 Office 兼容 32 位版本的 Office 的方式。
ms.openlocfilehash: 924f7a1aa891addc5841e6cdefc5226dcb056096
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779559"
---
# <a name="compatibility-between-the-32-bit-and-64-bit-versions-of-office"></a><span data-ttu-id="6ec34-103">32 位和 64 位版本的 Office 之间的兼容性</span><span class="sxs-lookup"><span data-stu-id="6ec34-103">Compatibility between the 32-bit and 64-bit versions of Office</span></span>

<span data-ttu-id="6ec34-104">找出与 64 位版本的 Office 兼容 32 位版本的 Office 的方式。</span><span class="sxs-lookup"><span data-stu-id="6ec34-104">Find out how the 32-bit version of Office is compatible with the 64-bit version of Office.</span></span>
  
<span data-ttu-id="6ec34-105">Office 应用程序有 32 位和 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="6ec34-105">Office applications are available in 32-bit and 64-bit versions.</span></span> 
  
<span data-ttu-id="6ec34-106">64 位版本的 Office，您可以增加功能，例如，当您使用 Microsoft Excel 2010 中的大量移动多个数据。</span><span class="sxs-lookup"><span data-stu-id="6ec34-106">The 64-bit versions of Office enable you to move more data around for increased capability, for example when you work with large numbers in Microsoft Excel 2010.</span></span> <span data-ttu-id="6ec34-107">编写 32 位代码时，您可以使用 64 位版本的 Office 作任何更改。</span><span class="sxs-lookup"><span data-stu-id="6ec34-107">When writing 32-bit code, you can use the 64-bit version of Office without any changes.</span></span> <span data-ttu-id="6ec34-108">但是，当您编写 64 位代码，您应该确保您的代码包含特定关键词和条件编译常量，以确保了与早期版本的 Office，向后兼容的代码和正确的代码正在执行，如果您混合使用 32 位和 64 位的代码。</span><span class="sxs-lookup"><span data-stu-id="6ec34-108">However, when you write 64-bit code, you should ensure that your code contains specific keywords and conditional compilation constants to ensure that the code is backward compatible with earlier version of Office, and that the correct code is being executed if you mix 32-bit and 64-bit code.</span></span>
  
<span data-ttu-id="6ec34-109">Office、 释放的 64 位版本中的 Visual Basic for Applications (VBA 7) 7.0 时，它适用于 32 位和 64 位应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ec34-109">Visual Basic for Applications 7.0 (VBA 7) is released in the 64-bit versions for Office, and it works with both 32-bit and 64-bit applications.</span></span> <span data-ttu-id="6ec34-110">本文中介绍的更改仅应用于 Office 的 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="6ec34-110">The changes described in this article apply only to the 64-bit versions of Office.</span></span> <span data-ttu-id="6ec34-111">您可以使用解决方案使用 32 位版本的 Microsoft Office 启用内置的早期版本的 Office 不进一步进行修改。</span><span class="sxs-lookup"><span data-stu-id="6ec34-111">Using the 32-bit versions of Microsoft Office enable you to use solutions built in previous versions of Office without further modifications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ec34-112">默认情况下，当您安装 64 位版本的 Office，您还安装 32 位版本和 64 位系统安装。</span><span class="sxs-lookup"><span data-stu-id="6ec34-112">By default, when you install a 64-bit version of Office, you also install the 32-bit version is installed along with the 64-bit system.</span></span> <span data-ttu-id="6ec34-113">您必须明确选择 Microsoft Office 64 位版本安装选项。</span><span class="sxs-lookup"><span data-stu-id="6ec34-113">You must explicitly select the Microsoft Office 64-bit version installation option.</span></span> 
  
<span data-ttu-id="6ec34-114">在 VBA 7 中，则必须更新现有 Windows API 语句 （**Declare**语句） 以使用 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="6ec34-114">In VBA 7, you must update existing Windows API statements (**Declare** statements) to work with the 64-bit version.</span></span> <span data-ttu-id="6ec34-115">此外，必须更新地址指针，并显示在使用这些语句的用户定义类型的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="6ec34-115">Additionally, you must update address pointers and display window handles in user-defined types that are used by these statements.</span></span> <span data-ttu-id="6ec34-116">更多详细信息以及在本文中的 32 位和 64 位版本和建议的解决方案之间的兼容性问题如下所述。</span><span class="sxs-lookup"><span data-stu-id="6ec34-116">This is discussed in more detail in this article as well as compatibility issues between the 32-bit and 64-bit versions and suggested solutions.</span></span> 
  
## <a name="comparing-32-bit-and-64-bit-systems"></a><span data-ttu-id="6ec34-117">将 32 位和 64 位系统进行比较</span><span class="sxs-lookup"><span data-stu-id="6ec34-117">Comparing 32-bit and 64-bit systems</span></span>
<span data-ttu-id="6ec34-118"><a name="odc_office_Compatibility32bit64bit_Comparing32BitSystemsto64BitSystems"> </a></span><span class="sxs-lookup"><span data-stu-id="6ec34-118"></span></span>

<span data-ttu-id="6ec34-119">构建与 64 位版本的 Office 的应用程序可以引用比 32 位版本的较大地址空间。</span><span class="sxs-lookup"><span data-stu-id="6ec34-119">Applications built with the 64-bit versions of Office can reference larger address spaces than 32-bit versions.</span></span> <span data-ttu-id="6ec34-120">这意味着，您可以使用更多物理内存数据比之前，可能会降低的开销花费注销物理内存的移动数据</span><span class="sxs-lookup"><span data-stu-id="6ec34-120">This means you can use more physical memory for data than before, potentially reducing the overhead spent moving data in and out of physical memory</span></span>
  
<span data-ttu-id="6ec34-121">除了在物理内存中引用特定的位置 （称为指针），您可以使用地址引用 （称为句柄） 的显示窗口标识符。</span><span class="sxs-lookup"><span data-stu-id="6ec34-121">In addition to referring specific locations (known as pointers) in physical memory, you can also use addresses to reference display window identifiers (known as handles).</span></span> <span data-ttu-id="6ec34-122">（以字节为单位） 的指针或句柄的大小取决于您是否使用 32 位或 64 位系统。</span><span class="sxs-lookup"><span data-stu-id="6ec34-122">The size (in bytes) of the pointer or handle depends on whether you're using a 32-bit or 64-bit system.</span></span> 
  
<span data-ttu-id="6ec34-123">如果您想要使用 64 位版本的 Office 中运行的现有解决方案，请注意下列选项：</span><span class="sxs-lookup"><span data-stu-id="6ec34-123">If you want to run your existing solutions with the 64-bit versions of Office, be aware of the following:</span></span>
  
- <span data-ttu-id="6ec34-124">在 Office 中的本机 64 位进程中无法加载 32 位二进制文件。</span><span class="sxs-lookup"><span data-stu-id="6ec34-124">Native 64-bit processes in Office cannot load 32-bit binaries.</span></span> <span data-ttu-id="6ec34-125">此举有望时您具有现有的 Microsoft ActiveX 控件和现有外接程序是一个常见的问题。</span><span class="sxs-lookup"><span data-stu-id="6ec34-125">This is expected to be a common issue when you have existing Microsoft ActiveX controls and existing add-ins.</span></span>
    
- <span data-ttu-id="6ec34-126">VBA 以前没有指针数据类型，因此您必须使用 32 位变量来存储指针和句柄。</span><span class="sxs-lookup"><span data-stu-id="6ec34-126">VBA previously didn't have a pointer data type, so you had to use 32-bit variables to store pointers and handles.</span></span> <span data-ttu-id="6ec34-127">现在，这些变量截断使用**Declare**语句时 API 调用返回的 64 位值。</span><span class="sxs-lookup"><span data-stu-id="6ec34-127">These variables now truncate 64-bit values returned by API calls when using **Declare** statements.</span></span> 
    
## <a name="vba-7-code-base"></a><span data-ttu-id="6ec34-128">VBA 7 基本代码</span><span class="sxs-lookup"><span data-stu-id="6ec34-128">VBA 7 code base</span></span>
<span data-ttu-id="6ec34-129"><a name="odc_office_Compatibility32bit64bit_IntroducingVBA7CodeBase"> </a></span><span class="sxs-lookup"><span data-stu-id="6ec34-129"></span></span>

<span data-ttu-id="6ec34-130">VBA 7 替换基本 Office 2007 和早期版本中的 VBA 代码。</span><span class="sxs-lookup"><span data-stu-id="6ec34-130">VBA 7 replaces the VBA code base in Office 2007 and earlier versions.</span></span> <span data-ttu-id="6ec34-131">VBA 7 是 32 位和 64 位 Office 版本中可用。</span><span class="sxs-lookup"><span data-stu-id="6ec34-131">VBA 7 is available in both the 32-bit and 64-bit versions of Office.</span></span> <span data-ttu-id="6ec34-132">它提供了两个条件编译常量：</span><span class="sxs-lookup"><span data-stu-id="6ec34-132">It provides two conditional compilation constants:</span></span> 
  
- <span data-ttu-id="6ec34-133">**VBA7** -有助于确保通过测试您的应用程序使用 VBA 7 或 VBA 的早期版本是否在您的代码的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="6ec34-133">**VBA7** - Helps ensure the backward compatibility of your code by testing whether your application is using VBA 7 or the previous version of VBA.</span></span> 
    
- <span data-ttu-id="6ec34-134">**Win64**测试是否为 32 位或 64 位运行代码。</span><span class="sxs-lookup"><span data-stu-id="6ec34-134">**Win64** Tests whether code is running as 32-bit or 64-bit.</span></span> 
    
<span data-ttu-id="6ec34-135">某些例外情况外，32 位版本的应用程序中的文档中的宏也可在 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="6ec34-135">With certain exceptions, the macros in a document that work in the 32-bit version of the application also work in the 64-bit version.</span></span>
  
## <a name="activex-control-and-com-add-in-compatibility"></a><span data-ttu-id="6ec34-136">ActiveX 控件和 COM 加载项兼容性</span><span class="sxs-lookup"><span data-stu-id="6ec34-136">ActiveX control and COM add-in compatibility</span></span>
<span data-ttu-id="6ec34-137"><a name="odc_office_Compatibility32bit64bit_ActiveXControlCOMAddinCompatibility"> </a></span><span class="sxs-lookup"><span data-stu-id="6ec34-137"></span></span>

<span data-ttu-id="6ec34-138">现有的 32 位 ActiveX 控件，不与 64 位版本的 Office 兼容。</span><span class="sxs-lookup"><span data-stu-id="6ec34-138">Existing 32-bit ActiveX controls, are not compatible with the 64-bit versions of Office.</span></span> <span data-ttu-id="6ec34-139">ActiveX 控件和 COM 对象：</span><span class="sxs-lookup"><span data-stu-id="6ec34-139">For ActiveX controls and COM objects:</span></span>
  
- <span data-ttu-id="6ec34-140">如果您有自己生成的 64 位版本的源代码。</span><span class="sxs-lookup"><span data-stu-id="6ec34-140">If you have the source code, generate a 64-bit version yourself.</span></span>
- <span data-ttu-id="6ec34-141">如果您没有源代码，请将供应商联系以获取更新版本。</span><span class="sxs-lookup"><span data-stu-id="6ec34-141">If you don't have the source code, contact the vendor for an updated version.</span></span>
    
<span data-ttu-id="6ec34-142">在 Office 中的本机 64 位进程中无法加载 32 位二进制文件。</span><span class="sxs-lookup"><span data-stu-id="6ec34-142">Native 64-bit processes in Office cannot load 32-bit binaries.</span></span> <span data-ttu-id="6ec34-143">这包括**MSComCtl** （TabStrip、 工具栏、 状态栏、 进度栏、 TreeView、 列表视图、 ImageList、 滑块、 ImageComboBox） 的公共控件和控件的**MSComCt2** （动画、 上下、 MonthView、 DateTimePicker，FlatScrollBar)。</span><span class="sxs-lookup"><span data-stu-id="6ec34-143">This includes the common controls of **MSComCtl** (TabStrip, Toolbar, StatusBar, ProgressBar, TreeView, ListViews, ImageList, Slider, ImageComboBox) and the controls of **MSComCt2** (Animation, UpDown, MonthView, DateTimePicker, FlatScrollBar).</span></span> <span data-ttu-id="6ec34-144">这些控件安装 32 位版本的 Office 早于 Office 2010。</span><span class="sxs-lookup"><span data-stu-id="6ec34-144">These controls were installed by 32-bit versions of Office earlier than Office 2010.</span></span> <span data-ttu-id="6ec34-145">您需要查找现有 VBA 解决方案迁移到 64 位版本的 Office 代码时使用这些控件的替代项。</span><span class="sxs-lookup"><span data-stu-id="6ec34-145">You'll need to find an alternative for your existing VBA solutions that use these controls when you migrate the code to the 64-bit versions of Office.</span></span> 
  
## <a name="api-compatibility"></a><span data-ttu-id="6ec34-146">API 兼容性</span><span class="sxs-lookup"><span data-stu-id="6ec34-146">API compatibility</span></span>
<span data-ttu-id="6ec34-147"><a name="odc_office_Compatibility32bit64bit_ApplicationProgrammingInterfaceCompatibility"> </a></span><span class="sxs-lookup"><span data-stu-id="6ec34-147"></span></span>

<span data-ttu-id="6ec34-148">VBA 和类型库的组合为您提供了大量功能来创建 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ec34-148">The combination of VBA and type libraries gives you lots of functionality to create Office applications.</span></span> <span data-ttu-id="6ec34-149">但是，有时必须与您通信直接计算机的操作系统和其他组件，如管理时内存或过程，使用用户界面元素 linke windows 和控件，或修改 Windows 注册表时。</span><span class="sxs-lookup"><span data-stu-id="6ec34-149">However, sometimes you must communicate directly with the computer's operating system and other components, such as when you manage memory or processes, when working with UI elements linke windows and controls, or when modifying the Windows registry.</span></span> <span data-ttu-id="6ec34-150">在这些情况下，最好的选择是使用 DLL 文件中嵌入外部函数之一。</span><span class="sxs-lookup"><span data-stu-id="6ec34-150">In these scenarios, your best option is to use one of the external functions that are embedded in DLL files.</span></span> <span data-ttu-id="6ec34-151">执行此操作的 API 调用使用**Declare**语句在 VBA 中。</span><span class="sxs-lookup"><span data-stu-id="6ec34-151">You do this in VBA by making API calls using **Declare** statements.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6ec34-152">Microsoft 提供的 Win32API.txt 文件包含 1,500 Declare 语句和用于复制到您的代码所需的**Declare**语句的工具。</span><span class="sxs-lookup"><span data-stu-id="6ec34-152">Microsoft provides a Win32API.txt file that contains 1,500 Declare statements and a tool to copy the **Declare** statement that you want into your code.</span></span> <span data-ttu-id="6ec34-153">但是，这些语句的 32 位系统，并且必须转换为 64 位使用下文中讨论的信息。</span><span class="sxs-lookup"><span data-stu-id="6ec34-153">However, these statements are for 32-bit systems and must be converted to 64-bit by using the information discussed later in this article.</span></span> <span data-ttu-id="6ec34-154">现有**Declare**语句不会在 64 位 VBA 中编译，直到将它们标记为可安全执行 64-bit 使用**PtrSafe**属性。</span><span class="sxs-lookup"><span data-stu-id="6ec34-154">Existing **Declare** statements won't compile in 64-bit VBA until they've been marked as safe for 64-bit by using the **PtrSafe** attribute.</span></span> <span data-ttu-id="6ec34-155">您可以在 Excel MVP Jan Karel Pieterse 网站，找到此类型的转换的示例[http://www.jkp-ads.com/articles/apideclarations.asp](http://www.jkp-ads.com/articles/apideclarations.asp)。</span><span class="sxs-lookup"><span data-stu-id="6ec34-155">You can find examples of this type of conversion at Excel MVP Jan Karel Pieterse's website at [http://www.jkp-ads.com/articles/apideclarations.asp](http://www.jkp-ads.com/articles/apideclarations.asp).</span></span> <span data-ttu-id="6ec34-156">[Office 代码兼容性检查器用户指南](http://technet.microsoft.com/en-us/library/ee833946%28office.14%29.aspx)是一个非常有用的工具，如果需要请检查**PtrSafe**属性的 API **Declare**语句的语法和相应的返回类型。</span><span class="sxs-lookup"><span data-stu-id="6ec34-156">The [Office Code Compatibility Inspector user's guide](http://technet.microsoft.com/en-us/library/ee833946%28office.14%29.aspx) is a useful tool to inspect the syntax of API **Declare** statements for the **PtrSafe** attribute, if needed, and the appropriate return type.</span></span> 
  
<span data-ttu-id="6ec34-157">**Declare**语句类似于以下内容，具体取决于您调用的子例程 （没有返回值） 或函数 （有返回值） 之一。</span><span class="sxs-lookup"><span data-stu-id="6ec34-157">**Declare** statements resemble one of the following, depending on whether you are calling a subroutine (which has no return value) or a function (which does have a return value).</span></span> 
  
```vb
Public/Private Declare Sub SubName Lib "LibName" Alias "AliasName" (argument list)
Public/Private Declare Function FunctionName Lib "Libname" alias "aliasname" (argument list) As Type

```

<span data-ttu-id="6ec34-158">**SubName**函数或**FunctionName**函数替换为实际的 DLL 文件中的过程的名称和表示从 VBA 代码调用该过程时使用的名称。</span><span class="sxs-lookup"><span data-stu-id="6ec34-158">The **SubName** function or **FunctionName** function is replaced by the actual name of the procedure in the DLL file and represents the name that is used when the procedure is called from VBA code.</span></span> <span data-ttu-id="6ec34-159">您还可以指定**AliasName**参数的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="6ec34-159">You can also specify an **AliasName** argument for the name of the procedure.</span></span> <span data-ttu-id="6ec34-160">包含要调用的过程的 DLL 文件的名称都遵循**Lib**关键字。</span><span class="sxs-lookup"><span data-stu-id="6ec34-160">The name of the DLL file that contains the procedure being called follows the **Lib** keyword.</span></span> <span data-ttu-id="6ec34-161">和最后，参数列表包含的参数和必须要传递给过程的数据类型。</span><span class="sxs-lookup"><span data-stu-id="6ec34-161">And finally, the argument list contains the parameters and the data types that must be passed to the procedure.</span></span> 
  
<span data-ttu-id="6ec34-162">下面的**Declare**语句将在 Windows 注册表中打开一个*子项*并替换其值。</span><span class="sxs-lookup"><span data-stu-id="6ec34-162">The following **Declare** statement opens a  *subkey*  in the Windows registry and replaces its value.</span></span> 
  
```vb
Declare Function RegOpenKeyA Lib "advapi32.dll" (ByVal Key As Long, ByVal SubKey As String, NewKey As Long) As Long
```

<span data-ttu-id="6ec34-163">**RegOpenKeyA** 函数的 Windows.h（窗口句柄）条目如下所示：</span><span class="sxs-lookup"><span data-stu-id="6ec34-163">The Windows.h (window handle) entry for the **RegOpenKeyA** function is as follows:</span></span> 
  
```vb
LONG RegOpenKeyA ( HKEY hKey, LPCSTR lpSubKey, HKEY *phkResult );
```

<span data-ttu-id="6ec34-164">在 Visual C 和 Microsoft Visual c + + 中，上面的示例将编译正确的 32 位和 64 位。</span><span class="sxs-lookup"><span data-stu-id="6ec34-164">In Visual C and Microsoft Visual C++, the previous example compiles correctly for both 32-bit and 64-bit.</span></span> <span data-ttu-id="6ec34-165">这是因为 HKEY 被定义为的指针，其大小反映代码在编译平台的内存大小。</span><span class="sxs-lookup"><span data-stu-id="6ec34-165">This is because HKEY is defined as a pointer, whose size reflects the memory size of the platform that the code is compiled in.</span></span>
  
<span data-ttu-id="6ec34-166">在早期版本的 VBA，没有任何特定指针数据类型，以便使用已**Long**数据类型。</span><span class="sxs-lookup"><span data-stu-id="6ec34-166">In previous versions of VBA, there was no specific pointer data type so the **Long** data type was used.</span></span> <span data-ttu-id="6ec34-167">因为**长**数据类型始终是 32 位，因为高 32 位可能被截断，或者可能覆盖其他内存地址在使用 64 位系统上使用时此分隔符。</span><span class="sxs-lookup"><span data-stu-id="6ec34-167">And because the **Long** data type is always 32-bits, this breaks when used on a system with 64-bit memory because the upper 32-bits might be truncated or might overwrite other memory addresses.</span></span> <span data-ttu-id="6ec34-168">任何一种情况会导致不可预测的行为或系统崩溃。</span><span class="sxs-lookup"><span data-stu-id="6ec34-168">Either of these situations can result in unpredictable behavior or system crashes.</span></span> 
  
<span data-ttu-id="6ec34-169">若要解决此问题，VBA，包括 true*指针*数据类型： **LongPtr**。</span><span class="sxs-lookup"><span data-stu-id="6ec34-169">To resolve this, VBA includes a true  *pointer*  data type: **LongPtr**.</span></span> <span data-ttu-id="6ec34-170">此新的数据类型，您可以编写原始**Declare**语句正确为：</span><span class="sxs-lookup"><span data-stu-id="6ec34-170">This new data type enables you to write the original **Declare** statement correctly as:</span></span> 
  
```vb
Declare PtrSafe Function RegOpenKeyA Lib "advapire32.dll" (ByVal hKey as LongPtr, ByVal lpSubKey As String, phkResult As LongPtr) As Long
```

<span data-ttu-id="6ec34-171">此数据类型和新**PtrSafe**属性，可以使用此**Declare**语句在 32 位或 64 位系统上。</span><span class="sxs-lookup"><span data-stu-id="6ec34-171">This data type and the new **PtrSafe** attribute enable you to use this **Declare** statement on either 32-bit or 64-bit systems.</span></span> <span data-ttu-id="6ec34-172">**PtrSafe**属性指示 VBA 编译器**Declare**语句面向于 Office 的 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="6ec34-172">The **PtrSafe** attribute indicates to the VBA compiler that the **Declare** statement is targeted for the 64-bit version of Office.</span></span> <span data-ttu-id="6ec34-173">如果没有此属性，在 64 位系统使用**Declare**语句将导致编译时错误。</span><span class="sxs-lookup"><span data-stu-id="6ec34-173">Without this attribute, using the **Declare** statement in a 64-bit system will result in a compile-time error.</span></span> <span data-ttu-id="6ec34-174">在 32 位版本的 Office 可选**PtrSafe**属性。</span><span class="sxs-lookup"><span data-stu-id="6ec34-174">The **PtrSafe** attribute is optional on the 32-bit version of Office.</span></span> <span data-ttu-id="6ec34-175">这使现有的**Declare**语句，以便他们始终需要具有。</span><span class="sxs-lookup"><span data-stu-id="6ec34-175">This enables existing **Declare** statements to work as they always have.</span></span> 
  
<span data-ttu-id="6ec34-176">下表提供了有关新限定符和数据 typeas 以及另一种数据类型、 两个转换运算符和三个函数的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6ec34-176">The following table provides more information about the new qualifier and data typeas well as another data type, two conversion operators, and three functions.</span></span>
  
|<span data-ttu-id="6ec34-177">类型</span><span class="sxs-lookup"><span data-stu-id="6ec34-177">Type</span></span>|<span data-ttu-id="6ec34-178">项</span><span class="sxs-lookup"><span data-stu-id="6ec34-178">Item</span></span>|<span data-ttu-id="6ec34-179">说明</span><span class="sxs-lookup"><span data-stu-id="6ec34-179">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6ec34-180">限定符</span><span class="sxs-lookup"><span data-stu-id="6ec34-180">Qualifier</span></span>  <br/> |<span data-ttu-id="6ec34-181">**PtrSafe**</span><span class="sxs-lookup"><span data-stu-id="6ec34-181">**PtrSafe**</span></span> <br/> |<span data-ttu-id="6ec34-p119">指示 **Declare** 语句与 64 位兼容。此属性在 64 位系统上是必需的。</span><span class="sxs-lookup"><span data-stu-id="6ec34-p119">Indicates that the **Declare** statement is compatible with 64-bits. This attribute is mandatory on 64-bit systems.  </span></span><br/> |
|<span data-ttu-id="6ec34-184">数据类型</span><span class="sxs-lookup"><span data-stu-id="6ec34-184">Data Type</span></span>  <br/> |<span data-ttu-id="6ec34-185">**LongPtr**</span><span class="sxs-lookup"><span data-stu-id="6ec34-185">**LongPtr**</span></span> <br/> |<span data-ttu-id="6ec34-186">变量数据类型，这是在 32 位版本和 64 位版本的 Microsoft Office 8 字节数据类型的 4 个字节数据类型。</span><span class="sxs-lookup"><span data-stu-id="6ec34-186">A variable data type which is a 4-bytes data type on 32-bit versions and an 8-byte data type on 64-bit versions of Microsoft Office.</span></span> <span data-ttu-id="6ec34-187">这是 office 的声明指针或新代码还可以旧版代码句柄，如果它具有要在 64 位版本中运行的推荐的方法。</span><span class="sxs-lookup"><span data-stu-id="6ec34-187">This is the recommended way of declaring a pointer or a handle for new code but also for legacy code if it has to run in the 64-bit version of Office.</span></span> <span data-ttu-id="6ec34-188">它只是支持在 VBA 7 运行时在 32 位和 64 位。</span><span class="sxs-lookup"><span data-stu-id="6ec34-188">It is only supported in the VBA 7 runtime on 32-bit and 64-bit.</span></span> <span data-ttu-id="6ec34-189">请注意，可以将数字值分配给它，但不是数值类型。</span><span class="sxs-lookup"><span data-stu-id="6ec34-189">Note that you can assign numeric values to it but not numeric types.</span></span>  <br/> |
|<span data-ttu-id="6ec34-190">数据类型</span><span class="sxs-lookup"><span data-stu-id="6ec34-190">Data Type</span></span>  <br/> |<span data-ttu-id="6ec34-191">**LongLong**</span><span class="sxs-lookup"><span data-stu-id="6ec34-191">**LongLong**</span></span> <br/> |<span data-ttu-id="6ec34-192">这是 8 字节数据类型，这是仅在 64 位版本的 Microsoft Office 中可用。</span><span class="sxs-lookup"><span data-stu-id="6ec34-192">This is an 8-byte data type which is available only in 64-bit versions of Microsoft Office.</span></span> <span data-ttu-id="6ec34-193">您可以分配数值，但不是数字类型 （以避免被截断）。</span><span class="sxs-lookup"><span data-stu-id="6ec34-193">You can assign numeric values but not numeric types (to avoid truncation).</span></span>  <br/> |
|<span data-ttu-id="6ec34-194">转换运算符</span><span class="sxs-lookup"><span data-stu-id="6ec34-194">Conversion Operator</span></span>  <br/> |<span data-ttu-id="6ec34-195">**CLngPtr**</span><span class="sxs-lookup"><span data-stu-id="6ec34-195">**CLngPtr**</span></span> <br/> |<span data-ttu-id="6ec34-196">将简单表达式转换为 **LongPtr** 数据类型。</span><span class="sxs-lookup"><span data-stu-id="6ec34-196">Converts a simple expression to a **LongPtr** data type.</span></span>  <br/> |
|<span data-ttu-id="6ec34-197">转换运算符</span><span class="sxs-lookup"><span data-stu-id="6ec34-197">Conversion Operator</span></span>  <br/> |<span data-ttu-id="6ec34-198">**CLngLng**</span><span class="sxs-lookup"><span data-stu-id="6ec34-198">**CLngLng**</span></span> <br/> |<span data-ttu-id="6ec34-199">将简单表达式转换为 **LongLong** 数据类型。</span><span class="sxs-lookup"><span data-stu-id="6ec34-199">Converts a simple expression to a **LongLong** data type.</span></span>  <br/> |
|<span data-ttu-id="6ec34-200">函数</span><span class="sxs-lookup"><span data-stu-id="6ec34-200">Function</span></span>  <br/> |<span data-ttu-id="6ec34-201">**VarPtr**</span><span class="sxs-lookup"><span data-stu-id="6ec34-201">**VarPtr**</span></span> <br/> |<span data-ttu-id="6ec34-p122">变量转换器。在 64 位版本上返回 **LongPtr**，在 32 位版本上返回 **Long**（4 字节）。</span><span class="sxs-lookup"><span data-stu-id="6ec34-p122">Variant converter. Returns a **LongPtr** on 64-bit versions, and a **Long** on 32-bit versions (4 bytes).  </span></span><br/> |
|<span data-ttu-id="6ec34-204">函数</span><span class="sxs-lookup"><span data-stu-id="6ec34-204">Function</span></span>  <br/> |<span data-ttu-id="6ec34-205">**ObjPtr**</span><span class="sxs-lookup"><span data-stu-id="6ec34-205">**ObjPtr**</span></span> <br/> |<span data-ttu-id="6ec34-p123">对象转换器。在 64 位版本上返回 **LongPtr**，在 32 位版本上返回 **Long**（4 字节）。</span><span class="sxs-lookup"><span data-stu-id="6ec34-p123">Object converter. Returns a **LongPtr** on 64-bit versions, and a **Long** on 32-bit versions (4 bytes).  </span></span><br/> |
|<span data-ttu-id="6ec34-208">函数</span><span class="sxs-lookup"><span data-stu-id="6ec34-208">Function</span></span>  <br/> |<span data-ttu-id="6ec34-209">**StrPtr**</span><span class="sxs-lookup"><span data-stu-id="6ec34-209">**StrPtr**</span></span> <br/> |<span data-ttu-id="6ec34-p124">字符串转换器。在 64 位版本上返回 **LongPtr**，在 32 位版本上返回 **Long**（4 字节）。</span><span class="sxs-lookup"><span data-stu-id="6ec34-p124">String converter. Returns a **LongPtr** on 64-bit versions, and a **Long** on 32-bit versions (4 bytes).  </span></span><br/> |
   
<span data-ttu-id="6ec34-212">下面的示例演示如何在 **Declare** 语句中使用其中某些项。</span><span class="sxs-lookup"><span data-stu-id="6ec34-212">The follow example shows how to use some of these items in a **Declare** statement.</span></span> 
  
```vb
Declare PtrSafe Function RegOpenKeyA Lib "advapi32.dll" (ByVal Key As LongPtr, ByVal SubKey As String, NewKey As LongPtr) As Long
```

<span data-ttu-id="6ec34-213">请注意，没有**PtrSafe**属性的**Declare**语句被假定不为与 64 位版本的 Office 兼容。</span><span class="sxs-lookup"><span data-stu-id="6ec34-213">Note that **Declare** statements without the **PtrSafe** attribute are assumed not to be compatible with the 64-bit version of Office.</span></span> 
  
<span data-ttu-id="6ec34-214">有两个条件编译常量： **VBA7**和**Win64**。</span><span class="sxs-lookup"><span data-stu-id="6ec34-214">There are two conditional compilation constants: **VBA7** and **Win64**.</span></span> <span data-ttu-id="6ec34-215">若要确保与 Microsoft Office 早期版本向后的兼容，您使用**VBA7**常量 （这是多个典型大小写） 阻止 64 位代码在早期版本的 Office 中使用。</span><span class="sxs-lookup"><span data-stu-id="6ec34-215">To ensure backward compatibility with previous versions of Microsoft Office, you use the **VBA7** constant (this is the more typical case) to prevent 64-bit code from being used in the earlier version of Office.</span></span> <span data-ttu-id="6ec34-216">对于不同的 32 位版本和 64 位版本，如调用其 32 位版本，使用其 64 位版本的**LongLong**的 API 和**长**数学的代码中，您将使用**Win64**常量。</span><span class="sxs-lookup"><span data-stu-id="6ec34-216">For code that is different between the 32-bit version and the 64-bit version, such as calling a math API that uses **LongLong** for its 64-bit version and **Long** for its 32-bit version, you use the **Win64** constant.</span></span> <span data-ttu-id="6ec34-217">下面的代码演示如何使用这两个常量。</span><span class="sxs-lookup"><span data-stu-id="6ec34-217">The following code shows the use of these two constants.</span></span> 
  
```vb
#if Win64 then
   Declare PtrSafe Function MyMathFunc Lib "User32" (ByVal N As LongLong) As LongLong
#else
   Declare Function MyMathFunc Lib "User32" (ByVal N As Long) As Long
#end if
#if VBA7 then
   Declare PtrSafe Sub MessageBeep Lib "User32" (ByVal N AS Long)
#else
   Declare Sub MessageBeep Lib "User32" (ByVal N AS Long)
#end if
```

<span data-ttu-id="6ec34-218">总之，如果您编写 64-bit 代码和打算在早期版本的 Office 中使用它，您需要使用**VBA7**条件编译常量。</span><span class="sxs-lookup"><span data-stu-id="6ec34-218">To summarize, if you write 64-bit code and intend to use it in previous versions of Office, you will want to use the **VBA7** conditional compilation constant.</span></span> <span data-ttu-id="6ec34-219">但是，如果您在 Office 中编写 32 位代码，该代码将运行在早期版本的 Office，而无需编译常数原样。</span><span class="sxs-lookup"><span data-stu-id="6ec34-219">However, if you write 32-bit code in Office, that code works as is in previous versions of Office without the need for the compilation constant.</span></span> <span data-ttu-id="6ec34-220">如果您想要确保您使用的 32 位语句为 32 位版本和 64 位版本的 64 位语句，最好的选择是使用**Win64**条件编译常量。</span><span class="sxs-lookup"><span data-stu-id="6ec34-220">If you want to ensure that you are using 32-bit statements for 32-bit versions and 64-bit statements for 64-bit versions, your best option is to use the **Win64** conditional compilation constant.</span></span> 
  
## <a name="using-conditional-compilation-attributes"></a><span data-ttu-id="6ec34-221">使用条件编译属性</span><span class="sxs-lookup"><span data-stu-id="6ec34-221">Using conditional compilation attributes</span></span>
<span data-ttu-id="6ec34-222"><a name="odc_office_Compatibility32bit64bit_UsingConditionalCompilationAttributes"> </a></span><span class="sxs-lookup"><span data-stu-id="6ec34-222"></span></span>

<span data-ttu-id="6ec34-223">下面的示例演示为需要更新的 32 位编写 VBA 代码。</span><span class="sxs-lookup"><span data-stu-id="6ec34-223">The following example shows VBA code written for 32-bit that needs to be updated.</span></span> <span data-ttu-id="6ec34-224">请注意进行了更新以使用**LongPtr** ，因为它们引用的句柄或指针在旧的代码中的数据类型。</span><span class="sxs-lookup"><span data-stu-id="6ec34-224">Notice the data types in the legacy code that are updated to use **LongPtr** because they refer to handles or pointers.</span></span> 
  
### <a name="vba-code-written-for-32-bit-versions"></a><span data-ttu-id="6ec34-225">VBA 代码编写的 32 位版本</span><span class="sxs-lookup"><span data-stu-id="6ec34-225">VBA code written for 32-bit versions</span></span>
  
```vb
Declare Function SHBrowseForFolder Lib "shell32.dll" _
  Alias "SHBrowseForFolderA" (lpBrowseInfo As BROWSEINFO) As Long
  
Public Type BROWSEINFO
  hOwner As Long
  pidlRoot As Long
  pszDisplayName As String
  lpszTitle As String
  ulFlags As Long
  lpfn As Long
  lParam As Long
  iImage As Long
End Type
```

### <a name="vba-code-rewritten-for-64-bit-versions"></a><span data-ttu-id="6ec34-226">重写的 64 位版本的 VBA 代码</span><span class="sxs-lookup"><span data-stu-id="6ec34-226">VBA code rewritten for 64-bit versions</span></span>
  
```vb
#if VBA7 then    ' VBA7 
Declare PtrSafe Function SHBrowseForFolder Lib "shell32.dll" _
  Alias "SHBrowseForFolderA" (lpBrowseInfo As BROWSEINFO) As Long
Public Type BROWSEINFO
  hOwner As LongPtr
  pidlRoot As Long
  pszDisplayName As String
  lpszTitle As String
  ulFlags As Long
  lpfn As LongPtr
  lParam As LongPtr
  iImage As Long
End Type
 
#else    ' Downlevel when using previous version of VBA7
Declare Function SHBrowseForFolder Lib "shell32.dll" _
  Alias "SHBrowseForFolderA" (lpBrowseInfo As BROWSEINFO) As Long
Public Type BROWSEINFO
  hOwner As Long
  pidlRoot As Long
  pszDisplayName As String
  lpszTitle As String
  ulFlags As Long
  lpfn As Long
  lParam As Long
  iImage As Long
End Type
 
#end if
Sub TestSHBrowseForFolder ()
    Dim bInfo As BROWSEINFO
    Dim pidList As Long
    bInfo.pidlRoot = 0&amp;
    bInfo.ulFlags = &amp;H1
    pidList = SHBrowseForFolder(bInfo)
End Sub
```

<span data-ttu-id="6ec34-227"><a name="odc_office_Compatibility32bit64bit_FrequentlyAskedQuestions"> </a></span><span class="sxs-lookup"><span data-stu-id="6ec34-227"></span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="6ec34-228">常见问题</span><span class="sxs-lookup"><span data-stu-id="6ec34-228">Frequently asked questions</span></span>

#### <a name="when-should-i-use-the-64-bit-version-of-office"></a><span data-ttu-id="6ec34-229">何时应使用 64 位版本的 Office？</span><span class="sxs-lookup"><span data-stu-id="6ec34-229">When should I use the 64-bit version of Office?</span></span>
  
<span data-ttu-id="6ec34-230">这是您使用空格 （Excel、 Word 等） 的主机应用程序的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6ec34-230">This is more a matter of which host application (Excel, Word, and so forth) you are using.</span></span> <span data-ttu-id="6ec34-231">例如，Excel 就能够处理与 64 位版本的 Microsoft Office 量较大的工作表。</span><span class="sxs-lookup"><span data-stu-id="6ec34-231">For example, Excel is able to handle much larger worksheets with the 64-bit version of Microsoft Office.</span></span>
  
#### <a name="can-i-install-64-bit-and-32-bit-versions-of-office-side-by-side"></a><span data-ttu-id="6ec34-232">可以安装 64 位和 32 位版本的 Office 并行？</span><span class="sxs-lookup"><span data-stu-id="6ec34-232">Can I install 64-bit and 32-bit versions of Office side-by-side?</span></span>
  
<span data-ttu-id="6ec34-233">否。</span><span class="sxs-lookup"><span data-stu-id="6ec34-233">No.</span></span>
  
#### <a name="when-should-i-convert-long-parameters-to-longptr"></a><span data-ttu-id="6ec34-234">何时应将长的参数为 LongPtr？</span><span class="sxs-lookup"><span data-stu-id="6ec34-234">When should I convert Long parameters to LongPtr?</span></span>
  
<span data-ttu-id="6ec34-235">您需要检查您要呼叫的函数 Microsoft 开发人员网络上的 Windows API 文档。</span><span class="sxs-lookup"><span data-stu-id="6ec34-235">You need to check the Windows API documentation on the Microsoft Developers Network for the function you want to call.</span></span> <span data-ttu-id="6ec34-236">控点和指针需要转换为**LongPtr**。</span><span class="sxs-lookup"><span data-stu-id="6ec34-236">Handles and pointers need to be converted to **LongPtr**.</span></span> <span data-ttu-id="6ec34-237">例如，文档的[RegOpenKeyA](http://msdn.microsoft.com/library/c8a590f2-3249-437f-a320-c7443d42b792.aspx)提供了以下签名：</span><span class="sxs-lookup"><span data-stu-id="6ec34-237">As an example, the documentation for [RegOpenKeyA](http://msdn.microsoft.com/library/c8a590f2-3249-437f-a320-c7443d42b792.aspx) provides the following signature:</span></span> 
  
```cs
LONG WINAPI RegOpenKeyEx(
  __in        HKEY hKey,
  __in_opt    LPCTSTR lpSubKey,
  __reserved  DWORD ulOptions,
  __in        REGSAM samDesired,
  __out       PHKEY phkResult
);
```

<span data-ttu-id="6ec34-238">参数的定义如下：</span><span class="sxs-lookup"><span data-stu-id="6ec34-238">The parameters are defined as:</span></span>
  
|<span data-ttu-id="6ec34-239">参数</span><span class="sxs-lookup"><span data-stu-id="6ec34-239">Parameter</span></span>|<span data-ttu-id="6ec34-240">说明</span><span class="sxs-lookup"><span data-stu-id="6ec34-240">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="6ec34-241">[in] hKey</span><span class="sxs-lookup"><span data-stu-id="6ec34-241">hKey [in]</span></span>  <br/> |<span data-ttu-id="6ec34-242">*处理*打开注册表项。</span><span class="sxs-lookup"><span data-stu-id="6ec34-242">A  *handle*  to an open registry key.</span></span>  <br/> |
|<span data-ttu-id="6ec34-243">lpSubKey [中，可选]</span><span class="sxs-lookup"><span data-stu-id="6ec34-243">lpSubKey [in, optional]</span></span>  <br/> |<span data-ttu-id="6ec34-244">要打开注册表子项的名称。</span><span class="sxs-lookup"><span data-stu-id="6ec34-244">The name of the registry subkey to be opened.</span></span>  <br/> |
|<span data-ttu-id="6ec34-245">ulOptions</span><span class="sxs-lookup"><span data-stu-id="6ec34-245">ulOptions</span></span>  <br/> |<span data-ttu-id="6ec34-246">此参数是保留，且必须为零。</span><span class="sxs-lookup"><span data-stu-id="6ec34-246">This parameter is reserved and must be zero.</span></span>  <br/> |
|<span data-ttu-id="6ec34-247">[in] samDesired</span><span class="sxs-lookup"><span data-stu-id="6ec34-247">samDesired [in]</span></span>  <br/> |<span data-ttu-id="6ec34-248">指定到项的所需的访问权限掩码。</span><span class="sxs-lookup"><span data-stu-id="6ec34-248">A mask that specifies the desired access rights to the key.</span></span>  <br/> |
|<span data-ttu-id="6ec34-249">phkResult [out]</span><span class="sxs-lookup"><span data-stu-id="6ec34-249">phkResult [out]</span></span>  <br/> |<span data-ttu-id="6ec34-250">指向一个变量来接收打开密钥的句柄的*指针*。</span><span class="sxs-lookup"><span data-stu-id="6ec34-250">A  *pointer*  to a variable that receives a handle to the opened key.</span></span>  <br/> |
   
<span data-ttu-id="6ec34-251">在[Win32API_PtrSafe.txt](http://www.microsoft.com/downloads/details.aspx?displaylang=en&amp;FamilyID=035b72a5-eef9-4baf-8dbc-63fbd2dd982b)， **Declare**语句被定义为：</span><span class="sxs-lookup"><span data-stu-id="6ec34-251">In [Win32API_PtrSafe.txt](http://www.microsoft.com/downloads/details.aspx?displaylang=en&amp;FamilyID=035b72a5-eef9-4baf-8dbc-63fbd2dd982b), the **Declare** statement is defined as:</span></span> 
  
```vb
Declare PtrSafe Function RegOpenKeyEx Lib "advapi32.dll" Alias "RegOpenKeyExA" (ByVal hKey As LongPtr , ByVal lpSubKey As String, ByVal ulOptions As Long, ByVal samDesired As Long, phkResult As LongPtr ) As Long
```

#### <a name="should-i-convert-pointers-and-handles-in-structures"></a><span data-ttu-id="6ec34-252">应将转换指针和结构中的句柄？</span><span class="sxs-lookup"><span data-stu-id="6ec34-252">Should I convert pointers and handles in structures?</span></span>
  
<span data-ttu-id="6ec34-253">能。</span><span class="sxs-lookup"><span data-stu-id="6ec34-253">Yes.</span></span> <span data-ttu-id="6ec34-254">请参阅 Win32API_PtrSafe.txt 中的**MSG**类型：</span><span class="sxs-lookup"><span data-stu-id="6ec34-254">See the **MSG** type in Win32API_PtrSafe.txt:</span></span> 
  
```vb
Type MSG
    hwnd As LongPtr 
    message As Long
    wParam As LongPtr 
    lParam As LongPtr 
    time As Long
    pt As POINTAPI
End TypeF
```

#### <a name="when-should-i-use-strptr-varpt-and-objptr"></a><span data-ttu-id="6ec34-255">何时应使用 strptr、 varpt 和 objptr？</span><span class="sxs-lookup"><span data-stu-id="6ec34-255">When should I use strptr, varpt, and objptr?</span></span>
  
<span data-ttu-id="6ec34-256">应使用这些函数可以分别检索到字符串、 变量和对象的指针。</span><span class="sxs-lookup"><span data-stu-id="6ec34-256">You should use these functions to retrieve pointers to strings, variables and objects, respectively.</span></span> <span data-ttu-id="6ec34-257">在 64 位版本的 Office，这些函数将返回 64-bit **LongPtr**，其中可以传递给**Declare**语句。</span><span class="sxs-lookup"><span data-stu-id="6ec34-257">On the 64-bit version of Office, these functions will return a 64-bit **LongPtr**, which can be passed to **Declare** statements.</span></span> <span data-ttu-id="6ec34-258">未从早期版本的 VBA 更改这些函数的用法。</span><span class="sxs-lookup"><span data-stu-id="6ec34-258">The use of these functions has not changed from previous versions of VBA.</span></span> <span data-ttu-id="6ec34-259">唯一的区别是，他们现在返回为**LongPtr**。</span><span class="sxs-lookup"><span data-stu-id="6ec34-259">The only difference is that they now return a **LongPtr**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6ec34-260">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ec34-260">See also</span></span>
<span data-ttu-id="6ec34-261"><a name="odc_office_Compatibility32bit64bit_AdditionalResources"> </a></span><span class="sxs-lookup"><span data-stu-id="6ec34-261"></span></span>

- [<span data-ttu-id="6ec34-262">解析 Declare 语句</span><span class="sxs-lookup"><span data-stu-id="6ec34-262">Anatomy of a Declare Statement</span></span>](https://msdn.microsoft.com/en-us/library/office/aa671659.aspx)
    

