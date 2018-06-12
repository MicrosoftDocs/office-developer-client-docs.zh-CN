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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 2dd61ee5cd0e2e671cc47425689287b8a437732f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773853"
---
# <a name="xlfree"></a><span data-ttu-id="9fcd9-104">xlFree</span><span class="sxs-lookup"><span data-stu-id="9fcd9-104">xlFree</span></span>

 <span data-ttu-id="9fcd9-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9fcd9-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="9fcd9-106">使用以释放内存资源分配由 Microsoft Excel 时创建返回值**XLOPER**/ **XLOPER12** [Excel4](excel4-excel12.md)、 [Excel4v](excel4v-excel12v.md)、 [Excel12](excel4-excel12.md)或[Excel12v](excel4v-excel12v.md)将调用。</span><span class="sxs-lookup"><span data-stu-id="9fcd9-106">Used to free memory resources allocated by Microsoft Excel when creating the return value **XLOPER**/ **XLOPER12** in a call to [Excel4](excel4-excel12.md), [Excel4v](excel4v-excel12v.md), [Excel12](excel4-excel12.md), or [Excel12v](excel4v-excel12v.md).</span></span> <span data-ttu-id="9fcd9-107">**XlFree**函数释放的辅助内存和将指针重置为**空**，但不会销毁**XLOPER**其他部件/ **XLOPER12**。</span><span class="sxs-lookup"><span data-stu-id="9fcd9-107">The **xlFree** function frees the auxiliary memory and resets the pointer to **NULL** but does not destroy other parts of the **XLOPER**/ **XLOPER12**.</span></span>
  
```cs
Excel4(xlFree, 0, n, LPXLOPER px_1, ..., LPXLOPER px_n);
Excel12(xlFree, 0, n, LPXLOPER12 px_1, ..., LPXLOPER12 px_n);
```

## <a name="parameters"></a><span data-ttu-id="9fcd9-108">参数</span><span class="sxs-lookup"><span data-stu-id="9fcd9-108">Parameters</span></span>

 <span data-ttu-id="9fcd9-109">_px_1，...px_n_</span><span class="sxs-lookup"><span data-stu-id="9fcd9-109">_px_1, ..., px_n_</span></span>
  
<span data-ttu-id="9fcd9-110">一个或多个**XLOPER**/ **XLOPER12**s 要释放。</span><span class="sxs-lookup"><span data-stu-id="9fcd9-110">One or more **XLOPER**/ **XLOPER12**s to be freed.</span></span> <span data-ttu-id="9fcd9-111">在 Excel 版本中最多为 2003年，可以传递的指针的最大数量为 30。</span><span class="sxs-lookup"><span data-stu-id="9fcd9-111">In Excel versions up to 2003, the maximum number of pointers that can be passed is 30.</span></span> <span data-ttu-id="9fcd9-112">从 Excel 2007 开始，这被增加到 255。</span><span class="sxs-lookup"><span data-stu-id="9fcd9-112">Starting in Excel 2007, this is increased to 255.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9fcd9-113">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="9fcd9-113">Property value/Return value</span></span>

<span data-ttu-id="9fcd9-114">此函数不返回值。</span><span class="sxs-lookup"><span data-stu-id="9fcd9-114">This function does not return a value.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9fcd9-115">备注</span><span class="sxs-lookup"><span data-stu-id="9fcd9-115">Remarks</span></span>

<span data-ttu-id="9fcd9-116">您必须释放返回值从**Excel4**或**Excel4v**获取每个**XLOPER**和返回值将从**Excel12**或获得**Excel12v**如果下列类型之一的每个**XLOPER12** : **xltypeStr**， **xltypeMulti**或**xltypeRef**。</span><span class="sxs-lookup"><span data-stu-id="9fcd9-116">You must free every **XLOPER** that you get as a return value from **Excel4** or **Excel4v** and every **XLOPER12** that you get as a return value from **Excel12** or **Excel12v** if they are one of the following types: **xltypeStr**, **xltypeMulti**, or **xltypeRef**.</span></span> <span data-ttu-id="9fcd9-117">始终是安全忙其他类型，即使它们不使用辅助内存，只要从**Excel4**或**Excel12**处获得。</span><span class="sxs-lookup"><span data-stu-id="9fcd9-117">It is always safe to free other types even if they do not use auxiliary memory, as long as you got them from **Excel4** or **Excel12**.</span></span>
  
<span data-ttu-id="9fcd9-118">其中您返回到 Excel 指向**XLOPER**/ **XLOPER12**仍包含 Excel 分配内存要释放，必须设置**xlbitXLFree**以确保内存的 Excel 版本。</span><span class="sxs-lookup"><span data-stu-id="9fcd9-118">Where you are returning to Excel a pointer to an **XLOPER**/ **XLOPER12** that still contains Excel-allocated memory to be freed, you must set the **xlbitXLFree** to ensure Excel releases the memory.</span></span> 
  
## <a name="example"></a><span data-ttu-id="9fcd9-119">示例</span><span class="sxs-lookup"><span data-stu-id="9fcd9-119">Example</span></span>

<span data-ttu-id="9fcd9-120">此示例调用**获取。WORKSPACE(1)** 返回哪些 Excel 当前正在运行字符串形式的平台。</span><span class="sxs-lookup"><span data-stu-id="9fcd9-120">This example calls **GET.WORKSPACE(1)** to return the platform on which Excel is currently running as a string.</span></span> <span data-ttu-id="9fcd9-121">代码将复制此返回到供以后使用缓冲区的字符串。</span><span class="sxs-lookup"><span data-stu-id="9fcd9-121">The code copies this returned string into a buffer for later use.</span></span> <span data-ttu-id="9fcd9-122">该代码将缓冲区放回**XLOPER12**更高版本用于 Excel 函数。</span><span class="sxs-lookup"><span data-stu-id="9fcd9-122">The code places the buffer back into the **XLOPER12** for later use with the Excel function.</span></span> <span data-ttu-id="9fcd9-123">最后，代码在警告框中显示的字符串。</span><span class="sxs-lookup"><span data-stu-id="9fcd9-123">Finally, the code displays the string in an alert box.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="9fcd9-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fcd9-124">See also</span></span>

- [<span data-ttu-id="9fcd9-125">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="9fcd9-125">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

