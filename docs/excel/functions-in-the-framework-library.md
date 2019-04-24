---
title: 框架库中的函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- 框架库函数 [excel 2007], 函数 [excel 2007], 框架库
localization_priority: Normal
ms.assetid: 7d9a13fd-9a4c-423e-bb08-4a5be57c7905
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 4eeb9e5db09592e98e9afb763efaa6be18eb2f7e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304051"
---
# <a name="functions-in-the-framework-library"></a><span data-ttu-id="ab50a-104">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="ab50a-104">Functions in the Framework Library</span></span>

<span data-ttu-id="ab50a-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ab50a-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="ab50a-106">创建框架库旨在帮助简化编写 xll。</span><span class="sxs-lookup"><span data-stu-id="ab50a-106">The Framework Library was created to help make writing XLLs easier.</span></span> <span data-ttu-id="ab50a-107">它包括用于管理**XLOPER**/ **XLOPER12**内存的简单函数、创建临时**XLOPER**/ **XLOPER12**、可靠地调用 Microsoft Excel 回调函数 (**Excel4**、 **Excel4v**、\* \* Excel12 \* *、* \* Excel12v \* \*), 并在附加的终端上打印调试字符串。</span><span class="sxs-lookup"><span data-stu-id="ab50a-107">It includes simple functions for managing **XLOPER**/ **XLOPER12** memory, creating temporary **XLOPER**/ **XLOPER12**, robustly calling the Microsoft Excel callback functions (**Excel4**, **Excel4v**, \*\* Excel12 \*\*, \*\* Excel12v \*\*) and printing debugging strings on an attached terminal.</span></span>
  
<span data-ttu-id="ab50a-108">此库中包含的函数有助于简化如下所示的一段代码。</span><span class="sxs-lookup"><span data-stu-id="ab50a-108">The functions included in this library help simplify a piece of code that looks like the following.</span></span>
  
```cs
XLOPER12 xMissing, xBool;
xMissing.xltype = xltypeMissing;
xBool.xltype = xltypeBool;
xBool.val.xbool = 0;
Excel12(xlcDisplay, 0, 2, (LPXLOPER12) &xMissing, (LPXLOPER12) &xBool);
```

<span data-ttu-id="ab50a-109">简化的代码如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="ab50a-109">The simplified code looks like the following example.</span></span>
  
```cs
Excel12f(xlcDisplay, 0, 2, TempMissing12(), TempBool12(0));
```

<span data-ttu-id="ab50a-110">框架库中包含以下函数:</span><span class="sxs-lookup"><span data-stu-id="ab50a-110">The following functions are included in the Framework library:</span></span>
  
||
|:-----|
|[<span data-ttu-id="ab50a-111">debugPrintf</span><span class="sxs-lookup"><span data-stu-id="ab50a-111">debugPrintf</span></span>](debugprintf.md) <br/> |
|<span data-ttu-id="ab50a-112">**GetTempMemory**</span><span class="sxs-lookup"><span data-stu-id="ab50a-112">**GetTempMemory**</span></span> <br/> |
|<span data-ttu-id="ab50a-113">**FreeAllTempMemory**</span><span class="sxs-lookup"><span data-stu-id="ab50a-113">**FreeAllTempMemory**</span></span> <br/> |
|[<span data-ttu-id="ab50a-114">InitFramework</span><span class="sxs-lookup"><span data-stu-id="ab50a-114">InitFramework</span></span>](initframework.md) <br/> |
|[<span data-ttu-id="ab50a-115">QuitFramework</span><span class="sxs-lookup"><span data-stu-id="ab50a-115">QuitFramework</span></span>](quitframework.md) <br/> |
   
