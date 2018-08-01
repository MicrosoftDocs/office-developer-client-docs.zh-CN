---
title: Excel/Excel12f
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Excel12f
keywords:
- excel 函数 [excel 2007，] Excel12f 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 4e6a9ccc-988d-42a9-8874-01f2ee29b835
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 56034984852713496465c3d1f79a9989fc47df1c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773678"
---
# <a name="excelexcel12f"></a><span data-ttu-id="0dc80-104">Excel/Excel12f</span><span class="sxs-lookup"><span data-stu-id="0dc80-104">Excel/Excel12f</span></span>

 <span data-ttu-id="0dc80-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0dc80-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="0dc80-106">Framework 库函数。</span><span class="sxs-lookup"><span data-stu-id="0dc80-106">Framework library functions.</span></span> <span data-ttu-id="0dc80-107">**Excel**是[Excel4](excel4-excel12.md)函数的包装。</span><span class="sxs-lookup"><span data-stu-id="0dc80-107">**Excel** is a wrapper for the [Excel4](excel4-excel12.md) function.</span></span> <span data-ttu-id="0dc80-108">**Excel12f**是[Excel12](excel4-excel12.md)函数的包装。</span><span class="sxs-lookup"><span data-stu-id="0dc80-108">**Excel12f** is a wrapper for the [Excel12](excel4-excel12.md) function.</span></span> <span data-ttu-id="0dc80-109">每个检查所有参数为零，这将指示创建临时**XLOPER**或**XLOPER12**失败。</span><span class="sxs-lookup"><span data-stu-id="0dc80-109">Each checks to see that none of the arguments is zero, which would indicate that the creation of a temporary **XLOPER** or **XLOPER12** failed.</span></span> <span data-ttu-id="0dc80-110">如果出现错误，每打印调试消息。</span><span class="sxs-lookup"><span data-stu-id="0dc80-110">If an error occurs, each prints a debug message.</span></span> <span data-ttu-id="0dc80-111">完成后，每个释放可能已创建的临时**XLOPER**s 和**XLOPER12**s 的所有临时内存。</span><span class="sxs-lookup"><span data-stu-id="0dc80-111">When finished, each frees all temporary memory that might have been created for temporary **XLOPER**s and **XLOPER12**s.</span></span>
  
 <span data-ttu-id="0dc80-112">只能从 DLL 启动与 Excel 2007 C API 库调用**Excel12f** 。</span><span class="sxs-lookup"><span data-stu-id="0dc80-112">**Excel12f** can only be called from a DLL starting with the Excel 2007 C API library.</span></span> <span data-ttu-id="0dc80-113">此外，它仅适用于运行 Excel 2007 中，从开始时，操作失败**xlretFailed** ，否则。</span><span class="sxs-lookup"><span data-stu-id="0dc80-113">Furthermore, it only works when running starting with Excel 2007, and fails with **xlretFailed** otherwise.</span></span> 
  
```cs
int Excel(int iFunction, LPXLOPER pxRes, int iCount, 
LPXLOPER argument1, ...);
int Excel12f(int iFunction, LPXLOPER12 pxRes, int iCount, 
LPXLOPER12 argument1, ...);
```

## <a name="parameters"></a><span data-ttu-id="0dc80-114">参数</span><span class="sxs-lookup"><span data-stu-id="0dc80-114">Parameters</span></span>

 <span data-ttu-id="0dc80-115">_iFunction_(**int**)</span><span class="sxs-lookup"><span data-stu-id="0dc80-115">_iFunction_ (**int**)</span></span>
  
<span data-ttu-id="0dc80-116">要呼叫的一个数字，指示命令或函数。</span><span class="sxs-lookup"><span data-stu-id="0dc80-116">A number indicating the command or function you want to call.</span></span> <span data-ttu-id="0dc80-117">有关详细信息，请参阅[Excel4/Excel12](excel4-excel12.md)。</span><span class="sxs-lookup"><span data-stu-id="0dc80-117">For more information, see [Excel4/Excel12](excel4-excel12.md).</span></span>
  
 <span data-ttu-id="0dc80-118">_pxRes_</span><span class="sxs-lookup"><span data-stu-id="0dc80-118">_pxRes_</span></span>
  
