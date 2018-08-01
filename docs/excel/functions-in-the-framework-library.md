---
title: 框架库中的函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
keywords:
- '[excel 2007] framework 库函数，函数 [Excel 2007，] Framework 库'
localization_priority: Normal
ms.assetid: 7d9a13fd-9a4c-423e-bb08-4a5be57c7905
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 1d3878e376f95be3b277f1bb1a59545eb0a631ac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773762"
---
# <a name="functions-in-the-framework-library"></a><span data-ttu-id="a6175-104">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="a6175-104">Functions in the Framework Library</span></span>

<span data-ttu-id="a6175-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a6175-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="a6175-106">创建框架库是为了帮助确保编写 Xll 更轻松。</span><span class="sxs-lookup"><span data-stu-id="a6175-106">The Framework Library was created to help make writing XLLs easier.</span></span> <span data-ttu-id="a6175-107">它包括用于管理**XLOPER**简单函数/ **XLOPER12**内存，创建临时**XLOPER**/ **XLOPER12**，始终能够调用 Microsoft Excel 回调函数 （**Excel4**、 **Excel4v*** * Excel12 * *，* * Excel12v * *) 和打印调试上附加终端的字符串。</span><span class="sxs-lookup"><span data-stu-id="a6175-107">It includes simple functions for managing **XLOPER**/ **XLOPER12** memory, creating temporary **XLOPER**/ **XLOPER12**, robustly calling the Microsoft Excel callback functions (**Excel4**, **Excel4v**, ** Excel12 **, ** Excel12v **) and printing debugging strings on an attached terminal.</span></span>
  
<span data-ttu-id="a6175-108">在此库中包含的功能有助于简化与以下内容类似的代码段。</span><span class="sxs-lookup"><span data-stu-id="a6175-108">The functions included in this library help simplify a piece of code that looks like the following.</span></span>
  
```cs
XLOPER12 xMissing, xBool;
xMissing.xltype = xltypeMissing;
xBool.xltype = xltypeBool;
xBool.val.xbool = 0;
Excel12(xlcDisplay, 0, 2, (LPXLOPER12) &xMissing, (LPXLOPER12) &xBool);
```

<span data-ttu-id="a6175-109">简化的代码类似于下面的示例。</span><span class="sxs-lookup"><span data-stu-id="a6175-109">The simplified code looks like the following example.</span></span>
  
```cs
Excel12f(xlcDisplay, 0, 2, TempMissing12(), TempBool12(0));
```

<span data-ttu-id="a6175-110">Framework 库中包含以下功能：</span><span class="sxs-lookup"><span data-stu-id="a6175-110">The following functions are included in the Framework library:</span></span>
  
||
|:-----|
|[<span data-ttu-id="a6175-111">debugPrintf</span><span class="sxs-lookup"><span data-stu-id="a6175-111">debugPrintf</span></span>](debugprintf.md) <br/> |
|<span data-ttu-id="a6175-112">**GetTempMemory**</span><span class="sxs-lookup"><span data-stu-id="a6175-112">**GetTempMemory**</span></span> <br/> |
|<span data-ttu-id="a6175-113">**FreeAllTempMemory**</span><span class="sxs-lookup"><span data-stu-id="a6175-113">**FreeAllTempMemory**</span></span> <br/> |
|[<span data-ttu-id="a6175-114">InitFramework</span><span class="sxs-lookup"><span data-stu-id="a6175-114">InitFramework</span></span>](initframework.md) <br/> |
|[<span data-ttu-id="a6175-115">QuitFramework</span><span class="sxs-lookup"><span data-stu-id="a6175-115">QuitFramework</span></span>](quitframework.md) <br/> |
   
