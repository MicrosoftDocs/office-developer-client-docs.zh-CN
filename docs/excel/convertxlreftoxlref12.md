---
title: ConvertXLRefToXLRef12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- ConvertXLRefToXLRef12
keywords:
- convertxlreftoxlref12 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 94580044-9497-425f-a31e-53bb4d94dc30
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 530cb9cce5b0023318ff6b8a0ff73472f8250aa3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432028"
---
# <a name="convertxlreftoxlref12"></a><span data-ttu-id="50e30-104">ConvertXLRefToXLRef12</span><span class="sxs-lookup"><span data-stu-id="50e30-104">ConvertXLRefToXLRef12</span></span>

<span data-ttu-id="50e30-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="50e30-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="50e30-106">尝试将 **XLREF** 转换为 **XLREF12** 的框架函数。</span><span class="sxs-lookup"><span data-stu-id="50e30-106">Framework function that attempts to convert an **XLREF** into an **XLREF12**.</span></span>
  
```cs
BOOL ConvertXLRefToXLRef12(LPXLREF pxRef, LPXLREF12 pxRef12);
```

## <a name="parameters"></a><span data-ttu-id="50e30-107">参数</span><span class="sxs-lookup"><span data-stu-id="50e30-107">Parameters</span></span>

 <span data-ttu-id="50e30-108">_pxRef_ (**LPXLREF**) </span><span class="sxs-lookup"><span data-stu-id="50e30-108">_pxRef_ (**LPXLREF**)</span></span>
  
<span data-ttu-id="50e30-109">指向源引用结构的指针。</span><span class="sxs-lookup"><span data-stu-id="50e30-109">Pointer to the source reference structure.</span></span>
  
 <span data-ttu-id="50e30-110">_pxRef12_ (**LPXLREF12)**</span><span class="sxs-lookup"><span data-stu-id="50e30-110">_pxRef12_ (**LPXLREF12**)</span></span>
  
<span data-ttu-id="50e30-111">指向要放置转换值的目标引用结构的指针。</span><span class="sxs-lookup"><span data-stu-id="50e30-111">Pointer to the target reference structure into which the converted value is to be placed.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="50e30-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="50e30-112">Property value/Return value</span></span>

 <span data-ttu-id="50e30-113">如果转换成功，则其为 **TRUE;** 否则为 **FALSE。**</span><span class="sxs-lookup"><span data-stu-id="50e30-113">**TRUE** if the conversion succeeded, **FALSE** otherwise.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="50e30-114">备注</span><span class="sxs-lookup"><span data-stu-id="50e30-114">Remarks</span></span>

<span data-ttu-id="50e30-115">如果传入的 **XLREF** 有效，则此操作应始终成功。</span><span class="sxs-lookup"><span data-stu-id="50e30-115">Provided that the passed-in **XLREF** is valid, this operation should always be successful.</span></span> <span data-ttu-id="50e30-116">相反，如果所提供的引用引用的 Excel 2007 工作表的一部分在早期版本中不受支持，则从 **XLREF12** 转换到 **XLREF（** 由 [ConvertXLRef12ToXLRef](convertxlref12toxlref.md)执行）会失败。</span><span class="sxs-lookup"><span data-stu-id="50e30-116">In contrast, conversion the other way from **XLREF12** to **XLREF**, performed by [ConvertXLRef12ToXLRef](convertxlref12toxlref.md), fails if the supplied reference refers to part of an Excel 2007 worksheet that is not supported in earlier versions.</span></span>
  
## <a name="example"></a><span data-ttu-id="50e30-117">示例</span><span class="sxs-lookup"><span data-stu-id="50e30-117">Example</span></span>

 `\SAMPLES\FRAMEWRK\FRAMEWRK.C`
  
```cs
BOOL ConvertXLRefToXLRef12(LPXLREF pxref, LPXLREF12 pxref12)
{
   if (pxref->rwLast >= pxref->rwFirst && pxref->colLast >= pxref->colFirst)
   {
      if (pxref->rwFirst >= 0 && pxref->colFirst >= 0)
      {
         pxref12->rwFirst = pxref->rwFirst;
         pxref12->rwLast = pxref->rwLast;
         pxref12->colFirst = pxref->colFirst;
         pxref12->colLast = pxref->colLast;
         return TRUE;
      }
   }
   return FALSE;
}
```

## <a name="see-also"></a><span data-ttu-id="50e30-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50e30-118">See also</span></span>



[<span data-ttu-id="50e30-119">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="50e30-119">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

