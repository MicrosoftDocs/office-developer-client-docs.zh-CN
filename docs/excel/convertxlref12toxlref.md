---
title: ConvertXLRef12ToXLRef
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- ConvertXLRef12ToXLRef
keywords:
- convertxlref12toxlref 函数 [excel 2007]
localization_priority: Normal
ms.assetid: b620ed21-73ef-489b-9c00-7be12bb41214
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 0a12052a93d030088feb548449955129ff5bdc0f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432651"
---
# <a name="convertxlref12toxlref"></a><span data-ttu-id="b4bf2-104">ConvertXLRef12ToXLRef</span><span class="sxs-lookup"><span data-stu-id="b4bf2-104">ConvertXLRef12ToXLRef</span></span>

<span data-ttu-id="b4bf2-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b4bf2-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="b4bf2-106">尝试将 **XLREF12** 转换为 **XLREF**。</span><span class="sxs-lookup"><span data-stu-id="b4bf2-106">Tries to convert an **XLREF12** into an **XLREF**.</span></span>
  
```cs
BOOL ConvertXLRefToXLRef12(LPXLREF12 pxRef12, LPXLREF pxRef);
```

## <a name="parameters"></a><span data-ttu-id="b4bf2-107">参数</span><span class="sxs-lookup"><span data-stu-id="b4bf2-107">Parameters</span></span>

 <span data-ttu-id="b4bf2-108">_pxRef12_ (**LPXLREF12)**</span><span class="sxs-lookup"><span data-stu-id="b4bf2-108">_pxRef12_ (**LPXLREF12**)</span></span>
  
<span data-ttu-id="b4bf2-109">指向源引用结构的指针。</span><span class="sxs-lookup"><span data-stu-id="b4bf2-109">Pointer to the source reference structure.</span></span>
  
 <span data-ttu-id="b4bf2-110">_pxRef_ (**LPXLREF**) </span><span class="sxs-lookup"><span data-stu-id="b4bf2-110">_pxRef_ (**LPXLREF**)</span></span>
  
<span data-ttu-id="b4bf2-111">指向要放置转换值的目标引用结构的指针。</span><span class="sxs-lookup"><span data-stu-id="b4bf2-111">Pointer to the target reference structure into which the converted value is to be placed.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b4bf2-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="b4bf2-112">Property value/Return value</span></span>

 <span data-ttu-id="b4bf2-113">如果转换成功，则其为 **TRUE;** 否则为 **FALSE。**</span><span class="sxs-lookup"><span data-stu-id="b4bf2-113">**TRUE** if the conversion succeeded, **FALSE** otherwise.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="b4bf2-114">备注</span><span class="sxs-lookup"><span data-stu-id="b4bf2-114">Remarks</span></span>

<span data-ttu-id="b4bf2-115">如果所提供的引用引用了早期版本中不支持的 Excel 2007 工作表的一部分，则从 **XLREF12** 到 **XLREF** 的转换将失败。</span><span class="sxs-lookup"><span data-stu-id="b4bf2-115">The conversion from **XLREF12** to **XLREF** fails if the supplied reference refers to part of a Excel 2007 worksheet that is not supported in earlier versions.</span></span> 
  
## <a name="example"></a><span data-ttu-id="b4bf2-116">示例</span><span class="sxs-lookup"><span data-stu-id="b4bf2-116">Example</span></span>

 `\SAMPLES\FRAMEWRK\FRAMEWRK.C`
  
```cs
BOOL ConvertXLRef12ToXLRef(LPXLREF12 pxref12, LPXLREF pxref)
{
   if (pxref12->rwLast >= pxref12->rwFirst && pxref12->colLast >= pxref12->colFirst)
   {
      if (pxref12->rwFirst >=0 && pxref12->colFirst >= 0)
      {
         if (pxref12->rwLast < rwMaxO8 && pxref12->colLast < colMaxO8)
         {
            pxref->rwFirst = (WORD)pxref12->rwFirst;
            pxref->rwLast = (WORD)pxref12->rwLast;
            pxref->colFirst = (BYTE)pxref12->colFirst;
            pxref->colLast = (BYTE)pxref12->colLast;
            return TRUE;
         }
      }
   }
   return FALSE;
}
```

## <a name="see-also"></a><span data-ttu-id="b4bf2-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4bf2-117">See also</span></span>



[<span data-ttu-id="b4bf2-118">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="b4bf2-118">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

