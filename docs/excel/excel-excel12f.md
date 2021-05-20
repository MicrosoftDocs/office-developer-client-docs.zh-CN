---
title: Excel/Excel12f
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Excel12f
keywords:
- excel 函数 [excel 2007]，Excel12f 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 4e6a9ccc-988d-42a9-8874-01f2ee29b835
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: f7ff6afac1737ee869e69fffd3dbed36a908b376
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431671"
---
# <a name="excelexcel12f"></a><span data-ttu-id="e595a-104">Excel/Excel12f</span><span class="sxs-lookup"><span data-stu-id="e595a-104">Excel/Excel12f</span></span>

 <span data-ttu-id="e595a-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e595a-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="e595a-106">框架库函数。</span><span class="sxs-lookup"><span data-stu-id="e595a-106">Framework library functions.</span></span> <span data-ttu-id="e595a-107">**Excel** [Excel4](excel4-excel12.md)函数的包装。</span><span class="sxs-lookup"><span data-stu-id="e595a-107">**Excel** is a wrapper for the [Excel4](excel4-excel12.md) function.</span></span> <span data-ttu-id="e595a-108">**Excel12f** 是 [Excel12](excel4-excel12.md) 函数的包装。</span><span class="sxs-lookup"><span data-stu-id="e595a-108">**Excel12f** is a wrapper for the [Excel12](excel4-excel12.md) function.</span></span> <span data-ttu-id="e595a-109">每个检查一次，发现没有任何参数为零，这表示创建临时 **XLOPER** 或 **XLOPER12** 失败。</span><span class="sxs-lookup"><span data-stu-id="e595a-109">Each checks to see that none of the arguments is zero, which would indicate that the creation of a temporary **XLOPER** or **XLOPER12** failed.</span></span> <span data-ttu-id="e595a-110">如果发生错误，则每个代码都打印一条调试消息。</span><span class="sxs-lookup"><span data-stu-id="e595a-110">If an error occurs, each prints a debug message.</span></span> <span data-ttu-id="e595a-111">完成后，每个将释放可能为临时 XLOPER 和 **XLOPER12** s 创建的所有临时内存。 </span><span class="sxs-lookup"><span data-stu-id="e595a-111">When finished, each frees all temporary memory that might have been created for temporary **XLOPER** s and **XLOPER12** s.</span></span>
  
 <span data-ttu-id="e595a-112">**Excel12f** 只能从从 Excel 2007 C API 库开始调用。</span><span class="sxs-lookup"><span data-stu-id="e595a-112">**Excel12f** can only be called from a DLL starting with the Excel 2007 C API library.</span></span> <span data-ttu-id="e595a-113">此外，它仅在从 2007 Excel运行时有效，否则使用 **xlretFailed** 失败。</span><span class="sxs-lookup"><span data-stu-id="e595a-113">Furthermore, it only works when running starting with Excel 2007, and fails with **xlretFailed** otherwise.</span></span> 
  
```cs
int Excel(int iFunction, LPXLOPER pxRes, int iCount, 
LPXLOPER argument1, ...);
int Excel12f(int iFunction, LPXLOPER12 pxRes, int iCount, 
LPXLOPER12 argument1, ...);
```

## <a name="parameters"></a><span data-ttu-id="e595a-114">参数</span><span class="sxs-lookup"><span data-stu-id="e595a-114">Parameters</span></span>

 <span data-ttu-id="e595a-115">_iFunction_ (**int)**</span><span class="sxs-lookup"><span data-stu-id="e595a-115">_iFunction_ (**int**)</span></span>
  
<span data-ttu-id="e595a-116">指示要调用的命令或函数的编号。</span><span class="sxs-lookup"><span data-stu-id="e595a-116">A number indicating the command or function you want to call.</span></span> <span data-ttu-id="e595a-117">有关详细信息，请参阅[Excel4/Excel12。](excel4-excel12.md)</span><span class="sxs-lookup"><span data-stu-id="e595a-117">For more information, see [Excel4/Excel12](excel4-excel12.md).</span></span>
  
 <span data-ttu-id="e595a-118">_pxRes_</span><span class="sxs-lookup"><span data-stu-id="e595a-118">_pxRes_</span></span>
  
