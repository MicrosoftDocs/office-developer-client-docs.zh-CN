---
title: Excel 中的内存管理
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- xloper12 内存 [excel 2007]，管理在 Excel 中的内存，Excel 堆栈，字符串 [Excel 2007]，管理内存，在 Excel 中，XLOPER 内存 [Excel 2007]，内存管理内存 [Excel 2007]，管理指南
localization_priority: Normal
ms.assetid: 3bf5195b-6235-43cf-8795-0c7b0a63a095
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 97c76d762fdc5e575c571804816e5581a7bec8bb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773806"
---
# <a name="memory-management-in-excel"></a><span data-ttu-id="c7f56-104">Excel 中的内存管理</span><span class="sxs-lookup"><span data-stu-id="c7f56-104">Memory Management in Excel</span></span>

 <span data-ttu-id="c7f56-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c7f56-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="c7f56-106">内存管理是最重要的担心，如果您想要创建高效的和稳定 xll （英文）。</span><span class="sxs-lookup"><span data-stu-id="c7f56-106">Memory management is the most important concern if you want to create efficient and stable XLLs.</span></span> <span data-ttu-id="c7f56-107">范围的 Microsoft Excel 中的问题会导致故障也管理内存 — 从低效的内存分配和初始化等小内存泄漏，例如 Excel 的不稳定的主要问题的小问题。</span><span class="sxs-lookup"><span data-stu-id="c7f56-107">Failure to manage memory well can lead to a range of problems in Microsoft Excel—from minor problems such as inefficient memory allocation and initialization and small memory leaks, to major problems such as the destabilization of Excel.</span></span>
  
<span data-ttu-id="c7f56-108">不当的内存严重添加在相关问题的最常见源。</span><span class="sxs-lookup"><span data-stu-id="c7f56-108">Mismanagement of memory is the most common source of serious add-in-related problems.</span></span> <span data-ttu-id="c7f56-109">因此，您应在内存管理生成的一致和良好-设计-通过策略与您的项目。</span><span class="sxs-lookup"><span data-stu-id="c7f56-109">Therefore, you should build your project with a consistent and well-thought-through strategy on memory management.</span></span> 
  
<span data-ttu-id="c7f56-110">内存管理变得 Microsoft Office Excel 2007 中引入了多线程的工作簿重新计算更复杂。</span><span class="sxs-lookup"><span data-stu-id="c7f56-110">Memory management became more complex in Microsoft Office Excel 2007 with the introduction of multithreaded workbook recalculation.</span></span> <span data-ttu-id="c7f56-111">如果您想要创建并导出线程安全工作表函数，必须管理生成多个线程争夺访问时可能出现的冲突。</span><span class="sxs-lookup"><span data-stu-id="c7f56-111">If you want to create and export thread-safe worksheet functions, you must manage the resulting conflicts that can occur when multiple threads compete for access.</span></span>
  
<span data-ttu-id="c7f56-112">有以下三种数据结构类型的内存注意事项：</span><span class="sxs-lookup"><span data-stu-id="c7f56-112">There are memory considerations for the following three data structure types:</span></span>
  
- <span data-ttu-id="c7f56-113">**XLOPER**s 和**XLOPER12**s</span><span class="sxs-lookup"><span data-stu-id="c7f56-113">**XLOPER**s and **XLOPER12**s</span></span>
    
- <span data-ttu-id="c7f56-114">不在**XLOPER**或**XLOPER12**的字符串</span><span class="sxs-lookup"><span data-stu-id="c7f56-114">Strings that are not in an **XLOPER** or **XLOPER12**</span></span>
    
- <span data-ttu-id="c7f56-115">**FP**和**FP12**阵列</span><span class="sxs-lookup"><span data-stu-id="c7f56-115">**FP** and **FP12** arrays</span></span> 
    
## <a name="xloperxloper12-memory"></a><span data-ttu-id="c7f56-116">XLOPER/XLOPER12 内存</span><span class="sxs-lookup"><span data-stu-id="c7f56-116">XLOPER/XLOPER12 Memory</span></span>

<span data-ttu-id="c7f56-117">**XLOPER**/ **XLOPER12**数据结构中有几个包含指向的内存，即 (**xltypeStr**) 字符串、 数组 (**xltypeMulti**) 和外部引用 (**xltypeRef**) 块的子类型。</span><span class="sxs-lookup"><span data-stu-id="c7f56-117">The **XLOPER**/ **XLOPER12** data structure has a few sub-types that contain pointers to blocks of memory, namely strings (**xltypeStr**), arrays (**xltypeMulti**) and external references (**xltypeRef**).</span></span> <span data-ttu-id="c7f56-118">还要注意**xltypeMulti**数组，可以包含字符串**XLOPER**/ **XLOPER12s**反过来指向其他块的内存。</span><span class="sxs-lookup"><span data-stu-id="c7f56-118">Note also that **xltypeMulti** arrays can contain string **XLOPER**/ **XLOPER12s** that in turn point to other blocks of memory.</span></span> 
  
<span data-ttu-id="c7f56-119">**XLOPER**/ **XLOPER12**可以创建以下几种方式：</span><span class="sxs-lookup"><span data-stu-id="c7f56-119">An **XLOPER**/ **XLOPER12** can be created in several ways:</span></span> 
  
- <span data-ttu-id="c7f56-120">由 Excel 时准备参数传递给 XLL 函数</span><span class="sxs-lookup"><span data-stu-id="c7f56-120">By Excel when preparing arguments to be passed to an XLL function</span></span>
    
- <span data-ttu-id="c7f56-121">由 Excel C API 中返回一个**XLOPER**或**XLOPER12**时调用</span><span class="sxs-lookup"><span data-stu-id="c7f56-121">By Excel when returning an **XLOPER** or **XLOPER12** in a C API call</span></span> 
    
- <span data-ttu-id="c7f56-122">按创建参数传递给 C API 时您 DLL 调用</span><span class="sxs-lookup"><span data-stu-id="c7f56-122">By your DLL when creating arguments to be passed to a C API call</span></span>
    
- <span data-ttu-id="c7f56-123">创建 XLL 函数返回值时 DLL</span><span class="sxs-lookup"><span data-stu-id="c7f56-123">By your DLL when creating an XLL function return value</span></span>
    
<span data-ttu-id="c7f56-124">以下几种方式可以分配一块的内存中内存指向类型之一：</span><span class="sxs-lookup"><span data-stu-id="c7f56-124">A block of memory within one of the memory-pointing types can be allocated in several ways:</span></span>
  
- <span data-ttu-id="c7f56-125">在这种情况下您无需分配或释放内存，它可以是任何函数在代码之外，您的 DLL 中的静态块。</span><span class="sxs-lookup"><span data-stu-id="c7f56-125">It can be a static block within your DLL outside any function code, in which case you do not have to allocate or free the memory.</span></span>
    
- <span data-ttu-id="c7f56-126">它可以是静态块内您的 DLL 中一些函数代码，在这种情况下您无需分配或释放内存。</span><span class="sxs-lookup"><span data-stu-id="c7f56-126">It can be a static block within your DLL within some function code, in which case you do not have to allocate or free the memory.</span></span>
    
- <span data-ttu-id="c7f56-127">它可以动态分配和释放您的 DLL 通过多种可能的方式： **malloc**和**免费**、**新建**和**删除**，等等。</span><span class="sxs-lookup"><span data-stu-id="c7f56-127">It can be dynamically allocated and freed by your DLL in several possible ways: **malloc** and **free**, **new** and **delete**, and so on.</span></span>
    
- <span data-ttu-id="c7f56-128">它可以由 Excel 动态分配。</span><span class="sxs-lookup"><span data-stu-id="c7f56-128">It can be dynamically allocated by Excel.</span></span>
    
<span data-ttu-id="c7f56-129">为**XLOPER**给定可能来源数/ **XLOPER12**内存和数的情况**XLOPER**/ **XLOPER12**可能已经分配的内存、 is not 此主题可以令人惊讶看起来很难。</span><span class="sxs-lookup"><span data-stu-id="c7f56-129">Given the number of possible origins for **XLOPER**/ **XLOPER12** memory and the number of situations in which the **XLOPER**/ **XLOPER12** might have had that memory assigned, it is not surprising that this subject can seem very difficult.</span></span> <span data-ttu-id="c7f56-130">但是，复杂性，会大大降低如果您执行多个规则和指导原则。</span><span class="sxs-lookup"><span data-stu-id="c7f56-130">However, the complexity can be greatly reduced if you follow several rules and guidelines.</span></span> 
  
