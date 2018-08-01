---
title: TempActiveColumn/TempActiveColumn12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempActiveColumn
- TempActiveColumn12
keywords:
- tempactivecolumn12 函数 [excel 2007，] TempActiveColumn 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 4b1f34c4-e7fa-4a0b-8fc5-c9d465ebb70c
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: ac3dbb0bb43527f790e6934d73bee30a33f8555f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773816"
---
# <a name="tempactivecolumntempactivecolumn12"></a><span data-ttu-id="5bca7-104">TempActiveColumn/TempActiveColumn12</span><span class="sxs-lookup"><span data-stu-id="5bca7-104">TempActiveColumn/TempActiveColumn12</span></span>

 <span data-ttu-id="5bca7-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5bca7-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="5bca7-106">创建临时**XLOPER**的框架库函数/ **XLOPER12**包含对整列在活动工作表上的外部引用。</span><span class="sxs-lookup"><span data-stu-id="5bca7-106">Framework library functions that create a temporary **XLOPER**/ **XLOPER12** containing an external reference to an entire column on the active sheet.</span></span> 
  
```cs
LPXLOPER TempActiveColumn(BYTE col);
LPXLOPER12 TempActiveColumn12(COL col);
```

## <a name="parameters"></a><span data-ttu-id="5bca7-107">参数</span><span class="sxs-lookup"><span data-stu-id="5bca7-107">Parameters</span></span>

 <span data-ttu-id="5bca7-108">_col_（**字节**）</span><span class="sxs-lookup"><span data-stu-id="5bca7-108">_col_ (**BYTE**)</span></span>
  
<span data-ttu-id="5bca7-109">要引用的列。</span><span class="sxs-lookup"><span data-stu-id="5bca7-109">The column to be referenced.</span></span> <span data-ttu-id="5bca7-110">这是从零开始的因此，列 A 传递为 0。</span><span class="sxs-lookup"><span data-stu-id="5bca7-110">This is zero-based so that column A is passed as 0.</span></span> <span data-ttu-id="5bca7-111">在 Microsoft Office Excel 2003 和早期版本，以及开始在兼容模式下运行的工作簿的 Excel 2007 中的最大值是 255 = 2 ^8-1，字节整数可以采取的最大值。</span><span class="sxs-lookup"><span data-stu-id="5bca7-111">In Microsoft Office Excel 2003 and earlier versions, and starting in Excel 2007 running a workbook in compatibility mode, the maximum value is 255 = 2^8 - 1 and is the maximum value that can be taken by a BYTE integer.</span></span> <span data-ttu-id="5bca7-112">启动运行工作簿的 Excel 2007 中的最大值是 16,383 = 2 ^14-1。</span><span class="sxs-lookup"><span data-stu-id="5bca7-112">Starting in Excel 2007 running a workbook, the maximum value is 16,383 = 2^14 - 1.</span></span> <span data-ttu-id="5bca7-113">COL 被定义为 XLCALL 中的 32 位有符号整数。H。</span><span class="sxs-lookup"><span data-stu-id="5bca7-113">COL is defined as a 32-bit signed integer in XLCALL.H.</span></span>
  
## <a name="return-value"></a><span data-ttu-id="5bca7-114">返回值</span><span class="sxs-lookup"><span data-stu-id="5bca7-114">Return value</span></span>

<span data-ttu-id="5bca7-115">返回对传入的列的**xltypeRef**外部引用。</span><span class="sxs-lookup"><span data-stu-id="5bca7-115">Returns an **xltypeRef** external reference to the column passed in.</span></span> 
  
## <a name="example"></a><span data-ttu-id="5bca7-116">示例</span><span class="sxs-lookup"><span data-stu-id="5bca7-116">Example</span></span>

<span data-ttu-id="5bca7-117">下面的示例使用**TempActiveColumn12**选择 B 整个列。</span><span class="sxs-lookup"><span data-stu-id="5bca7-117">The following example uses **TempActiveColumn12** to select the entire column B.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempActiveColumnExample(void)
{
    Excel12f(xlcSelect, 0, 1, TempActiveColumn12(1));
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="5bca7-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bca7-118">See also</span></span>



[<span data-ttu-id="5bca7-119">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="5bca7-119">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

