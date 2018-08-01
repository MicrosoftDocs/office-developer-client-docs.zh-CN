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
- tempactivecell12 函数 [excel 2007，] TempActiveCell 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: ac5a200d-32d5-4313-9a6d-d730032aaf10
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 8ad409a76195d67fa61e7991ce6527c40e0a3265
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773810"
---
# <a name="tempactivecelltempactivecell12"></a><span data-ttu-id="70dfa-104">TempActiveCell/TempActiveCell12</span><span class="sxs-lookup"><span data-stu-id="70dfa-104">TempActiveCell/TempActiveCell12</span></span>

 <span data-ttu-id="70dfa-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="70dfa-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="70dfa-106">创建临时**XLOPER**的框架库函数/ **XLOPER12**包含外部活动工作表的单元格引用。</span><span class="sxs-lookup"><span data-stu-id="70dfa-106">Framework library functions that create a temporary **XLOPER**/ **XLOPER12** containing an external reference to a cell on the active sheet.</span></span> 
  
```cs
LPXLOPER TempActiveCell(WORD row, BYTE col);
LPXLOPER12 TempActiveCell12(RW row, COL co);
```

## <a name="parameters"></a><span data-ttu-id="70dfa-107">参数</span><span class="sxs-lookup"><span data-stu-id="70dfa-107">Parameters</span></span>

 <span data-ttu-id="70dfa-108">_row_</span><span class="sxs-lookup"><span data-stu-id="70dfa-108">_row_</span></span>
  
<span data-ttu-id="70dfa-109">要引用的行。</span><span class="sxs-lookup"><span data-stu-id="70dfa-109">The row to be referenced.</span></span> <span data-ttu-id="70dfa-110">行参数是从零开始的所以第 1 行传递为 0。</span><span class="sxs-lookup"><span data-stu-id="70dfa-110">Row arguments are zero-based so that row 1 is passed as 0.</span></span> <span data-ttu-id="70dfa-111">在 Microsoft Office Excel 2003 和早期版本，以及开始在兼容模式下运行的工作簿的 Excel 2007 中的最大值是 65535 = 2 ^16-1，WORD 整数可以采取的最大值。</span><span class="sxs-lookup"><span data-stu-id="70dfa-111">In Microsoft Office Excel 2003 and earlier versions, and starting in Excel 2007 running a workbook in compatibility mode, the maximum value is 65,535 = 2^16 - 1 and is the maximum value that can be taken by a WORD integer.</span></span> <span data-ttu-id="70dfa-112">启动运行工作簿的 Excel 2007 中的最大值是 1048575 = 2 ^20-1。</span><span class="sxs-lookup"><span data-stu-id="70dfa-112">Starting in Excel 2007 running a workbook, the maximum value is 1,048,575 = 2^20 - 1.</span></span> <span data-ttu-id="70dfa-113">RW 被定义为 XLCALL 中的 32 位有符号整数。H。</span><span class="sxs-lookup"><span data-stu-id="70dfa-113">RW is defined as a 32-bit signed integer in XLCALL.H.</span></span>
  
 <span data-ttu-id="70dfa-114">_col_</span><span class="sxs-lookup"><span data-stu-id="70dfa-114">_col_</span></span>
  
<span data-ttu-id="70dfa-115">要引用的列。</span><span class="sxs-lookup"><span data-stu-id="70dfa-115">The column to be referenced.</span></span> <span data-ttu-id="70dfa-116">这是从零开始的因此，列 A 传递为 0。</span><span class="sxs-lookup"><span data-stu-id="70dfa-116">This is zero-based so that column A is passed as 0.</span></span> <span data-ttu-id="70dfa-117">在 Excel 2003 和早期版本，以及开始在兼容模式下运行的工作簿的 Excel 2007 中的最大值是 255 = 2 ^8-1，字节整数可以采取的最大值。</span><span class="sxs-lookup"><span data-stu-id="70dfa-117">In Excel 2003 and earlier versions, and starting in Excel 2007 running a workbook in compatibility mode, the maximum value is 255 = 2^8 - 1 and is the maximum value that can be taken by a BYTE integer.</span></span> <span data-ttu-id="70dfa-118">启动运行工作簿的 Excel 2007 中的最大值是 16,383 = 2 ^14-1。</span><span class="sxs-lookup"><span data-stu-id="70dfa-118">Starting in Excel 2007 running a workbook, the maximum value is 16,383 = 2^14 - 1.</span></span> <span data-ttu-id="70dfa-119">COL 被定义为 XLCALL 中的 32 位有符号整数。H。</span><span class="sxs-lookup"><span data-stu-id="70dfa-119">COL is defined as a 32-bit signed integer in XLCALL.H.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="70dfa-120">返回值</span><span class="sxs-lookup"><span data-stu-id="70dfa-120">Return value</span></span>

<span data-ttu-id="70dfa-121">返回对传入的单元格的**xltypeRef**外部引用。</span><span class="sxs-lookup"><span data-stu-id="70dfa-121">Returns an **xltypeRef** external reference to the cell passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="70dfa-122">示例</span><span class="sxs-lookup"><span data-stu-id="70dfa-122">Example</span></span>

<span data-ttu-id="70dfa-123">下面的示例使用**TempActiveCell12**活动工作表中显示的 B94 内容。</span><span class="sxs-lookup"><span data-stu-id="70dfa-123">The following example uses **TempActiveCell12** to display the contents of B94 on the active sheet.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempActiveCellExample(void)
{
   Excel12f(xlcAlert, 0, 1, TempActiveCell12(93,1));
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="70dfa-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70dfa-124">See also</span></span>



[<span data-ttu-id="70dfa-125">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="70dfa-125">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

