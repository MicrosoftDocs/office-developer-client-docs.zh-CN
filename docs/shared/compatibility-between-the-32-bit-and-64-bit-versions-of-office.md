---
title: 32 位版 Office 与 64 位版 Office 的兼容性
ms.date: 04/27/2016
ms.audience: ITPro
ms.assetid: ff49dc9e-daf8-43cf-8802-51c2537ed561
description: 了解 32 位版 Office 如何与 64 位版 Office 保持兼容。
localization_priority: Priority
ms.openlocfilehash: b03323b37b242c9992c47cd737ae54f3f9bbf2ca
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359820"
---
# <a name="compatibility-between-the-32-bit-and-64-bit-versions-of-office"></a><span data-ttu-id="0461e-103">32 位版 Office 与 64 位版 Office 的兼容性</span><span class="sxs-lookup"><span data-stu-id="0461e-103">Compatibility between the 32-bit and 64-bit versions of Office</span></span>

<span data-ttu-id="0461e-104">了解 32 位版 Office 如何与 64 位版 Office 保持兼容。</span><span class="sxs-lookup"><span data-stu-id="0461e-104">Find out how the 32-bit version of Office is compatible with the 64-bit version of Office.</span></span>
  
<span data-ttu-id="0461e-105">Office 应用程序分为 32 位版和 64 位版。</span><span class="sxs-lookup"><span data-stu-id="0461e-105">Office applications are available in 32-bit and 64-bit versions.</span></span> 
  
<span data-ttu-id="0461e-106">使用 64 位版 Office，可以移动更多数据，从而提升功能性，例如在 Microsoft Excel 2010 中处理大量数据时。</span><span class="sxs-lookup"><span data-stu-id="0461e-106">The 64-bit versions of Office enable you to move more data around for increased capability, for example when you work with large numbers in Microsoft Excel 2010.</span></span> <span data-ttu-id="0461e-107">编写 32 位代码时，可使用 64 位版 Office，无需进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="0461e-107">When writing 32-bit code, you can use the 64-bit version of Office without any changes.</span></span> <span data-ttu-id="0461e-108">然而，在编写 64 位代码时，应确保代码包含特定关键字和条件编译常量，以确保代码与旧版 Office 保持向后兼容性，且执行的是正确代码（如果混用 32 位和 64 位代码的话）。</span><span class="sxs-lookup"><span data-stu-id="0461e-108">However, when you write 64-bit code, you should ensure that your code contains specific keywords and conditional compilation constants to ensure that the code is backward compatible with earlier version of Office, and that the correct code is being executed if you mix 32-bit and 64-bit code.</span></span>
  
<span data-ttu-id="0461e-109">Visual Basic for Applications 7.0 (VBA 7) 是在 64 位版 Office 中发布，可用于 32 位和 64 位应用程序。</span><span class="sxs-lookup"><span data-stu-id="0461e-109">Visual Basic for Applications 7.0 (VBA 7) is released in the 64-bit versions for Office, and it works with both 32-bit and 64-bit applications.</span></span> <span data-ttu-id="0461e-110">本文所述的更改仅适用于 64 位版 Office。</span><span class="sxs-lookup"><span data-stu-id="0461e-110">The changes described in this article apply only to the 64-bit versions of Office.</span></span> <span data-ttu-id="0461e-111">使用 32 位版 Microsoft Office，可使用在旧版 Office 中生成的解决方案，无需进一步修改。</span><span class="sxs-lookup"><span data-stu-id="0461e-111">Using the 32-bit versions of Microsoft Office enable you to use solutions built in previous versions of Office without further modifications.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0461e-112">默认情况下，在你安装 64 位版 Office 后，32 位版本也与 64 位系统一起安装了。</span><span class="sxs-lookup"><span data-stu-id="0461e-112">By default, when you install a 64-bit version of Office, you also install the 32-bit version is installed along with the 64-bit system.</span></span> <span data-ttu-id="0461e-113">必须显式选择 Microsoft Office 64 位版本安装选项。</span><span class="sxs-lookup"><span data-stu-id="0461e-113">You must explicitly select the Microsoft Office 64-bit version installation option.</span></span> 
  
<span data-ttu-id="0461e-114">在 VBA 7 中，必须更新现有 Windows API 语句（**Declare** 语句），才能支持 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="0461e-114">In VBA 7, you must update existing Windows API statements (**Declare** statements) to work with the 64-bit version.</span></span> <span data-ttu-id="0461e-115">此外，还必须在这些语句使用的用户定义类型中更新地址指针和显示窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="0461e-115">Additionally, you must update address pointers and display window handles in user-defined types that are used by these statements.</span></span> <span data-ttu-id="0461e-116">本文更详细地介绍了这一点，以及 32 位版和 64 位版之间的兼容性问题和建议解决方案。</span><span class="sxs-lookup"><span data-stu-id="0461e-116">This is discussed in more detail in this article as well as compatibility issues between the 32-bit and 64-bit versions and suggested solutions.</span></span> 
  
## <a name="comparing-32-bit-and-64-bit-systems"></a><span data-ttu-id="0461e-117">比较 32 位和 64 位系统</span><span class="sxs-lookup"><span data-stu-id="0461e-117">Comparing 32-bit and 64-bit systems</span></span>
<span data-ttu-id="0461e-118"><a name="odc_office_Compatibility32bit64bit_Comparing32BitSystemsto64BitSystems"> </a></span><span class="sxs-lookup"><span data-stu-id="0461e-118"></span></span>