|<span data-ttu-id="ab50a-116">**用于 XLOPERs 的函数**</span><span class="sxs-lookup"><span data-stu-id="ab50a-116">**Functions Used with XLOPERs**</span></span>|<span data-ttu-id="ab50a-117">**用于 XLOPER12s 的函数**</span><span class="sxs-lookup"><span data-stu-id="ab50a-117">**Functions Used with XLOPER12s**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ab50a-118">Excel</span><span class="sxs-lookup"><span data-stu-id="ab50a-118">Excel</span></span>](excel-excel12f.md) <br/> |[<span data-ttu-id="ab50a-119">Excel12f</span><span class="sxs-lookup"><span data-stu-id="ab50a-119">Excel12f</span></span>](excel-excel12f.md) <br/> |
|[<span data-ttu-id="ab50a-120">TempNum</span><span class="sxs-lookup"><span data-stu-id="ab50a-120">TempNum</span></span>](tempnum-tempnum12.md) <br/> |[<span data-ttu-id="ab50a-121">TempNum12</span><span class="sxs-lookup"><span data-stu-id="ab50a-121">TempNum12</span></span>](tempnum-tempnum12.md) <br/> |
|[<span data-ttu-id="ab50a-122">TempStr</span><span class="sxs-lookup"><span data-stu-id="ab50a-122">TempStr</span></span>](tempstr.md) <br/> |[<span data-ttu-id="ab50a-123">TempStr12</span><span class="sxs-lookup"><span data-stu-id="ab50a-123">TempStr12</span></span>](tempstrconst-tempstr12.md) <br/> |
|[<span data-ttu-id="ab50a-124">TempStrConst</span><span class="sxs-lookup"><span data-stu-id="ab50a-124">TempStrConst</span></span>](tempstrconst-tempstr12.md) <br/> |[<span data-ttu-id="ab50a-125">TempStr12Const</span><span class="sxs-lookup"><span data-stu-id="ab50a-125">TempStr12Const</span></span>](tempstrconst-tempstr12.md) <br/> |
|[<span data-ttu-id="ab50a-126">TempBool</span><span class="sxs-lookup"><span data-stu-id="ab50a-126">TempBool</span></span>](tempbool-tempbool12.md) <br/> |[<span data-ttu-id="ab50a-127">TempBool12</span><span class="sxs-lookup"><span data-stu-id="ab50a-127">TempBool12</span></span>](tempbool-tempbool12.md) <br/> |
|[<span data-ttu-id="ab50a-128">TempInt</span><span class="sxs-lookup"><span data-stu-id="ab50a-128">TempInt</span></span>](tempint-tempint12.md) <br/> |[<span data-ttu-id="ab50a-129">TempInt12</span><span class="sxs-lookup"><span data-stu-id="ab50a-129">TempInt12</span></span>](tempint-tempint12.md) <br/> |
|[<span data-ttu-id="ab50a-130">TempErr</span><span class="sxs-lookup"><span data-stu-id="ab50a-130">TempErr</span></span>](temperr-temperr12.md) <br/> |[<span data-ttu-id="ab50a-131">TempErr12</span><span class="sxs-lookup"><span data-stu-id="ab50a-131">TempErr12</span></span>](temperr-temperr12.md) <br/> |
|[<span data-ttu-id="ab50a-132">TempActiveRef</span><span class="sxs-lookup"><span data-stu-id="ab50a-132">TempActiveRef</span></span>](tempactiveref-tempactiveref12.md) <br/> |[<span data-ttu-id="ab50a-133">TempActiveRef12</span><span class="sxs-lookup"><span data-stu-id="ab50a-133">TempActiveRef12</span></span>](tempactiveref-tempactiveref12.md) <br/> |
|[<span data-ttu-id="ab50a-134">TempActiveCell</span><span class="sxs-lookup"><span data-stu-id="ab50a-134">TempActiveCell</span></span>](tempactivecell-tempactivecell12.md) <br/> |[<span data-ttu-id="ab50a-135">TempActiveCell12</span><span class="sxs-lookup"><span data-stu-id="ab50a-135">TempActiveCell12</span></span>](tempactivecell-tempactivecell12.md) <br/> |
|[<span data-ttu-id="ab50a-136">TempActiveRow</span><span class="sxs-lookup"><span data-stu-id="ab50a-136">TempActiveRow</span></span>](tempactiverow-tempactiverow12.md) <br/> |[<span data-ttu-id="ab50a-137">TempActiveRow12</span><span class="sxs-lookup"><span data-stu-id="ab50a-137">TempActiveRow12</span></span>](tempactiverow-tempactiverow12.md) <br/> |
|[<span data-ttu-id="ab50a-138">TempActiveColumn</span><span class="sxs-lookup"><span data-stu-id="ab50a-138">TempActiveColumn</span></span>](tempactivecolumn-tempactivecolumn12.md) <br/> |[<span data-ttu-id="ab50a-139">TempActiveColumn12</span><span class="sxs-lookup"><span data-stu-id="ab50a-139">TempActiveColumn12</span></span>](tempactivecolumn-tempactivecolumn12.md) <br/> |
|[<span data-ttu-id="ab50a-140">TempMissing</span><span class="sxs-lookup"><span data-stu-id="ab50a-140">TempMissing</span></span>](tempmissing-tempmissing12.md) <br/> |[<span data-ttu-id="ab50a-141">TempMissing12</span><span class="sxs-lookup"><span data-stu-id="ab50a-141">TempMissing12</span></span>](tempmissing-tempmissing12.md) <br/> |
   
