---
title: xlSheetId
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlSheetId
keywords:
- xlsheetid 函数 [excel 2007]
localization_priority: Normal
ms.assetid: cb32059c-b899-49cf-8028-ff828998ab75
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: a2ca1bb478c5c985ad7032e30ed0cfe3aef31406
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428429"
---
# <a name="xlsheetid"></a><span data-ttu-id="29ae5-104">xlSheetId</span><span class="sxs-lookup"><span data-stu-id="29ae5-104">xlSheetId</span></span>

<span data-ttu-id="29ae5-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="29ae5-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="29ae5-106">查找已命名工作表的工作表 ID 以构建外部引用。</span><span class="sxs-lookup"><span data-stu-id="29ae5-106">Finds the sheet ID of a named sheet in order to construct external references.</span></span>
  
```cs
Excel12(xlSheetId, LPXLOPER12 pxRes, 1, LPXLOPER12 pxSheetName);
```

## <a name="parameters"></a><span data-ttu-id="29ae5-107">参数</span><span class="sxs-lookup"><span data-stu-id="29ae5-107">Parameters</span></span>

<span data-ttu-id="29ae5-108">_pxSheetName_ (**xltypeStr**) </span><span class="sxs-lookup"><span data-stu-id="29ae5-108">_pxSheetName_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="29ae5-109"> (可选) 。</span><span class="sxs-lookup"><span data-stu-id="29ae5-109">(Optional).</span></span> <span data-ttu-id="29ae5-110">要查找的书籍和工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="29ae5-110">The name of the book and sheet you want to find out about.</span></span> <span data-ttu-id="29ae5-111">如果省略 **，xlSheetId** 函数将返回活动工作表的工作表 (表) ID。</span><span class="sxs-lookup"><span data-stu-id="29ae5-111">If omitted, the **xlSheetId** function returns the sheet ID of the active (front) sheet.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="29ae5-112">返回值</span><span class="sxs-lookup"><span data-stu-id="29ae5-112">Return value</span></span>

<span data-ttu-id="29ae5-113">返回 _pxRes- \> val.mref.idSheet 中的工作表 ID。_</span><span class="sxs-lookup"><span data-stu-id="29ae5-113">Returns the sheet ID in  _pxRes-\>val.mref.idSheet_.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="29ae5-114">在此调用后  _，pxRes- \> val.mref.lpmref_ 数组指针设置为 NULL，因此无需调用 **xlFree** 来释放此类型通常包含的内存，尽管这样做完全安全。</span><span class="sxs-lookup"><span data-stu-id="29ae5-114">The  _pxRes-\>val.mref.lpmref_ array pointer is set to NULL after this call so that there is no need to call **xlFree** to release the memory that this type normally contains, although it is completely safe to do so.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="29ae5-115">备注</span><span class="sxs-lookup"><span data-stu-id="29ae5-115">Remarks</span></span>

<span data-ttu-id="29ae5-116">必须打开包含指定工作表的工作簿，以使用此函数。</span><span class="sxs-lookup"><span data-stu-id="29ae5-116">The workbook containing the specified sheet must be open to use this function.</span></span> <span data-ttu-id="29ae5-117">无法从 DLL 构造对未打开工作簿的引用。</span><span class="sxs-lookup"><span data-stu-id="29ae5-117">There is no way to construct a reference to an unopened workbook from a DLL.</span></span> <span data-ttu-id="29ae5-118">有关使用 **xlSheetId** 构造引用的详细信息，请参阅 memory [Management in Excel](memory-management-in-excel.md) for examples of **xltypeRef** construction。</span><span class="sxs-lookup"><span data-stu-id="29ae5-118">For more information about using **xlSheetId** to construct references, see [Memory Management in Excel](memory-management-in-excel.md) for examples of **xltypeRef** construction.</span></span> 
  
## <a name="example"></a><span data-ttu-id="29ae5-119">示例</span><span class="sxs-lookup"><span data-stu-id="29ae5-119">Example</span></span>

 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlSheetIdExample(void)
{       
   XLOPER12 xSheetName, xRes;
   xSheetName.xltype = xltypeStr;
   xSheetName.val.str = L"\022[BOOK1.XLSX]Sheet1";
   Excel12(xlSheetId, &xRes, 1, (LPXLOPER12)&xSheetName);
   Excel12f(xlcAlert, 0, 1, TempNum12(xRes.val.mref.idSheet));
   Excel12(xlFree, 0, 1, (LPXLOPER12)&xRes);
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="29ae5-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29ae5-120">See also</span></span>

- [<span data-ttu-id="29ae5-121">xlSheetNm</span><span class="sxs-lookup"><span data-stu-id="29ae5-121">xlSheetNm</span></span>](xlsheetnm.md)
- [<span data-ttu-id="29ae5-122">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="29ae5-122">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