### <a name="rules-for-working-with-xloperxloper12"></a><span data-ttu-id="c7f56-131">使用 XLOPER/XLOPER12 规则</span><span class="sxs-lookup"><span data-stu-id="c7f56-131">Rules for Working with XLOPER/XLOPER12</span></span>

- <span data-ttu-id="c7f56-132">不要尝试以释放内存中或覆盖**XLOPERs**/ 作为参数传递给 XLL 函数的**XLOPER12**s。</span><span class="sxs-lookup"><span data-stu-id="c7f56-132">Do not try to free memory or overwrite **XLOPERs**/ **XLOPER12**s that are passed as arguments to your XLL function.</span></span> <span data-ttu-id="c7f56-133">您应当将此类参数视为只读的。</span><span class="sxs-lookup"><span data-stu-id="c7f56-133">You should treat such arguments as read-only.</span></span> <span data-ttu-id="c7f56-134">有关详细信息，请参阅"返回**XLOPER**或**XLOPER12**就地修改参数由" [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)中。</span><span class="sxs-lookup"><span data-stu-id="c7f56-134">For more information, see "Returning **XLOPER** or **XLOPER12** by Modifying Arguments in Place" in [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
    
- <span data-ttu-id="c7f56-135">如果 Excel 已为**XLOPER**分配内存/ **XLOPER12**返回为您的 DLL 与 C API 调用中：</span><span class="sxs-lookup"><span data-stu-id="c7f56-135">If Excel has allocated memory for an **XLOPER**/ **XLOPER12** returned to your DLL in a call to the C API:</span></span> 
    
  - <span data-ttu-id="c7f56-136">您必须释放内存，当不再需要**XLOPER**/ **XLOPER12**使用[xlFree](xlfree.md)调用。</span><span class="sxs-lookup"><span data-stu-id="c7f56-136">You must free the memory when you no longer need the **XLOPER**/ **XLOPER12** using a call to [xlFree](xlfree.md).</span></span> <span data-ttu-id="c7f56-137">不要使用，任何其他方法，例如免费或删除释放的内存。</span><span class="sxs-lookup"><span data-stu-id="c7f56-137">Do not use any other method, such as free or delete, to release the memory.</span></span>
    
  - <span data-ttu-id="c7f56-138">如果返回的类型为**xltypeMulti**，不会覆盖任何**XLOPER**/ **XLOPER12**s 中的数组中，尤其是包含字符串，并特别是不其中您试图用字符串覆盖。</span><span class="sxs-lookup"><span data-stu-id="c7f56-138">If the returned type is **xltypeMulti**, do not overwrite any **XLOPER**/ **XLOPER12**s within the array, especially if they contain strings, and especially not where you are trying to overwrite with a string.</span></span>
    
  - <span data-ttu-id="c7f56-139">如果您想要返回**XLOPER**/ 到 DLL 函数的返回值为 Excel**XLOPER12** ，您必须判断 Excel 是否完成后，必须释放 Excel 的内存。</span><span class="sxs-lookup"><span data-stu-id="c7f56-139">If you want to return the **XLOPER**/ **XLOPER12** to Excel as your DLL function's return value, you must tell Excel that there is memory that Excel must release when done.</span></span> 
    
- <span data-ttu-id="c7f56-140">必须仅**XLOPER**上调用**xlFree** / **XLOPER12**创建用作的 C API 调用的返回值。</span><span class="sxs-lookup"><span data-stu-id="c7f56-140">You must only call **xlFree** on an **XLOPER**/ **XLOPER12** that was created as the return value to a C API call.</span></span> 
    
- <span data-ttu-id="c7f56-141">如果您的 DLL 已为**XLOPER**分配内存/ **XLOPER12**您想要返回到 Excel 作为您的 DLL 函数的返回值，您必须判断 Excel 是否存在 DLL 必须释放的内存。</span><span class="sxs-lookup"><span data-stu-id="c7f56-141">If your DLL has allocated memory for an **XLOPER**/ **XLOPER12** that you want to return to Excel as your DLL function's return value, you must tell Excel that there is memory that the DLL must release.</span></span> 
    
### <a name="guidelines-for-memory-management"></a><span data-ttu-id="c7f56-142">内存管理的指南</span><span class="sxs-lookup"><span data-stu-id="c7f56-142">Guidelines for Memory Management</span></span>

- <span data-ttu-id="c7f56-143">用于分配和释放内存的方法在 DLL 中保持一致。</span><span class="sxs-lookup"><span data-stu-id="c7f56-143">Be consistent in your DLL in the method that you use to allocate and release memory.</span></span> <span data-ttu-id="c7f56-144">避免混合方法。</span><span class="sxs-lookup"><span data-stu-id="c7f56-144">Avoid mixing methods.</span></span> <span data-ttu-id="c7f56-145">一个好方法是换行内存类或结构，您可以在其中更改而不需要更改您的代码在多个位置使用的方法中使用的方法。</span><span class="sxs-lookup"><span data-stu-id="c7f56-145">A good approach is to wrap the method that you are using up in a memory class or structure, within which you can change the method used without altering your code in many places.</span></span>
    
- <span data-ttu-id="c7f56-146">您的 DLL 中创建**xltypeMulti**数组时，需要对字符串分配内存的方式保持一致： 总是动态为其分配内存或始终使用静态内存。</span><span class="sxs-lookup"><span data-stu-id="c7f56-146">When you create **xltypeMulti** arrays within your DLL, be consistent in the way that you allocate memory for strings: always dynamically allocate the memory for them or always use static memory.</span></span> <span data-ttu-id="c7f56-147">如果这样做，当您要释放内存，您将知道，您必须始终或从不释放字符串。</span><span class="sxs-lookup"><span data-stu-id="c7f56-147">If you do this, when you are freeing the memory, you will know that you must either always or never free the strings.</span></span> 
    
- <span data-ttu-id="c7f56-148">复制 Excel 创建**XLOPER**时创建的 Excel 分配内存的深度副本/ **XLOPER12**。</span><span class="sxs-lookup"><span data-stu-id="c7f56-148">Make deep copies of Excel-allocated memory when you are copying an Excel-created **XLOPER**/ **XLOPER12**.</span></span>
    
- <span data-ttu-id="c7f56-149">请勿将 Excel 分配字符串**XLOPER**/ **XLOPER12**s **xltypeMulti**数组中的。</span><span class="sxs-lookup"><span data-stu-id="c7f56-149">Do not put Excel-allocated string **XLOPER**/ **XLOPER12**s within **xltypeMulti** arrays.</span></span> <span data-ttu-id="c7f56-150">字符串的深度副本并将指向副本存储数组中。</span><span class="sxs-lookup"><span data-stu-id="c7f56-150">Make deep copies of the strings and store pointers to the copies in the array.</span></span> 
    
## <a name="freeing-excel-allocated-xloperxloper12-memory"></a><span data-ttu-id="c7f56-151">释放 Excel 分配 XLOPER/XLOPER12 内存</span><span class="sxs-lookup"><span data-stu-id="c7f56-151">Freeing Excel-Allocated XLOPER/XLOPER12 Memory</span></span>

<span data-ttu-id="c7f56-152">请考虑以下 XLL 命令，其中使用**xlGetName**获取包含 DLL 的路径和文件名称的字符串，并将其显示在通知对话框中使用**xlcAlert**。</span><span class="sxs-lookup"><span data-stu-id="c7f56-152">Consider the following XLL command, which uses **xlGetName** to obtain a string containing the path and file name of the DLL and displays it in an alert dialog box using **xlcAlert**.</span></span>
  
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

<span data-ttu-id="c7f56-153">当函数不再需要通过**xDllName**指向的内存时，它可以释放其使用调用[xlFree 函数](xlfree.md)，仅 DLL C API 函数之一。</span><span class="sxs-lookup"><span data-stu-id="c7f56-153">When the function no longer needs the memory pointed to by **xDllName**, it can free it using a call to the [xlFree function](xlfree.md), one of the DLL-only C API functions.</span></span> 
  
<span data-ttu-id="c7f56-154">**XlFree**函数完全函数引用一节介绍了 （请参阅[C API 函数，可以将调用只能从 DLL 或 XLL](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)），但要注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="c7f56-154">The **xlFree** function is fully documented in the function reference section (see [C API Functions That Can Be Called Only from a DLL or XLL](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)), but be aware of the following:</span></span>
  
- <span data-ttu-id="c7f56-155">您可以将指针传递给多个**XLOPER**/ **XLOPER12**s **xlFree**，仅受 Excel (30 在 Excel 2003 中，从 Excel 2007 的 255) 运行版本中支持的函数参数数目限制将单个调用。</span><span class="sxs-lookup"><span data-stu-id="c7f56-155">You can pass pointers to more than one **XLOPER**/ **XLOPER12**s in a single call to **xlFree**, limited only by the number of function arguments supported in the running version of Excel (30 in Excel 2003, 255 starting in Excel 2007).</span></span>
    
- <span data-ttu-id="c7f56-156">**xlFree**将包含的指针设置为**NULL**以确保以尝试释放**XLOPER**/ 已释放的**XLOPER12**是安全的。</span><span class="sxs-lookup"><span data-stu-id="c7f56-156">**xlFree** sets the contained pointer to **NULL** to ensure that an attempt to free an **XLOPER**/ **XLOPER12** that has already been freed is safe.</span></span> <span data-ttu-id="c7f56-157">**xlFree**是唯一的 C API 函数的修改其参数。</span><span class="sxs-lookup"><span data-stu-id="c7f56-157">**xlFree** is the only C API function that modifies its arguments.</span></span> 
    
- <span data-ttu-id="c7f56-158">可以安全地在任何**XLOPER**上调用**xlFree** / **XLOPER12**用于 C API，无论其是否包含一个指向内存调用的返回值。</span><span class="sxs-lookup"><span data-stu-id="c7f56-158">You can safely call **xlFree** on any **XLOPER**/ **XLOPER12** used for the return value of a call to the C API, regardless of whether it contains a pointer to memory.</span></span> 
    
## <a name="returning-xloperxloper12s-to-be-freed-by-excel"></a><span data-ttu-id="c7f56-159">返回 XLOPER/XLOPER12s 释放由 Excel</span><span class="sxs-lookup"><span data-stu-id="c7f56-159">Returning XLOPER/XLOPER12s to be freed by Excel</span></span>

<span data-ttu-id="c7f56-160">假设您要修改上一节中的示例命令，并将其更改为返回 DLL 路径和文件名传递**布尔值** **true**参数和 **# n/A**否则为时的工作表函数。</span><span class="sxs-lookup"><span data-stu-id="c7f56-160">Suppose you wanted to modify the example command in the previous section and change it to a worksheet function that returns the DLL path and file name when passed a **Boolean** **true** argument, and **#N/A** otherwise.</span></span> <span data-ttu-id="c7f56-161">明确不能调用**xlFree**以返回到 Excel 之前版本的字符串内存。</span><span class="sxs-lookup"><span data-stu-id="c7f56-161">Clearly you cannot call **xlFree** to release the string memory before returning it to Excel.</span></span> <span data-ttu-id="c7f56-162">但是，如果它不会释放某个时刻外, 接程序会发生内存泄漏每次调用该函数。</span><span class="sxs-lookup"><span data-stu-id="c7f56-162">However, if it is not freed at some point, the add-in will leak memory every time the function is called.</span></span> <span data-ttu-id="c7f56-163">若要解决此问题，您可以设置一个位**XLOPER**的**xltype**字段中/ **XLOPER12**，定义为**xlbitXLFree** xlcall.h 中。</span><span class="sxs-lookup"><span data-stu-id="c7f56-163">To work around this problem, you can set a bit in the **xltype** field of the **XLOPER**/ **XLOPER12**, defined as **xlbitXLFree** in xlcall.h.</span></span> <span data-ttu-id="c7f56-164">设置通知 Excel 的值复制完成它必须释放返回的内存。</span><span class="sxs-lookup"><span data-stu-id="c7f56-164">Setting this tells Excel that it must free the returned memory when it has finished copying the value out.</span></span> 
  
### <a name="example"></a><span data-ttu-id="c7f56-165">示例</span><span class="sxs-lookup"><span data-stu-id="c7f56-165">Example</span></span>

<span data-ttu-id="c7f56-166">下面的代码示例显示在上一节转换为 XLL 工作表函数 XLL 命令。</span><span class="sxs-lookup"><span data-stu-id="c7f56-166">The following code example shows the XLL command in the previous section converted into an XLL worksheet function.</span></span>
  
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

<span data-ttu-id="c7f56-167">使用**XLOPER**XLL 函数/ **XLOPER12**s 必须声明为笔记记录和返回**XLOPER**指针/ **XLOPER12**s。</span><span class="sxs-lookup"><span data-stu-id="c7f56-167">XLL functions that use **XLOPER**/ **XLOPER12**s must be declared as taking and returning pointers to **XLOPER**/ **XLOPER12**s.</span></span> <span data-ttu-id="c7f56-168">在此示例中的静态**XLOPER12**函数中使用不安全的线程。</span><span class="sxs-lookup"><span data-stu-id="c7f56-168">The use in this example of a static **XLOPER12** within the function is not thread safe.</span></span> <span data-ttu-id="c7f56-169">您无法将此函数不正确注册为线程安全的但将风险**xRtnValue**一个线程另一个线程具有与其完成之前被覆盖。</span><span class="sxs-lookup"><span data-stu-id="c7f56-169">You could incorrectly register this function as thread safe, but you would risk **xRtnValue** being overwritten by one thread before another thread had finished with it.</span></span> 
  
<span data-ttu-id="c7f56-170">您必须为其分配的 Excel 回调调用后设置**xlbitXLFree** 。</span><span class="sxs-lookup"><span data-stu-id="c7f56-170">You must set **xlbitXLFree** after the call to the Excel callback that allocates it.</span></span> <span data-ttu-id="c7f56-171">如果您将其设置在此之前，它将被覆盖，并且没有所需效果。</span><span class="sxs-lookup"><span data-stu-id="c7f56-171">If you set it before this, it is overwritten and does not have the effect that you want.</span></span> <span data-ttu-id="c7f56-172">如果您打算使用作为对其他 C API 函数的调用中的参数的值，返回到工作表之前，您应任何此类呼叫后设置此位。</span><span class="sxs-lookup"><span data-stu-id="c7f56-172">If you intend to use the value as an argument in a call to another C API function before returning it to the worksheet, you should set this bit after any such call.</span></span> <span data-ttu-id="c7f56-173">否则，将将不执行检查**XLOPER**之前屏蔽此位的功能混淆/ **XLLOPER12**类型。</span><span class="sxs-lookup"><span data-stu-id="c7f56-173">Otherwise, you will confuse functions that do not mask this bit before checking the **XLOPER**/ **XLLOPER12** type.</span></span> 
  
## <a name="returning-xloperxloper12s-to-be-freed-by-the-dll"></a><span data-ttu-id="c7f56-174">返回 XLOPER/XLOPER12s 释放由 DLL</span><span class="sxs-lookup"><span data-stu-id="c7f56-174">Returning XLOPER/XLOPER12s to be freed by the DLL</span></span>

<span data-ttu-id="c7f56-175">类似于以下问题出现时您 XLL 已为**XLOPER**分配内存/ **XLOPER12**并想将它返回到 Excel。</span><span class="sxs-lookup"><span data-stu-id="c7f56-175">A similar problem to this occurs when your XLL has allocated memory for an **XLOPER**/ **XLOPER12** and wants to return it to Excel.</span></span> <span data-ttu-id="c7f56-176">Excel 识别可以设置**XLOPER** **xltype**字段中的另一位/ **XLOPER12**，定义为**xlbitDLLFree** xlcall.h 中。</span><span class="sxs-lookup"><span data-stu-id="c7f56-176">Excel recognizes another bit that can be set in the **xltype** field of the **XLOPER**/ **XLOPER12**, defined as **xlbitDLLFree** in xlcall.h.</span></span> 
  
<span data-ttu-id="c7f56-177">Excel 时接收**XLOPER**/ **XLOPER12**与此设置的位，它会尝试调用的函数，应通过调用[xlAutoFree](xlautofree-xlautofree12.md) （对于**XLOPER**s) 或**xlAutoFree12** （对于**XLOPER12**s) XLL 导出。</span><span class="sxs-lookup"><span data-stu-id="c7f56-177">When Excel receives **an XLOPER**/ **XLOPER12** with this bit set, it tries to call a function that should be exported by the XLL called [xlAutoFree](xlautofree-xlautofree12.md) (for **XLOPER**s) or **xlAutoFree12** (for **XLOPER12**s).</span></span> <span data-ttu-id="c7f56-178">函数引用中更详细地描述此函数 （请参阅[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)），但此处提供了示例最少实现。</span><span class="sxs-lookup"><span data-stu-id="c7f56-178">This function is described more fully in the function reference (see [Add-in Manager and XLL Interface Functions](add-in-manager-and-xll-interface-functions.md)), but an example minimal implementation is given here.</span></span> <span data-ttu-id="c7f56-179">其用途是以释放**XLOPER**/ **XLOPER12**内存与如何最初分配一致的方式。</span><span class="sxs-lookup"><span data-stu-id="c7f56-179">Its purpose is to free the **XLOPER**/ **XLOPER12** memory in a way that is consistent with how it was originally allocated.</span></span> 
  
