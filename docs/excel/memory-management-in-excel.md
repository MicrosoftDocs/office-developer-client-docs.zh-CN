---
title: Excel 中的内存管理
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- xloper12 memory [excel 2007], 管理 excel 中的内存, excel 堆栈, 字符串 [excel 2007], 管理内存, excel 中的内存管理, XLOPER memory [excel 2007], memory [excel 2007], 管理准则
localization_priority: Normal
ms.assetid: 3bf5195b-6235-43cf-8795-0c7b0a63a095
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: f129dac2971f01c8ada15f0028958132b1945746
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310456"
---
# <a name="memory-management-in-excel"></a><span data-ttu-id="85e10-104">Excel 中的内存管理</span><span class="sxs-lookup"><span data-stu-id="85e10-104">Memory Management in Excel</span></span>

 <span data-ttu-id="85e10-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="85e10-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="85e10-106">如果要创建高效而稳定的 xll, 则内存管理是最重要的考虑因素。</span><span class="sxs-lookup"><span data-stu-id="85e10-106">Memory management is the most important concern if you want to create efficient and stable XLLs.</span></span> <span data-ttu-id="85e10-107">无法正常管理内存可能会导致 Microsoft Excel 中的一系列问题, 从很少的问题 (例如, 低内存分配和初始化和小内存泄漏) 到重大问题 (如 Excel destabilization)。</span><span class="sxs-lookup"><span data-stu-id="85e10-107">Failure to manage memory well can lead to a range of problems in Microsoft Excel—from minor problems such as inefficient memory allocation and initialization and small memory leaks, to major problems such as the destabilization of Excel.</span></span>
  
<span data-ttu-id="85e10-108">Mismanagement 的内存是严重的加载项相关问题最常见的来源。</span><span class="sxs-lookup"><span data-stu-id="85e10-108">Mismanagement of memory is the most common source of serious add-in-related problems.</span></span> <span data-ttu-id="85e10-109">因此, 应生成项目, 并在内存管理上采用一致且思维的策略。</span><span class="sxs-lookup"><span data-stu-id="85e10-109">Therefore, you should build your project with a consistent and well-thought-through strategy on memory management.</span></span> 
  
<span data-ttu-id="85e10-110">随着多线程工作簿的重新计算, 内存管理在 Microsoft Office Excel 2007 中变得更加复杂。</span><span class="sxs-lookup"><span data-stu-id="85e10-110">Memory management became more complex in Microsoft Office Excel 2007 with the introduction of multithreaded workbook recalculation.</span></span> <span data-ttu-id="85e10-111">如果要创建和导出线程安全的工作表函数, 则必须管理在多个线程需要进行访问时可能发生的冲突。</span><span class="sxs-lookup"><span data-stu-id="85e10-111">If you want to create and export thread-safe worksheet functions, you must manage the resulting conflicts that can occur when multiple threads compete for access.</span></span>
  
<span data-ttu-id="85e10-112">对于以下三种数据结构类型, 存在内存注意事项:</span><span class="sxs-lookup"><span data-stu-id="85e10-112">There are memory considerations for the following three data structure types:</span></span>
  
- <span data-ttu-id="85e10-113">**XLOPER**s 和**XLOPER12**s</span><span class="sxs-lookup"><span data-stu-id="85e10-113">**XLOPER**s and **XLOPER12**s</span></span>
    
- <span data-ttu-id="85e10-114">不在**XLOPER**或**XLOPER12**中的字符串</span><span class="sxs-lookup"><span data-stu-id="85e10-114">Strings that are not in an **XLOPER** or **XLOPER12**</span></span>
    
- <span data-ttu-id="85e10-115">**FP**和**FP12**数组</span><span class="sxs-lookup"><span data-stu-id="85e10-115">**FP** and **FP12** arrays</span></span> 
    
## <a name="xloperxloper12-memory"></a><span data-ttu-id="85e10-116">XLOPER/XLOPER12 内存</span><span class="sxs-lookup"><span data-stu-id="85e10-116">XLOPER/XLOPER12 Memory</span></span>

<span data-ttu-id="85e10-117">**XLOPER**/ **XLOPER12**数据结构具有一些子类型, 其中包含指向内存块的指针, 即字符串 (**xltypeStr**)、数组 (**xltypeMulti**) 和外部引用 (**xltypeRef**)。</span><span class="sxs-lookup"><span data-stu-id="85e10-117">The **XLOPER**/ **XLOPER12** data structure has a few sub-types that contain pointers to blocks of memory, namely strings (**xltypeStr**), arrays (**xltypeMulti**) and external references (**xltypeRef**).</span></span> <span data-ttu-id="85e10-118">另请注意, **xltypeMulti**数组可以包含 string **XLOPER**/ **XLOPER12s** , 后者又指向其他内存块。</span><span class="sxs-lookup"><span data-stu-id="85e10-118">Note also that **xltypeMulti** arrays can contain string **XLOPER**/ **XLOPER12s** that in turn point to other blocks of memory.</span></span> 
  
<span data-ttu-id="85e10-119">可以通过以下几种方式创建**XLOPER**/ **XLOPER12** :</span><span class="sxs-lookup"><span data-stu-id="85e10-119">An **XLOPER**/ **XLOPER12** can be created in several ways:</span></span> 
  
- <span data-ttu-id="85e10-120">当准备要传递给 XLL 函数的参数时, Excel</span><span class="sxs-lookup"><span data-stu-id="85e10-120">By Excel when preparing arguments to be passed to an XLL function</span></span>
    
- <span data-ttu-id="85e10-121">在 C API 调用中返回**XLOPER**或**XLOPER12**时 Excel</span><span class="sxs-lookup"><span data-stu-id="85e10-121">By Excel when returning an **XLOPER** or **XLOPER12** in a C API call</span></span> 
    
- <span data-ttu-id="85e10-122">创建要传递给 C API 调用的参数时的 DLL</span><span class="sxs-lookup"><span data-stu-id="85e10-122">By your DLL when creating arguments to be passed to a C API call</span></span>
    
- <span data-ttu-id="85e10-123">在创建 XLL 函数返回值时的 DLL</span><span class="sxs-lookup"><span data-stu-id="85e10-123">By your DLL when creating an XLL function return value</span></span>
    
<span data-ttu-id="85e10-124">可以通过以下几种方式分配其中一种内存指向的类型中的内存块:</span><span class="sxs-lookup"><span data-stu-id="85e10-124">A block of memory within one of the memory-pointing types can be allocated in several ways:</span></span>
  
- <span data-ttu-id="85e10-125">它可以是任何函数代码外部 DLL 中的静态块, 在这种情况下, 您不必分配或释放内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-125">It can be a static block within your DLL outside any function code, in which case you do not have to allocate or free the memory.</span></span>
    
- <span data-ttu-id="85e10-126">它可以是某些函数代码内 DLL 中的静态块, 在这种情况下, 您不必分配或释放内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-126">It can be a static block within your DLL within some function code, in which case you do not have to allocate or free the memory.</span></span>
    
- <span data-ttu-id="85e10-127">可以通过几种可能的方式动态分配和释放 DLL: **malloc**和**free**、 **new**和**delete**等。</span><span class="sxs-lookup"><span data-stu-id="85e10-127">It can be dynamically allocated and freed by your DLL in several possible ways: **malloc** and **free**, **new** and **delete**, and so on.</span></span>
    
- <span data-ttu-id="85e10-128">它可以由 Excel 动态分配。</span><span class="sxs-lookup"><span data-stu-id="85e10-128">It can be dynamically allocated by Excel.</span></span>
    
<span data-ttu-id="85e10-129">给定**XLOPER**/ **XLOPER12**内存的可能来源, 以及**XLOPER**/ **XLOPER12**可能已分配该内存的情况数, 此主题不会令人吃惊看起来非常困难。</span><span class="sxs-lookup"><span data-stu-id="85e10-129">Given the number of possible origins for **XLOPER**/ **XLOPER12** memory and the number of situations in which the **XLOPER**/ **XLOPER12** might have had that memory assigned, it is not surprising that this subject can seem very difficult.</span></span> <span data-ttu-id="85e10-130">但是, 如果您遵循几个规则和准则, 则可以大大减少复杂性。</span><span class="sxs-lookup"><span data-stu-id="85e10-130">However, the complexity can be greatly reduced if you follow several rules and guidelines.</span></span> 
  
### <a name="rules-for-working-with-xloperxloper12"></a><span data-ttu-id="85e10-131">使用 XLOPER/XLOPER12 的规则</span><span class="sxs-lookup"><span data-stu-id="85e10-131">Rules for Working with XLOPER/XLOPER12</span></span>

