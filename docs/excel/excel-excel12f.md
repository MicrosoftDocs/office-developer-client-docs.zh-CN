---
title: Excel/Excel12f
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Excel12f
keywords:
- excel 函数 [excel 2007], Excel12f 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 4e6a9ccc-988d-42a9-8874-01f2ee29b835
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: f7ff6afac1737ee869e69fffd3dbed36a908b376
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310911"
---
# <a name="excelexcel12f"></a><span data-ttu-id="b80e4-104">Excel/Excel12f</span><span class="sxs-lookup"><span data-stu-id="b80e4-104">Excel/Excel12f</span></span>

 <span data-ttu-id="b80e4-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b80e4-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="b80e4-106">框架库函数。</span><span class="sxs-lookup"><span data-stu-id="b80e4-106">Framework library functions.</span></span> <span data-ttu-id="b80e4-107">**Excel**是[Excel4](excel4-excel12.md)函数的包装。</span><span class="sxs-lookup"><span data-stu-id="b80e4-107">**Excel** is a wrapper for the [Excel4](excel4-excel12.md) function.</span></span> <span data-ttu-id="b80e4-108">**Excel12f**是[Excel12](excel4-excel12.md)函数的包装。</span><span class="sxs-lookup"><span data-stu-id="b80e4-108">**Excel12f** is a wrapper for the [Excel12](excel4-excel12.md) function.</span></span> <span data-ttu-id="b80e4-109">每个检查到查看的参数是否均为零, 这表示临时**XLOPER**或**XLOPER12**的创建失败。</span><span class="sxs-lookup"><span data-stu-id="b80e4-109">Each checks to see that none of the arguments is zero, which would indicate that the creation of a temporary **XLOPER** or **XLOPER12** failed.</span></span> <span data-ttu-id="b80e4-110">如果发生错误, 每个都将打印一条调试消息。</span><span class="sxs-lookup"><span data-stu-id="b80e4-110">If an error occurs, each prints a debug message.</span></span> <span data-ttu-id="b80e4-111">完成后, 每个都将释放可能已为临时**XLOPER**s 和**XLOPER12**s 创建的所有临时内存。</span><span class="sxs-lookup"><span data-stu-id="b80e4-111">When finished, each frees all temporary memory that might have been created for temporary **XLOPER**s and **XLOPER12**s.</span></span>
  
 <span data-ttu-id="b80e4-112">仅可从 Excel 2007 C API 库开始的 DLL 调用**Excel12f** 。</span><span class="sxs-lookup"><span data-stu-id="b80e4-112">**Excel12f** can only be called from a DLL starting with the Excel 2007 C API library.</span></span> <span data-ttu-id="b80e4-113">此外, 它仅在从 Excel 2007 开始运行时才有效, 否则会与**xlretFailed**失败。</span><span class="sxs-lookup"><span data-stu-id="b80e4-113">Furthermore, it only works when running starting with Excel 2007, and fails with **xlretFailed** otherwise.</span></span> 
  
```cs
int Excel(int iFunction, LPXLOPER pxRes, int iCount, 
LPXLOPER argument1, ...);
int Excel12f(int iFunction, LPXLOPER12 pxRes, int iCount, 
LPXLOPER12 argument1, ...);
```

## <a name="parameters"></a><span data-ttu-id="b80e4-114">参数</span><span class="sxs-lookup"><span data-stu-id="b80e4-114">Parameters</span></span>

 <span data-ttu-id="b80e4-115">_iFunction_(**int**)</span><span class="sxs-lookup"><span data-stu-id="b80e4-115">_iFunction_ (**int**)</span></span>
  
<span data-ttu-id="b80e4-116">表示要调用的命令或函数的数字。</span><span class="sxs-lookup"><span data-stu-id="b80e4-116">A number indicating the command or function you want to call.</span></span> <span data-ttu-id="b80e4-117">有关详细信息, 请参阅[Excel4/Excel12](excel4-excel12.md)。</span><span class="sxs-lookup"><span data-stu-id="b80e4-117">For more information, see [Excel4/Excel12](excel4-excel12.md).</span></span>
  
 <span data-ttu-id="b80e4-118">_pxRes_</span><span class="sxs-lookup"><span data-stu-id="b80e4-118">_pxRes_</span></span>
  