### <a name="examples"></a><span data-ttu-id="c7f56-180">示例</span><span class="sxs-lookup"><span data-stu-id="c7f56-180">Examples</span></span>

<span data-ttu-id="c7f56-181">下面的示例函数将作用相同为以前函数之处在于它包含文本"此 dll 的完整路径名 is"DLL 名称之前。</span><span class="sxs-lookup"><span data-stu-id="c7f56-181">The following example function does the same as the previous function except that it includes the text "The full pathname for this DLL is " before the DLL name.</span></span>
  
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

<span data-ttu-id="c7f56-182">**XlAutoFree12**中导出以前的功能的 XLL 的至少具有足够实现将如下所示。</span><span class="sxs-lookup"><span data-stu-id="c7f56-182">A minimally sufficient implementation of **xlAutoFree12** in the XLL that exported the previous function would be as follows.</span></span> 
  
```cs
void WINAPI xlAutoFree12(LPXLOPER12 p_oper)
{
    if(p_oper->xltype == (xltypeStr | xlbitDLLFree))
        free(p_oper->val.str);
}
```

<span data-ttu-id="c7f56-183">如果 XLL 仅返回**XLOPER12**字符串，并且仅使用**malloc**分配这些字符串，此实现才足够。</span><span class="sxs-lookup"><span data-stu-id="c7f56-183">This implementation is only sufficient if the XLL only returns **XLOPER12** strings, and those strings are only allocated using **malloc**.</span></span> <span data-ttu-id="c7f56-184">请注意，测试</span><span class="sxs-lookup"><span data-stu-id="c7f56-184">Note that the test</span></span> 
  
 ` if(p_oper->xltype == xltypeStr) `
  
