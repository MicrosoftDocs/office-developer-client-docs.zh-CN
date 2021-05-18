---
title: TempActiveCell/TempActiveCell12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempActiveCell
- TempActiveCell12
keywords:
- tempactivecell12 函数 [excel 2007]，TempActiveCell 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: ac5a200d-32d5-4313-9a6d-d730032aaf10
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: f9bdb4cd9919d0e52654a3996ede99c4d1b35cc6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413190"
---
# <a name="tempactivecelltempactivecell12"></a><span data-ttu-id="fe918-104">TempActiveCell/TempActiveCell12</span><span class="sxs-lookup"><span data-stu-id="fe918-104">TempActiveCell/TempActiveCell12</span></span>

 <span data-ttu-id="fe918-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fe918-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="fe918-106">创建包含对活动工作表上单元格的外部引用的临时 /  **XLOPER XLOPER12** 的框架库函数。</span><span class="sxs-lookup"><span data-stu-id="fe918-106">Framework library functions that create a temporary **XLOPER**/ **XLOPER12** containing an external reference to a cell on the active sheet.</span></span> 
  
```cs
LPXLOPER TempActiveCell(WORD row, BYTE col);
LPXLOPER12 TempActiveCell12(RW row, COL co);
```

## <a name="parameters"></a><span data-ttu-id="fe918-107">参数</span><span class="sxs-lookup"><span data-stu-id="fe918-107">Parameters</span></span>

 <span data-ttu-id="fe918-108">_row_</span><span class="sxs-lookup"><span data-stu-id="fe918-108">_row_</span></span>
  
<span data-ttu-id="fe918-109">要引用的行。</span><span class="sxs-lookup"><span data-stu-id="fe918-109">The row to be referenced.</span></span> <span data-ttu-id="fe918-110">行参数从零开始，因此行 1 作为 0 传递。</span><span class="sxs-lookup"><span data-stu-id="fe918-110">Row arguments are zero-based so that row 1 is passed as 0.</span></span> <span data-ttu-id="fe918-111">在 Microsoft Office Excel 2003 及更早版本中，从 Excel 2007 开始在兼容模式下运行工作簿，最大值为 65，535 = 2^16 - 1，并且是 WORD 整数可以取的最大值。</span><span class="sxs-lookup"><span data-stu-id="fe918-111">In Microsoft Office Excel 2003 and earlier versions, and starting in Excel 2007 running a workbook in compatibility mode, the maximum value is 65,535 = 2^16 - 1 and is the maximum value that can be taken by a WORD integer.</span></span> <span data-ttu-id="fe918-112">从 2007 Excel工作簿开始，最大值为 1，048，575 = 2^20 - 1。</span><span class="sxs-lookup"><span data-stu-id="fe918-112">Starting in Excel 2007 running a workbook, the maximum value is 1,048,575 = 2^20 - 1.</span></span> <span data-ttu-id="fe918-113">RW 在 XLCALL.H 中定义为 32 位有符号整数。</span><span class="sxs-lookup"><span data-stu-id="fe918-113">RW is defined as a 32-bit signed integer in XLCALL.H.</span></span>
  
 <span data-ttu-id="fe918-114">_col_</span><span class="sxs-lookup"><span data-stu-id="fe918-114">_col_</span></span>
  
<span data-ttu-id="fe918-115">要引用的列。</span><span class="sxs-lookup"><span data-stu-id="fe918-115">The column to be referenced.</span></span> <span data-ttu-id="fe918-116">这是从零开始，以便列 A 作为 0 传递。</span><span class="sxs-lookup"><span data-stu-id="fe918-116">This is zero-based so that column A is passed as 0.</span></span> <span data-ttu-id="fe918-117">在 Excel 2003 及更早版本中，从 Excel 2007 开始，在兼容模式下运行工作簿时，最大值为 255 = 2^8 - 1，它是 BYTE 整数可以取的最大值。</span><span class="sxs-lookup"><span data-stu-id="fe918-117">In Excel 2003 and earlier versions, and starting in Excel 2007 running a workbook in compatibility mode, the maximum value is 255 = 2^8 - 1 and is the maximum value that can be taken by a BYTE integer.</span></span> <span data-ttu-id="fe918-118">从 2007 Excel工作簿开始，最大值为 16，383 = 2^14 - 1。</span><span class="sxs-lookup"><span data-stu-id="fe918-118">Starting in Excel 2007 running a workbook, the maximum value is 16,383 = 2^14 - 1.</span></span> <span data-ttu-id="fe918-119">COL 在 XLCALL.H 中定义为 32 位有符号整数。</span><span class="sxs-lookup"><span data-stu-id="fe918-119">COL is defined as a 32-bit signed integer in XLCALL.H.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="fe918-120">返回值</span><span class="sxs-lookup"><span data-stu-id="fe918-120">Return value</span></span>

<span data-ttu-id="fe918-121">返回对传入的单元格的 **xltypeRef** 外部引用。</span><span class="sxs-lookup"><span data-stu-id="fe918-121">Returns an **xltypeRef** external reference to the cell passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="fe918-122">示例</span><span class="sxs-lookup"><span data-stu-id="fe918-122">Example</span></span>

<span data-ttu-id="fe918-123">以下示例使用 **TempActiveCell12** 在活动工作表上显示 B94 的内容。</span><span class="sxs-lookup"><span data-stu-id="fe918-123">The following example uses **TempActiveCell12** to display the contents of B94 on the active sheet.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempActiveCellExample(void)
{
   Excel12f(xlcAlert, 0, 1, TempActiveCell12(93,1));
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="fe918-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe918-124">See also</span></span>



[<span data-ttu-id="fe918-125">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="fe918-125">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

