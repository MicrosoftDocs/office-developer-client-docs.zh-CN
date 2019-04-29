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
# <a name="xlfree"></a><span data-ttu-id="60a6f-104">xlFree</span><span class="sxs-lookup"><span data-stu-id="60a6f-104">xlFree</span></span>

 <span data-ttu-id="60a6f-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="60a6f-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="60a6f-106">用于在[Excel4](excel4-excel12.md)、 [Excel4v](excel4v-excel12v.md)、 [Excel12](excel4-excel12.md)或[Excel12v](excel4v-excel12v.md)的调用中创建返回值**XLOPER**/ **XLOPER12**时, 释放 Microsoft Excel 分配的内存资源。</span><span class="sxs-lookup"><span data-stu-id="60a6f-106">Used to free memory resources allocated by Microsoft Excel when creating the return value **XLOPER**/ **XLOPER12** in a call to [Excel4](excel4-excel12.md), [Excel4v](excel4v-excel12v.md), [Excel12](excel4-excel12.md), or [Excel12v](excel4v-excel12v.md).</span></span> <span data-ttu-id="60a6f-107">**xlFree**函数释放辅助内存, 并将指针重置为**NULL** , 但不会销毁**XLOPER**/ **XLOPER12**的其他部分。</span><span class="sxs-lookup"><span data-stu-id="60a6f-107">The **xlFree** function frees the auxiliary memory and resets the pointer to **NULL** but does not destroy other parts of the **XLOPER**/ **XLOPER12**.</span></span>
  
```cs
Excel4(xlFree, 0, n, LPXLOPER px_1, ..., LPXLOPER px_n);
Excel12(xlFree, 0, n, LPXLOPER12 px_1, ..., LPXLOPER12 px_n);
```

## <a name="parameters"></a><span data-ttu-id="60a6f-108">参数</span><span class="sxs-lookup"><span data-stu-id="60a6f-108">Parameters</span></span>

 <span data-ttu-id="60a6f-109">_px_1, ..., px_n_</span><span class="sxs-lookup"><span data-stu-id="60a6f-109">_px_1, ..., px_n_</span></span>
  
<span data-ttu-id="60a6f-110">一个或多个要释放的**XLOPER**/ **XLOPER12**s。</span><span class="sxs-lookup"><span data-stu-id="60a6f-110">One or more **XLOPER**/ **XLOPER12**s to be freed.</span></span> <span data-ttu-id="60a6f-111">在 Excel 版本中, 最多为2003个, 可以传递的最大指针数为30个。</span><span class="sxs-lookup"><span data-stu-id="60a6f-111">In Excel versions up to 2003, the maximum number of pointers that can be passed is 30.</span></span> <span data-ttu-id="60a6f-112">从 Excel 2007 开始, 这会增加到255。</span><span class="sxs-lookup"><span data-stu-id="60a6f-112">Starting in Excel 2007, this is increased to 255.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="60a6f-113">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="60a6f-113">Property value/Return value</span></span>

<span data-ttu-id="60a6f-114">此函数不返回值。</span><span class="sxs-lookup"><span data-stu-id="60a6f-114">This function does not return a value.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="60a6f-115">说明</span><span class="sxs-lookup"><span data-stu-id="60a6f-115">Remarks</span></span>

<span data-ttu-id="60a6f-116">您必须释放作为返回值从**Excel4**或**Excel4v**中获取的每个**XLOPER** , 以及从**Excel12**或**Excel12v**获取为返回值的每个**XLOPER12** , 如果它们是以下类型之一: **xltypeStr**、 **xltypeMulti**或**xltypeRef**。</span><span class="sxs-lookup"><span data-stu-id="60a6f-116">You must free every **XLOPER** that you get as a return value from **Excel4** or **Excel4v** and every **XLOPER12** that you get as a return value from **Excel12** or **Excel12v** if they are one of the following types: **xltypeStr**, **xltypeMulti**, or **xltypeRef**.</span></span> <span data-ttu-id="60a6f-117">即使您从**Excel4**或**Excel12**中获取了这些类型, 也始终可以安全地释放其他类型, 即使它们不使用辅助内存也是如此。</span><span class="sxs-lookup"><span data-stu-id="60a6f-117">It is always safe to free other types even if they do not use auxiliary memory, as long as you got them from **Excel4** or **Excel12**.</span></span>
  
<span data-ttu-id="60a6f-118">若要返回到 excel 的指针指向的**XLOPER**/ **XLOPER12**仍包含要释放的 Excel 分配内存, 则必须设置**xlbitXLFree**以确保 excel 释放内存。</span><span class="sxs-lookup"><span data-stu-id="60a6f-118">Where you are returning to Excel a pointer to an **XLOPER**/ **XLOPER12** that still contains Excel-allocated memory to be freed, you must set the **xlbitXLFree** to ensure Excel releases the memory.</span></span> 
  
## <a name="example"></a><span data-ttu-id="60a6f-119">示例</span><span class="sxs-lookup"><span data-stu-id="60a6f-119">Example</span></span>

<span data-ttu-id="60a6f-120">此示例调用**GET。工作区 (1)** 以返回 Excel 当前以字符串形式运行的平台。</span><span class="sxs-lookup"><span data-stu-id="60a6f-120">This example calls **GET.WORKSPACE(1)** to return the platform on which Excel is currently running as a string.</span></span> <span data-ttu-id="60a6f-121">代码将返回的字符串复制到缓冲区中, 以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="60a6f-121">The code copies this returned string into a buffer for later use.</span></span> <span data-ttu-id="60a6f-122">该代码将缓冲区放回**XLOPER12**中, 以供以后用于 Excel 函数。</span><span class="sxs-lookup"><span data-stu-id="60a6f-122">The code places the buffer back into the **XLOPER12** for later use with the Excel function.</span></span> <span data-ttu-id="60a6f-123">最后, 代码在警告框中显示字符串。</span><span class="sxs-lookup"><span data-stu-id="60a6f-123">Finally, the code displays the string in an alert box.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="60a6f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60a6f-124">See also</span></span>

- [<span data-ttu-id="60a6f-125">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="60a6f-125">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