<span data-ttu-id="0461e-119">与 32 位版相比，使用 64 位版 Office 生成的应用程序可以引用更大地址空间。</span><span class="sxs-lookup"><span data-stu-id="0461e-119">Applications built with the 64-bit versions of Office can reference larger address spaces than 32-bit versions.</span></span> <span data-ttu-id="0461e-120">也就是说，可以对数据使用比以往更多的物理内存，这样可能会减少在物理内存中移入和移出数据所需的开销</span><span class="sxs-lookup"><span data-stu-id="0461e-120">This means you can use more physical memory for data than before, potentially reducing the overhead spent moving data in and out of physical memory</span></span>
  
<span data-ttu-id="0461e-121">除了能够引用物理内存中的特定位置（称为“指针”）之外，还可以使用地址来引用显示窗口标识符（称为“句柄”）。</span><span class="sxs-lookup"><span data-stu-id="0461e-121">In addition to referring specific locations (known as pointers) in physical memory, you can also use addresses to reference display window identifiers (known as handles).</span></span> <span data-ttu-id="0461e-122">指针或句柄的大小（以字节为单位）取决于使用的是 32 位系统，还是 64 位系统。</span><span class="sxs-lookup"><span data-stu-id="0461e-122">The size (in bytes) of the pointer or handle depends on whether you're using a 32-bit or 64-bit system.</span></span> 
  
<span data-ttu-id="0461e-123">若要使用 64 位版 Office 运行现有解决方案，请注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="0461e-123">If you want to run your existing solutions with the 64-bit versions of Office, be aware of the following:</span></span>
  
- <span data-ttu-id="0461e-124">Office 中的本机 64 位进程无法加载 32 位二进制文件。</span><span class="sxs-lookup"><span data-stu-id="0461e-124">Native 64-bit processes in Office cannot load 32-bit binaries.</span></span> <span data-ttu-id="0461e-125">这应该是在现有 Microsoft ActiveX 控件和加载项时的常见问题。</span><span class="sxs-lookup"><span data-stu-id="0461e-125">This is expected to be a common issue when you have existing Microsoft ActiveX controls and existing add-ins.</span></span>
    
- <span data-ttu-id="0461e-126">VBA 以前没有指针数据类型，因此必须使用 32 位变量来存储指针和句柄。</span><span class="sxs-lookup"><span data-stu-id="0461e-126">VBA previously didn't have a pointer data type, so you had to use 32-bit variables to store pointers and handles.</span></span> <span data-ttu-id="0461e-127">这些变量现在会截断在使用 **Declare** 语句时由 API 调用返回的 64 位值。</span><span class="sxs-lookup"><span data-stu-id="0461e-127">These variables now truncate 64-bit values returned by API calls when using **Declare** statements.</span></span> 
    
## <a name="vba-7-code-base"></a><span data-ttu-id="0461e-128">VBA 7 基准代码</span><span class="sxs-lookup"><span data-stu-id="0461e-128">VBA 7 code base</span></span>
<span data-ttu-id="0461e-129"><a name="odc_office_Compatibility32bit64bit_IntroducingVBA7CodeBase"> </a></span><span class="sxs-lookup"><span data-stu-id="0461e-129"></span></span>

<span data-ttu-id="0461e-130">VBA 7 替换 Office 2007 及更低版本中的 VBA 基准代码。</span><span class="sxs-lookup"><span data-stu-id="0461e-130">VBA 7 replaces the VBA code base in Office 2007 and earlier versions.</span></span> <span data-ttu-id="0461e-131">VBA 7 可用于 32 位版和 64 位版 Office。</span><span class="sxs-lookup"><span data-stu-id="0461e-131">VBA 7 is available in both the 32-bit and 64-bit versions of Office.</span></span> <span data-ttu-id="0461e-132">它提供以下两个条件编译常量：</span><span class="sxs-lookup"><span data-stu-id="0461e-132">It provides two conditional compilation constants:</span></span> 
  
- <span data-ttu-id="0461e-133">**VBA7** - 通过测试应用程序使用的是 VBA 7 还是旧版 VBA，有助于确保代码的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="0461e-133">**VBA7** - Helps ensure the backward compatibility of your code by testing whether your application is using VBA 7 or the previous version of VBA.</span></span> 
    
- <span data-ttu-id="0461e-134">**Win64** - 测试代码是运行为 32 位代码，还是运行为 64 位代码。</span><span class="sxs-lookup"><span data-stu-id="0461e-134">**Win64** Tests whether code is running as 32-bit or 64-bit.</span></span> 
    
<span data-ttu-id="0461e-135">除一些例外，如果文档中的宏可用于 32 位版应用程序，也可用于 64 位版应用程序。</span><span class="sxs-lookup"><span data-stu-id="0461e-135">With certain exceptions, the macros in a document that work in the 32-bit version of the application also work in the 64-bit version.</span></span>
  
## <a name="activex-control-and-com-add-in-compatibility"></a><span data-ttu-id="0461e-136">ActiveX 控件和 COM 加载项兼容性</span><span class="sxs-lookup"><span data-stu-id="0461e-136">ActiveX control and COM add-in compatibility</span></span>
<span data-ttu-id="0461e-137"><a name="odc_office_Compatibility32bit64bit_ActiveXControlCOMAddinCompatibility"> </a></span><span class="sxs-lookup"><span data-stu-id="0461e-137"></span></span>

<span data-ttu-id="0461e-138">现有 32 位 ActiveX 控件与 64 位版 Office 不兼容。</span><span class="sxs-lookup"><span data-stu-id="0461e-138">Existing 32-bit ActiveX controls, are not compatible with the 64-bit versions of Office.</span></span> <span data-ttu-id="0461e-139">对于 ActiveX 控件和 COM 对象：</span><span class="sxs-lookup"><span data-stu-id="0461e-139">For ActiveX controls and COM objects:</span></span>
  
