---
title: Excel XLL 开发中的已知的问题
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 已知的问题 [excel 2007]
localization_priority: Normal
ms.assetid: 3dfecc0b-a91c-448e-8721-5d3486b625fa
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 34784f6895386efe7e6c3ca7ec213c7d71931058
ms.sourcegitcommit: f139451a43598b59da22775333779df691df460a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "26685177"
---
# <a name="known-issues-in-excel-xll-development"></a><span data-ttu-id="6551e-104">Excel XLL 开发中的已知的问题</span><span class="sxs-lookup"><span data-stu-id="6551e-104">Known Issues in Excel XLL Development</span></span>

 <span data-ttu-id="6551e-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6551e-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="6551e-106">本主题介绍在 XLL 开发过程中可能会遇到的 Microsoft Excel 中的已知的问题。</span><span class="sxs-lookup"><span data-stu-id="6551e-106">This topic describes known issues in Microsoft Excel that you might encounter in XLL development.</span></span>
  
## <a name="unregistering-xll-commands-and-functions"></a><span data-ttu-id="6551e-107">正在注销 XLL 命令和函数</span><span class="sxs-lookup"><span data-stu-id="6551e-107">Unregistering XLL Commands and Functions</span></span>

<span data-ttu-id="6551e-108">时 XLL 注册函数或命令，Excel 创建资源的新名称，并将引用的 DLL 函数与该名称相关联。</span><span class="sxs-lookup"><span data-stu-id="6551e-108">When an XLL registers a function or command, Excel creates a new name for the resource and associates a reference to the DLL function with that name.</span></span> <span data-ttu-id="6551e-109">名称取自第四个参数， *pxFunctionText* ， [xlfRegister](xlfregister-form-1.md)函数。</span><span class="sxs-lookup"><span data-stu-id="6551e-109">The name is taken from the fourth argument,  *pxFunctionText*  , of the [xlfRegister](xlfregister-form-1.md) function.</span></span> <span data-ttu-id="6551e-110">从管理工作表名称普通对话框中，此名称处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="6551e-110">This name is hidden from the normal dialog boxes for managing worksheet names.</span></span> <span data-ttu-id="6551e-111">取消注册的函数或命令，您必须通过使用[xlfSetName](xlfsetname.md)函数，传递的名称，但不是传递定义删除的名称。</span><span class="sxs-lookup"><span data-stu-id="6551e-111">To unregister a function or command, you must delete the name by using the [xlfSetName](xlfsetname.md) function, passing the name but not passing a definition.</span></span> <span data-ttu-id="6551e-112">但是，bug 阻止此移除函数向导列表的名称。</span><span class="sxs-lookup"><span data-stu-id="6551e-112">However, a bug prevents this from removing the name from the Function Wizard lists.</span></span> 
  
## <a name="argument-description-string-truncation-in-the-function-wizard"></a><span data-ttu-id="6551e-113">在函数向导的参数说明字符串截断</span><span class="sxs-lookup"><span data-stu-id="6551e-113">Argument Description String Truncation in the Function Wizard</span></span>

<span data-ttu-id="6551e-114">*PxArgumentHelp1*参数和所有后续**xlfRegister**函数参数是可选的对应于 XLL 函数的参数的字符串。</span><span class="sxs-lookup"><span data-stu-id="6551e-114">The  *pxArgumentHelp1*  parameter and all subsequent parameters of the **xlfRegister** function are optional strings that correspond to the arguments of the XLL function.</span></span> <span data-ttu-id="6551e-115">函数向导显示这些提供参数构造对话框中的帮助。</span><span class="sxs-lookup"><span data-stu-id="6551e-115">The Function Wizard displays these to provide help in the argument construction dialog box.</span></span> <span data-ttu-id="6551e-116">有时，Excel 将截断对应的最后一个参数由一个或两个字符时显示在对话框中的字符串。</span><span class="sxs-lookup"><span data-stu-id="6551e-116">Sometimes Excel truncates the string that corresponds to the final argument by one or two characters when displaying it in the dialog box.</span></span> <span data-ttu-id="6551e-117">可以通过添加其他"空字符串"作为函数注册的最后一个"参数帮助"参数来避免这种情况。</span><span class="sxs-lookup"><span data-stu-id="6551e-117">You can avoid this by adding an additional "empty string" as the last "argument help" parameter of your function registration.</span></span>
  
## <a name="binary-name-scope-limitation"></a><span data-ttu-id="6551e-118">二进制文件名称范围限制</span><span class="sxs-lookup"><span data-stu-id="6551e-118">Binary Name Scope Limitation</span></span>