|<span data-ttu-id="a6175-116">**用于 XLOPERs 函数**</span><span class="sxs-lookup"><span data-stu-id="a6175-116">**Functions Used with XLOPERs**</span></span>|<span data-ttu-id="a6175-117">**用于 XLOPER12s 函数**</span><span class="sxs-lookup"><span data-stu-id="a6175-117">**Functions Used with XLOPER12s**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a6175-118">Excel</span><span class="sxs-lookup"><span data-stu-id="a6175-118">Excel</span></span>](excel-excel12f.md) <br/> |[<span data-ttu-id="a6175-119">Excel12f</span><span class="sxs-lookup"><span data-stu-id="a6175-119">Excel12f</span></span>](excel-excel12f.md) <br/> |
|[<span data-ttu-id="a6175-120">TempNum</span><span class="sxs-lookup"><span data-stu-id="a6175-120">TempNum</span></span>](tempnum-tempnum12.md) <br/> |[<span data-ttu-id="a6175-121">TempNum12</span><span class="sxs-lookup"><span data-stu-id="a6175-121">TempNum12</span></span>](tempnum-tempnum12.md) <br/> |
|[<span data-ttu-id="a6175-122">TempStr</span><span class="sxs-lookup"><span data-stu-id="a6175-122">TempStr</span></span>](tempstr.md) <br/> |[<span data-ttu-id="a6175-123">TempStr12</span><span class="sxs-lookup"><span data-stu-id="a6175-123">TempStr12</span></span>](tempstrconst-tempstr12.md) <br/> |
|[<span data-ttu-id="a6175-124">TempStrConst</span><span class="sxs-lookup"><span data-stu-id="a6175-124">TempStrConst</span></span>](tempstrconst-tempstr12.md) <br/> |[<span data-ttu-id="a6175-125">TempStr12Const</span><span class="sxs-lookup"><span data-stu-id="a6175-125">TempStr12Const</span></span>](tempstrconst-tempstr12.md) <br/> |
|[<span data-ttu-id="a6175-126">TempBool</span><span class="sxs-lookup"><span data-stu-id="a6175-126">TempBool</span></span>](tempbool-tempbool12.md) <br/> |[<span data-ttu-id="a6175-127">TempBool12</span><span class="sxs-lookup"><span data-stu-id="a6175-127">TempBool12</span></span>](tempbool-tempbool12.md) <br/> |
|[<span data-ttu-id="a6175-128">TempInt</span><span class="sxs-lookup"><span data-stu-id="a6175-128">TempInt</span></span>](tempint-tempint12.md) <br/> |[<span data-ttu-id="a6175-129">TempInt12</span><span class="sxs-lookup"><span data-stu-id="a6175-129">TempInt12</span></span>](tempint-tempint12.md) <br/> |
|[<span data-ttu-id="a6175-130">TempErr</span><span class="sxs-lookup"><span data-stu-id="a6175-130">TempErr</span></span>](temperr-temperr12.md) <br/> |[<span data-ttu-id="a6175-131">TempErr12</span><span class="sxs-lookup"><span data-stu-id="a6175-131">TempErr12</span></span>](temperr-temperr12.md) <br/> |
|[<span data-ttu-id="a6175-132">TempActiveRef</span><span class="sxs-lookup"><span data-stu-id="a6175-132">TempActiveRef</span></span>](tempactiveref-tempactiveref12.md) <br/> |[<span data-ttu-id="a6175-133">TempActiveRef12</span><span class="sxs-lookup"><span data-stu-id="a6175-133">TempActiveRef12</span></span>](tempactiveref-tempactiveref12.md) <br/> |
|[<span data-ttu-id="a6175-134">TempActiveCell</span><span class="sxs-lookup"><span data-stu-id="a6175-134">TempActiveCell</span></span>](tempactivecell-tempactivecell12.md) <br/> |[<span data-ttu-id="a6175-135">TempActiveCell12</span><span class="sxs-lookup"><span data-stu-id="a6175-135">TempActiveCell12</span></span>](tempactivecell-tempactivecell12.md) <br/> |
|[<span data-ttu-id="a6175-136">TempActiveRow</span><span class="sxs-lookup"><span data-stu-id="a6175-136">TempActiveRow</span></span>](tempactiverow-tempactiverow12.md) <br/> |[<span data-ttu-id="a6175-137">TempActiveRow12</span><span class="sxs-lookup"><span data-stu-id="a6175-137">TempActiveRow12</span></span>](tempactiverow-tempactiverow12.md) <br/> |
|[<span data-ttu-id="a6175-138">TempActiveColumn</span><span class="sxs-lookup"><span data-stu-id="a6175-138">TempActiveColumn</span></span>](tempactivecolumn-tempactivecolumn12.md) <br/> |[<span data-ttu-id="a6175-139">TempActiveColumn12</span><span class="sxs-lookup"><span data-stu-id="a6175-139">TempActiveColumn12</span></span>](tempactivecolumn-tempactivecolumn12.md) <br/> |
|[<span data-ttu-id="a6175-140">TempMissing</span><span class="sxs-lookup"><span data-stu-id="a6175-140">TempMissing</span></span>](tempmissing-tempmissing12.md) <br/> |[<span data-ttu-id="a6175-141">TempMissing12</span><span class="sxs-lookup"><span data-stu-id="a6175-141">TempMissing12</span></span>](tempmissing-tempmissing12.md) <br/> |
   