- <span data-ttu-id="0461e-140">若有源代码，请自行生成 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="0461e-140">If you have the source code, generate a 64-bit version yourself.</span></span>
- <span data-ttu-id="0461e-141">若无源代码，请联系供应商，以获得更新后的版本。</span><span class="sxs-lookup"><span data-stu-id="0461e-141">If you don't have the source code, contact the vendor for an updated version.</span></span>
    
<span data-ttu-id="0461e-142">Office 中的本机 64 位进程无法加载 32 位二进制文件。</span><span class="sxs-lookup"><span data-stu-id="0461e-142">Native 64-bit processes in Office cannot load 32-bit binaries.</span></span> <span data-ttu-id="0461e-143">这包括 **MSComCtl** 的常见控件（TabStrip、Toolbar、StatusBar、ProgressBar、TreeView、ListViews、ImageList、Slider、ImageComboBox）和 **MSComCt2** 的控件（Animation、UpDown、MonthView、DateTimePicker、FlatScrollBar）。</span><span class="sxs-lookup"><span data-stu-id="0461e-143">This includes the common controls of **MSComCtl** (TabStrip, Toolbar, StatusBar, ProgressBar, TreeView, ListViews, ImageList, Slider, ImageComboBox) and the controls of **MSComCt2** (Animation, UpDown, MonthView, DateTimePicker, FlatScrollBar).</span></span> <span data-ttu-id="0461e-144">这些控件是由低于 Office 2010 的 32 位版 Office 进行安装。</span><span class="sxs-lookup"><span data-stu-id="0461e-144">These controls were installed by 32-bit versions of Office earlier than Office 2010.</span></span> <span data-ttu-id="0461e-145">将代码迁移到 64 位版 Office 时，必须寻找使用这些控件的现有 VBA 解决方案的替代方案。</span><span class="sxs-lookup"><span data-stu-id="0461e-145">You'll need to find an alternative for your existing VBA solutions that use these controls when you migrate the code to the 64-bit versions of Office.</span></span> 
  
## <a name="api-compatibility"></a><span data-ttu-id="0461e-146">API 兼容性</span><span class="sxs-lookup"><span data-stu-id="0461e-146">API compatibility</span></span>
<span data-ttu-id="0461e-147"><a name="odc_office_Compatibility32bit64bit_ApplicationProgrammingInterfaceCompatibility"> </a></span><span class="sxs-lookup"><span data-stu-id="0461e-147"></span></span>

