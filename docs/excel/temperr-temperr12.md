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
- temperr 函数 [excel 2007]，TempErr12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: cf8c26b2-ca2b-4dda-a02d-0ccbeac19106
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 68a0addc36ecf1b4491ab1e4f5b10f359bbc59c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410607"
---
# <a name="temperrtemperr12"></a><span data-ttu-id="49cb7-104">TempErr/TempErr12</span><span class="sxs-lookup"><span data-stu-id="49cb7-104">TempErr/TempErr12</span></span>

 <span data-ttu-id="49cb7-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="49cb7-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="49cb7-106">创建包含工作表错误临时 **XLOPER** /  **XLOPER12** Microsoft Excel库函数。</span><span class="sxs-lookup"><span data-stu-id="49cb7-106">Framework library function that creates a temporary **XLOPER**/ **XLOPER12** containing a Microsoft Excel worksheet error.</span></span> 
  
```cs
LPXLOPER TempErr(WORD err);
LPXLOPER12 TempErr12(BOOL err);
```

## <a name="parameters"></a><span data-ttu-id="49cb7-107">参数</span><span class="sxs-lookup"><span data-stu-id="49cb7-107">Parameters</span></span>

 <span data-ttu-id="49cb7-108">_err_</span><span class="sxs-lookup"><span data-stu-id="49cb7-108">_err_</span></span>
  
<span data-ttu-id="49cb7-109">所需的错误代码或等效文本数字，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="49cb7-109">The desired error code, or its literal numeric equivalent, as shown in the following table.</span></span>
  
|<span data-ttu-id="49cb7-110">**错误**</span><span class="sxs-lookup"><span data-stu-id="49cb7-110">**Error**</span></span>|<span data-ttu-id="49cb7-111">**XLCALL 中定义的错误代码。H**</span><span class="sxs-lookup"><span data-stu-id="49cb7-111">**Error code defined in XLCALL.H**</span></span>|<span data-ttu-id="49cb7-112">**小数等效项**</span><span class="sxs-lookup"><span data-stu-id="49cb7-112">**Decimal equivalent**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="49cb7-113">#NULL</span><span class="sxs-lookup"><span data-stu-id="49cb7-113">#NULL</span></span>  <br/> |<span data-ttu-id="49cb7-114">**xlerrNull**</span><span class="sxs-lookup"><span data-stu-id="49cb7-114">**xlerrNull**</span></span> <br/> |<span data-ttu-id="49cb7-115">0</span><span class="sxs-lookup"><span data-stu-id="49cb7-115">0</span></span>  <br/> |
|<span data-ttu-id="49cb7-116">#DIV/0!</span><span class="sxs-lookup"><span data-stu-id="49cb7-116">#DIV/0!</span></span>  <br/> |<span data-ttu-id="49cb7-117">**xlerrDiv0**</span><span class="sxs-lookup"><span data-stu-id="49cb7-117">**xlerrDiv0**</span></span> <br/> |<span data-ttu-id="49cb7-118">7 </span><span class="sxs-lookup"><span data-stu-id="49cb7-118">7</span></span>  <br/> |
|<span data-ttu-id="49cb7-119">#VALUE!</span><span class="sxs-lookup"><span data-stu-id="49cb7-119">#VALUE!</span></span>  <br/> |<span data-ttu-id="49cb7-120">**xlerrValue**</span><span class="sxs-lookup"><span data-stu-id="49cb7-120">**xlerrValue**</span></span> <br/> |<span data-ttu-id="49cb7-121">15</span><span class="sxs-lookup"><span data-stu-id="49cb7-121">15</span></span>  <br/> |
|<span data-ttu-id="49cb7-122">#REF!</span><span class="sxs-lookup"><span data-stu-id="49cb7-122">#REF!</span></span>  <br/> |<span data-ttu-id="49cb7-123">**xlerrRef**</span><span class="sxs-lookup"><span data-stu-id="49cb7-123">**xlerrRef**</span></span> <br/> |<span data-ttu-id="49cb7-124">23</span><span class="sxs-lookup"><span data-stu-id="49cb7-124">23</span></span>  <br/> |
|<span data-ttu-id="49cb7-125">#NAME?</span><span class="sxs-lookup"><span data-stu-id="49cb7-125">#NAME?</span></span>  <br/> |<span data-ttu-id="49cb7-126">**xlerrName**</span><span class="sxs-lookup"><span data-stu-id="49cb7-126">**xlerrName**</span></span> <br/> |<span data-ttu-id="49cb7-127">29</span><span class="sxs-lookup"><span data-stu-id="49cb7-127">29</span></span>  <br/> |
|<span data-ttu-id="49cb7-128">#NUM!</span><span class="sxs-lookup"><span data-stu-id="49cb7-128">#NUM!</span></span>  <br/> |<span data-ttu-id="49cb7-129">**xlerrNum**</span><span class="sxs-lookup"><span data-stu-id="49cb7-129">**xlerrNum**</span></span> <br/> |<span data-ttu-id="49cb7-130">36</span><span class="sxs-lookup"><span data-stu-id="49cb7-130">36</span></span>  <br/> |
|<span data-ttu-id="49cb7-131">#N/A</span><span class="sxs-lookup"><span data-stu-id="49cb7-131">#N/A</span></span>  <br/> |<span data-ttu-id="49cb7-132">**xlerrNA**</span><span class="sxs-lookup"><span data-stu-id="49cb7-132">**xlerrNA**</span></span> <br/> |<span data-ttu-id="49cb7-133">42</span><span class="sxs-lookup"><span data-stu-id="49cb7-133">42</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="49cb7-134">返回值</span><span class="sxs-lookup"><span data-stu-id="49cb7-134">Return value</span></span>

<span data-ttu-id="49cb7-135">返回包含传入的错误代码的 **xltypeBool。**</span><span class="sxs-lookup"><span data-stu-id="49cb7-135">Returns an **xltypeBool** containing the error code passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="49cb7-136">示例</span><span class="sxs-lookup"><span data-stu-id="49cb7-136">Example</span></span>

<span data-ttu-id="49cb7-137">此示例使用 **TempErr12** 函数返回一#VALUE！</span><span class="sxs-lookup"><span data-stu-id="49cb7-137">This example uses the **TempErr12** function to return a #VALUE!</span></span> <span data-ttu-id="49cb7-138">错误Excel。</span><span class="sxs-lookup"><span data-stu-id="49cb7-138">error to Excel.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="49cb7-139">框架库函数 **TempErr12** 从内部缓冲区分配内存，该缓冲区通常在调用 Framework 函数 **Excel12f** 时释放。</span><span class="sxs-lookup"><span data-stu-id="49cb7-139">The Framework library function **TempErr12** allocates memory from an internal buffer, which is normally freed when the Framework function **Excel12f** is called.</span></span> <span data-ttu-id="49cb7-140">如果在不调用 **Excel12f** 的情况下重复调用此示例函数，则会发生内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="49cb7-140">If this example function is called repeatedly without **Excel12f** being called, a memory leak occurs.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
LPXLOPER WINAPI TempErrExample(void)
{
    return TempErr12(xlerrValue);
}
```

## <a name="see-also"></a><span data-ttu-id="49cb7-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49cb7-141">See also</span></span>



[<span data-ttu-id="49cb7-142">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="49cb7-142">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

