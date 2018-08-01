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
- temperr 函数 [excel 2007，] TempErr12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: cf8c26b2-ca2b-4dda-a02d-0ccbeac19106
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 22c0ff1b8259fc0e5ee70edb06bb3db53781ff8c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773812"
---
# <a name="temperrtemperr12"></a><span data-ttu-id="f79d4-104">TempErr/TempErr12</span><span class="sxs-lookup"><span data-stu-id="f79d4-104">TempErr/TempErr12</span></span>

 <span data-ttu-id="f79d4-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f79d4-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="f79d4-106">创建临时**XLOPER**的框架库函数/ **XLOPER12**包含 Microsoft Excel 工作表错误。</span><span class="sxs-lookup"><span data-stu-id="f79d4-106">Framework library function that creates a temporary **XLOPER**/ **XLOPER12** containing a Microsoft Excel worksheet error.</span></span> 
  
```cs
LPXLOPER TempErr(WORD err);
LPXLOPER12 TempErr12(BOOL err);
```

## <a name="parameters"></a><span data-ttu-id="f79d4-107">参数</span><span class="sxs-lookup"><span data-stu-id="f79d4-107">Parameters</span></span>

 <span data-ttu-id="f79d4-108">_err_</span><span class="sxs-lookup"><span data-stu-id="f79d4-108">_err_</span></span>
  
<span data-ttu-id="f79d4-109">所需的错误代码或其文字等价数值下, 表中所示。</span><span class="sxs-lookup"><span data-stu-id="f79d4-109">The desired error code, or its literal numeric equivalent, as shown in the following table.</span></span>
  
|<span data-ttu-id="f79d4-110">**Error**</span><span class="sxs-lookup"><span data-stu-id="f79d4-110">**Error**</span></span>|<span data-ttu-id="f79d4-111">**XLCALL 中定义的错误代码。H**</span><span class="sxs-lookup"><span data-stu-id="f79d4-111">**Error code defined in XLCALL.H**</span></span>|<span data-ttu-id="f79d4-112">**十进制等效项**</span><span class="sxs-lookup"><span data-stu-id="f79d4-112">**Decimal equivalent**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f79d4-113">#NULL</span><span class="sxs-lookup"><span data-stu-id="f79d4-113">#NULL</span></span>  <br/> |<span data-ttu-id="f79d4-114">**xlerrNull**</span><span class="sxs-lookup"><span data-stu-id="f79d4-114">**xlerrNull**</span></span> <br/> |<span data-ttu-id="f79d4-115">0</span><span class="sxs-lookup"><span data-stu-id="f79d4-115">0</span></span>  <br/> |
|<span data-ttu-id="f79d4-116">#DIV/0!</span><span class="sxs-lookup"><span data-stu-id="f79d4-116">#DIV/0!</span></span>  <br/> |<span data-ttu-id="f79d4-117">**xlerrDiv0**</span><span class="sxs-lookup"><span data-stu-id="f79d4-117">**xlerrDiv0**</span></span> <br/> |<span data-ttu-id="f79d4-118">7</span><span class="sxs-lookup"><span data-stu-id="f79d4-118">7</span></span>  <br/> |
|<span data-ttu-id="f79d4-119">#VALUE!</span><span class="sxs-lookup"><span data-stu-id="f79d4-119">#VALUE!</span></span>  <br/> |<span data-ttu-id="f79d4-120">**xlerrValue**</span><span class="sxs-lookup"><span data-stu-id="f79d4-120">**xlerrValue**</span></span> <br/> |<span data-ttu-id="f79d4-121">15</span><span class="sxs-lookup"><span data-stu-id="f79d4-121">15</span></span>  <br/> |
|<span data-ttu-id="f79d4-122">#REF!</span><span class="sxs-lookup"><span data-stu-id="f79d4-122">#REF!</span></span>  <br/> |<span data-ttu-id="f79d4-123">**xlerrRef**</span><span class="sxs-lookup"><span data-stu-id="f79d4-123">**xlerrRef**</span></span> <br/> |<span data-ttu-id="f79d4-124">23</span><span class="sxs-lookup"><span data-stu-id="f79d4-124">23</span></span>  <br/> |
|<span data-ttu-id="f79d4-125">#NAME?</span><span class="sxs-lookup"><span data-stu-id="f79d4-125">#NAME?</span></span>  <br/> |<span data-ttu-id="f79d4-126">**xlerrName**</span><span class="sxs-lookup"><span data-stu-id="f79d4-126">**xlerrName**</span></span> <br/> |<span data-ttu-id="f79d4-127">29</span><span class="sxs-lookup"><span data-stu-id="f79d4-127">29</span></span>  <br/> |
|<span data-ttu-id="f79d4-128">#NUM!</span><span class="sxs-lookup"><span data-stu-id="f79d4-128">#NUM!</span></span>  <br/> |<span data-ttu-id="f79d4-129">**xlerrNum**</span><span class="sxs-lookup"><span data-stu-id="f79d4-129">**xlerrNum**</span></span> <br/> |<span data-ttu-id="f79d4-130">36</span><span class="sxs-lookup"><span data-stu-id="f79d4-130">36</span></span>  <br/> |
|<span data-ttu-id="f79d4-131">#N/A</span><span class="sxs-lookup"><span data-stu-id="f79d4-131">#N/A</span></span>  <br/> |<span data-ttu-id="f79d4-132">**xlerrNA**</span><span class="sxs-lookup"><span data-stu-id="f79d4-132">**xlerrNA**</span></span> <br/> |<span data-ttu-id="f79d4-133">42</span><span class="sxs-lookup"><span data-stu-id="f79d4-133">42</span></span>  <br/> |
   
## <a name="return-value"></a><span data-ttu-id="f79d4-134">返回值</span><span class="sxs-lookup"><span data-stu-id="f79d4-134">Return value</span></span>

<span data-ttu-id="f79d4-135">返回一个**xltypeBool**包含的错误代码中传递。</span><span class="sxs-lookup"><span data-stu-id="f79d4-135">Returns an **xltypeBool** containing the error code passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="f79d4-136">示例</span><span class="sxs-lookup"><span data-stu-id="f79d4-136">Example</span></span>

<span data-ttu-id="f79d4-137">本示例使用**TempErr12**函数返回 #VALUE ！</span><span class="sxs-lookup"><span data-stu-id="f79d4-137">This example uses the **TempErr12** function to return a #VALUE!</span></span> <span data-ttu-id="f79d4-138">到 Excel 时出错。</span><span class="sxs-lookup"><span data-stu-id="f79d4-138">error to Excel.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f79d4-139">Framework 库函数**TempErr12**从内部缓冲区，通常被释放调用框架函数**Excel12f**时分配内存。</span><span class="sxs-lookup"><span data-stu-id="f79d4-139">The Framework library function **TempErr12** allocates memory from an internal buffer, which is normally freed when the Framework function **Excel12f** is called.</span></span> <span data-ttu-id="f79d4-140">如果没有**Excel12f**调用重复调用此示例函数，则将发生内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="f79d4-140">If this example function is called repeatedly without **Excel12f** being called, a memory leak occurs.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
LPXLOPER WINAPI TempErrExample(void)
{
    return TempErr12(xlerrValue);
}
```

## <a name="see-also"></a><span data-ttu-id="f79d4-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f79d4-141">See also</span></span>



[<span data-ttu-id="f79d4-142">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="f79d4-142">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

