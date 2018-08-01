---
title: xlSheetNm
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlSheetNm
keywords:
- xlsheetnm 函数 [excel 2007]
localization_priority: Normal
ms.assetid: bcb16207-5499-4474-b006-51ccde1002d7
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 815565d886b1aea203f6b3b9774325d6b534abd2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773868"
---
# <a name="xlsheetnm"></a><span data-ttu-id="c8447-104">xlSheetNm</span><span class="sxs-lookup"><span data-stu-id="c8447-104">xlSheetNm</span></span>

<span data-ttu-id="c8447-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c8447-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="c8447-106">从包含内外部的引用，或者当前工作表的名称，如果传递内部参考其内部工作表 ID 返回工作表或宏表的名称。</span><span class="sxs-lookup"><span data-stu-id="c8447-106">Returns the name of a worksheet or macro sheet from its internal sheet ID contained within an external reference, or the name of the current sheet if passed an internal reference.</span></span>
  
```cs
Excel12(xlSheetNm, LPXLOPER12 pxRes, 1, LPXLOPER12 pxExtref);
```

## <a name="parameters"></a><span data-ttu-id="c8447-107">参数</span><span class="sxs-lookup"><span data-stu-id="c8447-107">Parameters</span></span>

<span data-ttu-id="c8447-108">_pxExtref_（**xltypeRef**或**xltypeSRef**）</span><span class="sxs-lookup"><span data-stu-id="c8447-108">_pxExtref_ (**xltypeRef** or **xltypeSRef**)</span></span>
  
<span data-ttu-id="c8447-109">对工作表名称所需的引用。</span><span class="sxs-lookup"><span data-stu-id="c8447-109">A reference to the sheet whose name you want.</span></span>
  
<span data-ttu-id="c8447-110">如果将传递外部引用 (**xltypeRef**) 它只需包含的工作表的 ID。</span><span class="sxs-lookup"><span data-stu-id="c8447-110">If you are passing an external reference (**xltypeRef**) it need only contain the ID of the sheet.</span></span> <span data-ttu-id="c8447-111">介绍在工作表单元格的数据结构将被忽略，无需提供。</span><span class="sxs-lookup"><span data-stu-id="c8447-111">The data structures that describe the cells on the worksheet are ignored and do not need to be provided.</span></span> <span data-ttu-id="c8447-112">如果 ID 设置为零，则**xlSheetNm**返回当前工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="c8447-112">If the ID is set to zero, **xlSheetNm** returns the name of the current sheet.</span></span> 
  
<span data-ttu-id="c8447-113">如果将传递内部引用 (**xltypeSef**)， **xlSheetNm**返回当前工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="c8447-113">If you are passing an internal reference (**xltypeSef**), **xlSheetNm** returns the name of the current sheet.</span></span> 
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c8447-114">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="c8447-114">Property value/Return value</span></span>

<span data-ttu-id="c8447-115">返回窗体中的工作表 (**xltypeStr**) 的名称`[Book1]Sheet1`。</span><span class="sxs-lookup"><span data-stu-id="c8447-115">Returns the name of the sheet (**xltypeStr**) in the form  `[Book1]Sheet1`.</span></span>
  
## <a name="example"></a><span data-ttu-id="c8447-116">示例</span><span class="sxs-lookup"><span data-stu-id="c8447-116">Example</span></span>

<span data-ttu-id="c8447-117">下面的示例显示从中调用该函数的工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="c8447-117">The following example displays the name of the sheet from which the function was called.</span></span> <span data-ttu-id="c8447-118">仅当从宏表执行 XLM 命令宏时调用，该函数可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="c8447-118">The function works correctly only if called from a macro sheet while executing an XLM command macro.</span></span> <span data-ttu-id="c8447-119">这是因为它调用**xlcAlert**，其中仅命令可执行的操作，则需要从工作表而不是对话框中，菜单上或**xlfCaller**返回的引用的顺序中的命令栏调用。</span><span class="sxs-lookup"><span data-stu-id="c8447-119">This is because it calls **xlcAlert**, which only commands can do, and it needs to be called from a sheet rather than a dialog box, menu, or command bar in order for **xlfCaller** to return a reference.</span></span> 
  
`\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlSheetNmExample(void)
{
   XLOPER12 xRes, xSheetName;
   Excel12(xlfCaller, &xRes, 0);
   Excel12(xlSheetNm, &xSheetName, 1, (LPXLOPER12)&xRes);
   Excel12(xlcAlert, 0, 1, (LPXLOPER12)&xSheetName);
   Excel12(xlFree, 0, 1, (LPXLOPER12)&xSheetName);
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="c8447-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8447-120">See also</span></span>

- [<span data-ttu-id="c8447-121">xlSheetId</span><span class="sxs-lookup"><span data-stu-id="c8447-121">xlSheetId</span></span>](xlsheetid.md)
- [<span data-ttu-id="c8447-122">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="c8447-122">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