<span data-ttu-id="b80e4-119">指向计算函数的结果的指针。</span><span class="sxs-lookup"><span data-stu-id="b80e4-119">A pointer to result of the evaluated function.</span></span> <span data-ttu-id="b80e4-120">在结果中指向的任何内存都将由 Excel 分配, 在 xlFree 不再需要时, 应在对[](xlfree.md)的调用中释放, 或者在将**xlbitXLFree**返回到 Excel 时将其设置为。</span><span class="sxs-lookup"><span data-stu-id="b80e4-120">Any memory pointed to in the result will have been allocated by Excel and should be freed in a call to [xlFree](xlfree.md) once it is no longer needed, or by setting **xlbitXLFree** if returning it to Excel.</span></span> 
  
 <span data-ttu-id="b80e4-121">_iCount_(**int**)</span><span class="sxs-lookup"><span data-stu-id="b80e4-121">_iCount_ (**int**)</span></span>
  
<span data-ttu-id="b80e4-122">将传递给函数的参数的数目。</span><span class="sxs-lookup"><span data-stu-id="b80e4-122">The number of arguments that will be passed to the function.</span></span> <span data-ttu-id="b80e4-123">从 Excel 2007 开始, 限制为255个参数。</span><span class="sxs-lookup"><span data-stu-id="b80e4-123">Starting in Excel 2007, the limit is 255 arguments.</span></span> <span data-ttu-id="b80e4-124">在早期版本中, 限制为30个。</span><span class="sxs-lookup"><span data-stu-id="b80e4-124">In earlier versions, the limit is 30.</span></span>
  
 <span data-ttu-id="b80e4-125">_argument1 .。。_</span><span class="sxs-lookup"><span data-stu-id="b80e4-125">_argument1, ..._</span></span>
  
<span data-ttu-id="b80e4-126">函数的可选参数。</span><span class="sxs-lookup"><span data-stu-id="b80e4-126">The optional arguments to the function.</span></span> <span data-ttu-id="b80e4-127">在**Excel**的情况下, 所有参数都必须是指向**XLOPER**s 的指针, 否则, 在**Excel12f**的情况下, 也必须是**XLOPER12**。</span><span class="sxs-lookup"><span data-stu-id="b80e4-127">All arguments must be pointers to **XLOPER**s in the case of **Excel**, or **XLOPER12**s in the case of **Excel12f**.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="b80e4-128">返回值</span><span class="sxs-lookup"><span data-stu-id="b80e4-128">Return value</span></span>

<span data-ttu-id="b80e4-129">这两个函数都返回与**Excel4**、 **Excel4v**、 **Excel12**和**Excel12v**相同的错误和成功代码。</span><span class="sxs-lookup"><span data-stu-id="b80e4-129">Both functions return the same error and success codes as **Excel4**, **Excel4v**, **Excel12**, and **Excel12v**.</span></span> <span data-ttu-id="b80e4-130">有关这些代码的完整说明, 请参阅[Excel4/Excel12](excel4-excel12.md) 。</span><span class="sxs-lookup"><span data-stu-id="b80e4-130">See [Excel4/Excel12](excel4-excel12.md) for a full description of these codes.</span></span> <span data-ttu-id="b80e4-131">此外, 如果检测到指向参数的 NULL 指针, 则这些框架函数将返回**xlretFailed** , 而不调用 C API。</span><span class="sxs-lookup"><span data-stu-id="b80e4-131">In addition, these Framework functions return **xlretFailed** without calling the C API if a NULL pointer to a parameter is detected.</span></span> 
  
## <a name="example"></a><span data-ttu-id="b80e4-132">示例</span><span class="sxs-lookup"><span data-stu-id="b80e4-132">Example</span></span>

<span data-ttu-id="b80e4-133">此示例将一个不正确的参数传递给**Excel12f**函数, 该函数将向调试器发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="b80e4-133">This example passes a bad argument to the **Excel12f** function, which sends a message to the debugger.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI Excel12fExample(void)
{
    Excel12f(xlcDisplay, 0, 1, 0);
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="b80e4-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b80e4-134">See also</span></span>



[<span data-ttu-id="b80e4-135">Excel4/Excel12</span><span class="sxs-lookup"><span data-stu-id="b80e4-135">Excel4/Excel12</span></span>](excel4-excel12.md)


[<span data-ttu-id="b80e4-136">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="b80e4-136">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

