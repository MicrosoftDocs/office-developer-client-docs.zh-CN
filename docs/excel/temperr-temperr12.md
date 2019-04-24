---
title: TempErr/TempErr12
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempErr
- TempErr12
keywords:
- temperr 函数 [excel 2007], TempErr12 函数 [excel 2007]
localization_priority: Normal
ms.assetid: cf8c26b2-ca2b-4dda-a02d-0ccbeac19106
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 68a0addc36ecf1b4491ab1e4f5b10f359bbc59c3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310344"
---
# <a name="temperrtemperr12"></a><span data-ttu-id="b045a-104">TempErr/TempErr12</span><span class="sxs-lookup"><span data-stu-id="b045a-104">TempErr/TempErr12</span></span>

 <span data-ttu-id="b045a-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b045a-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="b045a-106">Framework library 函数, 用于创建一个包含 Microsoft Excel 工作表错误的临时**XLOPER**/ **XLOPER12** 。</span><span class="sxs-lookup"><span data-stu-id="b045a-106">Framework library function that creates a temporary **XLOPER**/ **XLOPER12** containing a Microsoft Excel worksheet error.</span></span> 
  
```cs
LPXLOPER TempErr(WORD err);
LPXLOPER12 TempErr12(BOOL err);
```

## <a name="parameters"></a><span data-ttu-id="b045a-107">参数</span><span class="sxs-lookup"><span data-stu-id="b045a-107">Parameters</span></span>

 <span data-ttu-id="b045a-108">_err_</span><span class="sxs-lookup"><span data-stu-id="b045a-108">_err_</span></span>
  
<span data-ttu-id="b045a-109">所需的错误代码或其常数值等效项, 如下表所示。</span><span class="sxs-lookup"><span data-stu-id="b045a-109">The desired error code, or its literal numeric equivalent, as shown in the following table.</span></span>
  
|<span data-ttu-id="b045a-110">**Error**</span><span class="sxs-lookup"><span data-stu-id="b045a-110">**Error**</span></span>|<span data-ttu-id="b045a-111">**xlcall.h 中定义的错误代码。水平**</span><span class="sxs-lookup"><span data-stu-id="b045a-111">**Error code defined in XLCALL.H**</span></span>|<span data-ttu-id="b045a-112">**十进制等效项**</span><span class="sxs-lookup"><span data-stu-id="b045a-112">**Decimal equivalent**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b045a-113">#NULL</span><span class="sxs-lookup"><span data-stu-id="b045a-113">#NULL</span></span>  <br/> |<span data-ttu-id="b045a-114">**xlerrNull**</span><span class="sxs-lookup"><span data-stu-id="b045a-114">**xlerrNull**</span></span> <br/> |<span data-ttu-id="b045a-115">0</span><span class="sxs-lookup"><span data-stu-id="b045a-115">0</span></span>  <br/> |
|<span data-ttu-id="b045a-116">#DIV/0!</span><span class="sxs-lookup"><span data-stu-id="b045a-116">#DIV/0!</span></span>  <br/> |<span data-ttu-id="b045a-117">**xlerrDiv0**</span><span class="sxs-lookup"><span data-stu-id="b045a-117">**xlerrDiv0**</span></span> <br/> |<span data-ttu-id="b045a-118">步</span><span class="sxs-lookup"><span data-stu-id="b045a-118">7</span></span>  <br/> |
|<span data-ttu-id="b045a-119">#VALUE!</span><span class="sxs-lookup"><span data-stu-id="b045a-119">#VALUE!</span></span>  <br/> |<span data-ttu-id="b045a-120">**xlerrValue**</span><span class="sxs-lookup"><span data-stu-id="b045a-120">**xlerrValue**</span></span> <br/> |<span data-ttu-id="b045a-121">个</span><span class="sxs-lookup"><span data-stu-id="b045a-121">15</span></span>  <br/> |
|<span data-ttu-id="b045a-122">#REF!</span><span class="sxs-lookup"><span data-stu-id="b045a-122">#REF!</span></span>  <br/> |<span data-ttu-id="b045a-123">**xlerrRef**</span><span class="sxs-lookup"><span data-stu-id="b045a-123">**xlerrRef**</span></span> <br/> |<span data-ttu-id="b045a-124">上午</span><span class="sxs-lookup"><span data-stu-id="b045a-124">23</span></span>  <br/> |
|<span data-ttu-id="b045a-125">#NAME?</span><span class="sxs-lookup"><span data-stu-id="b045a-125">#NAME?</span></span>  <br/> |<span data-ttu-id="b045a-126">**xlerrName**</span><span class="sxs-lookup"><span data-stu-id="b045a-126">**xlerrName**</span></span> <br/> |<span data-ttu-id="b045a-127">29</span><span class="sxs-lookup"><span data-stu-id="b045a-127">29</span></span>  <br/> |
|<span data-ttu-id="b045a-128">#NUM!</span><span class="sxs-lookup"><span data-stu-id="b045a-128">#NUM!</span></span>  <br/> |<span data-ttu-id="b045a-129">**xlerrNum**</span><span class="sxs-lookup"><span data-stu-id="b045a-129">**xlerrNum**</span></span> <br/> |<span data-ttu-id="b045a-130">36</span><span class="sxs-lookup"><span data-stu-id="b045a-130">36</span></span>  <br/> |
|<span data-ttu-id="b045a-131">#N/A</span><span class="sxs-lookup"><span data-stu-id="b045a-131">#N/A</span></span>  <br/> |<span data-ttu-id="b045a-132">**xlerrNA**</span><span class="sxs-lookup"><span data-stu-id="b045a-132">**xlerrNA**</span></span> <br/> |<span data-ttu-id="b045a-133">42</span><span class="sxs-lookup"><span data-stu-id="b045a-133">42</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="b045a-134">返回值</span><span class="sxs-lookup"><span data-stu-id="b045a-134">Return value</span></span>

<span data-ttu-id="b045a-135">返回一个**xltypeBool** , 其中包含传入的错误代码。</span><span class="sxs-lookup"><span data-stu-id="b045a-135">Returns an **xltypeBool** containing the error code passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="b045a-136">示例</span><span class="sxs-lookup"><span data-stu-id="b045a-136">Example</span></span>

<span data-ttu-id="b045a-137">此示例使用**TempErr12**函数返回 #VALUE!</span><span class="sxs-lookup"><span data-stu-id="b045a-137">This example uses the **TempErr12** function to return a #VALUE!</span></span> <span data-ttu-id="b045a-138">对 Excel 的错误。</span><span class="sxs-lookup"><span data-stu-id="b045a-138">error to Excel.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b045a-139">框架库函数**TempErr12**从内部缓冲区分配内存, 该缓冲区通常在调用 Framework 函数**Excel12f**时释放。</span><span class="sxs-lookup"><span data-stu-id="b045a-139">The Framework library function **TempErr12** allocates memory from an internal buffer, which is normally freed when the Framework function **Excel12f** is called.</span></span> <span data-ttu-id="b045a-140">如果在未调用**Excel12f**的情况下重复调用此示例函数, 则会发生内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="b045a-140">If this example function is called repeatedly without **Excel12f** being called, a memory leak occurs.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
LPXLOPER WINAPI TempErrExample(void)
{
    return TempErr12(xlerrValue);
}
```

## <a name="see-also"></a><span data-ttu-id="b045a-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b045a-141">See also</span></span>



[<span data-ttu-id="b045a-142">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="b045a-142">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