<span data-ttu-id="6551e-119">仅在创建时所时处于活动状态的工作表再次处于活动状态时，可以检索二进制名称和它们的数据。</span><span class="sxs-lookup"><span data-stu-id="6551e-119">Binary names and their data can be retrieved only when the worksheet that was active at the time they were created is again active.</span></span> <span data-ttu-id="6551e-120">因为工作表函数 （仅命令可以执行此操作） 无法激活工作簿中的工作表，应用程序的二进制名称是非常有限。</span><span class="sxs-lookup"><span data-stu-id="6551e-120">Because worksheet functions cannot activate worksheets within a workbook (only commands can do this), applications of binary names are very limited.</span></span> <span data-ttu-id="6551e-121">如果您有才会调用从特定的表中的命令，例如，可以使用二进制文件的名称来存储与命令相关的数据。</span><span class="sxs-lookup"><span data-stu-id="6551e-121">If you have a command that is only invoked from a particular worksheet, for example, you could use a binary name to store command-related data.</span></span>
  
## <a name="xlset-and-workbooks-with-array-formulas"></a><span data-ttu-id="6551e-122">xlset，则和使用数组公式的工作簿</span><span class="sxs-lookup"><span data-stu-id="6551e-122">xlSet and Workbooks with Array Formulas</span></span>

<span data-ttu-id="6551e-123">在 Excel 2003 和早期版本中，如果您尝试将值分配给不是活动工作表，其中活动工作表上等效的范围包含数组公式的形式为工作表区域[xlset，则函数](xlset.md)将失败。</span><span class="sxs-lookup"><span data-stu-id="6551e-123">In Excel 2003 and earlier versions, the [xlSet function](xlset.md) fails if you try to assign values to a range on a worksheet that is not the active worksheet, where the equivalent range on the active sheet contains an array formula.</span></span> <span data-ttu-id="6551e-124">在这种情况下，Excel 将显示消息"无法更改为数组的一部分。"</span><span class="sxs-lookup"><span data-stu-id="6551e-124">In this case, Excel displays the message "You cannot change part of an array."</span></span> <span data-ttu-id="6551e-125">这被固定在 Excel 2007 中。</span><span class="sxs-lookup"><span data-stu-id="6551e-125">This was fixed in Excel 2007.</span></span> 
  
## <a name="circular-references-are-tolerated-in-data-tables"></a><span data-ttu-id="6551e-126">循环引用容许模拟运算表中</span><span class="sxs-lookup"><span data-stu-id="6551e-126">Circular References are Tolerated in Data Tables</span></span>

<span data-ttu-id="6551e-127">Excel 当前不会引发错误如果计算的模拟运算表基于表中的某些内容引用。</span><span class="sxs-lookup"><span data-stu-id="6551e-127">Excel currently does not raise an error if the calculation that a data table is based on refers to something in the table itself.</span></span> <span data-ttu-id="6551e-128">这种情况下可能会为太，您应该仔细时您正在创建或修改用于计算数据表值的公式。</span><span class="sxs-lookup"><span data-stu-id="6551e-128">As unlikely as this scenario might be, you should be careful when you are creating or modifying formulas that are used to calculate data table values.</span></span>
  
## <a name="converting-an-integer-xloper12-to-an-xloper"></a><span data-ttu-id="6551e-129">将整数 XLOPER12 转换为 XLOPER</span><span class="sxs-lookup"><span data-stu-id="6551e-129">Converting an Integer XLOPER12 to an XLOPER</span></span>

<span data-ttu-id="6551e-130">因为整数类型**xltypeInt** **XLOPER12**数据类型，32 位有符号的整数，但是它是仅 16 位有符号的整数中**XLOPER**数据类型，则可能中不能包含某些整数**XLOPER12**值整数**XLOPER**。</span><span class="sxs-lookup"><span data-stu-id="6551e-130">Because the integer type **xltypeInt** is a 32-bit signed integer in the **XLOPER12** data type, but it is only a 16-bit signed integer in the **XLOPER** data type, it is possible that some integer **XLOPER12** values cannot be contained in an integer **XLOPER**.</span></span> <span data-ttu-id="6551e-131">在 Excel 内部转换此类型，它获取解决此问题通过转换到浮点**xltypeNum** **XLOPER**的类型。</span><span class="sxs-lookup"><span data-stu-id="6551e-131">Where Excel converts this type internally, it gets around this problem by converting the type to a floating-point **xltypeNum** **XLOPER**.</span></span>
  