<span data-ttu-id="c7f56-185">在这种情况下会失败，因为**xlbitDLLFree**设置。</span><span class="sxs-lookup"><span data-stu-id="c7f56-185">would fail in this case because **xlbitDLLFree** is set.</span></span> 
  
<span data-ttu-id="c7f56-186">一般情况下， **xlAutoFree**和**xlAutoFree12**应实现，以便他们释放内存 XLL 创建**xltypeMulti**数组和**xltypeRef**外部引用相关联。</span><span class="sxs-lookup"><span data-stu-id="c7f56-186">In general, **xlAutoFree** and **xlAutoFree12** should be implemented so that they free memory associated with XLL-created **xltypeMulti** arrays and **xltypeRef** external references.</span></span> 
  
<span data-ttu-id="c7f56-187">您可能决定实施 XLL 函数，以便他们都返回动态分配**XLOPER**s 和**XLOPER12**s。</span><span class="sxs-lookup"><span data-stu-id="c7f56-187">You might decide to implement your XLL functions so that they ALL return dynamically allocated **XLOPER**s and **XLOPER12**s.</span></span> <span data-ttu-id="c7f56-188">在这种情况下，您需要在所有此类**XLOPER**s 和子类型无论**XLOPER12**s 上设置**xlbitDLLFree** 。</span><span class="sxs-lookup"><span data-stu-id="c7f56-188">In this case, you would need to set **xlbitDLLFree** on all such **XLOPER**s and **XLOPER12**s regardless of the sub-type.</span></span> <span data-ttu-id="c7f56-189">您还需要实施**xlAutoFree**和**xlAutoFree12**以便释放的此内存和也任何内存指向内**XLOPER**/ **XLOPER12**。</span><span class="sxs-lookup"><span data-stu-id="c7f56-189">You would also need to implement **xlAutoFree** and **xlAutoFree12** so that this memory was freed and also any memory pointed to within the **XLOPER**/ **XLOPER12**.</span></span> <span data-ttu-id="c7f56-190">此方法是一种方法使返回值线程安全的。</span><span class="sxs-lookup"><span data-stu-id="c7f56-190">This approach is one way to make the return value thread safe.</span></span> <span data-ttu-id="c7f56-191">例如，以前的功能可重写，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c7f56-191">For example, the previous function could be rewritten as follows.</span></span>
  
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

<span data-ttu-id="c7f56-192">有关**xlAutoFree**和**xlAutoFree12**的详细信息，请参阅[xlAutoFree/xlAutoFree12](xlautofree-xlautofree12.md)。</span><span class="sxs-lookup"><span data-stu-id="c7f56-192">For more information about **xlAutoFree** and **xlAutoFree12**, see [xlAutoFree/xlAutoFree12](xlautofree-xlautofree12.md).</span></span>
  
## <a name="returning-modify-in-place-arguments"></a><span data-ttu-id="c7f56-193">返回修改就地参数</span><span class="sxs-lookup"><span data-stu-id="c7f56-193">Returning Modify-in-Place Arguments</span></span>

<span data-ttu-id="c7f56-194">Excel 允许通过修改就地参数返回一个值，XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="c7f56-194">Excel allows an XLL function to return a value by modifying an argument in place.</span></span> <span data-ttu-id="c7f56-195">您可以仅处理此参数中传递作为指针。</span><span class="sxs-lookup"><span data-stu-id="c7f56-195">You can only do this with an argument passed in as a pointer.</span></span> <span data-ttu-id="c7f56-196">以类似，必须以告知 Excel 哪些参数将被修改一种注册的函数。</span><span class="sxs-lookup"><span data-stu-id="c7f56-196">To work like this, the function must be registered in a way that tells Excel which argument will be modified.</span></span> 
  
<span data-ttu-id="c7f56-197">返回一个值，此方法可通过指针传递的所有数据类型都支持，但对于以下类型的特别有用：</span><span class="sxs-lookup"><span data-stu-id="c7f56-197">This method of returning a value is supported for all data types that can be passed by pointer but is especially useful for the following types:</span></span>
  
- <span data-ttu-id="c7f56-198">长度计数和 null 结尾 ASCII 字节字符串</span><span class="sxs-lookup"><span data-stu-id="c7f56-198">Length-counted and null-terminated ASCII byte strings</span></span>
    
- <span data-ttu-id="c7f56-199">长度计数和空结尾 Unicode 宽字符字符串 （在 Excel 2007 中从开始）</span><span class="sxs-lookup"><span data-stu-id="c7f56-199">Length-counted and null-terminated Unicode wide character strings (starting in Excel 2007)</span></span>
    
- <span data-ttu-id="c7f56-200">**FP**浮点数组</span><span class="sxs-lookup"><span data-stu-id="c7f56-200">**FP** floating-point arrays</span></span> 
    
- <span data-ttu-id="c7f56-201">**FP12**浮点数组 （在 Excel 2007 中从开始）</span><span class="sxs-lookup"><span data-stu-id="c7f56-201">**FP12** floating-point arrays (starting in Excel 2007)</span></span> 
    