<span data-ttu-id="e595a-119">指向已计算函数结果的指针。</span><span class="sxs-lookup"><span data-stu-id="e595a-119">A pointer to result of the evaluated function.</span></span> <span data-ttu-id="e595a-120">结果中指向的任何内存都将由 Excel 并且应在 [不再需要 xlFree](xlfree.md)时通过调用 xlFree 中释放，或者通过设置 **xlbitXLFree（** 如果返回到 Excel） 来释放。</span><span class="sxs-lookup"><span data-stu-id="e595a-120">Any memory pointed to in the result will have been allocated by Excel and should be freed in a call to [xlFree](xlfree.md) once it is no longer needed, or by setting **xlbitXLFree** if returning it to Excel.</span></span> 
  
 <span data-ttu-id="e595a-121">_iCount_ (**int)**</span><span class="sxs-lookup"><span data-stu-id="e595a-121">_iCount_ (**int**)</span></span>
  
<span data-ttu-id="e595a-122">将传递给函数的参数数。</span><span class="sxs-lookup"><span data-stu-id="e595a-122">The number of arguments that will be passed to the function.</span></span> <span data-ttu-id="e595a-123">从 2007 Excel起，限制为 255 个参数。</span><span class="sxs-lookup"><span data-stu-id="e595a-123">Starting in Excel 2007, the limit is 255 arguments.</span></span> <span data-ttu-id="e595a-124">在早期版本中，限制为 30。</span><span class="sxs-lookup"><span data-stu-id="e595a-124">In earlier versions, the limit is 30.</span></span>
  
 <span data-ttu-id="e595a-125">_argument1， ..._</span><span class="sxs-lookup"><span data-stu-id="e595a-125">_argument1, ..._</span></span>
  
<span data-ttu-id="e595a-126">函数的可选参数。</span><span class="sxs-lookup"><span data-stu-id="e595a-126">The optional arguments to the function.</span></span> <span data-ttu-id="e595a-127">所有参数必须为指向 **XLOPER** 的指针（如果为 **Excel）** 或 **XLOPER12** s（**对于 Excel12f）。**</span><span class="sxs-lookup"><span data-stu-id="e595a-127">All arguments must be pointers to **XLOPER** s in the case of **Excel**, or **XLOPER12** s in the case of **Excel12f**.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="e595a-128">返回值</span><span class="sxs-lookup"><span data-stu-id="e595a-128">Return value</span></span>

<span data-ttu-id="e595a-129">这两个函数返回与 **Excel4、Excel4v、Excel12** 和 **Excel12v 相同的错误代码和成功代码**。  </span><span class="sxs-lookup"><span data-stu-id="e595a-129">Both functions return the same error and success codes as **Excel4**, **Excel4v**, **Excel12**, and **Excel12v**.</span></span> <span data-ttu-id="e595a-130">有关[这些代码的完整说明，请参阅 Excel4/Excel12。](excel4-excel12.md)</span><span class="sxs-lookup"><span data-stu-id="e595a-130">See [Excel4/Excel12](excel4-excel12.md) for a full description of these codes.</span></span> <span data-ttu-id="e595a-131">此外，如果检测到指向参数的 NULL 指针，这些 Framework 函数将返回 **xlretFailed，** 而不调用 C API。</span><span class="sxs-lookup"><span data-stu-id="e595a-131">In addition, these Framework functions return **xlretFailed** without calling the C API if a NULL pointer to a parameter is detected.</span></span> 
  
## <a name="example"></a><span data-ttu-id="e595a-132">示例</span><span class="sxs-lookup"><span data-stu-id="e595a-132">Example</span></span>

<span data-ttu-id="e595a-133">此示例将错误参数传递给 **Excel12f** 函数，该函数向调试器发送消息。</span><span class="sxs-lookup"><span data-stu-id="e595a-133">This example passes a bad argument to the **Excel12f** function, which sends a message to the debugger.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI Excel12fExample(void)
{
    Excel12f(xlcDisplay, 0, 1, 0);
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="e595a-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e595a-134">See also</span></span>



[<span data-ttu-id="e595a-135">Excel4/Excel12</span><span class="sxs-lookup"><span data-stu-id="e595a-135">Excel4/Excel12</span></span>](excel4-excel12.md)


[<span data-ttu-id="e595a-136">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="e595a-136">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