<span data-ttu-id="6551e-132">框架[XLOper12ToXLOper](xloper12toxloper.md)函数镜像与保持一致 Excel 内部此行为。</span><span class="sxs-lookup"><span data-stu-id="6551e-132">The Framework [XLOper12ToXLOper](xloper12toxloper.md) function mirrors this behavior to be consistent with Excel internally.</span></span> <span data-ttu-id="6551e-133">当您调用此函数时，您不应假定返回的**XLOPER**将始终为**xltypeInt**;如果**my_xloper**类型为**xltypeNum**读取**my_xloper.val.w**提供值为 false。</span><span class="sxs-lookup"><span data-stu-id="6551e-133">When you call this function, you should not assume that the returned **XLOPER** will always be **xltypeInt**; reading **my_xloper.val.w** gives a false value if the **my_xloper** type is **xltypeNum**.</span></span>
  
## <a name="returning-xloper-or-xloper12-by-modifying-arguments-in-place"></a><span data-ttu-id="6551e-134">通过修改就地参数返回 XLOPER 或 XLOPER12</span><span class="sxs-lookup"><span data-stu-id="6551e-134">Returning XLOPER or XLOPER12 by Modifying Arguments in Place</span></span>

<span data-ttu-id="6551e-135">Excel 允许通过修改就地参数返回**XLOPER**或**XLOPER12**函数的注册。</span><span class="sxs-lookup"><span data-stu-id="6551e-135">Excel permits the registration of functions that return an **XLOPER** or **XLOPER12** by modifying an argument in place.</span></span> <span data-ttu-id="6551e-136">但是，如果**XLOPER**/ **XLOPER12**参数指向内存，并将指针然后 DLL 函数的返回值被覆盖，Excel 可以泄漏内存。</span><span class="sxs-lookup"><span data-stu-id="6551e-136">However, if an **XLOPER**/ **XLOPER12** argument points to memory, and the pointer is then overwritten by the return value of the DLL function, Excel can leak memory.</span></span> <span data-ttu-id="6551e-137">Excel 不显示错误，但它最终可能崩溃。</span><span class="sxs-lookup"><span data-stu-id="6551e-137">Excel does not display an error, but it might eventually crash.</span></span> <span data-ttu-id="6551e-138">此外，如果 DLL 的返回值分配内存，Excel 可能尝试以释放内存，这可能导致即时应用程序崩溃。</span><span class="sxs-lookup"><span data-stu-id="6551e-138">Also, if the DLL allocated memory for the return value, Excel might try to free that memory, which could cause an immediate application crash.</span></span> <span data-ttu-id="6551e-139">因此，不应修改**XLOPER**/ 就地**XLOPER12**参数。</span><span class="sxs-lookup"><span data-stu-id="6551e-139">Therefore, you should not modify **XLOPER**/ **XLOPER12** arguments in place.</span></span> <span data-ttu-id="6551e-140">严格为只读的则应处理所有**XLOPER**或**XLOPER12**参数。</span><span class="sxs-lookup"><span data-stu-id="6551e-140">All **XLOPER** or **XLOPER12** arguments should be treated as strictly read-only.</span></span> 
  
<span data-ttu-id="6551e-141">有关详细信息，请参阅[在 Excel 中进行内存管理](memory-management-in-excel.md)。</span><span class="sxs-lookup"><span data-stu-id="6551e-141">For more information, see [Memory Management in Excel](memory-management-in-excel.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6551e-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6551e-142">See also</span></span>



[<span data-ttu-id="6551e-143">XLOper12ToXLOper</span><span class="sxs-lookup"><span data-stu-id="6551e-143">XLOper12ToXLOper</span></span>](xloper12toxloper.md)


[<span data-ttu-id="6551e-144">Developing Excel XLLs</span><span class="sxs-lookup"><span data-stu-id="6551e-144">Developing Excel XLLs</span></span>](developing-excel-xlls.md)
  
[<span data-ttu-id="6551e-145">Excel XLL SDK API 函数引用</span><span class="sxs-lookup"><span data-stu-id="6551e-145">Excel XLL SDK API Function Reference</span></span>](excel-xll-sdk-api-function-reference.md)
  
[<span data-ttu-id="6551e-146">在 Excel 中进行内存管理</span><span class="sxs-lookup"><span data-stu-id="6551e-146">Memory Management in Excel</span></span>](memory-management-in-excel.md)