<span data-ttu-id="0dc80-119">一个指针到计算函数的结果。</span><span class="sxs-lookup"><span data-stu-id="0dc80-119">A pointer to result of the evaluated function.</span></span> <span data-ttu-id="0dc80-120">在结果中指向任何内存将由 Excel 分配和应释放调用[xlFree](xlfree.md)后不再需要它，或通过设置**xlbitXLFree** ，如果它返回到 Excel 中。</span><span class="sxs-lookup"><span data-stu-id="0dc80-120">Any memory pointed to in the result will have been allocated by Excel and should be freed in a call to [xlFree](xlfree.md) once it is no longer needed, or by setting **xlbitXLFree** if returning it to Excel.</span></span> 
  
 <span data-ttu-id="0dc80-121">_iCount_(**int**)</span><span class="sxs-lookup"><span data-stu-id="0dc80-121">_iCount_ (**int**)</span></span>
  
<span data-ttu-id="0dc80-122">将传递给函数的参数数目。</span><span class="sxs-lookup"><span data-stu-id="0dc80-122">The number of arguments that will be passed to the function.</span></span> <span data-ttu-id="0dc80-123">从 Excel 2007 开始，限制为 255 的参数。</span><span class="sxs-lookup"><span data-stu-id="0dc80-123">Starting in Excel 2007, the limit is 255 arguments.</span></span> <span data-ttu-id="0dc80-124">在早期版本，限制为 30。</span><span class="sxs-lookup"><span data-stu-id="0dc80-124">In earlier versions, the limit is 30.</span></span>
  
 <span data-ttu-id="0dc80-125">_argument1..._</span><span class="sxs-lookup"><span data-stu-id="0dc80-125">_argument1, ..._</span></span>
  
<span data-ttu-id="0dc80-126">函数的可选参数。</span><span class="sxs-lookup"><span data-stu-id="0dc80-126">The optional arguments to the function.</span></span> <span data-ttu-id="0dc80-127">所有参数都必须为**XLOPER**s 对于**Excel**或对于**Excel12f** **XLOPER12**s 的指针。</span><span class="sxs-lookup"><span data-stu-id="0dc80-127">All arguments must be pointers to **XLOPER**s in the case of **Excel**, or **XLOPER12**s in the case of **Excel12f**.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="0dc80-128">返回值</span><span class="sxs-lookup"><span data-stu-id="0dc80-128">Return value</span></span>

<span data-ttu-id="0dc80-129">这两个函数将返回相同的错误和成功代码为**Excel4**、 **Excel4v**、 **Excel12**和**Excel12v**。</span><span class="sxs-lookup"><span data-stu-id="0dc80-129">Both functions return the same error and success codes as **Excel4**, **Excel4v**, **Excel12**, and **Excel12v**.</span></span> <span data-ttu-id="0dc80-130">有关这些代码的完整说明，请参阅[Excel4/Excel12](excel4-excel12.md) 。</span><span class="sxs-lookup"><span data-stu-id="0dc80-130">See [Excel4/Excel12](excel4-excel12.md) for a full description of these codes.</span></span> <span data-ttu-id="0dc80-131">此外，这些框架函数返回检测到**xlretFailed**而无需调用 C API 如果参数为 NULL 指针。</span><span class="sxs-lookup"><span data-stu-id="0dc80-131">In addition, these Framework functions return **xlretFailed** without calling the C API if a NULL pointer to a parameter is detected.</span></span> 
  
## <a name="example"></a><span data-ttu-id="0dc80-132">示例</span><span class="sxs-lookup"><span data-stu-id="0dc80-132">Example</span></span>

<span data-ttu-id="0dc80-133">本示例将错误的参数传递给**Excel12f**函数，它向调试器发送邮件。</span><span class="sxs-lookup"><span data-stu-id="0dc80-133">This example passes a bad argument to the **Excel12f** function, which sends a message to the debugger.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI Excel12fExample(void)
{
    Excel12f(xlcDisplay, 0, 1, 0);
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="0dc80-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0dc80-134">See also</span></span>



[<span data-ttu-id="0dc80-135">Excel4/Excel12</span><span class="sxs-lookup"><span data-stu-id="0dc80-135">Excel4/Excel12</span></span>](excel4-excel12.md)


[<span data-ttu-id="0dc80-136">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="0dc80-136">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