- <span data-ttu-id="85e10-132">请勿尝试释放内存或覆盖作为参数传递给 XLL 函数的**XLOPERs**/ **XLOPER12**s。</span><span class="sxs-lookup"><span data-stu-id="85e10-132">Do not try to free memory or overwrite **XLOPERs**/ **XLOPER12**s that are passed as arguments to your XLL function.</span></span> <span data-ttu-id="85e10-133">应将此类参数视为只读。</span><span class="sxs-lookup"><span data-stu-id="85e10-133">You should treat such arguments as read-only.</span></span> <span data-ttu-id="85e10-134">有关详细信息, 请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)中的 "通过修改参数就地返回**XLOPER**或**XLOPER12** "。</span><span class="sxs-lookup"><span data-stu-id="85e10-134">For more information, see "Returning **XLOPER** or **XLOPER12** by Modifying Arguments in Place" in [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
    
- <span data-ttu-id="85e10-135">如果 Excel 已为**XLOPER**/ **XLOPER12**分配了内存, 并且在对 C API 的调用中返回到 DLL:</span><span class="sxs-lookup"><span data-stu-id="85e10-135">If Excel has allocated memory for an **XLOPER**/ **XLOPER12** returned to your DLL in a call to the C API:</span></span> 
    
  - <span data-ttu-id="85e10-136">当不再需要使用对[xlFree](xlfree.md)的调用的**XLOPER**/ **XLOPER12**时, 必须释放内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-136">You must free the memory when you no longer need the **XLOPER**/ **XLOPER12** using a call to [xlFree](xlfree.md).</span></span> <span data-ttu-id="85e10-137">请勿使用任何其他方法 (如 "免费" 或 "删除") 来释放内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-137">Do not use any other method, such as free or delete, to release the memory.</span></span>
    
  - <span data-ttu-id="85e10-138">如果返回的类型为**xltypeMulti**, 请勿覆盖数组中的任何**XLOPER**/ **XLOPER12**s, 尤其是当它们包含字符串时, 尤其是您尝试使用字符串覆盖的位置。</span><span class="sxs-lookup"><span data-stu-id="85e10-138">If the returned type is **xltypeMulti**, do not overwrite any **XLOPER**/ **XLOPER12**s within the array, especially if they contain strings, and especially not where you are trying to overwrite with a string.</span></span>
    
  - <span data-ttu-id="85e10-139">如果要将**XLOPER**/ **XLOPER12**作为 DLL 函数的返回值返回到 excel, 则必须告诉 excel, 它是 excel 在完成时必须释放的内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-139">If you want to return the **XLOPER**/ **XLOPER12** to Excel as your DLL function's return value, you must tell Excel that there is memory that Excel must release when done.</span></span> 
    
- <span data-ttu-id="85e10-140">您只能在作为返回值为 C API 调用而创建的**XLOPER**/ **XLOPER12**上调用**xlFree** 。</span><span class="sxs-lookup"><span data-stu-id="85e10-140">You must only call **xlFree** on an **XLOPER**/ **XLOPER12** that was created as the return value to a C API call.</span></span> 
    
- <span data-ttu-id="85e10-141">如果您的 dll 已为**XLOPER**/ **XLOPER12**分配了内存, 而您希望以 dll 函数的返回值的形式返回到 excel, 则必须告诉 Excel dll 必须释放的内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-141">If your DLL has allocated memory for an **XLOPER**/ **XLOPER12** that you want to return to Excel as your DLL function's return value, you must tell Excel that there is memory that the DLL must release.</span></span> 
    
### <a name="guidelines-for-memory-management"></a><span data-ttu-id="85e10-142">内存管理指南</span><span class="sxs-lookup"><span data-stu-id="85e10-142">Guidelines for Memory Management</span></span>

- <span data-ttu-id="85e10-143">在您用于分配和释放内存的方法中的 DLL 中保持一致。</span><span class="sxs-lookup"><span data-stu-id="85e10-143">Be consistent in your DLL in the method that you use to allocate and release memory.</span></span> <span data-ttu-id="85e10-144">避免混合方法。</span><span class="sxs-lookup"><span data-stu-id="85e10-144">Avoid mixing methods.</span></span> <span data-ttu-id="85e10-145">一种很好的方法是包装您在内存类或结构中使用的方法, 在该方法中您可以更改使用的方法, 而无需在很多位置更改代码。</span><span class="sxs-lookup"><span data-stu-id="85e10-145">A good approach is to wrap the method that you are using up in a memory class or structure, within which you can change the method used without altering your code in many places.</span></span>
    
- <span data-ttu-id="85e10-146">在 DLL 中创建**xltypeMulti**数组时, 应在为字符串分配内存的方式中保持一致: 始终为它们动态分配内存或始终使用静态内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-146">When you create **xltypeMulti** arrays within your DLL, be consistent in the way that you allocate memory for strings: always dynamically allocate the memory for them or always use static memory.</span></span> <span data-ttu-id="85e10-147">如果执行此操作, 则释放内存时, 您将知道必须始终或从不释放字符串。</span><span class="sxs-lookup"><span data-stu-id="85e10-147">If you do this, when you are freeing the memory, you will know that you must either always or never free the strings.</span></span> 
    
- <span data-ttu-id="85e10-148">复制 excel 创建的**XLOPER**/ **XLOPER12**时, 请制作 excel 分配的内存的深层副本。</span><span class="sxs-lookup"><span data-stu-id="85e10-148">Make deep copies of Excel-allocated memory when you are copying an Excel-created **XLOPER**/ **XLOPER12**.</span></span>
    
- <span data-ttu-id="85e10-149">请勿将 Excel 分配的字符串**XLOPER**/ **XLOPER12**s 放在**xltypeMulti**数组中。</span><span class="sxs-lookup"><span data-stu-id="85e10-149">Do not put Excel-allocated string **XLOPER**/ **XLOPER12**s within **xltypeMulti** arrays.</span></span> <span data-ttu-id="85e10-150">制作字符串的深层副本并将指针存储到数组中的副本。</span><span class="sxs-lookup"><span data-stu-id="85e10-150">Make deep copies of the strings and store pointers to the copies in the array.</span></span> 
    
## <a name="freeing-excel-allocated-xloperxloper12-memory"></a><span data-ttu-id="85e10-151">释放 Excel 分配的 XLOPER/XLOPER12 内存</span><span class="sxs-lookup"><span data-stu-id="85e10-151">Freeing Excel-Allocated XLOPER/XLOPER12 Memory</span></span>

<span data-ttu-id="85e10-152">请考虑以下 XLL 命令, 该命令使用**xlGetName**获取包含 DLL 的路径和文件名的字符串, 并使用**xlcAlert**将其显示在警报对话框中。</span><span class="sxs-lookup"><span data-stu-id="85e10-152">Consider the following XLL command, which uses **xlGetName** to obtain a string containing the path and file name of the DLL and displays it in an alert dialog box using **xlcAlert**.</span></span>
  
```cs
int WINAPI show_DLL_name(void)
{
    XLOPER12 xDllName;
    if(Excel12(xlfGetName, &xDllName, 0) == xlretSuccess)
    {
        // Display the name.
        Excel12(xlcAlert, 0, 1, &xDllName);
        // Free the memory that Excel allocated for the string.
        Excel12(xlFree, 0, 1, &xDllName);
    }
    return 1;
}

```

<span data-ttu-id="85e10-153">当函数不再需要**xDllName**所指向的内存时, 它可以使用对[xlFree 函数](xlfree.md)(仅限 DLL 的 C API 函数之一) 的调用来释放它。</span><span class="sxs-lookup"><span data-stu-id="85e10-153">When the function no longer needs the memory pointed to by **xDllName**, it can free it using a call to the [xlFree function](xlfree.md), one of the DLL-only C API functions.</span></span> 
  
<span data-ttu-id="85e10-154">"函数引用" 一节中对**xlFree**函数进行了充分说明 (请参阅只能[从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)), 但请注意以下几点:</span><span class="sxs-lookup"><span data-stu-id="85e10-154">The **xlFree** function is fully documented in the function reference section (see [C API Functions That Can Be Called Only from a DLL or XLL](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)), but be aware of the following:</span></span>
  
- <span data-ttu-id="85e10-155">可以在对**xlFree**的一次调用中将指针传递给多个**XLOPER**/ **XLOPER12**s, 这只受运行版本的 excel 中支持的函数参数数 (在 excel 2003 中为 30, 255 从 excel 2007 开始)。</span><span class="sxs-lookup"><span data-stu-id="85e10-155">You can pass pointers to more than one **XLOPER**/ **XLOPER12**s in a single call to **xlFree**, limited only by the number of function arguments supported in the running version of Excel (30 in Excel 2003, 255 starting in Excel 2007).</span></span>
    
- <span data-ttu-id="85e10-156">**xlFree**将包含的指针设置为**NULL** , 以确保释放已释放的**XLOPER**/ **XLOPER12**的尝试是安全的。</span><span class="sxs-lookup"><span data-stu-id="85e10-156">**xlFree** sets the contained pointer to **NULL** to ensure that an attempt to free an **XLOPER**/ **XLOPER12** that has already been freed is safe.</span></span> <span data-ttu-id="85e10-157">**xlFree**是修改其参数的唯一 C API 函数。</span><span class="sxs-lookup"><span data-stu-id="85e10-157">**xlFree** is the only C API function that modifies its arguments.</span></span> 
    
- <span data-ttu-id="85e10-158">您可以在任何**XLOPER**/ **XLOPER12**上安全地调用**xlFree** , 以用于对 C API 的调用的返回值, 而不管它是否包含指向内存的指针。</span><span class="sxs-lookup"><span data-stu-id="85e10-158">You can safely call **xlFree** on any **XLOPER**/ **XLOPER12** used for the return value of a call to the C API, regardless of whether it contains a pointer to memory.</span></span> 
    
## <a name="returning-xloperxloper12s-to-be-freed-by-excel"></a><span data-ttu-id="85e10-159">返回要由 Excel 释放的 XLOPER/XLOPER12s</span><span class="sxs-lookup"><span data-stu-id="85e10-159">Returning XLOPER/XLOPER12s to be freed by Excel</span></span>

<span data-ttu-id="85e10-160">假设您想要修改上一节中的示例命令, 并将其更改为在传递**布尔\*\*\*\*值 true**参数时返回 DLL 路径和文件名的工作表函数, 否则 **#N/a** 。</span><span class="sxs-lookup"><span data-stu-id="85e10-160">Suppose you wanted to modify the example command in the previous section and change it to a worksheet function that returns the DLL path and file name when passed a **Boolean** **true** argument, and **#N/A** otherwise.</span></span> <span data-ttu-id="85e10-161">很明显, 在将字符串内存返回到 Excel 之前, 无法调用**xlFree**以释放字符串内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-161">Clearly you cannot call **xlFree** to release the string memory before returning it to Excel.</span></span> <span data-ttu-id="85e10-162">但是, 如果在某些情况下, 加载项将在每次调用函数时泄漏内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-162">However, if it is not freed at some point, the add-in will leak memory every time the function is called.</span></span> <span data-ttu-id="85e10-163">若要解决此问题, 您可以在**XLOPER**/ **XLOPER12**的 " **xltype** " 字段中设置一个位, 在 xlcall.h 中定义为**xlbitXLFree** 。</span><span class="sxs-lookup"><span data-stu-id="85e10-163">To work around this problem, you can set a bit in the **xltype** field of the **XLOPER**/ **XLOPER12**, defined as **xlbitXLFree** in xlcall.h.</span></span> <span data-ttu-id="85e10-164">设置它告诉 Excel 它必须在完成复制值后释放返回的内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-164">Setting this tells Excel that it must free the returned memory when it has finished copying the value out.</span></span> 
  
### <a name="example"></a><span data-ttu-id="85e10-165">示例</span><span class="sxs-lookup"><span data-stu-id="85e10-165">Example</span></span>

<span data-ttu-id="85e10-166">下面的代码示例显示了前一节中转换为 xll 工作表函数的 XLL 命令。</span><span class="sxs-lookup"><span data-stu-id="85e10-166">The following code example shows the XLL command in the previous section converted into an XLL worksheet function.</span></span>
  
```cs
LPXLOPER12 WINAPI get_DLL_name(int calculation_trigger)
{
    static XLOPER12 xRtnValue; // Not thread-safe
    Excel12(xlfGetName, &xRtnValue, 0);
// If xlfGetName failed, xRtnValue will be #VALUE!
    if(xRtnValue.xltype == xltypeStr)
    {
// Tell Excel to free the string memory after
// it has copied out the return value.
        xRtnValue.xltype |= xlbitXLFree;
    }
    return &xRtnValue;
}
```

<span data-ttu-id="85e10-167">使用**XLOPER**/ **XLOPER12**s 的 XLL 函数必须声明为采用 XLOPER XLOPER12 s, 并将指针返回到\*\*\*\*/ \*\*\*\* s。</span><span class="sxs-lookup"><span data-stu-id="85e10-167">XLL functions that use **XLOPER**/ **XLOPER12**s must be declared as taking and returning pointers to **XLOPER**/ **XLOPER12**s.</span></span> <span data-ttu-id="85e10-168">此函数中的静态**XLOPER12**在此示例中的用法不是线程安全的。</span><span class="sxs-lookup"><span data-stu-id="85e10-168">The use in this example of a static **XLOPER12** within the function is not thread safe.</span></span> <span data-ttu-id="85e10-169">您可能会错误地将此函数注册为线程安全, 但在另一个线程完成前一个线程将会将风险**xRtnValue**重写。</span><span class="sxs-lookup"><span data-stu-id="85e10-169">You could incorrectly register this function as thread safe, but you would risk **xRtnValue** being overwritten by one thread before another thread had finished with it.</span></span> 
  
<span data-ttu-id="85e10-170">在调用分配它的 Excel 回调之后, 必须设置**xlbitXLFree** 。</span><span class="sxs-lookup"><span data-stu-id="85e10-170">You must set **xlbitXLFree** after the call to the Excel callback that allocates it.</span></span> <span data-ttu-id="85e10-171">如果您设置此设置, 则它将被覆盖, 并且不会产生所需的效果。</span><span class="sxs-lookup"><span data-stu-id="85e10-171">If you set it before this, it is overwritten and does not have the effect that you want.</span></span> <span data-ttu-id="85e10-172">如果要在将值返回到工作表之前在调用另一 C API 函数的同时将该值用作参数, 应在任何此类调用之后设置此位。</span><span class="sxs-lookup"><span data-stu-id="85e10-172">If you intend to use the value as an argument in a call to another C API function before returning it to the worksheet, you should set this bit after any such call.</span></span> <span data-ttu-id="85e10-173">否则, 在检查**XLOPER**/ **XLLOPER12**类型之前, 不会混淆不屏蔽此位的函数。</span><span class="sxs-lookup"><span data-stu-id="85e10-173">Otherwise, you will confuse functions that do not mask this bit before checking the **XLOPER**/ **XLLOPER12** type.</span></span> 
  
## <a name="returning-xloperxloper12s-to-be-freed-by-the-dll"></a><span data-ttu-id="85e10-174">返回要由 DLL 释放的 XLOPER/XLOPER12s</span><span class="sxs-lookup"><span data-stu-id="85e10-174">Returning XLOPER/XLOPER12s to be freed by the DLL</span></span>

<span data-ttu-id="85e10-175">当 XLL 为**XLOPER**/ **XLOPER12**分配了内存并希望将其返回到 Excel 时, 会发生类似的问题。</span><span class="sxs-lookup"><span data-stu-id="85e10-175">A similar problem to this occurs when your XLL has allocated memory for an **XLOPER**/ **XLOPER12** and wants to return it to Excel.</span></span> <span data-ttu-id="85e10-176">Excel 可识别可在**XLOPER**/ **XLOPER12**的 " **xltype** " 字段中设置的另一位, 在 xlcall.h 中定义为**xlbitDLLFree** 。</span><span class="sxs-lookup"><span data-stu-id="85e10-176">Excel recognizes another bit that can be set in the **xltype** field of the **XLOPER**/ **XLOPER12**, defined as **xlbitDLLFree** in xlcall.h.</span></span> 
  
<span data-ttu-id="85e10-177">当 Excel 收到具有此位集的**XLOPER**/ **XLOPER12**时, 它会尝试调用一个函数, 该函数应由称为[xlAutoFree](xlautofree-xlautofree12.md) (对于**XLOPER**s) 或**xlAutoFree12** (对于**XLOPER12**s) 的 XLL 导出。</span><span class="sxs-lookup"><span data-stu-id="85e10-177">When Excel receives **an XLOPER**/ **XLOPER12** with this bit set, it tries to call a function that should be exported by the XLL called [xlAutoFree](xlautofree-xlautofree12.md) (for **XLOPER**s) or **xlAutoFree12** (for **XLOPER12**s).</span></span> <span data-ttu-id="85e10-178">函数引用中更全面地描述了此函数 (请参阅[外接程序管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)), 但此处提供了示例最少实现。</span><span class="sxs-lookup"><span data-stu-id="85e10-178">This function is described more fully in the function reference (see [Add-in Manager and XLL Interface Functions](add-in-manager-and-xll-interface-functions.md)), but an example minimal implementation is given here.</span></span> <span data-ttu-id="85e10-179">其目的是按照与最初分配的方式一致的方式释放**XLOPER**/ **XLOPER12**内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-179">Its purpose is to free the **XLOPER**/ **XLOPER12** memory in a way that is consistent with how it was originally allocated.</span></span> 
  
### <a name="examples"></a><span data-ttu-id="85e10-180">示例</span><span class="sxs-lookup"><span data-stu-id="85e10-180">Examples</span></span>

<span data-ttu-id="85e10-181">下面的示例函数与 previous 函数的作用相同, 不同之处在于它包含的文本 "此 dll 的完整路径名是 dll 名称之前"。</span><span class="sxs-lookup"><span data-stu-id="85e10-181">The following example function does the same as the previous function except that it includes the text "The full pathname for this DLL is " before the DLL name.</span></span>
  
```cs
#include <string.h>
LPXLOPER12 WINAPI get_DLL_name_2(int calculation_trigger)
{
    static XLOPER12 xRtnValue; // Not thread-safe
    Excel12(xlfGetName, &xRtnValue, 0);
// If xlfGetName failed, xRtnValue will be #VALUE!
    if(xRtnValue.xltype != xltypeStr)
        return &xRtnValue;
// Make a copy of the DLL path and file name.
    wchar_t *leader = L"The full pathname for this DLL is ";
    size_t leader_len = wcslen(leader);
    size_t dllname_len = xRtnValue.val.str[0];
    size_t msg_len = leader_len + dllname_len;
    wchar_t *msg_text = (wchar_t *)malloc(msg_len + 1);
    wcsncpy_s(msg_text + 1, leader, leader_len);
    wcsncpy_s(msg_text + 1 + leader_len, xRtnValue.val.str + 1,
        dllname_len);
    msg_text[0] = msg_len;
// Now the original string has been copied Excel can free it.
    Excel12(xlFree, 0, 1, &xRtnValue);
// Now reuse the XLOPER12 for the new string.
    xRtnValue.val.str = msg_text;
// Tell Excel to call back into the DLL to free the string
// memory after it has copied out the return value.
    xRtnValue.xltype     = xltypeStr | xlbitDLLFree;
    return &xRtnValue;
}
```

<span data-ttu-id="85e10-182">导出 previous 函数的 XLL 中至少有足够的**xlAutoFree12**实现将如下所示。</span><span class="sxs-lookup"><span data-stu-id="85e10-182">A minimally sufficient implementation of **xlAutoFree12** in the XLL that exported the previous function would be as follows.</span></span> 
  
```cs
void WINAPI xlAutoFree12(LPXLOPER12 p_oper)
{
    if(p_oper->xltype == (xltypeStr | xlbitDLLFree))
        free(p_oper->val.str);
}
```

<span data-ttu-id="85e10-183">仅当 XLL 仅返回**XLOPER12**字符串, 并且仅使用**malloc**分配这些字符串时, 此实现才足够。</span><span class="sxs-lookup"><span data-stu-id="85e10-183">This implementation is only sufficient if the XLL only returns **XLOPER12** strings, and those strings are only allocated using **malloc**.</span></span> <span data-ttu-id="85e10-184">请注意, 测试</span><span class="sxs-lookup"><span data-stu-id="85e10-184">Note that the test</span></span> 
  
 ` if(p_oper->xltype == xltypeStr) `
  
<span data-ttu-id="85e10-185">在这种情况下会失败, 因为设置了**xlbitDLLFree** 。</span><span class="sxs-lookup"><span data-stu-id="85e10-185">would fail in this case because **xlbitDLLFree** is set.</span></span> 
  
<span data-ttu-id="85e10-186">通常情况下, 应实现**xlAutoFree**和**xlAutoFree12** , 以便它们释放与 XLL 创建的**xltypeMulti**数组和**xltypeRef**外部引用关联的内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-186">In general, **xlAutoFree** and **xlAutoFree12** should be implemented so that they free memory associated with XLL-created **xltypeMulti** arrays and **xltypeRef** external references.</span></span> 
  
<span data-ttu-id="85e10-187">您可以决定实现 XLL 函数, 以便它们都返回动态分配的**XLOPER**s 和**XLOPER12**s。</span><span class="sxs-lookup"><span data-stu-id="85e10-187">You might decide to implement your XLL functions so that they ALL return dynamically allocated **XLOPER**s and **XLOPER12**s.</span></span> <span data-ttu-id="85e10-188">在这种情况下, 无论子类型如何, 都需要在所有此类**XLOPER**s 和**XLOPER12**s 上设置**xlbitDLLFree** 。</span><span class="sxs-lookup"><span data-stu-id="85e10-188">In this case, you would need to set **xlbitDLLFree** on all such **XLOPER**s and **XLOPER12**s regardless of the sub-type.</span></span> <span data-ttu-id="85e10-189">此外, 还需要实现**xlAutoFree**和**xlAutoFree12** , 以便在**XLOPER**/ **XLOPER12**中释放该内存, 也将其指向任何内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-189">You would also need to implement **xlAutoFree** and **xlAutoFree12** so that this memory was freed and also any memory pointed to within the **XLOPER**/ **XLOPER12**.</span></span> <span data-ttu-id="85e10-190">此方法是使返回值为安全的返回值的一种方法。</span><span class="sxs-lookup"><span data-stu-id="85e10-190">This approach is one way to make the return value thread safe.</span></span> <span data-ttu-id="85e10-191">例如, 可以重写 previous 函数, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="85e10-191">For example, the previous function could be rewritten as follows.</span></span>
  
```cs
#include <string.h>
LPXLOPER12 WINAPI get_DLL_name_3(int calculation_trigger)
{
// Thread-safe
    LPXLOPER12 pxRtnValue = (LPXLOPER12)malloc(sizeof(XLOPER12));
    Excel12(xlfGetName, pxRtnValue, 0);
// If xlfGetName failed, pxRtnValue will be #VALUE!
    if(pxRtnValue->xltype != xltypeStr)
    {
// Even though an error type does not point to memory,
// Excel needs to pass this oper to xlAutoFree12 to
// free pxRtnValue itself.
        pxRtnValue->xltype |= xlbitDLLFree;
        return pxRtnValue;
    }
// Make a copy of the DLL path and file name.
    wchar_t *leader = L"The full pathname for this DLL is ";
    size_t leader_len = wcslen(leader);
    size_t dllname_len = pxRtnValue->val.str[0];
    size_t msg_len = leader_len + dllname_len;
    wchar_t *msg_text = (wchar_t *)malloc(msg_len + 1);
    wcsncpy_s(msg_text + 1, leader, leader_len);
    wcsncpy_s(msg_text + 1 + leader_len, pxRtnValue->val.str + 1,
        dllname_len);
    msg_text[0] = msg_len;
// Now the original string has been copied Excel can free it.
    Excel12(xlFree, 0, 1, pxRtnValue);
// Now reuse the XLOPER12 for the new string.
    pxRtnValue->val.str = msg_text;
    pxRtnValue->xltype = xltypeStr | xlbitDLLFree;
    return pxRtnValue;
}
void WINAPI xlAutoFree12(LPXLOPER12 p_oper)
{
    if(p_oper->xltype == (xltypeStr | xlbitDLLFree))
        free(p_oper->val.str);
    free(p_oper);
}
```

<span data-ttu-id="85e10-192">有关**xlAutoFree**和**xlAutoFree12**的详细信息, 请参阅[xlAutoFree/xlAutoFree12](xlautofree-xlautofree12.md)。</span><span class="sxs-lookup"><span data-stu-id="85e10-192">For more information about **xlAutoFree** and **xlAutoFree12**, see [xlAutoFree/xlAutoFree12](xlautofree-xlautofree12.md).</span></span>
  
## <a name="returning-modify-in-place-arguments"></a><span data-ttu-id="85e10-193">返回 "就地修改" 参数</span><span class="sxs-lookup"><span data-stu-id="85e10-193">Returning Modify-in-Place Arguments</span></span>

<span data-ttu-id="85e10-194">Excel 允许 XLL 函数通过就地修改参数来返回值。</span><span class="sxs-lookup"><span data-stu-id="85e10-194">Excel allows an XLL function to return a value by modifying an argument in place.</span></span> <span data-ttu-id="85e10-195">仅可以使用作为指针传入的参数执行此操作。</span><span class="sxs-lookup"><span data-stu-id="85e10-195">You can only do this with an argument passed in as a pointer.</span></span> <span data-ttu-id="85e10-196">若要执行此操作, 必须注册该函数, 告知 Excel 将修改哪个参数。</span><span class="sxs-lookup"><span data-stu-id="85e10-196">To work like this, the function must be registered in a way that tells Excel which argument will be modified.</span></span> 
  
<span data-ttu-id="85e10-197">对于可以通过指针传递的所有数据类型, 返回值的方法均受支持, 但对于以下类型尤其有用:</span><span class="sxs-lookup"><span data-stu-id="85e10-197">This method of returning a value is supported for all data types that can be passed by pointer but is especially useful for the following types:</span></span>
  
- <span data-ttu-id="85e10-198">长度计数和以 null 结尾的 ASCII 字节字符串</span><span class="sxs-lookup"><span data-stu-id="85e10-198">Length-counted and null-terminated ASCII byte strings</span></span>
    
- <span data-ttu-id="85e10-199">长度计数和 null 终止的 Unicode 宽字符字符串 (在 Excel 2007 中启动)</span><span class="sxs-lookup"><span data-stu-id="85e10-199">Length-counted and null-terminated Unicode wide character strings (starting in Excel 2007)</span></span>
    
- <span data-ttu-id="85e10-200">**FP**浮点数组</span><span class="sxs-lookup"><span data-stu-id="85e10-200">**FP** floating-point arrays</span></span> 
    
- <span data-ttu-id="85e10-201">**FP12**浮点数组 (从 Excel 2007 中开始)</span><span class="sxs-lookup"><span data-stu-id="85e10-201">**FP12** floating-point arrays (starting in Excel 2007)</span></span> 
    
> [!NOTE]
> <span data-ttu-id="85e10-202">您不应尝试以这种方式返回**XLOPER**s 或**XLOPER12**s。</span><span class="sxs-lookup"><span data-stu-id="85e10-202">You should not try to return **XLOPER**s or **XLOPER12**s in this manner.</span></span> <span data-ttu-id="85e10-203">有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。</span><span class="sxs-lookup"><span data-stu-id="85e10-203">For more information, see [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span> 
  
<span data-ttu-id="85e10-204">使用此技术 (而不是仅使用 return 语句) 的优势在于, Excel 会为返回值分配内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-204">The advantage of using this technique, instead of just using the return statement, is that Excel allocates the memory for the return values.</span></span> <span data-ttu-id="85e10-205">Excel 读完返回的数据后, 将释放内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-205">Once Excel has finished reading the returned data, it releases the memory.</span></span> <span data-ttu-id="85e10-206">这将使内存管理任务远离 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="85e10-206">This takes the memory management tasks away from the XLL function.</span></span> <span data-ttu-id="85e10-207">此技术是线程安全的: 如果 Excel 在不同线程上同时调用, 则每个线程上的每个函数调用都有自己的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="85e10-207">This technique is thread safe: If called concurrently by Excel on different threads, each function call on each thread has its own buffer.</span></span>
  
<span data-ttu-id="85e10-208">这对以前列出的数据类型很有用, 具体是因为用于回调 DLL 以释放为**XLOPER**/ **XLOPER12**提供的释放内存后返回的机制对于简单字符串和**FP** / 不存在。**FP12**数组。</span><span class="sxs-lookup"><span data-stu-id="85e10-208">It is useful for the previously listed data types in particular because the mechanism for calling back into the DLL to free memory post-return that exists for **XLOPER**/ **XLOPER12**s does not exist for simple strings and **FP**/ **FP12** arrays.</span></span> <span data-ttu-id="85e10-209">因此, 当返回 DLL 创建的字符串或浮点数组时, 您有以下几种选择:</span><span class="sxs-lookup"><span data-stu-id="85e10-209">Therefore, when returning a DLL-created string or floating-point array, you have the following choices:</span></span> 
  
- <span data-ttu-id="85e10-210">将永久指针设置为动态分配的缓冲区, 返回指针。</span><span class="sxs-lookup"><span data-stu-id="85e10-210">Set a persistent pointer to a dynamically allocated buffer, return the pointer.</span></span> <span data-ttu-id="85e10-211">在下一次调用函数 (1) 时, 检查指针是否不为 null, (2) 释放在上一个调用中分配的资源, 并将指针重置为 null, (3) 重用指针以获取新分配的内存块。</span><span class="sxs-lookup"><span data-stu-id="85e10-211">On the next call to the function (1) check that the pointer is not null, (2) free the resources allocated on the previous call and reset the pointer to null, (3) reuse the pointer for a newly allocated block of memory.</span></span>
    
- <span data-ttu-id="85e10-212">在不需要释放的静态缓冲区中创建字符串和数组, 并返回指向该字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="85e10-212">Create your strings and arrays in a static buffer that does not need to be freed, and return a pointer to that.</span></span>
    
- <span data-ttu-id="85e10-213">将参数就地修改, 将字符串或数组直接写入空格设置的 Excel 中。</span><span class="sxs-lookup"><span data-stu-id="85e10-213">Modify an argument in place, writing your string or array directly into the space set aside by Excel.</span></span>
    
<span data-ttu-id="85e10-214">否则, 必须创建一个**XLOPER**/ **XLOPER12**, 并使用**xlbitDLLFree**和**xlAutoFree**/ **xlAutoFree12**释放这些资源。</span><span class="sxs-lookup"><span data-stu-id="85e10-214">Otherwise, you must create an **XLOPER**/ **XLOPER12**, and use **xlbitDLLFree** and **xlAutoFree**/ **xlAutoFree12** to release the resources.</span></span> 
  
<span data-ttu-id="85e10-215">在传递与返回值类型相同的参数的情况下, 最后一个选项可能是最简单的。</span><span class="sxs-lookup"><span data-stu-id="85e10-215">The last option might be the simplest in those cases in which you are being passed an argument of the same type as the return value.</span></span> <span data-ttu-id="85e10-216">要记住的关键点是缓冲区大小受到限制, 您必须非常小心地避免溢出。</span><span class="sxs-lookup"><span data-stu-id="85e10-216">The key point to remember is that the buffer sizes are limited and you must be very careful not to overrun them.</span></span> <span data-ttu-id="85e10-217">此错误可能导致 Excel 崩溃。</span><span class="sxs-lookup"><span data-stu-id="85e10-217">Getting this wrong could crash Excel.</span></span> <span data-ttu-id="85e10-218">接下来讨论字符串和**FP**/ **FP12**数组的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="85e10-218">Buffer sizes for strings and **FP**/ **FP12** arrays are discussed next.</span></span> 
  
## <a name="strings"></a><span data-ttu-id="85e10-219">字符串</span><span class="sxs-lookup"><span data-stu-id="85e10-219">Strings</span></span>

<span data-ttu-id="85e10-220">在应用程序和外接程序中, 管理字符串内存的问题最常见的原因是不稳定的原因。在给定了处理字符串的各种方式的情况下, 它可能是可理解的: null-终止或长度计数 (或两者);静态或动态缓冲区;固定长度或几乎无限制的长度;操作系统托管内存 (例如 OLE Bstr) 或非托管字符串;等。</span><span class="sxs-lookup"><span data-stu-id="85e10-220">Problems with the management of string memory are arguably the most common cause of instability in applications and add-ins. It is understandable perhaps, given the variety of ways in which strings are handled: null-terminated or length-counted (or both); static or dynamic buffers; fixed length or almost unlimited length; operating-system managed memory (for example, OLE Bstr) or unmanaged strings; and so on.</span></span>
  
<span data-ttu-id="85e10-221">c/c + + 程序员最熟悉以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="85e10-221">C/C++ programmers are most familiar with null-terminated strings.</span></span> <span data-ttu-id="85e10-222">标准 C 库设计为可处理此类字符串。</span><span class="sxs-lookup"><span data-stu-id="85e10-222">The standard C library is designed to work with such strings.</span></span> <span data-ttu-id="85e10-223">代码中的静态字符串将编译为以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="85e10-223">Static string literals in code are compiled into null-terminated strings.</span></span> <span data-ttu-id="85e10-224">或者, Excel 处理的长度计数字符串不是一般的以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="85e10-224">Alternatively, Excel works with length-counted strings that are not in general null-terminated.</span></span> <span data-ttu-id="85e10-225">这些事实的组合要求 DLL/XLL 内的清晰且一致的方法, 有关如何处理字符串和字符串内存。</span><span class="sxs-lookup"><span data-stu-id="85e10-225">The combination of these facts requires a clear and consistent approach within your DLL/XLL regarding how you handle strings and string memory.</span></span>
  
<span data-ttu-id="85e10-226">最常见的问题如下:</span><span class="sxs-lookup"><span data-stu-id="85e10-226">The most common problems are as follows:</span></span>
  
- <span data-ttu-id="85e10-227">将 null 或无效指针传递给需要有效指针的函数, 但不会检查指针的有效性本身。</span><span class="sxs-lookup"><span data-stu-id="85e10-227">The passing of a null or invalid pointer to a function that expects a valid pointer and does not or cannot check the pointer's validity itself.</span></span>
    
- <span data-ttu-id="85e10-228">函数的界限的 overrunning, 该函数不能根据所写入的字符串的长度检查缓冲区长度, 也不能检查缓冲区长度。</span><span class="sxs-lookup"><span data-stu-id="85e10-228">The overrunning of the bounds of a string buffer by a function that does not or cannot check the length of the buffer against the length of the string being written.</span></span>
    
- <span data-ttu-id="85e10-229">尝试释放静态或已释放的字符串缓冲区内存, 或者不是以与释放方式一致的方式分配的。</span><span class="sxs-lookup"><span data-stu-id="85e10-229">Trying to free string buffer memory that is either static, or has been freed already, or was not allocated in a way that is consistent with how it is being freed.</span></span>
    
- <span data-ttu-id="85e10-230">由于无法分配或释放字符串而导致的内存泄漏, 通常位于频繁调用的函数中。</span><span class="sxs-lookup"><span data-stu-id="85e10-230">Memory leaks that result from strings being allocated and then not freed, usually in a frequently called function.</span></span>
    
### <a name="rules-for-strings"></a><span data-ttu-id="85e10-231">字符串规则</span><span class="sxs-lookup"><span data-stu-id="85e10-231">Rules for Strings</span></span>

<span data-ttu-id="85e10-232">与**XLOPER**/ **XLOPER**s 一样, 应遵循一些规则和准则。</span><span class="sxs-lookup"><span data-stu-id="85e10-232">As with **XLOPER**/ **XLOPER**s, there are rules and guidelines you should follow.</span></span> <span data-ttu-id="85e10-233">准则与上一节中给出的准则相同。</span><span class="sxs-lookup"><span data-stu-id="85e10-233">The guidelines are the same as given in the previous section.</span></span> <span data-ttu-id="85e10-234">下面的规则是特定于字符串的规则的扩展。</span><span class="sxs-lookup"><span data-stu-id="85e10-234">The rules here are an extension of the rules specifically for strings.</span></span>
  
 <span data-ttu-id="85e10-235">**原则**</span><span class="sxs-lookup"><span data-stu-id="85e10-235">**Rules:**</span></span>
  
- <span data-ttu-id="85e10-236">请勿尝试释放内存或覆盖作为参数传递给 XLL 函数的字符串**XLOPER**/ **XLOPER12**s 或简单的长度计数或以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="85e10-236">Do not try to free memory or overwrite string **XLOPER**/ **XLOPER12**s or simple length-counted or null-terminated strings passed as arguments to your XLL function.</span></span> <span data-ttu-id="85e10-237">应将此类参数视为只读。</span><span class="sxs-lookup"><span data-stu-id="85e10-237">You should treat such arguments as read-only.</span></span>
    
- <span data-ttu-id="85e10-238">Excel 为 string **XLOPER**/ **XLOPER12**分配内存对于 C API 回调函数的返回值, 请使用**xlFree**将其释放, 如果将其从 XLL 函数返回到 Excel, 则将其设置为**xlbitXLFree** 。</span><span class="sxs-lookup"><span data-stu-id="85e10-238">Where Excel allocates memory for a string **XLOPER**/ **XLOPER12** for the return value of a C API callback function, use **xlFree** to free it, or set **xlbitXLFree** if returning it to Excel from an XLL function.</span></span> 
    
- <span data-ttu-id="85e10-239">您的 DLL 动态分配**XLOPER**/ **XLOPER12**的字符串缓冲区, 请使用与完成时的分配方式一致的方式将其释放, 或者在将\*\*\*\* 其从 XLL 函数返回到 Excel 中时将其释放, 或者在**xlAutoFree**/  **xlAutoFree12**。</span><span class="sxs-lookup"><span data-stu-id="85e10-239">Where your DLL dynamically allocates a string buffer for an **XLOPER**/ **XLOPER12**, free it in a way consistent with how you allocated it when done, or set **xlbitDLLFree** if returning it to Excel from an XLL function and then free it in **xlAutoFree**/ **xlAutoFree12**.</span></span>
    
- <span data-ttu-id="85e10-240">如果 Excel 已为在对 C API 的调用中返回到 DLL 的**xltypeMulti**数组分配内存, 请勿覆盖该数组中的任何字符串**XLOPER**/ **XLOPER12**s。</span><span class="sxs-lookup"><span data-stu-id="85e10-240">If Excel has allocated memory for an **xltypeMulti** array returned to your DLL in a call to the C API, do not overwrite any string **XLOPER**/ **XLOPER12**s within the array.</span></span> <span data-ttu-id="85e10-241">此类数组必须仅使用**xlFree**释放, 或者在 XLL 函数返回时通过设置**xlbitXLFree**来释放。</span><span class="sxs-lookup"><span data-stu-id="85e10-241">Such arrays must only be freed using **xlFree**, or, if being returned by an XLL function, by setting **xlbitXLFree**.</span></span>
    
### <a name="string-types-supported"></a><span data-ttu-id="85e10-242">支持的字符串类型</span><span class="sxs-lookup"><span data-stu-id="85e10-242">String Types Supported</span></span>

<span data-ttu-id="85e10-243">**C API xltypeStr XLOPER/XLOPER12s**</span><span class="sxs-lookup"><span data-stu-id="85e10-243">**C API xltypeStr XLOPER/XLOPER12s**</span></span>

|<span data-ttu-id="85e10-244">\* \* 字节字符串: \* \* XLOPER \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="85e10-244">\*\*Byte strings: \*\*XLOPER\*\*\*\*</span></span>|<span data-ttu-id="85e10-245">\* \* 宽字符字符串: \* \* XLOPER12 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="85e10-245">\*\*Wide character strings: \*\*XLOPER12\*\*\*\*</span></span>|
|:-----|:-----|
|<span data-ttu-id="85e10-246">Excel 的所有版本</span><span class="sxs-lookup"><span data-stu-id="85e10-246">All versions of Excel</span></span>  <br/> |<span data-ttu-id="85e10-247">在 Excel 2007 中启动</span><span class="sxs-lookup"><span data-stu-id="85e10-247">Starting in Excel 2007</span></span>  <br/> |
|<span data-ttu-id="85e10-248">最大长度: 255 扩展 ASCII 字节</span><span class="sxs-lookup"><span data-stu-id="85e10-248">Max length: 255 extended ASCII bytes</span></span>  <br/> |<span data-ttu-id="85e10-249">最大长度 32767 Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="85e10-249">Maximum length 32,767 Unicode chars</span></span>  <br/> |
|<span data-ttu-id="85e10-250">First (无符号) 字节 = 长度</span><span class="sxs-lookup"><span data-stu-id="85e10-250">First (unsigned) byte = length</span></span>  <br/> |<span data-ttu-id="85e10-251">第一个 Unicode 字符 = 长度</span><span class="sxs-lookup"><span data-stu-id="85e10-251">First Unicode character = length</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="85e10-252">请勿假定**XLOPER**或**XLOPER12**字符串的 null 终止。</span><span class="sxs-lookup"><span data-stu-id="85e10-252">Do not assume null termination of **XLOPER** or **XLOPER12** strings.</span></span> 
  
<span data-ttu-id="85e10-253">**c/c + + 字符串**</span><span class="sxs-lookup"><span data-stu-id="85e10-253">**C/C++ strings**</span></span>

|<span data-ttu-id="85e10-254">**字节字符串**</span><span class="sxs-lookup"><span data-stu-id="85e10-254">**Byte strings**</span></span>|<span data-ttu-id="85e10-255">**宽字符字符串**</span><span class="sxs-lookup"><span data-stu-id="85e10-255">**Wide character strings**</span></span>|
|:-----|:-----|
|<span data-ttu-id="85e10-256">以 Null 结尾 (**char** \*) "C" 最大长度: 255 扩展 ASCII 字节</span><span class="sxs-lookup"><span data-stu-id="85e10-256">Null-terminated (**char** \*) "C" Max length: 255 extended ASCII bytes</span></span>  <br/> |<span data-ttu-id="85e10-257">以 Null 结尾 (**wchar_t** \*) "C%" 最大长度 32767 Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="85e10-257">Null-terminated (**wchar_t** \*) "C%" Maximum length 32,767 Unicode chars</span></span>  <br/> |
|<span data-ttu-id="85e10-258">Length 计数 (**无符号 char** \*) "D"</span><span class="sxs-lookup"><span data-stu-id="85e10-258">Length-counted (**unsigned char** \*) "D"</span></span>  <br/> |<span data-ttu-id="85e10-259">长度计数 (**wchar_t** \*) "D%"</span><span class="sxs-lookup"><span data-stu-id="85e10-259">Length-counted (**wchar_t** \*) "D%"</span></span>  <br/> |
   
### <a name="strings-in-xltypemulti-xloperxloper12-arrays"></a><span data-ttu-id="85e10-260">xltypeMulti XLOPER/XLOPER12 数组中的字符串</span><span class="sxs-lookup"><span data-stu-id="85e10-260">Strings in xltypeMulti XLOPER/XLOPER12 Arrays</span></span>

<span data-ttu-id="85e10-261">在几种情况下, Excel 将创建一个**xltypeMulti**数组, 以便在 DLL/XLL 中使用。</span><span class="sxs-lookup"><span data-stu-id="85e10-261">In several cases, Excel creates an **xltypeMulti** array for use in your DLL/XLL.</span></span> <span data-ttu-id="85e10-262">其中几个 XLM 信息函数返回此类数组。</span><span class="sxs-lookup"><span data-stu-id="85e10-262">Several of the XLM information functions return such arrays.</span></span> <span data-ttu-id="85e10-263">例如, 当传递参数*44*时, C API 函数**xlfGetWorkspace**返回一个包含描述所有当前注册的 DLL 过程的字符串的数组。</span><span class="sxs-lookup"><span data-stu-id="85e10-263">For example, the C API function **xlfGetWorkspace**, when passed the argument  *44*  , returns an array containing strings that describe all the currently registered DLL procedures.</span></span> <span data-ttu-id="85e10-264">C API 函数**xlfDialogBox**返回其 array 参数的修改副本, 其中包含字符串的深层副本。</span><span class="sxs-lookup"><span data-stu-id="85e10-264">The C API function **xlfDialogBox** returns a modified copy of its array argument, containing deep copies of the strings.</span></span> <span data-ttu-id="85e10-265">在 xll 遇到**xltypeMulti**数组的最常见方法是, 它已作为参数传递给 XLL 函数, 或者已通过区域引用强制转换为此类型。</span><span class="sxs-lookup"><span data-stu-id="85e10-265">Perhaps the most common way an XLL encounters an **xltypeMulti** array is where it has been passed as an argument to an XLL function, or it has been coerced to this type from a range reference.</span></span> <span data-ttu-id="85e10-266">在这些情况下, Excel 会在源单元格中创建字符串的深层副本, 并指向数组中的这些副本。</span><span class="sxs-lookup"><span data-stu-id="85e10-266">In these latter cases, Excel creates deep copies of the strings in the source cells and points to these within the array.</span></span> 
  
<span data-ttu-id="85e10-267">若要在 DLL 中修改这些字符串, 应制作自己的深层副本。</span><span class="sxs-lookup"><span data-stu-id="85e10-267">Where you want to modify these strings in your DLL, you should make your own deep copies.</span></span> <span data-ttu-id="85e10-268">当您创建自己的**xltypeMulti**数组时, 不应在其中放置 Excel 分配的字符串**XLOPER**/ **XLOPER12**s。</span><span class="sxs-lookup"><span data-stu-id="85e10-268">When you are creating your own **xltypeMulti** arrays, you should not place Excel-allocated string **XLOPER**/ **XLOPER12**s within them.</span></span> <span data-ttu-id="85e10-269">这种风险稍后不会正确释放它们, 也不会将其全部释放。</span><span class="sxs-lookup"><span data-stu-id="85e10-269">This risks you not freeing them correctly later, or not freeing them at all.</span></span> <span data-ttu-id="85e10-270">此外, 还应制作字符串的深层副本并将指针存储到数组中的副本。</span><span class="sxs-lookup"><span data-stu-id="85e10-270">Again, you should make deep copies of the strings and store pointers to the copies in the array.</span></span>
  
 <span data-ttu-id="85e10-271">**示例**</span><span class="sxs-lookup"><span data-stu-id="85e10-271">**Examples**</span></span>
  
<span data-ttu-id="85e10-272">下面的示例函数创建长度计数的 Unicode 字符串的动态分配副本。</span><span class="sxs-lookup"><span data-stu-id="85e10-272">The following example function creates a dynamically allocated copy of a length-counted Unicode string.</span></span> <span data-ttu-id="85e10-273">请注意, 调用方必须最终使用**delete**[] 释放在此示例中分配的内存, 并且源字符串未假定为 null 终止。</span><span class="sxs-lookup"><span data-stu-id="85e10-273">Note that the caller must ultimately free the memory allocated in this example using **delete**[], and that the source string is not assumed to be null terminated.</span></span> <span data-ttu-id="85e10-274">如果需要安全, 则将截断复制字符串, 且不能终止 null。</span><span class="sxs-lookup"><span data-stu-id="85e10-274">The copy string is truncated if necessary for safety, and is not null terminated.</span></span>
  
```cs
#include <string.h>
#define MAX_V12_STRBUFFLEN    32678
    
wchar_t * deep_copy_wcs(const wchar_t *p_source)
{
    if(!p_source)
        return NULL;
    size_t source_len = p_source[0];
    bool truncated = false;
    if(source_len >= MAX_V12_STRBUFFLEN)
    {
        source_len = MAX_V12_STRBUFFLEN - 1; // Truncate the copy
        truncated = true;
    }
    wchar_t *p_copy = new wchar_t[source_len + 1];
    wcsncpy_s(p_copy, p_source, source_len + 1);
    if(truncated)
        p_copy[0] = source_len;
    return p_copy;
}
```

<span data-ttu-id="85e10-275">然后, 可以安全地使用此函数复制**XLOPER12**, 如下面的可导出 XLL 函数中所示, 该函数返回其参数的副本 (如果它是字符串)。</span><span class="sxs-lookup"><span data-stu-id="85e10-275">This function can then be safely used to copy an **XLOPER12**, as shown in the following exportable XLL function that returns a copy of its argument if it is a string.</span></span> <span data-ttu-id="85e10-276">所有其他类型都以零长度字符串的形式返回。</span><span class="sxs-lookup"><span data-stu-id="85e10-276">All other types are returned as a zero-length string.</span></span> <span data-ttu-id="85e10-277">请注意, 区域不会得到处理—函数将返回 **#VALUE!**。</span><span class="sxs-lookup"><span data-stu-id="85e10-277">Note that ranges are not handled—the function returns **#VALUE!**.</span></span> <span data-ttu-id="85e10-278">函数必须注册为采用类型 U 参数, 以便以值的形式传递引用。</span><span class="sxs-lookup"><span data-stu-id="85e10-278">The function must be registered as taking a type U argument so that references are passed in as values.</span></span> <span data-ttu-id="85e10-279">这与内置工作表函数**T ()** 等效, 除了**AsText**也将错误转换为零长度字符串。</span><span class="sxs-lookup"><span data-stu-id="85e10-279">This is equivalent to the built-in worksheet function **T()** except that **AsText** also converts errors to zero-length strings.</span></span> <span data-ttu-id="85e10-280">此代码示例假定**xlAutoFree12**使用**delete**释放传入的指针以及它的内容。</span><span class="sxs-lookup"><span data-stu-id="85e10-280">This code example assumes that **xlAutoFree12** frees the passed-in pointer, and also its contents, using **delete**.</span></span>
  
```cs
LPXLOPER12 WINAPI AsText(LPXLOPER12 pArg)
{
    LPXLOPER12 pRtnVal = new XLOPER12;
// If the input was an array, only operate on the top-left element.
    LPXLOPER *pTemp;
    if(pArg->xltype == xltypeMulti)
        pTemp = pArg->val.array.lparray;
    else
        pTemp = pArg;
    switch(pTemp->xltype)
    {
        case xltypeErr:
        case xltypeNum:
        case xltypeMissing:
        case xltypeNil:
        case xltypeBool:
            pRtnVal->xltype = xltypeStr | xlbitDLLFree;
            pRtnVal->val.str = deep_copy_wcs(L"\000");
            return pRtnVal;
        case xltypeStr:
            pRtnVal->xltype = xltypeStr | xlbitDLLFree;
            pRtnVal->val.str = deep_copy_wcs(pTemp->val.str);
            return pRtnVal;
        
        default: // xltypeSRef, xltypeRef, xltypeFlow, xltypeInt
            pRtnVal->xltype = xltypeErr | xlbitDLLFree;
            pRtnVal->val.err = xlerrValue;
            return pRtnVal;
    }
}
```

### <a name="returning-modify-in-place-string-arguments"></a><span data-ttu-id="85e10-281">返回就地修改字符串参数</span><span class="sxs-lookup"><span data-stu-id="85e10-281">Returning Modify-in-Place String Arguments</span></span>

<span data-ttu-id="85e10-282">注册为**F**、 **g**、 **F%** 和**G%** 类型的参数可以就地修改。</span><span class="sxs-lookup"><span data-stu-id="85e10-282">Arguments registered as types **F**, **G**, **F%**, and **G%** can be modified in place.</span></span> <span data-ttu-id="85e10-283">Excel 在为这些类型准备字符串参数时, 将创建最大长度缓冲区。</span><span class="sxs-lookup"><span data-stu-id="85e10-283">When Excel is preparing string arguments for these types, it creates a maximum length buffer.</span></span> <span data-ttu-id="85e10-284">然后, 它将参数字符串复制到该字符串中, 即使该字符串要短得多。</span><span class="sxs-lookup"><span data-stu-id="85e10-284">Then it copies the argument string into that, even if this string is very much shorter.</span></span> <span data-ttu-id="85e10-285">这使 XLL 函数能够将其返回值直接写入同一内存中。</span><span class="sxs-lookup"><span data-stu-id="85e10-285">This enables the XLL function to write its return value directly into the same memory.</span></span> 
  
<span data-ttu-id="85e10-286">为这些类型单独设置的缓冲区大小如下所示:</span><span class="sxs-lookup"><span data-stu-id="85e10-286">Buffer sizes set apart for these types are as follows:</span></span>
  
- <span data-ttu-id="85e10-287">**字节字符串:** 256 个字节, 包括长度计数器 (type G) 或 null 终止 (F 类型)。</span><span class="sxs-lookup"><span data-stu-id="85e10-287">**Byte strings:** 256 bytes including the length counter (type G) or null-termination (type F).</span></span> 
    
- <span data-ttu-id="85e10-288">**Unicode 字符串:** 32768 宽字符 (65536 个字节), 包括长度计数器 (type G%)或 null-终止 (类型为 F%)。</span><span class="sxs-lookup"><span data-stu-id="85e10-288">**Unicode strings:** 32,768 wide characters (65,536 bytes) including the length counter (type G%) or null-termination (type F%).</span></span> 
    
> [!NOTE]
> <span data-ttu-id="85e10-289">您无法直接从 Visual Basic for Applications (VBA) 调用这样的函数, 因为您无法确保已分配足够大的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="85e10-289">You cannot call such a function directly from Visual Basic for Applications (VBA) because you cannot ensure that a sufficiently large buffer has been allocated.</span></span> <span data-ttu-id="85e10-290">如果显式传递足够大的缓冲区, 则只能从另一个 DLL 安全地调用这样的函数。</span><span class="sxs-lookup"><span data-stu-id="85e10-290">You can only call such a function from another DLL safely if you have explicitly passed a big enough buffer.</span></span> 
  
<span data-ttu-id="85e10-291">下面的示例展示了 XLL 函数, 该函数使用标准库函数**wcsrev**反转传入的以 null 结尾的宽字符字符串。</span><span class="sxs-lookup"><span data-stu-id="85e10-291">Here is an example of an XLL function that reverses a passed-in null-terminated wide character string using the standard library function **wcsrev**.</span></span> <span data-ttu-id="85e10-292">此示例中的参数将注册为类型**F%**。</span><span class="sxs-lookup"><span data-stu-id="85e10-292">The argument in this case would be registered as type **F%**.</span></span>
  
```cs
void WINAPI reverse_text_xl12(wchar_t *text)
{
    _wcsrev(text);
}
```

## <a name="persistent-storage-binary-names"></a><span data-ttu-id="85e10-293">永久性存储 (二进制名称)</span><span class="sxs-lookup"><span data-stu-id="85e10-293">Persistent Storage (Binary Names)</span></span>

<span data-ttu-id="85e10-294">二进制名称定义并与二进制块 (即非结构化的数据与工作簿一起存储) 相关联。</span><span class="sxs-lookup"><span data-stu-id="85e10-294">Binary names are defined and associated with blocks of binary, that is, unstructured, data that is stored together with the workbook.</span></span> <span data-ttu-id="85e10-295">它们是使用函数[xlDefineBinaryName](xldefinebinaryname.md)创建的, 并使用函数[xlGetBinaryName](xlgetbinaryname.md)检索数据。</span><span class="sxs-lookup"><span data-stu-id="85e10-295">They are created using the function [xlDefineBinaryName](xldefinebinaryname.md), and the data is retrieved using the function [xlGetBinaryName](xlgetbinaryname.md).</span></span> <span data-ttu-id="85e10-296">函数引用中更详细地介绍了这两个函数 (请参阅[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)), 并且两者都使用**xltypeBigData** **XLOPER**/ **XLOPER12**。</span><span class="sxs-lookup"><span data-stu-id="85e10-296">Both functions are described in more detail in the function reference (see [C API Functions That Can Be Called Only from a DLL or XLL](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)), and both use the **xltypeBigData** **XLOPER**/ **XLOPER12**.</span></span> 
  
<span data-ttu-id="85e10-297">有关限制二进制名称的实际应用程序的已知问题的信息, 请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。</span><span class="sxs-lookup"><span data-stu-id="85e10-297">For information about known issues that limit the practical applications of binary names, see [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
## <a name="excel-stack"></a><span data-ttu-id="85e10-298">Excel 堆栈</span><span class="sxs-lookup"><span data-stu-id="85e10-298">Excel Stack</span></span>

<span data-ttu-id="85e10-299">Excel 将与它所加载的所有 dll 共享其堆栈空间。</span><span class="sxs-lookup"><span data-stu-id="85e10-299">Excel shares its stack space with all the DLLs it has loaded.</span></span> <span data-ttu-id="85e10-300">堆栈空间通常不足以满足普通使用, 并且只要您遵循几条准则, 就不必担心它。</span><span class="sxs-lookup"><span data-stu-id="85e10-300">Stack space is usually more than adequate for ordinary use, and you do not need to be concerned about it as long as you follow a few guidelines:</span></span> 
  
- <span data-ttu-id="85e10-301">不要通过堆栈上的值将非常大的结构作为参数传递给函数。</span><span class="sxs-lookup"><span data-stu-id="85e10-301">Do not pass very large structures as arguments to functions by value on the stack.</span></span> <span data-ttu-id="85e10-302">改为传递指针或引用。</span><span class="sxs-lookup"><span data-stu-id="85e10-302">Pass pointers or references instead.</span></span>
    
- <span data-ttu-id="85e10-303">不要在堆栈上返回大型结构。</span><span class="sxs-lookup"><span data-stu-id="85e10-303">Do not return large structures on the stack.</span></span> <span data-ttu-id="85e10-304">将指针返回到静态或动态分配的内存, 或使用通过引用传递的参数。</span><span class="sxs-lookup"><span data-stu-id="85e10-304">Return pointers to static or dynamically allocated memory, or use arguments passed by reference.</span></span>
    
- <span data-ttu-id="85e10-305">不要在函数代码中声明非常大的自动变量结构。</span><span class="sxs-lookup"><span data-stu-id="85e10-305">Do not declare very large automatic variable structures in the function code.</span></span> <span data-ttu-id="85e10-306">如果需要, 请将它们声明为静态。</span><span class="sxs-lookup"><span data-stu-id="85e10-306">If you need them, declare them as static.</span></span>
    
- <span data-ttu-id="85e10-307">请勿以递归方式调用函数, 除非您确信递归的深度始终为浅。</span><span class="sxs-lookup"><span data-stu-id="85e10-307">Do not call functions recursively unless you are sure the depth of recursion will always be shallow.</span></span> <span data-ttu-id="85e10-308">请尝试改为使用循环。</span><span class="sxs-lookup"><span data-stu-id="85e10-308">Try using a loop instead.</span></span>
    
<span data-ttu-id="85e10-309">当 DLL 使用 C API 回调 excel 时, Excel 首先检查堆栈中是否有足够的空间, 可以进行最差的使用情况调用。</span><span class="sxs-lookup"><span data-stu-id="85e10-309">When a DLL calls back into Excel using the C API, Excel first checks whether there is enough space on the stack for the worst-case usage call that could be made.</span></span> <span data-ttu-id="85e10-310">如果它认为可能没有足够的聊天室, 则该调用将无法安全, 即使该特定调用可能有足够的空间。</span><span class="sxs-lookup"><span data-stu-id="85e10-310">If it thinks there might be insufficient room, it will fail the call to be safe, even though there might actually have been enough space for that particular call.</span></span> <span data-ttu-id="85e10-311">在这种情况下, 回调将返回代码**xlretFailed**。</span><span class="sxs-lookup"><span data-stu-id="85e10-311">In this case, the callbacks return the code **xlretFailed**.</span></span> <span data-ttu-id="85e10-312">对于 c api 和堆栈的普通使用, 不太可能导致 c api 调用失败。</span><span class="sxs-lookup"><span data-stu-id="85e10-312">For ordinary use of the C API and the stack, this is an unlikely cause of the failure of a C API call.</span></span>
  
<span data-ttu-id="85e10-313">如果您关注或只是想要避免由于不可解释的故障而导致堆栈空间不足, 则可以使用对[xlStack](xlstack.md)函数的调用来查明堆栈空间的数量。</span><span class="sxs-lookup"><span data-stu-id="85e10-313">If you are concerned, or just curious, or you want to eliminate lack of stack space as a reason for an unexplained failure, you can find out how much stack space there is with a call to the [xlStack](xlstack.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="85e10-314">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85e10-314">See also</span></span>



[<span data-ttu-id="85e10-315">Excel 中的多线程重新计算</span><span class="sxs-lookup"><span data-stu-id="85e10-315">Multithreaded Recalculation in Excel</span></span>](multithreaded-recalculation-in-excel.md)
  
[<span data-ttu-id="85e10-316">Excel 中的多线程和内存争用</span><span class="sxs-lookup"><span data-stu-id="85e10-316">Multithreading and Memory Contention in Excel</span></span>](multithreading-and-memory-contention-in-excel.md)
  
[<span data-ttu-id="85e10-317">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="85e10-317">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