> [!NOTE]
> <span data-ttu-id="c7f56-202">不应尝试这种方式返回**XLOPER**s 或**XLOPER12**s。</span><span class="sxs-lookup"><span data-stu-id="c7f56-202">You should not try to return **XLOPER**s or **XLOPER12**s in this manner.</span></span> <span data-ttu-id="c7f56-203">有关详细信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。</span><span class="sxs-lookup"><span data-stu-id="c7f56-203">For more information, see [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span> 
  
<span data-ttu-id="c7f56-204">使用此技术，而不只需使用返回的语句的好处是 Excel 的返回值分配的内存。</span><span class="sxs-lookup"><span data-stu-id="c7f56-204">The advantage of using this technique, instead of just using the return statement, is that Excel allocates the memory for the return values.</span></span> <span data-ttu-id="c7f56-205">完成后读取返回的数据的 Excel，它释放内存。</span><span class="sxs-lookup"><span data-stu-id="c7f56-205">Once Excel has finished reading the returned data, it releases the memory.</span></span> <span data-ttu-id="c7f56-206">这将内存离开 XLL 函数的管理任务。</span><span class="sxs-lookup"><span data-stu-id="c7f56-206">This takes the memory management tasks away from the XLL function.</span></span> <span data-ttu-id="c7f56-207">线程安全利用此方法是： 如果同时调用在不同线程上由 Excel，每个线程上的每个函数调用具有自己的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c7f56-207">This technique is thread safe: If called concurrently by Excel on different threads, each function call on each thread has its own buffer.</span></span>
  
<span data-ttu-id="c7f56-208">非常有用的前面列出的数据类型特别是因为后调用以释放内存的 DLL 的机制后返回存在**XLOPER**/ 简单字符串和**FP**不存在**XLOPER12**s/ **FP12**数组。</span><span class="sxs-lookup"><span data-stu-id="c7f56-208">It is useful for the previously listed data types in particular because the mechanism for calling back into the DLL to free memory post-return that exists for **XLOPER**/ **XLOPER12**s does not exist for simple strings and **FP**/ **FP12** arrays.</span></span> <span data-ttu-id="c7f56-209">因此，当返回 DLL 创建字符串或浮点数组，您有以下选择：</span><span class="sxs-lookup"><span data-stu-id="c7f56-209">Therefore, when returning a DLL-created string or floating-point array, you have the following choices:</span></span> 
  
- <span data-ttu-id="c7f56-210">设置为动态分配缓冲区的持久的指针，则返回指针。</span><span class="sxs-lookup"><span data-stu-id="c7f56-210">Set a persistent pointer to a dynamically allocated buffer, return the pointer.</span></span> <span data-ttu-id="c7f56-211">在下次调用函数 （1） 检查指针不为 null，（2） 免费资源分配上以前的呼叫，将指针重置为 null，重复 （3） 使用的内存新分配块的指针。</span><span class="sxs-lookup"><span data-stu-id="c7f56-211">On the next call to the function (1) check that the pointer is not null, (2) free the resources allocated on the previous call and reset the pointer to null, (3) reuse the pointer for a newly allocated block of memory.</span></span>
    
- <span data-ttu-id="c7f56-212">在不需要释放，并返回一个指针的静态缓冲区中创建您的字符串和数组。</span><span class="sxs-lookup"><span data-stu-id="c7f56-212">Create your strings and arrays in a static buffer that does not need to be freed, and return a pointer to that.</span></span>
    
- <span data-ttu-id="c7f56-213">修改就地情况下，直接到由 Excel 设置留出空间编写您的字符串或阵列的参数。</span><span class="sxs-lookup"><span data-stu-id="c7f56-213">Modify an argument in place, writing your string or array directly into the space set aside by Excel.</span></span>
    
<span data-ttu-id="c7f56-214">否则，您必须创建**XLOPER**/ **XLOPER12**，以及使用**xlbitDLLFree**和**xlAutoFree**/ **xlAutoFree12**以释放资源。</span><span class="sxs-lookup"><span data-stu-id="c7f56-214">Otherwise, you must create an **XLOPER**/ **XLOPER12**, and use **xlbitDLLFree** and **xlAutoFree**/ **xlAutoFree12** to release the resources.</span></span> 
  
<span data-ttu-id="c7f56-215">可能在这些情况下，其中您正在相同类型的参数作为传递返回值的最简单的最后一个选项。</span><span class="sxs-lookup"><span data-stu-id="c7f56-215">The last option might be the simplest in those cases in which you are being passed an argument of the same type as the return value.</span></span> <span data-ttu-id="c7f56-216">要记住的关键点是缓冲区大小被限制，并且必须谨慎以溢出它们。</span><span class="sxs-lookup"><span data-stu-id="c7f56-216">The key point to remember is that the buffer sizes are limited and you must be very careful not to overrun them.</span></span> <span data-ttu-id="c7f56-217">获取此错误可能会崩溃 Excel。</span><span class="sxs-lookup"><span data-stu-id="c7f56-217">Getting this wrong could crash Excel.</span></span> <span data-ttu-id="c7f56-218">缓冲区大小的字符串和**FP**/ **FP12**数组的后面进行讨论。</span><span class="sxs-lookup"><span data-stu-id="c7f56-218">Buffer sizes for strings and **FP**/ **FP12** arrays are discussed next.</span></span> 
  
## <a name="strings"></a><span data-ttu-id="c7f56-219">字符串</span><span class="sxs-lookup"><span data-stu-id="c7f56-219">Strings</span></span>

<span data-ttu-id="c7f56-220">字符串内存管理问题可以说是在应用程序和加载项的不稳定的最常见原因。它易于理解可能是，提供的各种方法中处理字符串： 空终止或长度计数 （或两者）;静态或动态缓冲区;固定的长度或几乎不限的长度;操作系统托管内存 (例如，OLE Bstr) 或非托管的字符串;等等。</span><span class="sxs-lookup"><span data-stu-id="c7f56-220">Problems with the management of string memory are arguably the most common cause of instability in applications and add-ins. It is understandable perhaps, given the variety of ways in which strings are handled: null-terminated or length-counted (or both); static or dynamic buffers; fixed length or almost unlimited length; operating-system managed memory (for example, OLE Bstr) or unmanaged strings; and so on.</span></span>
  
<span data-ttu-id="c7f56-221">C/c + + 程序员熟悉最 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="c7f56-221">C/C++ programmers are most familiar with null-terminated strings.</span></span> <span data-ttu-id="c7f56-222">标准 C 库旨在处理此类字符串。</span><span class="sxs-lookup"><span data-stu-id="c7f56-222">The standard C library is designed to work with such strings.</span></span> <span data-ttu-id="c7f56-223">在代码中的静态字符串编译为 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="c7f56-223">Static string literals in code are compiled into null-terminated strings.</span></span> <span data-ttu-id="c7f56-224">此外，Excel 适用于是不通常 null 结尾的长度计数的字符串。</span><span class="sxs-lookup"><span data-stu-id="c7f56-224">Alternatively, Excel works with length-counted strings that are not in general null-terminated.</span></span> <span data-ttu-id="c7f56-225">这些信息的组合需要有关如何处理字符串和字符串内存您 DLL/XLL 中清除和一致的方法。</span><span class="sxs-lookup"><span data-stu-id="c7f56-225">The combination of these facts requires a clear and consistent approach within your DLL/XLL regarding how you handle strings and string memory.</span></span>
  
<span data-ttu-id="c7f56-226">最常见的问题如下所示：</span><span class="sxs-lookup"><span data-stu-id="c7f56-226">The most common problems are as follows:</span></span>
  
- <span data-ttu-id="c7f56-227">到需要有效指针和不或无法检查指针的有效性本身的函数为 null 或无效指针传递。</span><span class="sxs-lookup"><span data-stu-id="c7f56-227">The passing of a null or invalid pointer to a function that expects a valid pointer and does not or cannot check the pointer's validity itself.</span></span>
    
- <span data-ttu-id="c7f56-228">致使溢出的字符串缓冲区的边界由一个函数不或无法检查针对写入的字符串的长度缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="c7f56-228">The overrunning of the bounds of a string buffer by a function that does not or cannot check the length of the buffer against the length of the string being written.</span></span>
    
- <span data-ttu-id="c7f56-229">尝试释放字符串缓冲区内存的是静态、 已，已释放或未分配与如何释放一致的方式。</span><span class="sxs-lookup"><span data-stu-id="c7f56-229">Trying to free string buffer memory that is either static, or has been freed already, or was not allocated in a way that is consistent with how it is being freed.</span></span>
    
- <span data-ttu-id="c7f56-230">内存泄漏字符串被分配，然后不释放，通常在经常调用的函数的结果。</span><span class="sxs-lookup"><span data-stu-id="c7f56-230">Memory leaks that result from strings being allocated and then not freed, usually in a frequently called function.</span></span>
    
### <a name="rules-for-strings"></a><span data-ttu-id="c7f56-231">字符串规则</span><span class="sxs-lookup"><span data-stu-id="c7f56-231">Rules for Strings</span></span>

<span data-ttu-id="c7f56-232">**XLOPER**与/ **XLOPER**s 有规则，您应遵循的准则。</span><span class="sxs-lookup"><span data-stu-id="c7f56-232">As with **XLOPER**/ **XLOPER**s, there are rules and guidelines you should follow.</span></span> <span data-ttu-id="c7f56-233">上一节中，准则是与给定相同。</span><span class="sxs-lookup"><span data-stu-id="c7f56-233">The guidelines are the same as given in the previous section.</span></span> <span data-ttu-id="c7f56-234">下面的规则是专为字符串的规则的一种扩展。</span><span class="sxs-lookup"><span data-stu-id="c7f56-234">The rules here are an extension of the rules specifically for strings.</span></span>
  
 <span data-ttu-id="c7f56-235">**规则：**</span><span class="sxs-lookup"><span data-stu-id="c7f56-235">**Rules:**</span></span>
  
- <span data-ttu-id="c7f56-236">不要尝试以释放内存中或覆盖字符串**XLOPER**/ **XLOPER12**s 或简单的长度计数或空结尾字符串作为参数传递给 XLL 函数。</span><span class="sxs-lookup"><span data-stu-id="c7f56-236">Do not try to free memory or overwrite string **XLOPER**/ **XLOPER12**s or simple length-counted or null-terminated strings passed as arguments to your XLL function.</span></span> <span data-ttu-id="c7f56-237">您应当将此类参数视为只读的。</span><span class="sxs-lookup"><span data-stu-id="c7f56-237">You should treat such arguments as read-only.</span></span>
    
- <span data-ttu-id="c7f56-238">Excel 字符串**XLOPER**分配内存的其中/ **XLOPER12**的 C API 回调函数，返回值使用**xlFree**忙，或如果从 XLL 函数返回到 Excel 设置**xlbitXLFree** 。</span><span class="sxs-lookup"><span data-stu-id="c7f56-238">Where Excel allocates memory for a string **XLOPER**/ **XLOPER12** for the return value of a C API callback function, use **xlFree** to free it, or set **xlbitXLFree** if returning it to Excel from an XLL function.</span></span> 
    
- <span data-ttu-id="c7f56-239">其中 DLL 动态字符串的一个缓冲区分配**XLOPER**/ **XLOPER12**，忙时进行设置，或如果从 XLL 函数返回到 Excel 设置**xlbitDLLFree**分配方式与一致的方式，然后释放中**xlAutoFree**/  **xlAutoFree12**。</span><span class="sxs-lookup"><span data-stu-id="c7f56-239">Where your DLL dynamically allocates a string buffer for an **XLOPER**/ **XLOPER12**, free it in a way consistent with how you allocated it when done, or set **xlbitDLLFree** if returning it to Excel from an XLL function and then free it in **xlAutoFree**/ **xlAutoFree12**.</span></span>
    
- <span data-ttu-id="c7f56-240">如果 Excel 已返回到 C API 调用 DLL **xltypeMulti**数组分配内存，不会覆盖任何字符串**XLOPER**/ 在阵列中的**XLOPER12**s。</span><span class="sxs-lookup"><span data-stu-id="c7f56-240">If Excel has allocated memory for an **xltypeMulti** array returned to your DLL in a call to the C API, do not overwrite any string **XLOPER**/ **XLOPER12**s within the array.</span></span> <span data-ttu-id="c7f56-241">此类数组才必须释放即可使用**xlFree**，或者，如果正在 XLL 函数返回，通过设置**xlbitXLFree**。</span><span class="sxs-lookup"><span data-stu-id="c7f56-241">Such arrays must only be freed using **xlFree**, or, if being returned by an XLL function, by setting **xlbitXLFree**.</span></span>
    
### <a name="string-types-supported"></a><span data-ttu-id="c7f56-242">支持的字符串类型</span><span class="sxs-lookup"><span data-stu-id="c7f56-242">String Types Supported</span></span>

<span data-ttu-id="c7f56-243">**C API xltypeStr XLOPER/XLOPER12s**</span><span class="sxs-lookup"><span data-stu-id="c7f56-243">**C API xltypeStr XLOPER/XLOPER12s**</span></span>

|<span data-ttu-id="c7f56-244">\* \* 字节字符串: \* \* XLOPER \*\*\*</span><span class="sxs-lookup"><span data-stu-id="c7f56-244">**Byte strings: **XLOPER****</span></span>|<span data-ttu-id="c7f56-245">\* \* 宽字符的字符串: \* \* XLOPER12 \*\*\*</span><span class="sxs-lookup"><span data-stu-id="c7f56-245">**Wide character strings: **XLOPER12****</span></span>|
|:-----|:-----|
|<span data-ttu-id="c7f56-246">所有版本的 Excel</span><span class="sxs-lookup"><span data-stu-id="c7f56-246">All versions of Excel</span></span>  <br/> |<span data-ttu-id="c7f56-247">从 Excel 2007</span><span class="sxs-lookup"><span data-stu-id="c7f56-247">Starting in Excel 2007</span></span>  <br/> |
|<span data-ttu-id="c7f56-248">最大长度： 255 扩展 ASCII 字节</span><span class="sxs-lookup"><span data-stu-id="c7f56-248">Max length: 255 extended ASCII bytes</span></span>  <br/> |<span data-ttu-id="c7f56-249">最大长度 32767 Unicode 字符数</span><span class="sxs-lookup"><span data-stu-id="c7f56-249">Maximum length 32,767 Unicode chars</span></span>  <br/> |
|<span data-ttu-id="c7f56-250">（无符号） 的第一个字节 = 长度</span><span class="sxs-lookup"><span data-stu-id="c7f56-250">First (unsigned) byte = length</span></span>  <br/> |<span data-ttu-id="c7f56-251">第一个 Unicode 字符 = 长度</span><span class="sxs-lookup"><span data-stu-id="c7f56-251">First Unicode character = length</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="c7f56-252">请假定 null 终止**XLOPER**或**XLOPER12**字符串。</span><span class="sxs-lookup"><span data-stu-id="c7f56-252">Do not assume null termination of **XLOPER** or **XLOPER12** strings.</span></span> 
  
<span data-ttu-id="c7f56-253">**C/c + + 字符串**</span><span class="sxs-lookup"><span data-stu-id="c7f56-253">**C/C++ strings**</span></span>

|<span data-ttu-id="c7f56-254">**字节字符串**</span><span class="sxs-lookup"><span data-stu-id="c7f56-254">**Byte strings**</span></span>|<span data-ttu-id="c7f56-255">**宽字符的字符串**</span><span class="sxs-lookup"><span data-stu-id="c7f56-255">**Wide character strings**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c7f56-256">Null 结尾 (**char** \*)"C"最大长度： 255 扩展 ASCII 字节</span><span class="sxs-lookup"><span data-stu-id="c7f56-256">Null-terminated (**char** \*) "C" Max length: 255 extended ASCII bytes</span></span>  <br/> |<span data-ttu-id="c7f56-257">Null 结尾 (**wchar_t** \*)"C %"最大长度 32767 Unicode 字符数</span><span class="sxs-lookup"><span data-stu-id="c7f56-257">Null-terminated (**wchar_t** \*) "C%" Maximum length 32,767 Unicode chars</span></span>  <br/> |
|<span data-ttu-id="c7f56-258">长度计数 (**未签署的 char** \*)"D"</span><span class="sxs-lookup"><span data-stu-id="c7f56-258">Length-counted (**unsigned char** \*) "D"</span></span>  <br/> |<span data-ttu-id="c7f56-259">长度计数 (**wchar_t** \*)"D %"</span><span class="sxs-lookup"><span data-stu-id="c7f56-259">Length-counted (**wchar_t** \*) "D%"</span></span>  <br/> |
   
### <a name="strings-in-xltypemulti-xloperxloper12-arrays"></a><span data-ttu-id="c7f56-260">XltypeMulti XLOPER/XLOPER12 数组中的字符串</span><span class="sxs-lookup"><span data-stu-id="c7f56-260">Strings in xltypeMulti XLOPER/XLOPER12 Arrays</span></span>

<span data-ttu-id="c7f56-261">在某些情况下，Excel 将新建用于 DLL/XLL **xltypeMulti**数组。</span><span class="sxs-lookup"><span data-stu-id="c7f56-261">In several cases, Excel creates an **xltypeMulti** array for use in your DLL/XLL.</span></span> <span data-ttu-id="c7f56-262">有几个 XLM 信息函数返回这样的数组。</span><span class="sxs-lookup"><span data-stu-id="c7f56-262">Several of the XLM information functions return such arrays.</span></span> <span data-ttu-id="c7f56-263">例如，C API 函数**xlfGetWorkspace**，当传递参数*44*中，返回包含所有当前注册的 DLL 过程描述的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="c7f56-263">For example, the C API function **xlfGetWorkspace**, when passed the argument  *44*  , returns an array containing strings that describe all the currently registered DLL procedures.</span></span> <span data-ttu-id="c7f56-264">C API 函数**xlfDialogBox**返回包含字符串的深层副本其数组参数修改的副本。</span><span class="sxs-lookup"><span data-stu-id="c7f56-264">The C API function **xlfDialogBox** returns a modified copy of its array argument, containing deep copies of the strings.</span></span> <span data-ttu-id="c7f56-265">可能 XLL 遇到**xltypeMulti**数组的最常见方式是，它具有已作为参数传递给 XLL 函数，或它具有已强制转换为此类型从区域引用。</span><span class="sxs-lookup"><span data-stu-id="c7f56-265">Perhaps the most common way an XLL encounters an **xltypeMulti** array is where it has been passed as an argument to an XLL function, or it has been coerced to this type from a range reference.</span></span> <span data-ttu-id="c7f56-266">在这些后的情况下，Excel 将新建深入份中的源单元格和指向这些数组中的字符串。</span><span class="sxs-lookup"><span data-stu-id="c7f56-266">In these latter cases, Excel creates deep copies of the strings in the source cells and points to these within the array.</span></span> 
  
<span data-ttu-id="c7f56-267">想要修改在 DLL，这些字符串应创建您自己深入的副本。</span><span class="sxs-lookup"><span data-stu-id="c7f56-267">Where you want to modify these strings in your DLL, you should make your own deep copies.</span></span> <span data-ttu-id="c7f56-268">当您正在创建您自己**xltypeMulti**数组时，不应将 Excel 分配字符串**XLOPER**/ 其中**XLOPER12**s。</span><span class="sxs-lookup"><span data-stu-id="c7f56-268">When you are creating your own **xltypeMulti** arrays, you should not place Excel-allocated string **XLOPER**/ **XLOPER12**s within them.</span></span> <span data-ttu-id="c7f56-269">此风险您没有释放它们正确更高版本，或不根本释放。</span><span class="sxs-lookup"><span data-stu-id="c7f56-269">This risks you not freeing them correctly later, or not freeing them at all.</span></span> <span data-ttu-id="c7f56-270">同样，您应创建的字符串的深度副本和数组中存储的副本的指针。</span><span class="sxs-lookup"><span data-stu-id="c7f56-270">Again, you should make deep copies of the strings and store pointers to the copies in the array.</span></span>
  
 <span data-ttu-id="c7f56-271">**示例**</span><span class="sxs-lookup"><span data-stu-id="c7f56-271">**Examples**</span></span>
  
<span data-ttu-id="c7f56-272">下面的示例函数创建动态分配的长度计数 Unicode 字符串的副本。</span><span class="sxs-lookup"><span data-stu-id="c7f56-272">The following example function creates a dynamically allocated copy of a length-counted Unicode string.</span></span> <span data-ttu-id="c7f56-273">请注意，呼叫者最终必须释放在此示例中使用**删除**[]，分配的内存和源字符串不假定为 null 终止。</span><span class="sxs-lookup"><span data-stu-id="c7f56-273">Note that the caller must ultimately free the memory allocated in this example using **delete**[], and that the source string is not assumed to be null terminated.</span></span> <span data-ttu-id="c7f56-274">该副本字符串被截断为了安全，必要时，不为 null 终止。</span><span class="sxs-lookup"><span data-stu-id="c7f56-274">The copy string is truncated if necessary for safety, and is not null terminated.</span></span>
  
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

<span data-ttu-id="c7f56-275">此函数可然后安全地用于复制**XLOPER12**，如下面的可导出 XLL 函数的返回其参数的副本，如果它是一个字符串中所示。</span><span class="sxs-lookup"><span data-stu-id="c7f56-275">This function can then be safely used to copy an **XLOPER12**, as shown in the following exportable XLL function that returns a copy of its argument if it is a string.</span></span> <span data-ttu-id="c7f56-276">所有其他类型为零长度字符串返回。</span><span class="sxs-lookup"><span data-stu-id="c7f56-276">All other types are returned as a zero-length string.</span></span> <span data-ttu-id="c7f56-277">请注意，不会处理区域 — 此函数返回 **#VALUE ！**。</span><span class="sxs-lookup"><span data-stu-id="c7f56-277">Note that ranges are not handled—the function returns **#VALUE!**.</span></span> <span data-ttu-id="c7f56-278">为采用类型 U 参数，以便引用中传递的值必须注册的函数。</span><span class="sxs-lookup"><span data-stu-id="c7f56-278">The function must be registered as taking a type U argument so that references are passed in as values.</span></span> <span data-ttu-id="c7f56-279">这是等价于内置工作表函数**T()** ，之处在于**AsText**还将错误转换为零长度字符串。</span><span class="sxs-lookup"><span data-stu-id="c7f56-279">This is equivalent to the built-in worksheet function **T()** except that **AsText** also converts errors to zero-length strings.</span></span> <span data-ttu-id="c7f56-280">此代码示例假定该**xlAutoFree12**释放传入的指针，以及其内容，使用**删除**。</span><span class="sxs-lookup"><span data-stu-id="c7f56-280">This code example assumes that **xlAutoFree12** frees the passed-in pointer, and also its contents, using **delete**.</span></span>
  
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

### <a name="returning-modify-in-place-string-arguments"></a><span data-ttu-id="c7f56-281">返回修改就地字符串参数</span><span class="sxs-lookup"><span data-stu-id="c7f56-281">Returning Modify-in-Place String Arguments</span></span>

<span data-ttu-id="c7f56-282">**F**、 **G**、 **%f%**，参数注册为类型，并可以就地修改**G %** 。</span><span class="sxs-lookup"><span data-stu-id="c7f56-282">Arguments registered as types **F**, **G**, **F%**, and **G%** can be modified in place.</span></span> <span data-ttu-id="c7f56-283">在 Excel 准备这些类型的字符串参数时，它会创建的最大长度缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c7f56-283">When Excel is preparing string arguments for these types, it creates a maximum length buffer.</span></span> <span data-ttu-id="c7f56-284">然后它将复制的参数字符串到，即使此字符串是很大程度较短。</span><span class="sxs-lookup"><span data-stu-id="c7f56-284">Then it copies the argument string into that, even if this string is very much shorter.</span></span> <span data-ttu-id="c7f56-285">这样，XLL 函数，直接将其返回值写入同一内存。</span><span class="sxs-lookup"><span data-stu-id="c7f56-285">This enables the XLL function to write its return value directly into the same memory.</span></span> 
  
<span data-ttu-id="c7f56-286">缓冲区大小分开为这些类型如下所示：</span><span class="sxs-lookup"><span data-stu-id="c7f56-286">Buffer sizes set apart for these types are as follows:</span></span>
  
- <span data-ttu-id="c7f56-287">**字节字符串：** 256 字节包括长度计数器 （类型 G） 或 null 终止 （F 类型）。</span><span class="sxs-lookup"><span data-stu-id="c7f56-287">**Byte strings:** 256 bytes including the length counter (type G) or null-termination (type F).</span></span> 
    
- <span data-ttu-id="c7f56-288">**Unicode 字符串：** 32,768 个宽字符 （65536 字节） 包括长度计数器 （类型 G %） 或 null 终止 （F 类型 %）。</span><span class="sxs-lookup"><span data-stu-id="c7f56-288">**Unicode strings:** 32,768 wide characters (65,536 bytes) including the length counter (type G%) or null-termination (type F%).</span></span> 
    
> [!NOTE]
> <span data-ttu-id="c7f56-289">不能调用此类函数直接从 Visual Basic for Applications (VBA) 因为您不能确保已分配足够大缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c7f56-289">You cannot call such a function directly from Visual Basic for Applications (VBA) because you cannot ensure that a sufficiently large buffer has been allocated.</span></span> <span data-ttu-id="c7f56-290">您只能调用此类函数从另一个 DLL 安全地如果显式过去足够大缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c7f56-290">You can only call such a function from another DLL safely if you have explicitly passed a big enough buffer.</span></span> 
  
<span data-ttu-id="c7f56-291">下面是一个反转传入的 null 结尾宽字符字符串使用标准库函数**wcsrev**XLL 函数的示例。</span><span class="sxs-lookup"><span data-stu-id="c7f56-291">Here is an example of an XLL function that reverses a passed-in null-terminated wide character string using the standard library function **wcsrev**.</span></span> <span data-ttu-id="c7f56-292">参数在此情况下将注册键入**F %**。</span><span class="sxs-lookup"><span data-stu-id="c7f56-292">The argument in this case would be registered as type **F%**.</span></span>
  
```cs
void WINAPI reverse_text_xl12(wchar_t *text)
{
    _wcsrev(text);
}
```

## <a name="persistent-storage-binary-names"></a><span data-ttu-id="c7f56-293">永久存储 （二进制名称）</span><span class="sxs-lookup"><span data-stu-id="c7f56-293">Persistent Storage (Binary Names)</span></span>

<span data-ttu-id="c7f56-294">二进制名称定义和关联的二进制文件，即，与工作簿一起存储的非结构化数据块。</span><span class="sxs-lookup"><span data-stu-id="c7f56-294">Binary names are defined and associated with blocks of binary, that is, unstructured, data that is stored together with the workbook.</span></span> <span data-ttu-id="c7f56-295">它们使用函数[xlDefineBinaryName](xldefinebinaryname.md)中，创建和使用函数[xlGetBinaryName](xlgetbinaryname.md)检索数据。</span><span class="sxs-lookup"><span data-stu-id="c7f56-295">They are created using the function [xlDefineBinaryName](xldefinebinaryname.md), and the data is retrieved using the function [xlGetBinaryName](xlgetbinaryname.md).</span></span> <span data-ttu-id="c7f56-296">函数参考中的更详细地介绍这两个函数 （请参阅[C API 函数，可以将调用只能从 DLL 或 XLL](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)），并同时使用**xltypeBigData** **XLOPER**/ **XLOPER12**。</span><span class="sxs-lookup"><span data-stu-id="c7f56-296">Both functions are described in more detail in the function reference (see [C API Functions That Can Be Called Only from a DLL or XLL](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)), and both use the **xltypeBigData** **XLOPER**/ **XLOPER12**.</span></span> 
  
<span data-ttu-id="c7f56-297">有关限制的二进制名称的实际应用程序的已知问题的信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。</span><span class="sxs-lookup"><span data-stu-id="c7f56-297">For information about known issues that limit the practical applications of binary names, see [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
## <a name="excel-stack"></a><span data-ttu-id="c7f56-298">Excel 堆栈</span><span class="sxs-lookup"><span data-stu-id="c7f56-298">Excel Stack</span></span>

<span data-ttu-id="c7f56-299">Excel 与它已加载的所有 Dll 共享其堆栈空间。</span><span class="sxs-lookup"><span data-stu-id="c7f56-299">Excel shares its stack space with all the DLLs it has loaded.</span></span> <span data-ttu-id="c7f56-300">堆栈空间通常是多个适用于普通的使用，并不需要是长短它，只要您遵循的一些准则：</span><span class="sxs-lookup"><span data-stu-id="c7f56-300">Stack space is usually more than adequate for ordinary use, and you do not need to be concerned about it as long as you follow a few guidelines:</span></span> 
  
- <span data-ttu-id="c7f56-301">不非常大的结构作为参数传递给函数的值堆栈上。</span><span class="sxs-lookup"><span data-stu-id="c7f56-301">Do not pass very large structures as arguments to functions by value on the stack.</span></span> <span data-ttu-id="c7f56-302">应传递指针或引用。</span><span class="sxs-lookup"><span data-stu-id="c7f56-302">Pass pointers or references instead.</span></span>
    
- <span data-ttu-id="c7f56-303">不在堆栈返回大型结构。</span><span class="sxs-lookup"><span data-stu-id="c7f56-303">Do not return large structures on the stack.</span></span> <span data-ttu-id="c7f56-304">返回到静态或动态分配内存的指针，或使用参数传递的引用。</span><span class="sxs-lookup"><span data-stu-id="c7f56-304">Return pointers to static or dynamically allocated memory, or use arguments passed by reference.</span></span>
    
- <span data-ttu-id="c7f56-305">不要声明中的函数代码非常大自动变量结构。</span><span class="sxs-lookup"><span data-stu-id="c7f56-305">Do not declare very large automatic variable structures in the function code.</span></span> <span data-ttu-id="c7f56-306">如果需要它们，则将这些声明为静态。</span><span class="sxs-lookup"><span data-stu-id="c7f56-306">If you need them, declare them as static.</span></span>
    
- <span data-ttu-id="c7f56-307">不要调用函数以递归方式，除非您确信的递归深度将始终为浅表。</span><span class="sxs-lookup"><span data-stu-id="c7f56-307">Do not call functions recursively unless you are sure the depth of recursion will always be shallow.</span></span> <span data-ttu-id="c7f56-308">转为尝试使用循环。</span><span class="sxs-lookup"><span data-stu-id="c7f56-308">Try using a loop instead.</span></span>
    
<span data-ttu-id="c7f56-309">当 DLL 到 Excel 中使用 C API 回拨时，Excel 将首先检查无法所做的最长使用率调用堆栈上是否有足够的空间。</span><span class="sxs-lookup"><span data-stu-id="c7f56-309">When a DLL calls back into Excel using the C API, Excel first checks whether there is enough space on the stack for the worst-case usage call that could be made.</span></span> <span data-ttu-id="c7f56-310">如果它认为可能没有足够的空间，它将失败呼叫为安全起见，尽管可能实际上没有足够的空间用于该特定的呼叫。</span><span class="sxs-lookup"><span data-stu-id="c7f56-310">If it thinks there might be insufficient room, it will fail the call to be safe, even though there might actually have been enough space for that particular call.</span></span> <span data-ttu-id="c7f56-311">在这种情况下，回调返回代码**xlretFailed**。</span><span class="sxs-lookup"><span data-stu-id="c7f56-311">In this case, the callbacks return the code **xlretFailed**.</span></span> <span data-ttu-id="c7f56-312">对于普通使用 C API 和堆栈，这是不可能的 C API 调用失败的原因。</span><span class="sxs-lookup"><span data-stu-id="c7f56-312">For ordinary use of the C API and the stack, this is an unlikely cause of the failure of a C API call.</span></span>
  
<span data-ttu-id="c7f56-313">如果您是担心，还是只好奇，或您想要消除堆栈空间不足作为不清楚失败的原因，您可以找到出多少堆栈空间是对[xlStack](xlstack.md)函数的调用。</span><span class="sxs-lookup"><span data-stu-id="c7f56-313">If you are concerned, or just curious, or you want to eliminate lack of stack space as a reason for an unexplained failure, you can find out how much stack space there is with a call to the [xlStack](xlstack.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c7f56-314">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7f56-314">See also</span></span>



[<span data-ttu-id="c7f56-315">Excel 中的多线程重新计算</span><span class="sxs-lookup"><span data-stu-id="c7f56-315">Multithreaded Recalculation in Excel</span></span>](multithreaded-recalculation-in-excel.md)
  
[<span data-ttu-id="c7f56-316">Excel 中的多线程处理和内存争用</span><span class="sxs-lookup"><span data-stu-id="c7f56-316">Multithreading and Memory Contention in Excel</span></span>](multithreading-and-memory-contention-in-excel.md)
  
[<span data-ttu-id="c7f56-317">Developing Excel XLLs</span><span class="sxs-lookup"><span data-stu-id="c7f56-317">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

