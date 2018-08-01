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
ms.openlocfilehash: e4e184d4e456ffe26292fe31b1b41463834216f9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773858"
---
# <a name="xlsheetid"></a><span data-ttu-id="39350-104">xlSheetId</span><span class="sxs-lookup"><span data-stu-id="39350-104">xlSheetId</span></span>

<span data-ttu-id="39350-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="39350-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="39350-106">若要构建外部引用查找命名工作表的工作表 ID。</span><span class="sxs-lookup"><span data-stu-id="39350-106">Finds the sheet ID of a named sheet in order to construct external references.</span></span>
  
```cs
Excel12(xlSheetId, LPXLOPER12 pxRes, 1, LPXLOPER12 pxSheetName);
```

## <a name="parameters"></a><span data-ttu-id="39350-107">参数</span><span class="sxs-lookup"><span data-stu-id="39350-107">Parameters</span></span>

<span data-ttu-id="39350-108">_pxSheetName_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="39350-108">_pxSheetName_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="39350-109">（可选）。</span><span class="sxs-lookup"><span data-stu-id="39350-109">(Optional).</span></span> <span data-ttu-id="39350-110">要了解有关簿和工作表的名称。</span><span class="sxs-lookup"><span data-stu-id="39350-110">The name of the book and sheet you want to find out about.</span></span> <span data-ttu-id="39350-111">如果省略，则**xlSheetId**函数将返回活动 （前端） 工作表的工作表 ID。</span><span class="sxs-lookup"><span data-stu-id="39350-111">If omitted, the **xlSheetId** function returns the sheet ID of the active (front) sheet.</span></span> 
  
## <a name="return-value"></a><span data-ttu-id="39350-112">返回值</span><span class="sxs-lookup"><span data-stu-id="39350-112">Return value</span></span>

<span data-ttu-id="39350-113">返回中的工作表 ID _pxRes-\>val.mref.idSheet_。</span><span class="sxs-lookup"><span data-stu-id="39350-113">Returns the sheet ID in  _pxRes-\>val.mref.idSheet_.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="39350-114">_PxRes-\>val.mref.lpmref_数组指针设置为 NULL 此呼叫后，以便不需要调用**xlFree**释放内存中通常包含此类型，尽管完全可以安全地这样做。</span><span class="sxs-lookup"><span data-stu-id="39350-114">The  _pxRes-\>val.mref.lpmref_ array pointer is set to NULL after this call so that there is no need to call **xlFree** to release the memory that this type normally contains, although it is completely safe to do so.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="39350-115">说明</span><span class="sxs-lookup"><span data-stu-id="39350-115">Remarks</span></span>

<span data-ttu-id="39350-116">包含指定的工作表的工作簿必须打开要使用此函数。</span><span class="sxs-lookup"><span data-stu-id="39350-116">The workbook containing the specified sheet must be open to use this function.</span></span> <span data-ttu-id="39350-117">没有方法来构造向未打开工作簿从 DLL 的引用。</span><span class="sxs-lookup"><span data-stu-id="39350-117">There is no way to construct a reference to an unopened workbook from a DLL.</span></span> <span data-ttu-id="39350-118">有关使用**xlSheetId**构造引用的详细信息，请参阅[在 Excel 中进行内存管理](memory-management-in-excel.md) **xltypeRef**构造的示例。</span><span class="sxs-lookup"><span data-stu-id="39350-118">For more information about using **xlSheetId** to construct references, see [Memory Management in Excel](memory-management-in-excel.md) for examples of **xltypeRef** construction.</span></span> 
  
## <a name="example"></a><span data-ttu-id="39350-119">示例</span><span class="sxs-lookup"><span data-stu-id="39350-119">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="39350-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39350-120">See also</span></span>

- [<span data-ttu-id="39350-121">xlSheetNm</span><span class="sxs-lookup"><span data-stu-id="39350-121">xlSheetNm</span></span>](xlsheetnm.md)
- [<span data-ttu-id="39350-122">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="39350-122">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