<span data-ttu-id="ab50a-142">使用这些函数可缩短写入 DLL 或 XLL 所需的时间量。</span><span class="sxs-lookup"><span data-stu-id="ab50a-142">Use of these functions shortens the amount of time required to write a DLL or XLL.</span></span> <span data-ttu-id="ab50a-143">从示例应用程序开始开发一般也缩短了开发时间。</span><span class="sxs-lookup"><span data-stu-id="ab50a-143">Starting development from the sample application GENERIC also shortens development time.</span></span> <span data-ttu-id="ab50a-144">使用 GENERIC。C 作为模板来帮助设置 XLL 框架, 然后将现有代码替换为您自己的代码。</span><span class="sxs-lookup"><span data-stu-id="ab50a-144">Use GENERIC.C as a template to help set up the framework of an XLL, and then replace the existing code with your own.</span></span>
  
<span data-ttu-id="ab50a-145">临时**XLOPER**/ **XLOPER12**函数使用由框架库管理的本地堆中的内存创建**XLOPER**/ **XLOPER12**值。</span><span class="sxs-lookup"><span data-stu-id="ab50a-145">The temporary **XLOPER**/ **XLOPER12** functions create **XLOPER**/ **XLOPER12** values by using memory from a local heap managed by the Framework library.</span></span> <span data-ttu-id="ab50a-146">在调用**FreeAllTempMemory**函数或任一**Excel**或**Excel12f**函数之前, **XLOPER**/ **XLOPER12**值始终有效。</span><span class="sxs-lookup"><span data-stu-id="ab50a-146">The **XLOPER**/ **XLOPER12** values remain valid until you call the **FreeAllTempMemory** function or either of the **Excel** or **Excel12f** functions.</span></span> <span data-ttu-id="ab50a-147">( **Excel**和**Excel12f**函数在返回之前释放所有临时内存。)</span><span class="sxs-lookup"><span data-stu-id="ab50a-147">(The **Excel** and **Excel12f** functions free all temporary memory before returning.)</span></span> 
  
<span data-ttu-id="ab50a-148">若要使用框架库函数, 必须包含 FRAMEWRK。H 文件, 并添加 FRAMEWRK。C 或 FRMWRK32。LIB 文件到代码项目。</span><span class="sxs-lookup"><span data-stu-id="ab50a-148">To use the Framework library functions, you must include the FRAMEWRK.H file in your C code and add the FRAMEWRK.C or FRMWRK32.LIB files to your code project.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ab50a-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab50a-149">See also</span></span>

- [<span data-ttu-id="ab50a-150">Excel XLL SDK API Function Reference</span><span class="sxs-lookup"><span data-stu-id="ab50a-150">Excel XLL SDK API Function Reference</span></span>](excel-xll-sdk-api-function-reference.md)

