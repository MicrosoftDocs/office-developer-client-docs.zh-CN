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
- tempactiveref 函数 [excel 2007，] TempActiveRef12 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 7c69d15a-294b-4545-983b-720409001e0e
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 5c2e82dcaf9bf562048b5d2582ece1bd262b47eb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773813"
---
# <a name="tempactivereftempactiveref12"></a><span data-ttu-id="f3c42-104">TempActiveRef/TempActiveRef12</span><span class="sxs-lookup"><span data-stu-id="f3c42-104">TempActiveRef/TempActiveRef12</span></span>

 <span data-ttu-id="f3c42-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f3c42-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="f3c42-106">创建临时**XLOPER**的框架库函数/ **XLOPER12**包含对活动工作表上单元格的矩形块的外部引用。</span><span class="sxs-lookup"><span data-stu-id="f3c42-106">Framework library function that creates a temporary **XLOPER**/ **XLOPER12** containing an external reference to rectangular block of cells on the active sheet.</span></span> 
  
```cs
LPXLOPER TempActiveRef(WORD rwFirst, WORD rwLast, BYTE colFirst, BYTE colLast);
LPXLOPER12 TempActiveRef12(ROW rwFirst, ROW rwLast, COL colFirst, COL colLast);
```

## <a name="parameters"></a><span data-ttu-id="f3c42-107">参数</span><span class="sxs-lookup"><span data-stu-id="f3c42-107">Parameters</span></span>

 <span data-ttu-id="f3c42-108">_rwFirst_</span><span class="sxs-lookup"><span data-stu-id="f3c42-108">_rwFirst_</span></span>
  
<span data-ttu-id="f3c42-109">起始行的引用。</span><span class="sxs-lookup"><span data-stu-id="f3c42-109">The starting row of the reference.</span></span>
  
 <span data-ttu-id="f3c42-110">_rwLast_</span><span class="sxs-lookup"><span data-stu-id="f3c42-110">_rwLast_</span></span>
  
<span data-ttu-id="f3c42-111">引用的结束行。</span><span class="sxs-lookup"><span data-stu-id="f3c42-111">The ending row of the reference.</span></span>
  
<span data-ttu-id="f3c42-112">行参数是从零开始的所以第 1 行传递为 0。</span><span class="sxs-lookup"><span data-stu-id="f3c42-112">Row arguments are zero-based so that row 1 is passed as 0.</span></span> <span data-ttu-id="f3c42-113">在 Microsoft Office Excel 2003 和早期版本，以及开始在兼容模式下运行的工作簿的 Excel 2007 中的最大值是 65535 = 2 ^16-1，WORD 整数可以采取的最大值。</span><span class="sxs-lookup"><span data-stu-id="f3c42-113">In Microsoft Office Excel 2003 and earlier versions, and starting in Excel 2007 running a workbook in compatibility mode, the maximum value is 65,535 = 2^16 - 1 and is the maximum value that can be taken by a WORD integer.</span></span> <span data-ttu-id="f3c42-114">启动运行工作簿的 Excel 2007 中的最大值是 1048575 = 2 ^20-1。</span><span class="sxs-lookup"><span data-stu-id="f3c42-114">Starting in Excel 2007 running a workbook, the maximum value is 1,048,575 = 2^20 - 1.</span></span> <span data-ttu-id="f3c42-115">RW 被定义为 XLCALL 中的 32 位有符号整数。H。</span><span class="sxs-lookup"><span data-stu-id="f3c42-115">RW is defined as a 32-bit signed integer in XLCALL.H.</span></span>
  
 <span data-ttu-id="f3c42-116">_colFirst_</span><span class="sxs-lookup"><span data-stu-id="f3c42-116">_colFirst_</span></span>
  
<span data-ttu-id="f3c42-117">参考的起始列号。</span><span class="sxs-lookup"><span data-stu-id="f3c42-117">The starting column number of the reference.</span></span>
  
 <span data-ttu-id="f3c42-118">_colLast_</span><span class="sxs-lookup"><span data-stu-id="f3c42-118">_colLast_</span></span>
  
<span data-ttu-id="f3c42-119">参考的结束的列号。</span><span class="sxs-lookup"><span data-stu-id="f3c42-119">The ending column number of the reference.</span></span>
  
<span data-ttu-id="f3c42-120">列参数是从零开始的所以该列 A 传递为 0。</span><span class="sxs-lookup"><span data-stu-id="f3c42-120">Column arguments are zero-based so that column A is passed as 0.</span></span> <span data-ttu-id="f3c42-121">在 Excel 2003 和早期版本，以及开始在兼容模式下运行的工作簿的 Excel 2007 中的最大值是 255 = 2 ^8-1，字节整数可以采取的最大值。</span><span class="sxs-lookup"><span data-stu-id="f3c42-121">In Excel 2003 and earlier versions, and starting in Excel 2007 running a workbook in compatibility mode, the maximum value is 255 = 2^8 - 1 and is the maximum value that can be taken by a BYTE integer.</span></span> <span data-ttu-id="f3c42-122">启动运行工作簿的 Excel 2007 中的最大值是 16,383 = 2 ^14-1。</span><span class="sxs-lookup"><span data-stu-id="f3c42-122">Starting in Excel 2007 running a workbook, the maximum value is 16,383 = 2^14 - 1.</span></span> <span data-ttu-id="f3c42-123">COL 被定义为 XLCALL 中的 32 位有符号整数。H。</span><span class="sxs-lookup"><span data-stu-id="f3c42-123">COL is defined as a 32-bit signed integer in XLCALL.H.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="f3c42-124">返回值</span><span class="sxs-lookup"><span data-stu-id="f3c42-124">Return value</span></span>

<span data-ttu-id="f3c42-125">返回对传入的单元格的矩形块**xltypeRef**外部引用。</span><span class="sxs-lookup"><span data-stu-id="f3c42-125">Returns an **xltypeRef** external reference to rectangular block of cells passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="f3c42-126">示例</span><span class="sxs-lookup"><span data-stu-id="f3c42-126">Example</span></span>

<span data-ttu-id="f3c42-127">本示例使用**TempActiveRef12**函数选择单元格 A105:C110。</span><span class="sxs-lookup"><span data-stu-id="f3c42-127">This example uses the **TempActiveRef12** function to select cells A105:C110.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempActiveRefExample(void)
{
    Excel12f(xlcSelect, 0, 1, TempActiveRef12(104, 109, 0, 2));
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="f3c42-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3c42-128">See also</span></span>



[<span data-ttu-id="f3c42-129">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="f3c42-129">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

