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
- tempactivecell12 函数 [excel 2007], TempActiveCell 函数 [excel 2007]
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
# <a name="tempactivecelltempactivecell12"></a><span data-ttu-id="cc8e6-104">TempActiveCell/TempActiveCell12</span><span class="sxs-lookup"><span data-stu-id="cc8e6-104">TempActiveCell/TempActiveCell12</span></span>

 <span data-ttu-id="cc8e6-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cc8e6-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="cc8e6-106">框架库函数, 用于创建一个临时的**XLOPER**/ **XLOPER12** , 其中包含对活动工作表上的单元格的外部引用。</span><span class="sxs-lookup"><span data-stu-id="cc8e6-106">Framework library functions that create a temporary **XLOPER**/ **XLOPER12** containing an external reference to a cell on the active sheet.</span></span> 
  
```cs
LPXLOPER TempActiveCell(WORD row, BYTE col);
LPXLOPER12 TempActiveCell12(RW row, COL co);
```

## <a name="parameters"></a><span data-ttu-id="cc8e6-107">参数</span><span class="sxs-lookup"><span data-stu-id="cc8e6-107">Parameters</span></span>

 <span data-ttu-id="cc8e6-108">_行_</span><span class="sxs-lookup"><span data-stu-id="cc8e6-108">_row_</span></span>
  
<span data-ttu-id="cc8e6-109">要引用的行。</span><span class="sxs-lookup"><span data-stu-id="cc8e6-109">The row to be referenced.</span></span> <span data-ttu-id="cc8e6-110">行参数从零开始, 以便将行1作为0传递。</span><span class="sxs-lookup"><span data-stu-id="cc8e6-110">Row arguments are zero-based so that row 1 is passed as 0.</span></span> <span data-ttu-id="cc8e6-111">在 Microsoft Office Excel 2003 及更早版本中, 在兼容模式下运行工作簿的 excel 2007 中, 最大值为 65535 = 2 ^ 16-1, 是单词整数可以采用的最大值。</span><span class="sxs-lookup"><span data-stu-id="cc8e6-111">In Microsoft Office Excel 2003 and earlier versions, and starting in Excel 2007 running a workbook in compatibility mode, the maximum value is 65,535 = 2^16 - 1 and is the maximum value that can be taken by a WORD integer.</span></span> <span data-ttu-id="cc8e6-112">从运行工作簿的 Excel 2007 开始, 最大值为 1048575 = 2 ^ 20-1。</span><span class="sxs-lookup"><span data-stu-id="cc8e6-112">Starting in Excel 2007 running a workbook, the maximum value is 1,048,575 = 2^20 - 1.</span></span> <span data-ttu-id="cc8e6-113">RW 在 xlcall.h 中定义为32位有符号整数。水平.</span><span class="sxs-lookup"><span data-stu-id="cc8e6-113">RW is defined as a 32-bit signed integer in XLCALL.H.</span></span>
  
 <span data-ttu-id="cc8e6-114">_均值_</span><span class="sxs-lookup"><span data-stu-id="cc8e6-114">_col_</span></span>
  
<span data-ttu-id="cc8e6-115">要引用的列。</span><span class="sxs-lookup"><span data-stu-id="cc8e6-115">The column to be referenced.</span></span> <span data-ttu-id="cc8e6-116">这是从零开始的, 以便将列 A 作为0传递。</span><span class="sxs-lookup"><span data-stu-id="cc8e6-116">This is zero-based so that column A is passed as 0.</span></span> <span data-ttu-id="cc8e6-117">在 excel 2003 和早期版本中, 并且在兼容模式下运行工作簿的 excel 2007 中, 最大值为 255 = 2 ^ 8-1, 是字节整数可以采用的最大值。</span><span class="sxs-lookup"><span data-stu-id="cc8e6-117">In Excel 2003 and earlier versions, and starting in Excel 2007 running a workbook in compatibility mode, the maximum value is 255 = 2^8 - 1 and is the maximum value that can be taken by a BYTE integer.</span></span> <span data-ttu-id="cc8e6-118">从运行工作簿的 Excel 2007 开始, 最大值为 16383 = 2 ^ 14-1。</span><span class="sxs-lookup"><span data-stu-id="cc8e6-118">Starting in Excel 2007 running a workbook, the maximum value is 16,383 = 2^14 - 1.</span></span> <span data-ttu-id="cc8e6-119">COL 在 xlcall.h 中定义为32位有符号整数。水平.</span><span class="sxs-lookup"><span data-stu-id="cc8e6-119">COL is defined as a 32-bit signed integer in XLCALL.H.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="cc8e6-120">返回值</span><span class="sxs-lookup"><span data-stu-id="cc8e6-120">Return value</span></span>

<span data-ttu-id="cc8e6-121">返回对传入的单元格的**xltypeRef**外部引用。</span><span class="sxs-lookup"><span data-stu-id="cc8e6-121">Returns an **xltypeRef** external reference to the cell passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="cc8e6-122">示例</span><span class="sxs-lookup"><span data-stu-id="cc8e6-122">Example</span></span>

<span data-ttu-id="cc8e6-123">下面的示例使用**TempActiveCell12**显示活动工作表上的 B94 的内容。</span><span class="sxs-lookup"><span data-stu-id="cc8e6-123">The following example uses **TempActiveCell12** to display the contents of B94 on the active sheet.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempActiveCellExample(void)
{
   Excel12f(xlcAlert, 0, 1, TempActiveCell12(93,1));
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="cc8e6-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc8e6-124">See also</span></span>



[<span data-ttu-id="cc8e6-125">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="cc8e6-125">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