<span data-ttu-id="a6175-142">使用这些函数缩短编写 DLL 或 XLL 所需的时间量。</span><span class="sxs-lookup"><span data-stu-id="a6175-142">Use of these functions shortens the amount of time required to write a DLL or XLL.</span></span> <span data-ttu-id="a6175-143">示例应用程序从开始开发泛型还缩短了开发时间。</span><span class="sxs-lookup"><span data-stu-id="a6175-143">Starting development from the sample application GENERIC also shortens development time.</span></span> <span data-ttu-id="a6175-144">使用通用。C 作为模板帮助设置 XLL 的框架，然后用您自己中替换现有代码。</span><span class="sxs-lookup"><span data-stu-id="a6175-144">Use GENERIC.C as a template to help set up the framework of an XLL, and then replace the existing code with your own.</span></span>
  
<span data-ttu-id="a6175-145">临时**XLOPER**/ **XLOPER12**函数创建**XLOPER**/ **XLOPER12**值使用的内存从本地堆由 Framework 库。</span><span class="sxs-lookup"><span data-stu-id="a6175-145">The temporary **XLOPER**/ **XLOPER12** functions create **XLOPER**/ **XLOPER12** values by using memory from a local heap managed by the Framework library.</span></span> <span data-ttu-id="a6175-146">**XLOPER**/ **XLOPER12**值保持有效，直到您调用**FreeAllTempMemory**函数或任一**Excel**或**Excel12f**函数。</span><span class="sxs-lookup"><span data-stu-id="a6175-146">The **XLOPER**/ **XLOPER12** values remain valid until you call the **FreeAllTempMemory** function or either of the **Excel** or **Excel12f** functions.</span></span> <span data-ttu-id="a6175-147">（的**Excel**和**Excel12f**函数释放所有临时内存返回之前。）</span><span class="sxs-lookup"><span data-stu-id="a6175-147">(The **Excel** and **Excel12f** functions free all temporary memory before returning.)</span></span> 
  
<span data-ttu-id="a6175-148">若要使用的框架库函数，您必须包括 FRAMEWRK。H C 代码文件，并添加 FRAMEWRK。C 或 FRMWRK32。LIB 文件复制到您的代码项目。</span><span class="sxs-lookup"><span data-stu-id="a6175-148">To use the Framework library functions, you must include the FRAMEWRK.H file in your C code and add the FRAMEWRK.C or FRMWRK32.LIB files to your code project.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a6175-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6175-149">See also</span></span>

- [<span data-ttu-id="a6175-150">Excel XLL SDK API Function Reference</span><span class="sxs-lookup"><span data-stu-id="a6175-150">Excel XLL SDK API Function Reference</span></span>](excel-xll-sdk-api-function-reference.md)

