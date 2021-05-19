---
title: TempActiveRef/TempActiveRef12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempActiveRef
- TempActiveRef12
keywords:
- tempactiveref 函数 [excel 2007]，TempActiveRef12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 7c69d15a-294b-4545-983b-720409001e0e
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 58feee8f43e0f90f710c9e4387684dcb6d173a7b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415542"
---
# <a name="tempactivereftempactiveref12"></a><span data-ttu-id="7ade3-104">TempActiveRef/TempActiveRef12</span><span class="sxs-lookup"><span data-stu-id="7ade3-104">TempActiveRef/TempActiveRef12</span></span>

 <span data-ttu-id="7ade3-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7ade3-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="7ade3-106">创建临时 **XLOPER** /  **XLOPER12** 的框架库函数，其中包含对活动工作表上单元格矩形块的外部引用。</span><span class="sxs-lookup"><span data-stu-id="7ade3-106">Framework library function that creates a temporary **XLOPER**/ **XLOPER12** containing an external reference to rectangular block of cells on the active sheet.</span></span> 
  
```cs
LPXLOPER TempActiveRef(WORD rwFirst, WORD rwLast, BYTE colFirst, BYTE colLast);
LPXLOPER12 TempActiveRef12(ROW rwFirst, ROW rwLast, COL colFirst, COL colLast);
```

## <a name="parameters"></a><span data-ttu-id="7ade3-107">参数</span><span class="sxs-lookup"><span data-stu-id="7ade3-107">Parameters</span></span>

 <span data-ttu-id="7ade3-108">_rwFirst_</span><span class="sxs-lookup"><span data-stu-id="7ade3-108">_rwFirst_</span></span>
  
<span data-ttu-id="7ade3-109">引用的起始行。</span><span class="sxs-lookup"><span data-stu-id="7ade3-109">The starting row of the reference.</span></span>
  
 <span data-ttu-id="7ade3-110">_rwLast_</span><span class="sxs-lookup"><span data-stu-id="7ade3-110">_rwLast_</span></span>
  
<span data-ttu-id="7ade3-111">引用的结束行。</span><span class="sxs-lookup"><span data-stu-id="7ade3-111">The ending row of the reference.</span></span>
  
<span data-ttu-id="7ade3-112">行参数从零开始，因此行 1 作为 0 传递。</span><span class="sxs-lookup"><span data-stu-id="7ade3-112">Row arguments are zero-based so that row 1 is passed as 0.</span></span> <span data-ttu-id="7ade3-113">在 Microsoft Office Excel 2003 及更早版本中，从 Excel 2007 开始在兼容模式下运行工作簿，最大值为 65，535 = 2^16 - 1，并且是 WORD 整数可以取的最大值。</span><span class="sxs-lookup"><span data-stu-id="7ade3-113">In Microsoft Office Excel 2003 and earlier versions, and starting in Excel 2007 running a workbook in compatibility mode, the maximum value is 65,535 = 2^16 - 1 and is the maximum value that can be taken by a WORD integer.</span></span> <span data-ttu-id="7ade3-114">从 2007 Excel工作簿开始，最大值为 1，048，575 = 2^20 - 1。</span><span class="sxs-lookup"><span data-stu-id="7ade3-114">Starting in Excel 2007 running a workbook, the maximum value is 1,048,575 = 2^20 - 1.</span></span> <span data-ttu-id="7ade3-115">RW 在 XLCALL.H 中定义为 32 位有符号整数。</span><span class="sxs-lookup"><span data-stu-id="7ade3-115">RW is defined as a 32-bit signed integer in XLCALL.H.</span></span>
  
 <span data-ttu-id="7ade3-116">_colFirst_</span><span class="sxs-lookup"><span data-stu-id="7ade3-116">_colFirst_</span></span>
  
<span data-ttu-id="7ade3-117">引用的起始列号。</span><span class="sxs-lookup"><span data-stu-id="7ade3-117">The starting column number of the reference.</span></span>
  
 <span data-ttu-id="7ade3-118">_colLast_</span><span class="sxs-lookup"><span data-stu-id="7ade3-118">_colLast_</span></span>
  
<span data-ttu-id="7ade3-119">引用的结束列号。</span><span class="sxs-lookup"><span data-stu-id="7ade3-119">The ending column number of the reference.</span></span>
  
<span data-ttu-id="7ade3-120">列参数从零开始，以便列 A 作为 0 传递。</span><span class="sxs-lookup"><span data-stu-id="7ade3-120">Column arguments are zero-based so that column A is passed as 0.</span></span> <span data-ttu-id="7ade3-121">在 Excel 2003 及更早版本中，从 Excel 2007 开始，在兼容模式下运行工作簿时，最大值为 255 = 2^8 - 1，它是 BYTE 整数可以取的最大值。</span><span class="sxs-lookup"><span data-stu-id="7ade3-121">In Excel 2003 and earlier versions, and starting in Excel 2007 running a workbook in compatibility mode, the maximum value is 255 = 2^8 - 1 and is the maximum value that can be taken by a BYTE integer.</span></span> <span data-ttu-id="7ade3-122">从 2007 Excel工作簿开始，最大值为 16，383 = 2^14 - 1。</span><span class="sxs-lookup"><span data-stu-id="7ade3-122">Starting in Excel 2007 running a workbook, the maximum value is 16,383 = 2^14 - 1.</span></span> <span data-ttu-id="7ade3-123">COL 在 XLCALL.H 中定义为 32 位有符号整数。</span><span class="sxs-lookup"><span data-stu-id="7ade3-123">COL is defined as a 32-bit signed integer in XLCALL.H.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="7ade3-124">返回值</span><span class="sxs-lookup"><span data-stu-id="7ade3-124">Return value</span></span>

<span data-ttu-id="7ade3-125">返回对传入的单元格矩形块的 **xltypeRef** 外部引用。</span><span class="sxs-lookup"><span data-stu-id="7ade3-125">Returns an **xltypeRef** external reference to rectangular block of cells passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="7ade3-126">示例</span><span class="sxs-lookup"><span data-stu-id="7ade3-126">Example</span></span>

<span data-ttu-id="7ade3-127">此示例使用 **TempActiveRef12** 函数选择单元格 A105：C110。</span><span class="sxs-lookup"><span data-stu-id="7ade3-127">This example uses the **TempActiveRef12** function to select cells A105:C110.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempActiveRefExample(void)
{
    Excel12f(xlcSelect, 0, 1, TempActiveRef12(104, 109, 0, 2));
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="7ade3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ade3-128">See also</span></span>



[<span data-ttu-id="7ade3-129">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="7ade3-129">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

