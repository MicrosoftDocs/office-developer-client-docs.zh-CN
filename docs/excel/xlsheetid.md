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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: a2ca1bb478c5c985ad7032e30ed0cfe3aef31406
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310302"
---
# <a name="xlsheetid"></a><span data-ttu-id="82116-104">xlSheetId</span><span class="sxs-lookup"><span data-stu-id="82116-104">xlSheetId</span></span>

<span data-ttu-id="82116-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="82116-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="82116-106">查找命名工作表的工作表 ID, 以便构造外部引用。</span><span class="sxs-lookup"><span data-stu-id="82116-106">Finds the sheet ID of a named sheet in order to construct external references.</span></span>
  
```cs
Excel12(xlSheetId, LPXLOPER12 pxRes, 1, LPXLOPER12 pxSheetName);
```

## <a name="parameters"></a><span data-ttu-id="82116-107">参数</span><span class="sxs-lookup"><span data-stu-id="82116-107">Parameters</span></span>

<span data-ttu-id="82116-108">_pxSheetName_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="82116-108">_pxSheetName_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="82116-109">(可选)。</span><span class="sxs-lookup"><span data-stu-id="82116-109">(Optional).</span></span> <span data-ttu-id="82116-110">要查找的简介册和工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="82116-110">The name of the book and sheet you want to find out about.</span></span> <span data-ttu-id="82116-111">如果省略, 则**xlSheetId**函数返回活动 (前) 工作表的工作表 ID。</span><span class="sxs-lookup"><span data-stu-id="82116-111">If omitted, the **xlSheetId** function returns the sheet ID of the active (front) sheet.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="82116-112">返回值</span><span class="sxs-lookup"><span data-stu-id="82116-112">Return value</span></span>

<span data-ttu-id="82116-113">返回_pxRes-\>mref_中的工作表 ID。</span><span class="sxs-lookup"><span data-stu-id="82116-113">Returns the sheet ID in  _pxRes-\>val.mref.idSheet_.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="82116-114">在此调用之后, _pxRes\>_ 数组指针将设置为 NULL, 这样就无需调用**xlFree**来释放该类型通常包含的内存, 尽管这样做是完全安全的。</span><span class="sxs-lookup"><span data-stu-id="82116-114">The  _pxRes-\>val.mref.lpmref_ array pointer is set to NULL after this call so that there is no need to call **xlFree** to release the memory that this type normally contains, although it is completely safe to do so.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="82116-115">注解</span><span class="sxs-lookup"><span data-stu-id="82116-115">Remarks</span></span>

<span data-ttu-id="82116-116">必须打开包含指定工作表的工作簿, 才能使用此函数。</span><span class="sxs-lookup"><span data-stu-id="82116-116">The workbook containing the specified sheet must be open to use this function.</span></span> <span data-ttu-id="82116-117">无法从 DLL 构造对未打开的工作簿的引用。</span><span class="sxs-lookup"><span data-stu-id="82116-117">There is no way to construct a reference to an unopened workbook from a DLL.</span></span> <span data-ttu-id="82116-118">有关使用**xlSheetId**构建引用的详细信息, 请参阅[Excel 中的内存管理](memory-management-in-excel.md), 了解**xltypeRef**构造的示例。</span><span class="sxs-lookup"><span data-stu-id="82116-118">For more information about using **xlSheetId** to construct references, see [Memory Management in Excel](memory-management-in-excel.md) for examples of **xltypeRef** construction.</span></span> 
  
## <a name="example"></a><span data-ttu-id="82116-119">示例</span><span class="sxs-lookup"><span data-stu-id="82116-119">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="82116-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82116-120">See also</span></span>

- [<span data-ttu-id="82116-121">xlSheetNm</span><span class="sxs-lookup"><span data-stu-id="82116-121">xlSheetNm</span></span>](xlsheetnm.md)
- [<span data-ttu-id="82116-122">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="82116-122">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

