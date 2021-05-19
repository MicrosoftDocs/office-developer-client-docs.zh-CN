---
title: 内存管理Excel
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- xloper12 memory [excel 2007]，managing memory in Excel，Excel stack，strings [Excel 2007]， managing memory，memory management in Excel，XLOPER memory [Excel 2007]，memory [Excel 2007]， management guidelines
localization_priority: Normal
ms.assetid: 3bf5195b-6235-43cf-8795-0c7b0a63a095
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: f129dac2971f01c8ada15f0028958132b1945746
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419539"
---
# <a name="memory-management-in-excel"></a><span data-ttu-id="4fb6e-104">内存管理Excel</span><span class="sxs-lookup"><span data-stu-id="4fb6e-104">Memory Management in Excel</span></span>

 <span data-ttu-id="4fb6e-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4fb6e-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="4fb6e-106">如果要创建高效且稳定的 XLL，内存管理是最重要的问题。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-106">Memory management is the most important concern if you want to create efficient and stable XLLs.</span></span> <span data-ttu-id="4fb6e-107">未能很好地管理内存可能导致 Microsoft Excel 中出现一系列问题，从低效率的内存分配和初始化和小内存泄漏等次要问题，到主要问题（如 Excel 的不稳定）。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-107">Failure to manage memory well can lead to a range of problems in Microsoft Excel—from minor problems such as inefficient memory allocation and initialization and small memory leaks, to major problems such as the destabilization of Excel.</span></span>
  
<span data-ttu-id="4fb6e-108">内存管理不当是严重加载项相关问题的最常见来源。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-108">Mismanagement of memory is the most common source of serious add-in-related problems.</span></span> <span data-ttu-id="4fb6e-109">因此，应在内存管理方面制定一致且经过思考的策略来构建项目。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-109">Therefore, you should build your project with a consistent and well-thought-through strategy on memory management.</span></span> 
  
<span data-ttu-id="4fb6e-110">随着多线程工作簿重新计算Microsoft Office Excel 2007 年，内存管理变得更加复杂。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-110">Memory management became more complex in Microsoft Office Excel 2007 with the introduction of multithreaded workbook recalculation.</span></span> <span data-ttu-id="4fb6e-111">如果要创建和导出线程安全工作表函数，则必须管理在多个线程竞争访问时生成的冲突。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-111">If you want to create and export thread-safe worksheet functions, you must manage the resulting conflicts that can occur when multiple threads compete for access.</span></span>
  
<span data-ttu-id="4fb6e-112">对于以下三种数据结构类型，存在内存注意事项：</span><span class="sxs-lookup"><span data-stu-id="4fb6e-112">There are memory considerations for the following three data structure types:</span></span>
  
- <span data-ttu-id="4fb6e-113">**XLOPER** 和 **XLOPER12** s</span><span class="sxs-lookup"><span data-stu-id="4fb6e-113">**XLOPER** s and **XLOPER12** s</span></span>
    
- <span data-ttu-id="4fb6e-114">不在 XLOPER 或 **XLOPER12 中的字符串**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-114">Strings that are not in an **XLOPER** or **XLOPER12**</span></span>
    
- <span data-ttu-id="4fb6e-115">**FP** 和 **FP12** 数组</span><span class="sxs-lookup"><span data-stu-id="4fb6e-115">**FP** and **FP12** arrays</span></span> 
    
## <a name="xloperxloper12-memory"></a><span data-ttu-id="4fb6e-116">XLOPER/XLOPER12 内存</span><span class="sxs-lookup"><span data-stu-id="4fb6e-116">XLOPER/XLOPER12 Memory</span></span>

<span data-ttu-id="4fb6e-117">**XLOPER** XLOPER12 数据结构具有一些子类型，其中包含指向内存块的指针，即字符串 /   (**xltypeStr**) 、数组 (**xltypeMulti**) 和外部引用 (**xltypeRef**) 。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-117">The **XLOPER**/ **XLOPER12** data structure has a few sub-types that contain pointers to blocks of memory, namely strings (**xltypeStr**), arrays (**xltypeMulti**) and external references (**xltypeRef**).</span></span> <span data-ttu-id="4fb6e-118">另请注意 **，xltypeMulti** 数组可以包含字符串 **XLOPER** /  **XLOPER12，** 而字符串又指向其他内存块。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-118">Note also that **xltypeMulti** arrays can contain string **XLOPER**/ **XLOPER12s** that in turn point to other blocks of memory.</span></span> 
  
<span data-ttu-id="4fb6e-119">可通过 **多种方式创建** /  **XLOPER XLOPER12：**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-119">An **XLOPER**/ **XLOPER12** can be created in several ways:</span></span> 
  
- <span data-ttu-id="4fb6e-120">By Excel when preparing arguments to be passed to an XLL function</span><span class="sxs-lookup"><span data-stu-id="4fb6e-120">By Excel when preparing arguments to be passed to an XLL function</span></span>
    
- <span data-ttu-id="4fb6e-121">By Excel when returning an **XLOPER** or **XLOPER12** in a C API call</span><span class="sxs-lookup"><span data-stu-id="4fb6e-121">By Excel when returning an **XLOPER** or **XLOPER12** in a C API call</span></span> 
    
- <span data-ttu-id="4fb6e-122">通过 DLL 创建要传递给 C API 调用的参数</span><span class="sxs-lookup"><span data-stu-id="4fb6e-122">By your DLL when creating arguments to be passed to a C API call</span></span>
    
- <span data-ttu-id="4fb6e-123">通过 DLL 创建 XLL 函数返回值</span><span class="sxs-lookup"><span data-stu-id="4fb6e-123">By your DLL when creating an XLL function return value</span></span>
    
<span data-ttu-id="4fb6e-124">可以通过多种方式分配其中一种内存指向类型中的内存块：</span><span class="sxs-lookup"><span data-stu-id="4fb6e-124">A block of memory within one of the memory-pointing types can be allocated in several ways:</span></span>
  
- <span data-ttu-id="4fb6e-125">它可以是 DLL 中任何函数代码之外的静态块，在这种情况下，你不需要分配或释放内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-125">It can be a static block within your DLL outside any function code, in which case you do not have to allocate or free the memory.</span></span>
    
- <span data-ttu-id="4fb6e-126">它可以是 DLL 中某些函数代码内的静态块，在这种情况下，你不需要分配或释放内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-126">It can be a static block within your DLL within some function code, in which case you do not have to allocate or free the memory.</span></span>
    
- <span data-ttu-id="4fb6e-127">DLL 可以通过几种可能的方式动态分配和释放它：**用户** 分配和释放、新建和删除等。  </span><span class="sxs-lookup"><span data-stu-id="4fb6e-127">It can be dynamically allocated and freed by your DLL in several possible ways: **malloc** and **free**, **new** and **delete**, and so on.</span></span>
    
- <span data-ttu-id="4fb6e-128">它可以由用户动态Excel。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-128">It can be dynamically allocated by Excel.</span></span>
    