<span data-ttu-id="0461e-148">通过结合使用 VBA 和类型库，可以使用许多功能来创建 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0461e-148">The combination of VBA and type libraries gives you lots of functionality to create Office applications.</span></span> <span data-ttu-id="0461e-149">不过，有时必须直接与计算机操作系统及其他组件通信，如在管理内存或进程时、在处理窗口和控件等 UI 元素时或在修改 Windows 注册表时。</span><span class="sxs-lookup"><span data-stu-id="0461e-149">However, sometimes you must communicate directly with the computer's operating system and other components, such as when you manage memory or processes, when working with UI elements linke windows and controls, or when modifying the Windows registry.</span></span> <span data-ttu-id="0461e-150">在这些情况下，最佳选择是使用 DLL 文件中嵌入的外部函数之一。</span><span class="sxs-lookup"><span data-stu-id="0461e-150">In these scenarios, your best option is to use one of the external functions that are embedded in DLL files.</span></span> <span data-ttu-id="0461e-151">为此，在 VBA 中，可使用 **Declare** 语句执行 API 调用。</span><span class="sxs-lookup"><span data-stu-id="0461e-151">You do this in VBA by making API calls using **Declare** statements.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0461e-152">Microsoft 提供了包含 1,500 条 Declare 语句的 Win32API.txt 文件，以及用于将所需 **Declare** 语句复制到代码中的工具。</span><span class="sxs-lookup"><span data-stu-id="0461e-152">Microsoft provides a Win32API.txt file that contains 1,500 Declare statements and a tool to copy the **Declare** statement that you want into your code.</span></span> <span data-ttu-id="0461e-153">不过，这些语句适用于 32 位系统，必须根据本文稍后介绍的信息转换为 64 位。</span><span class="sxs-lookup"><span data-stu-id="0461e-153">However, these statements are for 32-bit systems and must be converted to 64-bit by using the information discussed later in this article.</span></span> <span data-ttu-id="0461e-154">只有在使用 **PtrSafe** 属性将现有 **Declare** 语句标记为 64 位安全后，才能在 64 位 VBA 中编译这些语句。</span><span class="sxs-lookup"><span data-stu-id="0461e-154">Existing **Declare** statements won't compile in 64-bit VBA until they've been marked as safe for 64-bit by using the **PtrSafe** attribute.</span></span> <span data-ttu-id="0461e-155">有关此类转换的示例，可以访问 Excel MVP Jan Karel Pieterse 的网站 ([https://www.jkp-ads.com/articles/apideclarations.asp](https://www.jkp-ads.com/articles/apideclarations.asp))。</span><span class="sxs-lookup"><span data-stu-id="0461e-155">You can find examples of this type of conversion at Excel MVP Jan Karel Pieterse's website at [https://www.jkp-ads.com/articles/apideclarations.asp](https://www.jkp-ads.com/articles/apideclarations.asp).</span></span> <span data-ttu-id="0461e-156">[Office 代码兼容性检查器用户指南](https://technet.microsoft.com/zh-CN/library/ee833946%28office.14%29.aspx)是一款实用工具，可用于检查 API **Declare** 语句的语法中是否有 **PtrSafe** 属性，以及相应的返回类型（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="0461e-156">The [Office Code Compatibility Inspector user's guide](https://technet.microsoft.com/zh-CN/library/ee833946%28office.14%29.aspx) is a useful tool to inspect the syntax of API **Declare** statements for the **PtrSafe** attribute, if needed, and the appropriate return type.</span></span> 
  
<span data-ttu-id="0461e-157">**Declare** 语句类似于以下代码之一，具体取决于调用的是子例程（没有返回值）还是函数（有返回值）。</span><span class="sxs-lookup"><span data-stu-id="0461e-157">**Declare** statements resemble one of the following, depending on whether you are calling a subroutine (which has no return value) or a function (which does have a return value).</span></span> 
  
```vb
Public/Private Declare Sub SubName Lib "LibName" Alias "AliasName" (argument list)
Public/Private Declare Function FunctionName Lib "Libname" alias "aliasname" (argument list) As Type

```

<span data-ttu-id="0461e-158">**SubName** 函数或 **FunctionName** 函数替换为 DLL 文件中过程的实际名称，并表示通过 VBA 代码调用过程时使用的名称。</span><span class="sxs-lookup"><span data-stu-id="0461e-158">The **SubName** function or **FunctionName** function is replaced by the actual name of the procedure in the DLL file and represents the name that is used when the procedure is called from VBA code.</span></span> <span data-ttu-id="0461e-159">还可以对过程名称指定 **AliasName** 参数。</span><span class="sxs-lookup"><span data-stu-id="0461e-159">You can also specify an **AliasName** argument for the name of the procedure.</span></span> <span data-ttu-id="0461e-160">包含正在调用过程的 DLL 文件的名称跟在 **Lib** 关键字后面。</span><span class="sxs-lookup"><span data-stu-id="0461e-160">The name of the DLL file that contains the procedure being called follows the **Lib** keyword.</span></span> <span data-ttu-id="0461e-161">最后，参数列表包含必须传递给过程的参数和数据类型。</span><span class="sxs-lookup"><span data-stu-id="0461e-161">And finally, the argument list contains the parameters and the data types that must be passed to the procedure.</span></span> 
  
<span data-ttu-id="0461e-162">下面的 **Declare** 语句打开 Windows 注册表中的*子项*，并替换它的值。</span><span class="sxs-lookup"><span data-stu-id="0461e-162">The following **Declare** statement opens a  *subkey*  in the Windows registry and replaces its value.</span></span> 
  
```vb
Declare Function RegOpenKeyA Lib "advapi32.dll" (ByVal Key As Long, ByVal SubKey As String, NewKey As Long) As Long
```

<span data-ttu-id="0461e-163">**RegOpenKeyA** 函数的 Windows.h（窗口句柄）条目如下所示：</span><span class="sxs-lookup"><span data-stu-id="0461e-163">The Windows.h (window handle) entry for the **RegOpenKeyA** function is as follows:</span></span> 
  
```vb
LONG RegOpenKeyA ( HKEY hKey, LPCSTR lpSubKey, HKEY *phkResult );
```

<span data-ttu-id="0461e-164">在 Visual C 和 Microsoft Visual C++ 中，上一示例针对 32 位和 64 位进行了正确编译。</span><span class="sxs-lookup"><span data-stu-id="0461e-164">In Visual C and Microsoft Visual C++, the previous example compiles correctly for both 32-bit and 64-bit.</span></span> <span data-ttu-id="0461e-165">这是因为 HKEY 被定义为指针，它的大小反映了代码编译平台的内存大小。</span><span class="sxs-lookup"><span data-stu-id="0461e-165">This is because HKEY is defined as a pointer, whose size reflects the memory size of the platform that the code is compiled in.</span></span>
  
<span data-ttu-id="0461e-166">在旧版 VBA 中，由于没有具体指针数据类型，因此使用了 **Long** 数据类型。</span><span class="sxs-lookup"><span data-stu-id="0461e-166">In previous versions of VBA, there was no specific pointer data type so the **Long** data type was used.</span></span> <span data-ttu-id="0461e-167">由于 **Long** 数据类型始终是 32 位，因此在使用 64 位内存的系统中使用它时就会中断，因为上面的 32 位可能会被截断或覆盖其他内存地址。</span><span class="sxs-lookup"><span data-stu-id="0461e-167">And because the **Long** data type is always 32-bits, this breaks when used on a system with 64-bit memory because the upper 32-bits might be truncated or might overwrite other memory addresses.</span></span> <span data-ttu-id="0461e-168">这两种情况都可能会导致不可预测行为发生或系统故障。</span><span class="sxs-lookup"><span data-stu-id="0461e-168">Either of these situations can result in unpredictable behavior or system crashes.</span></span> 
  
<span data-ttu-id="0461e-169">为了解决此问题，VBA 添加了真正的*指针*数据类型：**LongPtr**。</span><span class="sxs-lookup"><span data-stu-id="0461e-169">To resolve this, VBA includes a true  *pointer*  data type: **LongPtr**.</span></span> <span data-ttu-id="0461e-170">使用这一新数据类型，可以将原始 **Declare** 语句正确编写为：</span><span class="sxs-lookup"><span data-stu-id="0461e-170">This new data type enables you to write the original **Declare** statement correctly as:</span></span> 
  
```vb
Declare PtrSafe Function RegOpenKeyA Lib "advapire32.dll" (ByVal hKey as LongPtr, ByVal lpSubKey As String, phkResult As LongPtr) As Long
```

<span data-ttu-id="0461e-171">结合使用这一数据类型和新 **PtrSafe** 属性，可以在 32 位或 64 位系统上使用此 **Declare** 语句。</span><span class="sxs-lookup"><span data-stu-id="0461e-171">This data type and the new **PtrSafe** attribute enable you to use this **Declare** statement on either 32-bit or 64-bit systems.</span></span> <span data-ttu-id="0461e-172">**PtrSafe**属性向 VBA 编译器指明，**Declare** 语句针对的是 64 位版 Office。</span><span class="sxs-lookup"><span data-stu-id="0461e-172">The **PtrSafe** attribute indicates to the VBA compiler that the **Declare** statement is targeted for the 64-bit version of Office.</span></span> <span data-ttu-id="0461e-173">如果没有这一属性，在 64 位系统中使用 **Declare** 语句会生成编译时错误。</span><span class="sxs-lookup"><span data-stu-id="0461e-173">Without this attribute, using the **Declare** statement in a 64-bit system will result in a compile-time error.</span></span> <span data-ttu-id="0461e-174">在 32 位版 Office 中，**PtrSafe** 是可选属性。</span><span class="sxs-lookup"><span data-stu-id="0461e-174">The **PtrSafe** attribute is optional on the 32-bit version of Office.</span></span> <span data-ttu-id="0461e-175">这样一来，现有 **Declare** 语句就可以像往常一样正常运行了。</span><span class="sxs-lookup"><span data-stu-id="0461e-175">This enables existing **Declare** statements to work as they always have.</span></span> 
  
<span data-ttu-id="0461e-176">下表详细介绍了新限定符和数据类型以及另一种数据类型、两个转换运算符和三个函数。</span><span class="sxs-lookup"><span data-stu-id="0461e-176">The following table provides more information about the new qualifier and data typeas well as another data type, two conversion operators, and three functions.</span></span>
  
|<span data-ttu-id="0461e-177">类型</span><span class="sxs-lookup"><span data-stu-id="0461e-177">Type</span></span>|<span data-ttu-id="0461e-178">Item</span><span class="sxs-lookup"><span data-stu-id="0461e-178">Item</span></span>|<span data-ttu-id="0461e-179">说明</span><span class="sxs-lookup"><span data-stu-id="0461e-179">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0461e-180">限定符</span><span class="sxs-lookup"><span data-stu-id="0461e-180">Qualifier</span></span>  <br/> |<span data-ttu-id="0461e-181">**PtrSafe**</span><span class="sxs-lookup"><span data-stu-id="0461e-181">**PtrSafe**</span></span> <br/> |<span data-ttu-id="0461e-p119">指明 **Declare** 语句与 64 位兼容。此属性是 64 位系统中的必需属性。</span><span class="sxs-lookup"><span data-stu-id="0461e-p119">Indicates that the **Declare** statement is compatible with 64-bits. This attribute is mandatory on 64-bit systems.  </span></span><br/> |
|<span data-ttu-id="0461e-184">数据类型</span><span class="sxs-lookup"><span data-stu-id="0461e-184">Data Type</span></span>  <br/> |<span data-ttu-id="0461e-185">**LongPtr**</span><span class="sxs-lookup"><span data-stu-id="0461e-185">**LongPtr**</span></span> <br/> |<span data-ttu-id="0461e-186">可变数据类型，在 32 位版 Microsoft Office 上为 4 字节数据类型，在 64 位版 Microsoft Office 上为 8 字节数据类型。</span><span class="sxs-lookup"><span data-stu-id="0461e-186">A variable data type which is a 4-bytes data type on 32-bit versions and an 8-byte data type on 64-bit versions of Microsoft Office.</span></span> <span data-ttu-id="0461e-187">这是为新代码声明指针或句柄的推荐方法，也是为旧代码声明指针或句柄的推荐方法（如果必须在 64 位版 Office 中运行的话）。</span><span class="sxs-lookup"><span data-stu-id="0461e-187">This is the recommended way of declaring a pointer or a handle for new code but also for legacy code if it has to run in the 64-bit version of Office.</span></span> <span data-ttu-id="0461e-188">只在 32 位和 64 位的 VBA 7 运行时中才受支持。</span><span class="sxs-lookup"><span data-stu-id="0461e-188">It is only supported in the VBA 7 runtime on 32-bit and 64-bit.</span></span> <span data-ttu-id="0461e-189">请注意，可以向它分配数值，但不能分配数值类型。</span><span class="sxs-lookup"><span data-stu-id="0461e-189">Note that you can assign numeric values to it but not numeric types.</span></span>  <br/> |
|<span data-ttu-id="0461e-190">数据类型</span><span class="sxs-lookup"><span data-stu-id="0461e-190">Data Type</span></span>  <br/> |<span data-ttu-id="0461e-191">**LongLong**</span><span class="sxs-lookup"><span data-stu-id="0461e-191">**LongLong**</span></span> <br/> |<span data-ttu-id="0461e-192">这是 8 字节数据类型，仅在 64 位版 Microsoft Office 中可用。</span><span class="sxs-lookup"><span data-stu-id="0461e-192">This is an 8-byte data type which is available only in 64-bit versions of Microsoft Office.</span></span> <span data-ttu-id="0461e-193">可以指定数值，但不能指定数值类型（以免发生截断）。</span><span class="sxs-lookup"><span data-stu-id="0461e-193">You can assign numeric values but not numeric types (to avoid truncation).</span></span>  <br/> |
|<span data-ttu-id="0461e-194">转换运算符</span><span class="sxs-lookup"><span data-stu-id="0461e-194">Conversion Operator</span></span>  <br/> |<span data-ttu-id="0461e-195">**CLngPtr**</span><span class="sxs-lookup"><span data-stu-id="0461e-195">**CLngPtr**</span></span> <br/> |<span data-ttu-id="0461e-196">将简单表达式转换为 **LongPtr** 数据类型。</span><span class="sxs-lookup"><span data-stu-id="0461e-196">Converts a simple expression to a **LongPtr** data type.</span></span>  <br/> |
|<span data-ttu-id="0461e-197">转换运算符</span><span class="sxs-lookup"><span data-stu-id="0461e-197">Conversion Operator</span></span>  <br/> |<span data-ttu-id="0461e-198">**CLngLng**</span><span class="sxs-lookup"><span data-stu-id="0461e-198">**CLngLng**</span></span> <br/> |<span data-ttu-id="0461e-199">将简单表达式转换为 **LongLong** 数据类型。</span><span class="sxs-lookup"><span data-stu-id="0461e-199">Converts a simple expression to a **LongLong** data type.</span></span>  <br/> |
|<span data-ttu-id="0461e-200">函数</span><span class="sxs-lookup"><span data-stu-id="0461e-200">Function</span></span>  <br/> |<span data-ttu-id="0461e-201">**VarPtr**</span><span class="sxs-lookup"><span data-stu-id="0461e-201">**VarPtr**</span></span> <br/> |<span data-ttu-id="0461e-p122">变体转换器。在 64 位版本上返回 **LongPtr**，在 32 位版本（4 字节）上返回 **Long**。</span><span class="sxs-lookup"><span data-stu-id="0461e-p122">Variant converter. Returns a **LongPtr** on 64-bit versions, and a **Long** on 32-bit versions (4 bytes).  </span></span><br/> |
|<span data-ttu-id="0461e-204">函数</span><span class="sxs-lookup"><span data-stu-id="0461e-204">Function</span></span>  <br/> |<span data-ttu-id="0461e-205">**ObjPtr**</span><span class="sxs-lookup"><span data-stu-id="0461e-205">**ObjPtr**</span></span> <br/> |<span data-ttu-id="0461e-p123">对象转换器。在 64 位版本上返回 **LongPtr**，在 32 位版本（4 字节）上返回 **Long**。</span><span class="sxs-lookup"><span data-stu-id="0461e-p123">Object converter. Returns a **LongPtr** on 64-bit versions, and a **Long** on 32-bit versions (4 bytes).  </span></span><br/> |
|<span data-ttu-id="0461e-208">函数</span><span class="sxs-lookup"><span data-stu-id="0461e-208">Function</span></span>  <br/> |<span data-ttu-id="0461e-209">**StrPtr**</span><span class="sxs-lookup"><span data-stu-id="0461e-209">**StrPtr**</span></span> <br/> |<span data-ttu-id="0461e-p124">字符串转换器。在 64 位版本上返回 **LongPtr**，在 32 位版本（4 字节）上返回 **Long**。</span><span class="sxs-lookup"><span data-stu-id="0461e-p124">String converter. Returns a **LongPtr** on 64-bit versions, and a **Long** on 32-bit versions (4 bytes).  </span></span><br/> |
   
<span data-ttu-id="0461e-212">下面的示例展示了如何在 **Declare** 语句中使用其中部分项。</span><span class="sxs-lookup"><span data-stu-id="0461e-212">The follow example shows how to use some of these items in a **Declare** statement.</span></span> 
  
```vb
Declare PtrSafe Function RegOpenKeyA Lib "advapi32.dll" (ByVal Key As LongPtr, ByVal SubKey As String, NewKey As LongPtr) As Long
```

<span data-ttu-id="0461e-213">请注意，没有 **PtrSafe** 属性的 **Declare** 语句被认定为与 64 位版 Office 不兼容。</span><span class="sxs-lookup"><span data-stu-id="0461e-213">Note that **Declare** statements without the **PtrSafe** attribute are assumed not to be compatible with the 64-bit version of Office.</span></span> 
  
<span data-ttu-id="0461e-214">有以下两个条件编译常量：**VBA7** 和 **Win64**。</span><span class="sxs-lookup"><span data-stu-id="0461e-214">There are two conditional compilation constants: **VBA7** and **Win64**.</span></span> <span data-ttu-id="0461e-215">为了确保与旧版 Microsoft Office 保持向后兼容性，可使用 **VBA7** 常量（这是更典型的情况），以防在旧版 Office 中使用 64 位代码。</span><span class="sxs-lookup"><span data-stu-id="0461e-215">To ensure backward compatibility with previous versions of Microsoft Office, you use the **VBA7** constant (this is the more typical case) to prevent 64-bit code from being used in the earlier version of Office.</span></span> <span data-ttu-id="0461e-216">对于因 32 位版本和 64 位版本而异的代码（如调用的数学 API 对 64 位版本使用 **LongLong**，而对 32 位版本使用 **Long**），可使用 **Win64** 常量。</span><span class="sxs-lookup"><span data-stu-id="0461e-216">For code that is different between the 32-bit version and the 64-bit version, such as calling a math API that uses **LongLong** for its 64-bit version and **Long** for its 32-bit version, you use the **Win64** constant.</span></span> <span data-ttu-id="0461e-217">下面的代码展示了如何使用这两个常量。</span><span class="sxs-lookup"><span data-stu-id="0461e-217">The following code shows the use of these two constants.</span></span> 
  
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

<span data-ttu-id="0461e-218">总而言之，如果编写 64 位代码并打算在旧版 Office 中使用它，不妨使用 **VBA7** 条件编译常量。</span><span class="sxs-lookup"><span data-stu-id="0461e-218">To summarize, if you write 64-bit code and intend to use it in previous versions of Office, you will want to use the **VBA7** conditional compilation constant.</span></span> <span data-ttu-id="0461e-219">不过，如果你在 Office 中编写 32 位代码，此代码的工作方式与在旧版 Office 中相同，无需编译常量。</span><span class="sxs-lookup"><span data-stu-id="0461e-219">However, if you write 32-bit code in Office, that code works as is in previous versions of Office without the need for the compilation constant.</span></span> <span data-ttu-id="0461e-220">若要确保对 32 位版本使用 32 位语句，并对 64 位版本使用 64 位语句，最佳选择是使用 **Win64** 条件编译常量。</span><span class="sxs-lookup"><span data-stu-id="0461e-220">If you want to ensure that you are using 32-bit statements for 32-bit versions and 64-bit statements for 64-bit versions, your best option is to use the **Win64** conditional compilation constant.</span></span> 
  
## <a name="using-conditional-compilation-attributes"></a><span data-ttu-id="0461e-221">使用条件编译属性</span><span class="sxs-lookup"><span data-stu-id="0461e-221">Using conditional compilation attributes</span></span>
<span data-ttu-id="0461e-222"><a name="odc_office_Compatibility32bit64bit_UsingConditionalCompilationAttributes"> </a></span><span class="sxs-lookup"><span data-stu-id="0461e-222"></span></span>

<span data-ttu-id="0461e-223">下面的示例展示了为 32 位版本编写的 VBA 代码（需要更新）。</span><span class="sxs-lookup"><span data-stu-id="0461e-223">The following example shows VBA code written for 32-bit that needs to be updated.</span></span> <span data-ttu-id="0461e-224">请注意，旧代码中的数据类型更新为使用 **LongPtr**，因为它们引用句柄或指针。</span><span class="sxs-lookup"><span data-stu-id="0461e-224">Notice the data types in the legacy code that are updated to use **LongPtr** because they refer to handles or pointers.</span></span> 
  
### <a name="vba-code-written-for-32-bit-versions"></a><span data-ttu-id="0461e-225">为 32 位版本编写的 VBA 代码</span><span class="sxs-lookup"><span data-stu-id="0461e-225">VBA code written for 32-bit versions</span></span>
  
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

### <a name="vba-code-rewritten-for-64-bit-versions"></a><span data-ttu-id="0461e-226">为 64 位版本重写的 VBA 代码</span><span class="sxs-lookup"><span data-stu-id="0461e-226">VBA code rewritten for 64-bit versions</span></span>
  
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

<span data-ttu-id="0461e-227"><a name="odc_office_Compatibility32bit64bit_FrequentlyAskedQuestions"> </a></span><span class="sxs-lookup"><span data-stu-id="0461e-227"></span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="0461e-228">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="0461e-228">Frequently asked questions</span></span>

#### <a name="when-should-i-use-the-64-bit-version-of-office"></a><span data-ttu-id="0461e-229">何时应使用 64 位版 Office？</span><span class="sxs-lookup"><span data-stu-id="0461e-229">When should I use the 64-bit version of Office?</span></span>
  
<span data-ttu-id="0461e-230">这个问题更像是要使用哪个主机应用程序（Excel、Word 等）。</span><span class="sxs-lookup"><span data-stu-id="0461e-230">This is more a matter of which host application (Excel, Word, and so forth) you are using.</span></span> <span data-ttu-id="0461e-231">例如，如果使用 64 位版 Microsoft Office，Excel 可以处理更大的工作表。</span><span class="sxs-lookup"><span data-stu-id="0461e-231">For example, Excel is able to handle much larger worksheets with the 64-bit version of Microsoft Office.</span></span>
  
#### <a name="can-i-install-64-bit-and-32-bit-versions-of-office-side-by-side"></a><span data-ttu-id="0461e-232">能否并行安装 64 位版和 32 位版 Office？</span><span class="sxs-lookup"><span data-stu-id="0461e-232">Can I install 64-bit and 32-bit versions of Office side-by-side?</span></span>
  
<span data-ttu-id="0461e-233">否。</span><span class="sxs-lookup"><span data-stu-id="0461e-233">No.</span></span>
  
#### <a name="when-should-i-convert-long-parameters-to-longptr"></a><span data-ttu-id="0461e-234">何时应将 Long 参数转换为 LongPtr？</span><span class="sxs-lookup"><span data-stu-id="0461e-234">When should I convert Long parameters to LongPtr?</span></span>
  
<span data-ttu-id="0461e-235">需要查看要调用函数在 Microsoft Developer Network 上的 Windows API 文档。</span><span class="sxs-lookup"><span data-stu-id="0461e-235">You need to check the Windows API documentation on the Microsoft Developers Network for the function you want to call.</span></span> <span data-ttu-id="0461e-236">必须将句柄和指针转换为 **LongPtr**。</span><span class="sxs-lookup"><span data-stu-id="0461e-236">Handles and pointers need to be converted to **LongPtr**.</span></span> <span data-ttu-id="0461e-237">例如，[RegOpenKeyA](https://msdn.microsoft.com/library/c8a590f2-3249-437f-a320-c7443d42b792.aspx) 的文档提供以下签名：</span><span class="sxs-lookup"><span data-stu-id="0461e-237">As an example, the documentation for [RegOpenKeyA](https://msdn.microsoft.com/library/c8a590f2-3249-437f-a320-c7443d42b792.aspx) provides the following signature:</span></span> 
  
```cs
LONG WINAPI RegOpenKeyEx(
  __in        HKEY hKey,
  __in_opt    LPCTSTR lpSubKey,
  __reserved  DWORD ulOptions,
  __in        REGSAM samDesired,
  __out       PHKEY phkResult
);
```

<span data-ttu-id="0461e-238">参数的定义如下：</span><span class="sxs-lookup"><span data-stu-id="0461e-238">The parameters are defined as:</span></span>
  
|<span data-ttu-id="0461e-239">参数</span><span class="sxs-lookup"><span data-stu-id="0461e-239">Parameter</span></span>|<span data-ttu-id="0461e-240">说明</span><span class="sxs-lookup"><span data-stu-id="0461e-240">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="0461e-241">hKey [in]</span><span class="sxs-lookup"><span data-stu-id="0461e-241">hKey [in]</span></span>  <br/> |<span data-ttu-id="0461e-242">打开注册表项的*句柄*。</span><span class="sxs-lookup"><span data-stu-id="0461e-242">A  *handle*  to an open registry key.</span></span>  <br/> |
|<span data-ttu-id="0461e-243">lpSubKey [in, optional]</span><span class="sxs-lookup"><span data-stu-id="0461e-243">lpSubKey [in, optional]</span></span>  <br/> |<span data-ttu-id="0461e-244">要打开的注册表子项的名称。</span><span class="sxs-lookup"><span data-stu-id="0461e-244">The name of the registry subkey to be opened.</span></span>  <br/> |
|<span data-ttu-id="0461e-245">ulOptions</span><span class="sxs-lookup"><span data-stu-id="0461e-245">ulOptions</span></span>  <br/> |<span data-ttu-id="0461e-246">此为保留参数，且必须为零。</span><span class="sxs-lookup"><span data-stu-id="0461e-246">This parameter is reserved and must be zero.</span></span>  <br/> |
|<span data-ttu-id="0461e-247">samDesired [in]</span><span class="sxs-lookup"><span data-stu-id="0461e-247">samDesired [in]</span></span>  <br/> |<span data-ttu-id="0461e-248">指定所需密钥访问权限的掩码。</span><span class="sxs-lookup"><span data-stu-id="0461e-248">A mask that specifies the desired access rights to the key.</span></span>  <br/> |
|<span data-ttu-id="0461e-249">phkResult [out]</span><span class="sxs-lookup"><span data-stu-id="0461e-249">phkResult [out]</span></span>  <br/> |<span data-ttu-id="0461e-250">指向接收已打开密钥的句柄的变量的*指针*。</span><span class="sxs-lookup"><span data-stu-id="0461e-250">A  *pointer*  to a variable that receives a handle to the opened key.</span></span>  <br/> |
   
<span data-ttu-id="0461e-251">在 [Win32API_PtrSafe.txt](https://www.microsoft.com/downloads/details.aspx?displaylang=en&amp;FamilyID=035b72a5-eef9-4baf-8dbc-63fbd2dd982b) 中，**Declare** 语句的定义如下：</span><span class="sxs-lookup"><span data-stu-id="0461e-251">In [Win32API_PtrSafe.txt](https://www.microsoft.com/downloads/details.aspx?displaylang=en&amp;FamilyID=035b72a5-eef9-4baf-8dbc-63fbd2dd982b), the **Declare** statement is defined as:</span></span> 
  
```vb
Declare PtrSafe Function RegOpenKeyEx Lib "advapi32.dll" Alias "RegOpenKeyExA" (ByVal hKey As LongPtr , ByVal lpSubKey As String, ByVal ulOptions As Long, ByVal samDesired As Long, phkResult As LongPtr ) As Long
```

#### <a name="should-i-convert-pointers-and-handles-in-structures"></a><span data-ttu-id="0461e-252">是否应在结构中转换指针和句柄？</span><span class="sxs-lookup"><span data-stu-id="0461e-252">Should I convert pointers and handles in structures?</span></span>
  
<span data-ttu-id="0461e-253">是。</span><span class="sxs-lookup"><span data-stu-id="0461e-253">Yes.</span></span> <span data-ttu-id="0461e-254">请参阅 Win32API_PtrSafe.txt 中的 **MSG** 类型：</span><span class="sxs-lookup"><span data-stu-id="0461e-254">See the **MSG** type in Win32API_PtrSafe.txt:</span></span> 
  
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

#### <a name="when-should-i-use-strptr-varpt-and-objptr"></a><span data-ttu-id="0461e-255">何时应使用 strptr、varpt 和 objptr？</span><span class="sxs-lookup"><span data-stu-id="0461e-255">When should I use strptr, varpt, and objptr?</span></span>
  
<span data-ttu-id="0461e-256">应使用这些函数来分别检索指向字符串、变量和对象的指针。</span><span class="sxs-lookup"><span data-stu-id="0461e-256">You should use these functions to retrieve pointers to strings, variables and objects, respectively.</span></span> <span data-ttu-id="0461e-257">在 64 位版 Office 上，这些函数返回可以传递给 **Declare** 语句的 64 位 **LongPtr**。</span><span class="sxs-lookup"><span data-stu-id="0461e-257">On the 64-bit version of Office, these functions will return a 64-bit **LongPtr**, which can be passed to **Declare** statements.</span></span> <span data-ttu-id="0461e-258">与旧版 VBA 相比，这些函数的用法没有改变。</span><span class="sxs-lookup"><span data-stu-id="0461e-258">The use of these functions has not changed from previous versions of VBA.</span></span> <span data-ttu-id="0461e-259">唯一区别是，它们现在返回 **LongPtr**。</span><span class="sxs-lookup"><span data-stu-id="0461e-259">The only difference is that they now return a **LongPtr**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0461e-260">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0461e-260">See also</span></span>
<span data-ttu-id="0461e-261"><a name="odc_office_Compatibility32bit64bit_AdditionalResources"> </a></span><span class="sxs-lookup"><span data-stu-id="0461e-261"></span></span>

- [<span data-ttu-id="0461e-262">Declare 语句剖析</span><span class="sxs-lookup"><span data-stu-id="0461e-262">Anatomy of a Declare Statement</span></span>](https://msdn.microsoft.com/library/office/aa671659.aspx)
    

