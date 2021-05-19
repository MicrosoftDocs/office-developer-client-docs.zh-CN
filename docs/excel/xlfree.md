---
title: xlFree
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlFree
keywords:
- xlfree 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 8ce2eef2-0138-495d-b6cb-bbb727a3cda4
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: de1c75ad65acacd44644e9bfb111b30abd0a578e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424712"
---
# <a name="xlfree"></a><span data-ttu-id="d4889-104">xlFree</span><span class="sxs-lookup"><span data-stu-id="d4889-104">xlFree</span></span>

 <span data-ttu-id="d4889-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d4889-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="d4889-106">用于在对 /  [Excel4、Excel4v、Excel12](excel4-excel12.md)或 [Excel12v](excel4v-excel12v.md)的调用中Microsoft Excel **XLOPER XLOPER12** [](excel4-excel12.md)创建返回值时，释放由 Microsoft Excel 分配的内存资源。 [](excel4v-excel12v.md)</span><span class="sxs-lookup"><span data-stu-id="d4889-106">Used to free memory resources allocated by Microsoft Excel when creating the return value **XLOPER**/ **XLOPER12** in a call to [Excel4](excel4-excel12.md), [Excel4v](excel4v-excel12v.md), [Excel12](excel4-excel12.md), or [Excel12v](excel4v-excel12v.md).</span></span> <span data-ttu-id="d4889-107">**xlFree** 函数释放辅助内存，将指针重置为 **NULL，** 但不销毁 **XLOPER** /  **XLOPER12** 的其他部分。</span><span class="sxs-lookup"><span data-stu-id="d4889-107">The **xlFree** function frees the auxiliary memory and resets the pointer to **NULL** but does not destroy other parts of the **XLOPER**/ **XLOPER12**.</span></span>
  
```cs
Excel4(xlFree, 0, n, LPXLOPER px_1, ..., LPXLOPER px_n);
Excel12(xlFree, 0, n, LPXLOPER12 px_1, ..., LPXLOPER12 px_n);
```

## <a name="parameters"></a><span data-ttu-id="d4889-108">参数</span><span class="sxs-lookup"><span data-stu-id="d4889-108">Parameters</span></span>

 <span data-ttu-id="d4889-109">_px_1、...、px_n_</span><span class="sxs-lookup"><span data-stu-id="d4889-109">_px_1, ..., px_n_</span></span>
  
<span data-ttu-id="d4889-110">要释放的 **一** 个或多个 /  **XLOPER XLOPER12。**</span><span class="sxs-lookup"><span data-stu-id="d4889-110">One or more **XLOPER**/ **XLOPER12** s to be freed.</span></span> <span data-ttu-id="d4889-111">在Excel 2003 版本中，可以传递的最大指针数为 30。</span><span class="sxs-lookup"><span data-stu-id="d4889-111">In Excel versions up to 2003, the maximum number of pointers that can be passed is 30.</span></span> <span data-ttu-id="d4889-112">从 2007 Excel，增加到 255。</span><span class="sxs-lookup"><span data-stu-id="d4889-112">Starting in Excel 2007, this is increased to 255.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d4889-113">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="d4889-113">Property value/Return value</span></span>

<span data-ttu-id="d4889-114">此函数不返回值。</span><span class="sxs-lookup"><span data-stu-id="d4889-114">This function does not return a value.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d4889-115">备注</span><span class="sxs-lookup"><span data-stu-id="d4889-115">Remarks</span></span>

<span data-ttu-id="d4889-116">您必须释放从 **Excel4 或** **Excel4v** 获取的作为返回值获取的 **每个 XLOPER，** 以及从 Excel12 或 **Excel12v** 获取的作为返回值获取的每一 **个 XLOPER（** 如果它们是以下类型之一 **）：xltypeStr、xltypeMulti** 或 **xltypeRef**。  </span><span class="sxs-lookup"><span data-stu-id="d4889-116">You must free every **XLOPER** that you get as a return value from **Excel4** or **Excel4v** and every **XLOPER12** that you get as a return value from **Excel12** or **Excel12v** if they are one of the following types: **xltypeStr**, **xltypeMulti**, or **xltypeRef**.</span></span> <span data-ttu-id="d4889-117">释放其他类型的内存始终安全，即使它们不使用辅助内存，只要从 **Excel4** 或 **Excel12** 获得它们。</span><span class="sxs-lookup"><span data-stu-id="d4889-117">It is always safe to free other types even if they do not use auxiliary memory, as long as you got them from **Excel4** or **Excel12**.</span></span>
  
<span data-ttu-id="d4889-118">如果返回到 Excel指向 **仍** 包含要释放的 Excel 分配的内存的 /  **XLOPER XLOPER12** 的指针，则必须设置 **xlbitXLFree** 以确保 Excel 释放内存。</span><span class="sxs-lookup"><span data-stu-id="d4889-118">Where you are returning to Excel a pointer to an **XLOPER**/ **XLOPER12** that still contains Excel-allocated memory to be freed, you must set the **xlbitXLFree** to ensure Excel releases the memory.</span></span> 
  
## <a name="example"></a><span data-ttu-id="d4889-119">示例</span><span class="sxs-lookup"><span data-stu-id="d4889-119">Example</span></span>

<span data-ttu-id="d4889-120">此示例调用 **GET。WORKSPACE (1)** 返回当前作为字符串Excel运行平台。</span><span class="sxs-lookup"><span data-stu-id="d4889-120">This example calls **GET.WORKSPACE(1)** to return the platform on which Excel is currently running as a string.</span></span> <span data-ttu-id="d4889-121">代码将返回的字符串复制到缓冲区中，供以后使用。</span><span class="sxs-lookup"><span data-stu-id="d4889-121">The code copies this returned string into a buffer for later use.</span></span> <span data-ttu-id="d4889-122">该代码将缓冲区重新放入 **XLOPER12** 中，供以后与 Excel 函数一同使用。</span><span class="sxs-lookup"><span data-stu-id="d4889-122">The code places the buffer back into the **XLOPER12** for later use with the Excel function.</span></span> <span data-ttu-id="d4889-123">最后，代码在警报框中显示字符串。</span><span class="sxs-lookup"><span data-stu-id="d4889-123">Finally, the code displays the string in an alert box.</span></span> 
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlFreeExample(void)
{
   XLOPER12 xRes, xInt;
   XCHAR buffer[cchMaxStz];
   int i,len;
   // Create an XLOPER12 for the argument to Getworkspace.
   xInt.xltype = xltypeInt;
   xInt.val.w = 1;
   // Call GetWorkspace.
   Excel12f(xlfGetWorkspace, &xRes, 1, (LPXLOPER12)&xInt);
   
   // Get the length of the returned string
   len = (int)xRes.val.str[0];
   //Take into account 1st char, which contains the length
   //and the null terminator. Truncate if necessary to fit
   //buffer.
   if (len > cchMaxStz - 2)
      len = cchMaxStz - 2;
   // Copy to buffer.
   for(i = 1; i <= len; i++)
      buffer[i] = xRes.val.str[i];
   // Null terminate, Not necessary but a good idea.
   buffer[len] = '\0';
   buffer[0] = len;
   // Free the string returned from Excel.
   Excel12f(xlFree, 0, 1, &xRes);
   // Create a new string XLOPER12 for the alert.
   xRes.xltype = xltypeStr;
   xRes.val.str = buffer;
   // Show the alert.
   Excel12f(xlcAlert, 0, 1, (LPXLOPER12)&xRes);
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="d4889-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4889-124">See also</span></span>

- [<span data-ttu-id="d4889-125">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="d4889-125">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