<span data-ttu-id="4fb6e-129">鉴于 /  **XLOPER XLOPER12** 内存的可能来源数量以及 **XLOPER** /  **XLOPER12** 可能分配了该内存的情况数，此主题似乎很难理解，这并不奇怪。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-129">Given the number of possible origins for **XLOPER**/ **XLOPER12** memory and the number of situations in which the **XLOPER**/ **XLOPER12** might have had that memory assigned, it is not surprising that this subject can seem very difficult.</span></span> <span data-ttu-id="4fb6e-130">但是，如果您遵循多个规则和准则，复杂性可能会大大降低。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-130">However, the complexity can be greatly reduced if you follow several rules and guidelines.</span></span> 
  
### <a name="rules-for-working-with-xloperxloper12"></a><span data-ttu-id="4fb6e-131">使用 XLOPER/XLOPER12 的规则</span><span class="sxs-lookup"><span data-stu-id="4fb6e-131">Rules for Working with XLOPER/XLOPER12</span></span>

- <span data-ttu-id="4fb6e-132">不要尝试释放内存或覆盖作为参数传递给 XLL 函数的 **XLOPERs** /  **XLOPER12。**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-132">Do not try to free memory or overwrite **XLOPERs**/ **XLOPER12** s that are passed as arguments to your XLL function.</span></span> <span data-ttu-id="4fb6e-133">您应将此类参数视为只读。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-133">You should treat such arguments as read-only.</span></span> <span data-ttu-id="4fb6e-134">有关详细信息，请参阅 XLL 开发中的已知问题中的"通过修改就地参数返回 **XLOPER** [Excel XLOPER12"。](known-issues-in-excel-xll-development.md) </span><span class="sxs-lookup"><span data-stu-id="4fb6e-134">For more information, see "Returning **XLOPER** or **XLOPER12** by Modifying Arguments in Place" in [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
    
- <span data-ttu-id="4fb6e-135">如果Excel在调用 C API 时为返回到 DLL 的 /  **XLOPER XLOPER12** 分配了内存：</span><span class="sxs-lookup"><span data-stu-id="4fb6e-135">If Excel has allocated memory for an **XLOPER**/ **XLOPER12** returned to your DLL in a call to the C API:</span></span> 
    
  - <span data-ttu-id="4fb6e-136">当不再需要 **XLOPER** /  **XLOPER12** 时，必须使用对 [xlFree 的](xlfree.md)调用释放内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-136">You must free the memory when you no longer need the **XLOPER**/ **XLOPER12** using a call to [xlFree](xlfree.md).</span></span> <span data-ttu-id="4fb6e-137">请勿使用任何其他方法（如释放或删除）释放内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-137">Do not use any other method, such as free or delete, to release the memory.</span></span>
    
  - <span data-ttu-id="4fb6e-138">如果返回的类型是 **xltypeMulti**，请不要覆盖数组内的任何 /  **XLOPER XLOPER12，** 尤其是在它们包含字符串时，尤其是在您尝试用字符串覆盖的位置。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-138">If the returned type is **xltypeMulti**, do not overwrite any **XLOPER**/ **XLOPER12** s within the array, especially if they contain strings, and especially not where you are trying to overwrite with a string.</span></span>
    
  - <span data-ttu-id="4fb6e-139">如果要将 /  **XLOPER XLOPER12** 返回到 Excel 作为 DLL 函数的返回值，则必须告诉 Excel有一些内存Excel完成后必须释放。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-139">If you want to return the **XLOPER**/ **XLOPER12** to Excel as your DLL function's return value, you must tell Excel that there is memory that Excel must release when done.</span></span> 
    
- <span data-ttu-id="4fb6e-140">只能对作为 C API 调用的返回值创建的 **XLOPER** XLOPER12 调用 **xlFree。** /  </span><span class="sxs-lookup"><span data-stu-id="4fb6e-140">You must only call **xlFree** on an **XLOPER**/ **XLOPER12** that was created as the return value to a C API call.</span></span> 
    
- <span data-ttu-id="4fb6e-141">如果 DLL 为 **要** 作为 DLL 函数的返回值返回到 Excel 的 /  **XLOPER XLOPER12** 分配了内存，则必须告诉 Excel存在 DLL 必须释放的内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-141">If your DLL has allocated memory for an **XLOPER**/ **XLOPER12** that you want to return to Excel as your DLL function's return value, you must tell Excel that there is memory that the DLL must release.</span></span> 
    
### <a name="guidelines-for-memory-management"></a><span data-ttu-id="4fb6e-142">内存管理指南</span><span class="sxs-lookup"><span data-stu-id="4fb6e-142">Guidelines for Memory Management</span></span>

- <span data-ttu-id="4fb6e-143">在用于分配和释放内存的方法的 DLL 中保持一致。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-143">Be consistent in your DLL in the method that you use to allocate and release memory.</span></span> <span data-ttu-id="4fb6e-144">避免混合方法。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-144">Avoid mixing methods.</span></span> <span data-ttu-id="4fb6e-145">一个好方法是将所使用的方法包装在内存类或结构中，可以在其中更改所使用的方法，而无需在许多位置更改代码。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-145">A good approach is to wrap the method that you are using up in a memory class or structure, within which you can change the method used without altering your code in many places.</span></span>
    
- <span data-ttu-id="4fb6e-146">在 DLL 内创建 **xltypeMulti** 数组时，为字符串分配内存的方式保持一致：始终为字符串动态分配内存或始终使用静态内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-146">When you create **xltypeMulti** arrays within your DLL, be consistent in the way that you allocate memory for strings: always dynamically allocate the memory for them or always use static memory.</span></span> <span data-ttu-id="4fb6e-147">如果这样做，在释放内存时，你将知道必须始终释放或从不释放字符串。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-147">If you do this, when you are freeing the memory, you will know that you must either always or never free the strings.</span></span> 
    
- <span data-ttu-id="4fb6e-148">复制已Excel **XLOPER** /  **XLOPER12** Excel分配的内存的深层副本。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-148">Make deep copies of Excel-allocated memory when you are copying an Excel-created **XLOPER**/ **XLOPER12**.</span></span>
    
- <span data-ttu-id="4fb6e-149">不要将Excel的字符串 **XLOPER** /  **XLOPER12** 置于 **xltypeMulti** 数组中。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-149">Do not put Excel-allocated string **XLOPER**/ **XLOPER12** s within **xltypeMulti** arrays.</span></span> <span data-ttu-id="4fb6e-150">创建字符串的深层副本，并存储指向数组中副本的指针。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-150">Make deep copies of the strings and store pointers to the copies in the array.</span></span> 
    
## <a name="freeing-excel-allocated-xloperxloper12-memory"></a><span data-ttu-id="4fb6e-151">释放Excel-Allocated XLOPER/XLOPER12 内存</span><span class="sxs-lookup"><span data-stu-id="4fb6e-151">Freeing Excel-Allocated XLOPER/XLOPER12 Memory</span></span>

<span data-ttu-id="4fb6e-152">请考虑以下 XLL 命令，该命令使用 **xlGetName** 获取包含 DLL 的路径和文件名的字符串，并使用 **xlcAlert** 在警报对话框中显示它。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-152">Consider the following XLL command, which uses **xlGetName** to obtain a string containing the path and file name of the DLL and displays it in an alert dialog box using **xlcAlert**.</span></span>
  
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

<span data-ttu-id="4fb6e-153">当函数不再需要 **xDllName** 指向的内存时，它可以使用对 [xlFree](xlfree.md)函数（一个仅 DLL C API 函数）的调用释放它。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-153">When the function no longer needs the memory pointed to by **xDllName**, it can free it using a call to the [xlFree function](xlfree.md), one of the DLL-only C API functions.</span></span> 
  
<span data-ttu-id="4fb6e-154">**xlFree** 函数完全记录在函数引用部分 (请参阅 [C API Functions That Can Be Called Only from a DLL or XLL](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)) ， but be aware of the following：</span><span class="sxs-lookup"><span data-stu-id="4fb6e-154">The **xlFree** function is fully documented in the function reference section (see [C API Functions That Can Be Called Only from a DLL or XLL](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)), but be aware of the following:</span></span>
  
- <span data-ttu-id="4fb6e-155">可以在对 xlFree 的单个调用中将指针传递给多个 /  **XLOPER XLOPER12，** 这仅受 Excel 2003 年 200) 7 年 Excel 年 255 年 2003 年 255 年 Excel (30 的运行版本所支持的函数参数数限制。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-155">You can pass pointers to more than one **XLOPER**/ **XLOPER12** s in a single call to **xlFree**, limited only by the number of function arguments supported in the running version of Excel (30 in Excel 2003, 255 starting in Excel 2007).</span></span>
    
- <span data-ttu-id="4fb6e-156">**xlFree** 将包含的指针设置为 **NULL，** 以确保释放已释放的 **XLOPER** /  **XLOPER12** 的尝试是安全的。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-156">**xlFree** sets the contained pointer to **NULL** to ensure that an attempt to free an **XLOPER**/ **XLOPER12** that has already been freed is safe.</span></span> <span data-ttu-id="4fb6e-157">**xlFree** 是唯一一个修改其参数的 C API 函数。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-157">**xlFree** is the only C API function that modifies its arguments.</span></span> 
    
- <span data-ttu-id="4fb6e-158">你可以安全地在用于 C API 调用的返回值的任何 **XLOPER XLOPER12** 上调用 **xlFree，** 无论它是否包含指向内存的 /  指针。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-158">You can safely call **xlFree** on any **XLOPER**/ **XLOPER12** used for the return value of a call to the C API, regardless of whether it contains a pointer to memory.</span></span> 
    
## <a name="returning-xloperxloper12s-to-be-freed-by-excel"></a><span data-ttu-id="4fb6e-159">返回 XLOPER/XLOPER12s 以由 Excel</span><span class="sxs-lookup"><span data-stu-id="4fb6e-159">Returning XLOPER/XLOPER12s to be freed by Excel</span></span>

<span data-ttu-id="4fb6e-160">假设您要修改上一节中的示例命令，并更改为在传递 **布尔** **true** 参数时返回 DLL 路径和文件名的工作表函数 **，#N/A。**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-160">Suppose you wanted to modify the example command in the previous section and change it to a worksheet function that returns the DLL path and file name when passed a **Boolean** **true** argument, and **#N/A** otherwise.</span></span> <span data-ttu-id="4fb6e-161">很明显，在将字符串内存返回到字符串内存之前，无法调用 **xlFree** Excel。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-161">Clearly you cannot call **xlFree** to release the string memory before returning it to Excel.</span></span> <span data-ttu-id="4fb6e-162">但是，如果在某些时候未释放它，则每次调用函数时，外接程序都会泄漏内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-162">However, if it is not freed at some point, the add-in will leak memory every time the function is called.</span></span> <span data-ttu-id="4fb6e-163">若要解决此问题，可以在 **XLOPER** XLOPER12 的 **xltype** 字段中设置位，在 /  xlcall.h 中定义为 **xlbitXLFree。**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-163">To work around this problem, you can set a bit in the **xltype** field of the **XLOPER**/ **XLOPER12**, defined as **xlbitXLFree** in xlcall.h.</span></span> <span data-ttu-id="4fb6e-164">设置此设置Excel复制完值后必须释放返回的内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-164">Setting this tells Excel that it must free the returned memory when it has finished copying the value out.</span></span> 
  
### <a name="example"></a><span data-ttu-id="4fb6e-165">示例</span><span class="sxs-lookup"><span data-stu-id="4fb6e-165">Example</span></span>

<span data-ttu-id="4fb6e-166">以下代码示例演示上一节中转换为 XLL 工作表函数的 XLL 命令。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-166">The following code example shows the XLL command in the previous section converted into an XLL worksheet function.</span></span>
  
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

<span data-ttu-id="4fb6e-167">使用 **XLOPER** XLOPER12 的 XLL 函数必须声明为采用并返回指向 /  **XLOPER** /  **XLOPER12** 的指针。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-167">XLL functions that use **XLOPER**/ **XLOPER12** s must be declared as taking and returning pointers to **XLOPER**/ **XLOPER12** s.</span></span> <span data-ttu-id="4fb6e-168">此示例中对函数中的静态 **XLOPER12** 的使用不是线程安全的。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-168">The use in this example of a static **XLOPER12** within the function is not thread safe.</span></span> <span data-ttu-id="4fb6e-169">你可以错误地将此函数注册为线程安全函数，但存在在另一个线程完成之前被一个线程覆盖 **xRtnValue** 的风险。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-169">You could incorrectly register this function as thread safe, but you would risk **xRtnValue** being overwritten by one thread before another thread had finished with it.</span></span> 
  
<span data-ttu-id="4fb6e-170">必须在调用 **分配 xlbitXLFree** 的 Excel设置 xlbitXLFree。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-170">You must set **xlbitXLFree** after the call to the Excel callback that allocates it.</span></span> <span data-ttu-id="4fb6e-171">如果在之前设置它，它将被覆盖，并且没有你需要的效果。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-171">If you set it before this, it is overwritten and does not have the effect that you want.</span></span> <span data-ttu-id="4fb6e-172">如果你打算在将值返回到工作表之前，在调用另一个 C API 函数时将该值用作参数，应在任何此类调用后设置此位。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-172">If you intend to use the value as an argument in a call to another C API function before returning it to the worksheet, you should set this bit after any such call.</span></span> <span data-ttu-id="4fb6e-173">否则，在检查 **XLOPER** /  **XLLOPER12** 类型之前，将混淆未屏蔽此位的函数。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-173">Otherwise, you will confuse functions that do not mask this bit before checking the **XLOPER**/ **XLLOPER12** type.</span></span> 
  
## <a name="returning-xloperxloper12s-to-be-freed-by-the-dll"></a><span data-ttu-id="4fb6e-174">返回 DLL 要释放的 XLOPER/XLOPER12</span><span class="sxs-lookup"><span data-stu-id="4fb6e-174">Returning XLOPER/XLOPER12s to be freed by the DLL</span></span>

<span data-ttu-id="4fb6e-175">当 XLL 为 **XLOPER XLOPER12** 分配了内存，并且想要将内存返回到 /  **XLOPER12** 时，会出现与此类似的Excel。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-175">A similar problem to this occurs when your XLL has allocated memory for an **XLOPER**/ **XLOPER12** and wants to return it to Excel.</span></span> <span data-ttu-id="4fb6e-176">Excel可在 **XLOPER XLOPER12** 的 **xltype** 字段中设置的另一位，在 /  xlcall.h 中定义为 **xlbitDLLFree。**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-176">Excel recognizes another bit that can be set in the **xltype** field of the **XLOPER**/ **XLOPER12**, defined as **xlbitDLLFree** in xlcall.h.</span></span> 
  
<span data-ttu-id="4fb6e-177">当 Excel 收到具有此位集的 **XLOPER** XLOPER12 时，它会尝试调用一个应由 XLL 导出的函数，称为 /  [xlAutoFree](xlautofree-xlautofree12.md) (的 **XLOPER**) 或 **xlAutoFree12** (for **XLOPER12** s) 。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-177">When Excel receives **an XLOPER**/ **XLOPER12** with this bit set, it tries to call a function that should be exported by the XLL called [xlAutoFree](xlautofree-xlautofree12.md) (for **XLOPER** s) or **xlAutoFree12** (for **XLOPER12** s).</span></span> <span data-ttu-id="4fb6e-178">此函数在函数参考中进行了更全面 (请参阅加载项管理器和 [XLL](add-in-manager-and-xll-interface-functions.md) 接口函数) ，但此处提供了一个最小实现示例。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-178">This function is described more fully in the function reference (see [Add-in Manager and XLL Interface Functions](add-in-manager-and-xll-interface-functions.md)), but an example minimal implementation is given here.</span></span> <span data-ttu-id="4fb6e-179">它的目的是以与 **最初分配** 方式一致的方式释放 /  **XLOPER XLOPER12** 内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-179">Its purpose is to free the **XLOPER**/ **XLOPER12** memory in a way that is consistent with how it was originally allocated.</span></span> 
  
### <a name="examples"></a><span data-ttu-id="4fb6e-180">示例</span><span class="sxs-lookup"><span data-stu-id="4fb6e-180">Examples</span></span>

<span data-ttu-id="4fb6e-181">以下示例函数执行与上一函数相同的操作，只不过它在 DLL 名称之前包含文本"此 DLL 的完整路径名是"。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-181">The following example function does the same as the previous function except that it includes the text "The full pathname for this DLL is " before the DLL name.</span></span>
  
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

<span data-ttu-id="4fb6e-182">导出上一函数的 **XLL 中 xlAutoFree12** 的最少足够实现如下所示。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-182">A minimally sufficient implementation of **xlAutoFree12** in the XLL that exported the previous function would be as follows.</span></span> 
  
```cs
void WINAPI xlAutoFree12(LPXLOPER12 p_oper)
{
    if(p_oper->xltype == (xltypeStr | xlbitDLLFree))
        free(p_oper->val.str);
}
```

<span data-ttu-id="4fb6e-183">此实现仅在 XLL 仅返回 **XLOPER12** 字符串，并且这些字符串仅使用可能oc 进行 **分配时才足够**。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-183">This implementation is only sufficient if the XLL only returns **XLOPER12** strings, and those strings are only allocated using **malloc**.</span></span> <span data-ttu-id="4fb6e-184">请注意，测试</span><span class="sxs-lookup"><span data-stu-id="4fb6e-184">Note that the test</span></span> 
  
 ` if(p_oper->xltype == xltypeStr) `
  
<span data-ttu-id="4fb6e-185">在这种情况下将失败，因为已设置 **xlbitDLLFree。**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-185">would fail in this case because **xlbitDLLFree** is set.</span></span> 
  
<span data-ttu-id="4fb6e-186">通常， **应实现 xlAutoFree** 和 **xlAutoFree12，** 以便它们释放与 XLL 创建的 **xltypeMulti** 数组和 **xltypeRef** 外部引用关联的内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-186">In general, **xlAutoFree** and **xlAutoFree12** should be implemented so that they free memory associated with XLL-created **xltypeMulti** arrays and **xltypeRef** external references.</span></span> 
  
<span data-ttu-id="4fb6e-187">你可能决定实现 XLL 函数，以便它们全部返回动态分配的 **XLOPER** 和 **XLOPER12。**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-187">You might decide to implement your XLL functions so that they ALL return dynamically allocated **XLOPER** s and **XLOPER12** s.</span></span> <span data-ttu-id="4fb6e-188">在这种情况下，你需要在所有此类 XLOPER 和 **XLOPER12** 上设置 **xlbitDLLFree，** 而不管子类型如何。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-188">In this case, you would need to set **xlbitDLLFree** on all such **XLOPER** s and **XLOPER12** s regardless of the sub-type.</span></span> <span data-ttu-id="4fb6e-189">你还需要实现 **xlAutoFree** 和 **xlAutoFree12，** 以便释放此内存以及 **指向 XLOPER** /  **XLOPER12** 内的任何内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-189">You would also need to implement **xlAutoFree** and **xlAutoFree12** so that this memory was freed and also any memory pointed to within the **XLOPER**/ **XLOPER12**.</span></span> <span data-ttu-id="4fb6e-190">此方法是保证返回值线程安全的一种方法。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-190">This approach is one way to make the return value thread safe.</span></span> <span data-ttu-id="4fb6e-191">例如，可以按如下方式重写上一个函数。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-191">For example, the previous function could be rewritten as follows.</span></span>
  
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

<span data-ttu-id="4fb6e-192">有关 **xlAutoFree** 和 **xlAutoFree12** 的信息，请参阅 [xlAutoFree/xlAutoFree12。](xlautofree-xlautofree12.md)</span><span class="sxs-lookup"><span data-stu-id="4fb6e-192">For more information about **xlAutoFree** and **xlAutoFree12**, see [xlAutoFree/xlAutoFree12](xlautofree-xlautofree12.md).</span></span>
  
## <a name="returning-modify-in-place-arguments"></a><span data-ttu-id="4fb6e-193">返回就地修改参数</span><span class="sxs-lookup"><span data-stu-id="4fb6e-193">Returning Modify-in-Place Arguments</span></span>

<span data-ttu-id="4fb6e-194">Excel XLL 函数通过就地修改参数来返回值。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-194">Excel allows an XLL function to return a value by modifying an argument in place.</span></span> <span data-ttu-id="4fb6e-195">只能使用作为指针传入的参数来这样做。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-195">You can only do this with an argument passed in as a pointer.</span></span> <span data-ttu-id="4fb6e-196">若要如此工作，必须注册函数，以告知用户Excel将修改哪个参数。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-196">To work like this, the function must be registered in a way that tells Excel which argument will be modified.</span></span> 
  
<span data-ttu-id="4fb6e-197">此方法返回值的方法受可通过指针传递的所有数据类型的支持，但对于以下类型尤其有用：</span><span class="sxs-lookup"><span data-stu-id="4fb6e-197">This method of returning a value is supported for all data types that can be passed by pointer but is especially useful for the following types:</span></span>
  
- <span data-ttu-id="4fb6e-198">长度计数字符串和以 null 结束的 ASCII 字节字符串</span><span class="sxs-lookup"><span data-stu-id="4fb6e-198">Length-counted and null-terminated ASCII byte strings</span></span>
    
- <span data-ttu-id="4fb6e-199">自 2007 年 7 (起，长度计数字符串和以 null Excel Unicode 宽字符) </span><span class="sxs-lookup"><span data-stu-id="4fb6e-199">Length-counted and null-terminated Unicode wide character strings (starting in Excel 2007)</span></span>
    
- <span data-ttu-id="4fb6e-200">**FP** 浮点数组</span><span class="sxs-lookup"><span data-stu-id="4fb6e-200">**FP** floating-point arrays</span></span> 
    
- <span data-ttu-id="4fb6e-201">**FP12** 浮点数组 (2007 Excel起) </span><span class="sxs-lookup"><span data-stu-id="4fb6e-201">**FP12** floating-point arrays (starting in Excel 2007)</span></span> 
    
> [!NOTE]
> <span data-ttu-id="4fb6e-202">不应尝试以此方式返回 **XLOPER** 或 **XLOPER12。**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-202">You should not try to return **XLOPER** s or **XLOPER12** s in this manner.</span></span> <span data-ttu-id="4fb6e-203">有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-203">For more information, see [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span> 
  
<span data-ttu-id="4fb6e-204">使用此技术（而不只是使用 return 语句）的优点是，Excel为返回值分配内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-204">The advantage of using this technique, instead of just using the return statement, is that Excel allocates the memory for the return values.</span></span> <span data-ttu-id="4fb6e-205">一Excel读取完返回的数据后，它将释放内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-205">Once Excel has finished reading the returned data, it releases the memory.</span></span> <span data-ttu-id="4fb6e-206">这会将内存管理任务从 XLL 函数中消失。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-206">This takes the memory management tasks away from the XLL function.</span></span> <span data-ttu-id="4fb6e-207">此技术是线程安全的：如果由不同线程上的Excel调用，则每个线程上的每个函数调用都有其自己的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-207">This technique is thread safe: If called concurrently by Excel on different threads, each function call on each thread has its own buffer.</span></span>
  
<span data-ttu-id="4fb6e-208">它尤其适用于前面列出的数据类型，因为对于简单字符串和 /  **FP** FP12 数组，不存在用于调用回 DLL 以释放 XLOPER **XLOPER12** s 的内存回发机制。 /  </span><span class="sxs-lookup"><span data-stu-id="4fb6e-208">It is useful for the previously listed data types in particular because the mechanism for calling back into the DLL to free memory post-return that exists for **XLOPER**/ **XLOPER12** s does not exist for simple strings and **FP**/ **FP12** arrays.</span></span> <span data-ttu-id="4fb6e-209">因此，当返回 DLL 创建的字符串或浮点数组时，有以下选择：</span><span class="sxs-lookup"><span data-stu-id="4fb6e-209">Therefore, when returning a DLL-created string or floating-point array, you have the following choices:</span></span> 
  
- <span data-ttu-id="4fb6e-210">将永久性指针设置为动态分配的缓冲区，返回指针。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-210">Set a persistent pointer to a dynamically allocated buffer, return the pointer.</span></span> <span data-ttu-id="4fb6e-211">下次调用函数 (1) 时，检查指针是否为空， (2) 释放上一次调用中分配的资源，将指针重置为 null， (3) 将指针重新用于新分配的内存块。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-211">On the next call to the function (1) check that the pointer is not null, (2) free the resources allocated on the previous call and reset the pointer to null, (3) reuse the pointer for a newly allocated block of memory.</span></span>
    
- <span data-ttu-id="4fb6e-212">在不需要释放的静态缓冲区创建字符串和数组，并返回指向该缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-212">Create your strings and arrays in a static buffer that does not need to be freed, and return a pointer to that.</span></span>
    
- <span data-ttu-id="4fb6e-213">就地修改参数，将字符串或数组直接写入由 Excel。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-213">Modify an argument in place, writing your string or array directly into the space set aside by Excel.</span></span>
    
<span data-ttu-id="4fb6e-214">否则，必须创建 **XLOPER** /  **XLOPER12**，并使用 **xlbitDLLFree** 和 **xlAutoFree** /  **xlAutoFree12** 释放资源。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-214">Otherwise, you must create an **XLOPER**/ **XLOPER12**, and use **xlbitDLLFree** and **xlAutoFree**/ **xlAutoFree12** to release the resources.</span></span> 
  
<span data-ttu-id="4fb6e-215">在向传递的参数类型与返回值类型相同的情况下，最后一个选项可能最简单。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-215">The last option might be the simplest in those cases in which you are being passed an argument of the same type as the return value.</span></span> <span data-ttu-id="4fb6e-216">需要记住的关键点是，缓冲区大小有限，你必须非常小心，不要溢出它们。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-216">The key point to remember is that the buffer sizes are limited and you must be very careful not to overrun them.</span></span> <span data-ttu-id="4fb6e-217">如果出错，可能会Excel。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-217">Getting this wrong could crash Excel.</span></span> <span data-ttu-id="4fb6e-218">接下来将讨论字符串和 /  **FP FP12** 数组的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-218">Buffer sizes for strings and **FP**/ **FP12** arrays are discussed next.</span></span> 
  
## <a name="strings"></a><span data-ttu-id="4fb6e-219">字符串</span><span class="sxs-lookup"><span data-stu-id="4fb6e-219">Strings</span></span>

<span data-ttu-id="4fb6e-220">字符串内存管理问题可能是应用程序和外接程序中不稳定的最常见原因。鉴于处理字符串的方式有多种，可能可以理解：以 null 结束或长度计算 (或两) ;静态或动态缓冲区;固定长度或几乎无限制长度;操作系统托管内存 (例如，OLE Bstr) 或非托管字符串;等。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-220">Problems with the management of string memory are arguably the most common cause of instability in applications and add-ins. It is understandable perhaps, given the variety of ways in which strings are handled: null-terminated or length-counted (or both); static or dynamic buffers; fixed length or almost unlimited length; operating-system managed memory (for example, OLE Bstr) or unmanaged strings; and so on.</span></span>
  
<span data-ttu-id="4fb6e-221">C/C++ 程序员最熟悉以 null 结束的字符串。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-221">C/C++ programmers are most familiar with null-terminated strings.</span></span> <span data-ttu-id="4fb6e-222">标准 C 库旨在处理此类字符串。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-222">The standard C library is designed to work with such strings.</span></span> <span data-ttu-id="4fb6e-223">代码中的静态字符串文本编译为以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-223">Static string literals in code are compiled into null-terminated strings.</span></span> <span data-ttu-id="4fb6e-224">或者，Excel使用长度计数字符串，这些字符串通常不以 null 结束。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-224">Alternatively, Excel works with length-counted strings that are not in general null-terminated.</span></span> <span data-ttu-id="4fb6e-225">这些事实的组合需要 DLL/XLL 中关于如何处理字符串和字符串内存的清晰且一致的方法。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-225">The combination of these facts requires a clear and consistent approach within your DLL/XLL regarding how you handle strings and string memory.</span></span>
  
<span data-ttu-id="4fb6e-226">最常见的问题如下所示：</span><span class="sxs-lookup"><span data-stu-id="4fb6e-226">The most common problems are as follows:</span></span>
  
- <span data-ttu-id="4fb6e-227">将空指针或无效指针传递给需要有效指针的函数，并且不会或不能检查指针本身的有效性。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-227">The passing of a null or invalid pointer to a function that expects a valid pointer and does not or cannot check the pointer's validity itself.</span></span>
    
- <span data-ttu-id="4fb6e-228">不或无法根据要写入的字符串的长度检查缓冲区长度的函数溢出字符串缓冲区边界。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-228">The overrunning of the bounds of a string buffer by a function that does not or cannot check the length of the buffer against the length of the string being written.</span></span>
    
- <span data-ttu-id="4fb6e-229">尝试释放静态或已释放或未按照与释放方式一致的方式分配字符串缓冲区内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-229">Trying to free string buffer memory that is either static, or has been freed already, or was not allocated in a way that is consistent with how it is being freed.</span></span>
    
- <span data-ttu-id="4fb6e-230">通常，在经常调用的函数中，由于字符串被分配然后没有释放，内存会泄漏。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-230">Memory leaks that result from strings being allocated and then not freed, usually in a frequently called function.</span></span>
    
### <a name="rules-for-strings"></a><span data-ttu-id="4fb6e-231">字符串的规则</span><span class="sxs-lookup"><span data-stu-id="4fb6e-231">Rules for Strings</span></span>

<span data-ttu-id="4fb6e-232">与 **XLOPER** /  **XLOPER** 一样，应遵循一些规则和准则。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-232">As with **XLOPER**/ **XLOPER** s, there are rules and guidelines you should follow.</span></span> <span data-ttu-id="4fb6e-233">指南与上一节中提供的准则相同。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-233">The guidelines are the same as given in the previous section.</span></span> <span data-ttu-id="4fb6e-234">此处的规则是专门针对字符串的规则扩展。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-234">The rules here are an extension of the rules specifically for strings.</span></span>
  
 <span data-ttu-id="4fb6e-235">**规则：**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-235">**Rules:**</span></span>
  
- <span data-ttu-id="4fb6e-236">不要尝试释放内存或覆盖字符串 **XLOPER** /  **XLOPER12** s 或作为参数传递给 XLL 函数的简单长度计数字符串或以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-236">Do not try to free memory or overwrite string **XLOPER**/ **XLOPER12** s or simple length-counted or null-terminated strings passed as arguments to your XLL function.</span></span> <span data-ttu-id="4fb6e-237">您应将此类参数视为只读。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-237">You should treat such arguments as read-only.</span></span>
    
- <span data-ttu-id="4fb6e-238">其中Excel为字符串 **XLOPER** XLOPER12 分配内存作为 C API 回调函数的返回值，使用 xlFree 释放它，或设置 /  **xlbitXLFree（** 如果从 XLL 函数返回到 Excel）。 </span><span class="sxs-lookup"><span data-stu-id="4fb6e-238">Where Excel allocates memory for a string **XLOPER**/ **XLOPER12** for the return value of a C API callback function, use **xlFree** to free it, or set **xlbitXLFree** if returning it to Excel from an XLL function.</span></span> 
    
- <span data-ttu-id="4fb6e-239">当 DLL 为 **XLOPER** XLOPER12 动态分配字符串缓冲区时，按照完成时分配的方式释放该缓冲区;如果从 XLL 函数将 /  xlbitDLLFree 返回到 Excel，然后在 **xlAutoFree** xlAutoFree12 中释放它，则设置 **xlbitDLLFree。** /  </span><span class="sxs-lookup"><span data-stu-id="4fb6e-239">Where your DLL dynamically allocates a string buffer for an **XLOPER**/ **XLOPER12**, free it in a way consistent with how you allocated it when done, or set **xlbitDLLFree** if returning it to Excel from an XLL function and then free it in **xlAutoFree**/ **xlAutoFree12**.</span></span>
    
- <span data-ttu-id="4fb6e-240">如果Excel为调用 C API 时返回到 DLL 的 **xltypeMulti** 数组分配了内存，请不要覆盖数组内的任何字符串 **XLOPER** /  **XLOPER12。**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-240">If Excel has allocated memory for an **xltypeMulti** array returned to your DLL in a call to the C API, do not overwrite any string **XLOPER**/ **XLOPER12** s within the array.</span></span> <span data-ttu-id="4fb6e-241">此类数组只能使用 **xlFree** 释放，或者，如果由 XLL 函数返回，则通过设置 **xlbitXLFree** 释放。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-241">Such arrays must only be freed using **xlFree**, or, if being returned by an XLL function, by setting **xlbitXLFree**.</span></span>
    
### <a name="string-types-supported"></a><span data-ttu-id="4fb6e-242">支持的字符串类型</span><span class="sxs-lookup"><span data-stu-id="4fb6e-242">String Types Supported</span></span>

<span data-ttu-id="4fb6e-243">**C API xltypeStr XLOPER/XLOPER12s**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-243">**C API xltypeStr XLOPER/XLOPER12s**</span></span>

|<span data-ttu-id="4fb6e-244">**字节字符串：**XLOPER\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4fb6e-244">\*\*Byte strings: \*\*XLOPER\*\*\*\*</span></span>|<span data-ttu-id="4fb6e-245">**宽字符字符串：**XLOPER12\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4fb6e-245">\*\*Wide character strings: \*\*XLOPER12\*\*\*\*</span></span>|
|:-----|:-----|
|<span data-ttu-id="4fb6e-246">Excel 的所有版本</span><span class="sxs-lookup"><span data-stu-id="4fb6e-246">All versions of Excel</span></span>  <br/> |<span data-ttu-id="4fb6e-247">自 Excel 2007 起</span><span class="sxs-lookup"><span data-stu-id="4fb6e-247">Starting in Excel 2007</span></span>  <br/> |
|<span data-ttu-id="4fb6e-248">最大长度：255 个扩展的 ASCII 字节</span><span class="sxs-lookup"><span data-stu-id="4fb6e-248">Max length: 255 extended ASCII bytes</span></span>  <br/> |<span data-ttu-id="4fb6e-249">最大长度 32，767 Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="4fb6e-249">Maximum length 32,767 Unicode chars</span></span>  <br/> |
|<span data-ttu-id="4fb6e-250">First (unsigned) byte = length</span><span class="sxs-lookup"><span data-stu-id="4fb6e-250">First (unsigned) byte = length</span></span>  <br/> |<span data-ttu-id="4fb6e-251">第一个 Unicode 字符 = 长度</span><span class="sxs-lookup"><span data-stu-id="4fb6e-251">First Unicode character = length</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="4fb6e-252">不要假定 XLOPER 或 **XLOPER12** 字符串的 null 终止。 </span><span class="sxs-lookup"><span data-stu-id="4fb6e-252">Do not assume null termination of **XLOPER** or **XLOPER12** strings.</span></span> 
  
<span data-ttu-id="4fb6e-253">**C/C++ 字符串**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-253">**C/C++ strings**</span></span>

|<span data-ttu-id="4fb6e-254">**字节字符串**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-254">**Byte strings**</span></span>|<span data-ttu-id="4fb6e-255">**宽字符串**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-255">**Wide character strings**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4fb6e-256">以 Null (**字符** \*) "C" 最大长度：255 个扩展的 ASCII 字节</span><span class="sxs-lookup"><span data-stu-id="4fb6e-256">Null-terminated (**char** \*) "C" Max length: 255 extended ASCII bytes</span></span>  <br/> |<span data-ttu-id="4fb6e-257">以 Null (wchar_t \***)** "C%" 最大长度 32，767 Unicode 字符</span><span class="sxs-lookup"><span data-stu-id="4fb6e-257">Null-terminated (**wchar_t** \*) "C%" Maximum length 32,767 Unicode chars</span></span>  <br/> |
|<span data-ttu-id="4fb6e-258">长度计数 (无符号 **字符** \*) "D"</span><span class="sxs-lookup"><span data-stu-id="4fb6e-258">Length-counted (**unsigned char** \*) "D"</span></span>  <br/> |<span data-ttu-id="4fb6e-259">长度计算 **(wchar_t** \*) "D%"</span><span class="sxs-lookup"><span data-stu-id="4fb6e-259">Length-counted (**wchar_t** \*) "D%"</span></span>  <br/> |
   
### <a name="strings-in-xltypemulti-xloperxloper12-arrays"></a><span data-ttu-id="4fb6e-260">xltypeMulti XLOPER/XLOPER12 数组中的字符串</span><span class="sxs-lookup"><span data-stu-id="4fb6e-260">Strings in xltypeMulti XLOPER/XLOPER12 Arrays</span></span>

<span data-ttu-id="4fb6e-261">在某些情况下，Excel创建用于 DLL/XLL 的 **xltypeMulti** 数组。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-261">In several cases, Excel creates an **xltypeMulti** array for use in your DLL/XLL.</span></span> <span data-ttu-id="4fb6e-262">一些 XLM 信息函数将返回此类数组。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-262">Several of the XLM information functions return such arrays.</span></span> <span data-ttu-id="4fb6e-263">例如，C API 函数 **xlfGetWorkspace** 在传递参数  *44*  时返回一个包含字符串的数组，该字符串描述所有当前注册的 DLL 过程。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-263">For example, the C API function **xlfGetWorkspace**, when passed the argument  *44*  , returns an array containing strings that describe all the currently registered DLL procedures.</span></span> <span data-ttu-id="4fb6e-264">C API 函数 **xlfDialogBox** 返回其数组参数的修改副本，其中包含字符串的深层副本。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-264">The C API function **xlfDialogBox** returns a modified copy of its array argument, containing deep copies of the strings.</span></span> <span data-ttu-id="4fb6e-265">XLL 遇到 **xltypeMulti** 数组的最常见方式可能是，它作为参数传递给 XLL 函数，或者它已通过范围引用强制转换为此类型。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-265">Perhaps the most common way an XLL encounters an **xltypeMulti** array is where it has been passed as an argument to an XLL function, or it has been coerced to this type from a range reference.</span></span> <span data-ttu-id="4fb6e-266">在后一种情况下，Excel在源单元格中创建字符串的深层副本，并指向数组中的这些字符串。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-266">In these latter cases, Excel creates deep copies of the strings in the source cells and points to these within the array.</span></span> 
  
<span data-ttu-id="4fb6e-267">在要修改 DLL 中的这些字符串的地方，应制作自己的深层副本。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-267">Where you want to modify these strings in your DLL, you should make your own deep copies.</span></span> <span data-ttu-id="4fb6e-268">当您创建自己的 **xltypeMulti** 数组时，不应将Excel的 **字符串 XLOPER** /  **XLOPER12** 放在其中。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-268">When you are creating your own **xltypeMulti** arrays, you should not place Excel-allocated string **XLOPER**/ **XLOPER12** s within them.</span></span> <span data-ttu-id="4fb6e-269">这有风险：你以后无法正确释放它们，或者完全无法释放它们。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-269">This risks you not freeing them correctly later, or not freeing them at all.</span></span> <span data-ttu-id="4fb6e-270">同样，应制作字符串的深层副本，并存储指向数组中副本的指针。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-270">Again, you should make deep copies of the strings and store pointers to the copies in the array.</span></span>
  
 <span data-ttu-id="4fb6e-271">**示例**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-271">**Examples**</span></span>
  
<span data-ttu-id="4fb6e-272">以下示例函数创建长度计数型 Unicode 字符串的动态分配副本。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-272">The following example function creates a dynamically allocated copy of a length-counted Unicode string.</span></span> <span data-ttu-id="4fb6e-273">请注意，调用方最终必须使用 **delete**[] 释放此示例中分配的内存，并且不会假定源字符串以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-273">Note that the caller must ultimately free the memory allocated in this example using **delete**[], and that the source string is not assumed to be null terminated.</span></span> <span data-ttu-id="4fb6e-274">出于安全需要，复制字符串将被截断，并且不会以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-274">The copy string is truncated if necessary for safety, and is not null terminated.</span></span>
  
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

<span data-ttu-id="4fb6e-275">然后，可以安全地使用此函数复制 **XLOPER12，** 如下面的可导出 XLL 函数所示，该函数返回其参数的副本（如果它是字符串）。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-275">This function can then be safely used to copy an **XLOPER12**, as shown in the following exportable XLL function that returns a copy of its argument if it is a string.</span></span> <span data-ttu-id="4fb6e-276">所有其他类型作为零长度字符串返回。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-276">All other types are returned as a zero-length string.</span></span> <span data-ttu-id="4fb6e-277">请注意，不处理范围 - 函数返回 **#VALUE！。**</span><span class="sxs-lookup"><span data-stu-id="4fb6e-277">Note that ranges are not handled—the function returns **#VALUE!**.</span></span> <span data-ttu-id="4fb6e-278">该函数必须注册为采用类型 U 参数，以便引用作为值传入。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-278">The function must be registered as taking a type U argument so that references are passed in as values.</span></span> <span data-ttu-id="4fb6e-279">这相当于内置工作表函数 **T ()\*\*\*\*除了 AsText** 还会将错误转换为零长度字符串。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-279">This is equivalent to the built-in worksheet function **T()** except that **AsText** also converts errors to zero-length strings.</span></span> <span data-ttu-id="4fb6e-280">此代码示例假定 **xlAutoFree12** 使用 delete 释放传入指针及其 **内容**。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-280">This code example assumes that **xlAutoFree12** frees the passed-in pointer, and also its contents, using **delete**.</span></span>
  
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

### <a name="returning-modify-in-place-string-arguments"></a><span data-ttu-id="4fb6e-281">返回就地修改字符串参数</span><span class="sxs-lookup"><span data-stu-id="4fb6e-281">Returning Modify-in-Place String Arguments</span></span>

<span data-ttu-id="4fb6e-282">注册为类型 **F、G、F%** 和 **G%** 的参数可以就地进行修改。 </span><span class="sxs-lookup"><span data-stu-id="4fb6e-282">Arguments registered as types **F**, **G**, **F%**, and **G%** can be modified in place.</span></span> <span data-ttu-id="4fb6e-283">当Excel为这些类型准备字符串参数时，它将创建最大长度缓冲区。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-283">When Excel is preparing string arguments for these types, it creates a maximum length buffer.</span></span> <span data-ttu-id="4fb6e-284">然后它将参数字符串复制到该字符串中，即使此字符串要短得多。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-284">Then it copies the argument string into that, even if this string is very much shorter.</span></span> <span data-ttu-id="4fb6e-285">这使 XLL 函数能够直接将返回值写入同一内存。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-285">This enables the XLL function to write its return value directly into the same memory.</span></span> 
  
<span data-ttu-id="4fb6e-286">为这些类型设置的缓冲区大小如下所示：</span><span class="sxs-lookup"><span data-stu-id="4fb6e-286">Buffer sizes set apart for these types are as follows:</span></span>
  
- <span data-ttu-id="4fb6e-287">**字节字符串** ：256 个字节，包括长度计数器 (类型 G) 或 null-termination (类型 F) 。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-287">**Byte strings:** 256 bytes including the length counter (type G) or null-termination (type F).</span></span> 
    
- <span data-ttu-id="4fb6e-288">**Unicode** 字符串：32，768 个宽字符 (65，536 字节) 包括长度计数器 (类型 G%) 或空终止 (类型 F%) 。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-288">**Unicode strings:** 32,768 wide characters (65,536 bytes) including the length counter (type G%) or null-termination (type F%).</span></span> 
    
> [!NOTE]
> <span data-ttu-id="4fb6e-289">您无法直接从 VBA Visual Basic for Applications (调用此类) ，因为您无法确保已分配了一个非常大的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-289">You cannot call such a function directly from Visual Basic for Applications (VBA) because you cannot ensure that a sufficiently large buffer has been allocated.</span></span> <span data-ttu-id="4fb6e-290">只有在显式传递了足够大的缓冲区时，才能安全地从另一个 DLL 调用此类函数。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-290">You can only call such a function from another DLL safely if you have explicitly passed a big enough buffer.</span></span> 
  
<span data-ttu-id="4fb6e-291">下面是一个 XLL 函数示例，该函数使用标准库函数 **wcsrev** 反向传递以 null 结尾的宽字符串。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-291">Here is an example of an XLL function that reverses a passed-in null-terminated wide character string using the standard library function **wcsrev**.</span></span> <span data-ttu-id="4fb6e-292">本例中的参数将注册为 **F% 类型**。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-292">The argument in this case would be registered as type **F%**.</span></span>
  
```cs
void WINAPI reverse_text_xl12(wchar_t *text)
{
    _wcsrev(text);
}
```

## <a name="persistent-storage-binary-names"></a><span data-ttu-id="4fb6e-293">持久存储 (二进制) </span><span class="sxs-lookup"><span data-stu-id="4fb6e-293">Persistent Storage (Binary Names)</span></span>

<span data-ttu-id="4fb6e-294">二进制名称定义并关联到二进制块，即与工作簿一起存储的非结构化数据。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-294">Binary names are defined and associated with blocks of binary, that is, unstructured, data that is stored together with the workbook.</span></span> <span data-ttu-id="4fb6e-295">它们使用 [xlDefineBinaryName](xldefinebinaryname.md)函数创建，并且使用 [函数 xlGetBinaryName](xlgetbinaryname.md)检索数据。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-295">They are created using the function [xlDefineBinaryName](xldefinebinaryname.md), and the data is retrieved using the function [xlGetBinaryName](xlgetbinaryname.md).</span></span> <span data-ttu-id="4fb6e-296">这两个函数在函数参考 (请参阅 [C API Functions That Can Be Called Only from a DLL or XLL](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)) ， and both use the **xltypeBigData** **XLOPER** /  **XLOPER12**.</span><span class="sxs-lookup"><span data-stu-id="4fb6e-296">Both functions are described in more detail in the function reference (see [C API Functions That Can Be Called Only from a DLL or XLL](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)), and both use the **xltypeBigData** **XLOPER**/ **XLOPER12**.</span></span> 
  
<span data-ttu-id="4fb6e-297">有关限制二进制名称的实际应用程序的已知问题的信息，请参阅[XLL](known-issues-in-excel-xll-development.md)开发中的已知Excel问题。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-297">For information about known issues that limit the practical applications of binary names, see [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
## <a name="excel-stack"></a><span data-ttu-id="4fb6e-298">Excel堆栈</span><span class="sxs-lookup"><span data-stu-id="4fb6e-298">Excel Stack</span></span>

<span data-ttu-id="4fb6e-299">Excel加载的所有 DLL 共享其堆栈空间。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-299">Excel shares its stack space with all the DLLs it has loaded.</span></span> <span data-ttu-id="4fb6e-300">堆栈空间通常足以供普通使用，只要你遵循以下准则，就无需担心它：</span><span class="sxs-lookup"><span data-stu-id="4fb6e-300">Stack space is usually more than adequate for ordinary use, and you do not need to be concerned about it as long as you follow a few guidelines:</span></span> 
  
- <span data-ttu-id="4fb6e-301">不要将非常大的结构作为参数传递给堆栈上的值函数。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-301">Do not pass very large structures as arguments to functions by value on the stack.</span></span> <span data-ttu-id="4fb6e-302">传递指针或引用。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-302">Pass pointers or references instead.</span></span>
    
- <span data-ttu-id="4fb6e-303">请勿在堆栈上返回大型结构。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-303">Do not return large structures on the stack.</span></span> <span data-ttu-id="4fb6e-304">返回指向静态或动态分配的内存的指针，或使用通过引用传递的参数。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-304">Return pointers to static or dynamically allocated memory, or use arguments passed by reference.</span></span>
    
- <span data-ttu-id="4fb6e-305">请勿在函数代码中声明非常大的自动变量结构。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-305">Do not declare very large automatic variable structures in the function code.</span></span> <span data-ttu-id="4fb6e-306">如果需要，请将其声明为静态。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-306">If you need them, declare them as static.</span></span>
    
- <span data-ttu-id="4fb6e-307">除非确定递归深度始终浅表，否则不要以递归调用函数。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-307">Do not call functions recursively unless you are sure the depth of recursion will always be shallow.</span></span> <span data-ttu-id="4fb6e-308">请尝试改为使用循环。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-308">Try using a loop instead.</span></span>
    
<span data-ttu-id="4fb6e-309">当 DLL 使用 C API Excel回调用时，Excel首先检查堆栈上是否有足够的空间进行可能进行的最差情况使用调用。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-309">When a DLL calls back into Excel using the C API, Excel first checks whether there is enough space on the stack for the worst-case usage call that could be made.</span></span> <span data-ttu-id="4fb6e-310">如果它认为空间可能不足，则即使该特定呼叫实际上可能有足够的空间，呼叫也将无法安全。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-310">If it thinks there might be insufficient room, it will fail the call to be safe, even though there might actually have been enough space for that particular call.</span></span> <span data-ttu-id="4fb6e-311">在这种情况下，回调返回代码 **xlretFailed**。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-311">In this case, the callbacks return the code **xlretFailed**.</span></span> <span data-ttu-id="4fb6e-312">对于 C API 和堆栈的普通使用，这不太可能是 C API 调用失败的原因。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-312">For ordinary use of the C API and the stack, this is an unlikely cause of the failure of a C API call.</span></span>
  
<span data-ttu-id="4fb6e-313">如果你担心或只是想知道，或者希望消除堆栈空间不足作为未说明故障的原因，可以通过调用 [xlStack](xlstack.md) 函数来了解存在多少堆栈空间。</span><span class="sxs-lookup"><span data-stu-id="4fb6e-313">If you are concerned, or just curious, or you want to eliminate lack of stack space as a reason for an unexplained failure, you can find out how much stack space there is with a call to the [xlStack](xlstack.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4fb6e-314">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fb6e-314">See also</span></span>



[<span data-ttu-id="4fb6e-315">Excel 中的多线程重新计算</span><span class="sxs-lookup"><span data-stu-id="4fb6e-315">Multithreaded Recalculation in Excel</span></span>](multithreaded-recalculation-in-excel.md)
  
[<span data-ttu-id="4fb6e-316">线程中的多线程和内存Excel</span><span class="sxs-lookup"><span data-stu-id="4fb6e-316">Multithreading and Memory Contention in Excel</span></span>](multithreading-and-memory-contention-in-excel.md)
  
[<span data-ttu-id="4fb6e-317">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="4fb6e-317">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

