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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: f2830633482e5329d285907b610386b708c406a4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773646"
---
# <a name="convertxlreftoxlref12"></a><span data-ttu-id="75e69-104">ConvertXLRefToXLRef12</span><span class="sxs-lookup"><span data-stu-id="75e69-104">ConvertXLRefToXLRef12</span></span>

<span data-ttu-id="75e69-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="75e69-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="75e69-106">尝试**XLREF**转换**XLREF12**的框架函数。</span><span class="sxs-lookup"><span data-stu-id="75e69-106">Framework function that attempts to convert an **XLREF** into an **XLREF12**.</span></span>
  
```cs
BOOL ConvertXLRefToXLRef12(LPXLREF pxRef, LPXLREF12 pxRef12);
```

## <a name="parameters"></a><span data-ttu-id="75e69-107">参数</span><span class="sxs-lookup"><span data-stu-id="75e69-107">Parameters</span></span>

 <span data-ttu-id="75e69-108">_pxRef_(**LPXLREF**)</span><span class="sxs-lookup"><span data-stu-id="75e69-108">_pxRef_ (**LPXLREF**)</span></span>
  
<span data-ttu-id="75e69-109">指向源引用结构。</span><span class="sxs-lookup"><span data-stu-id="75e69-109">Pointer to the source reference structure.</span></span>
  
 <span data-ttu-id="75e69-110">_pxRef12_(**LPXLREF12**)</span><span class="sxs-lookup"><span data-stu-id="75e69-110">_pxRef12_ (**LPXLREF12**)</span></span>
  
<span data-ttu-id="75e69-111">转换后的值是放置到其中的目标引用结构的指针。</span><span class="sxs-lookup"><span data-stu-id="75e69-111">Pointer to the target reference structure into which the converted value is to be placed.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="75e69-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="75e69-112">Property value/Return value</span></span>

 <span data-ttu-id="75e69-113">如果为**TRUE**转换成功， **FALSE**否则。</span><span class="sxs-lookup"><span data-stu-id="75e69-113">**TRUE** if the conversion succeeded, **FALSE** otherwise.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="75e69-114">备注</span><span class="sxs-lookup"><span data-stu-id="75e69-114">Remarks</span></span>

<span data-ttu-id="75e69-115">传入的**XLREF**是有效的则此操作应始终为成功。</span><span class="sxs-lookup"><span data-stu-id="75e69-115">Provided that the passed-in **XLREF** is valid, this operation should always be successful.</span></span> <span data-ttu-id="75e69-116">相比之下，转换的其他方式从**XLREF12** **XLREF**，由[ConvertXLRef12ToXLRef](convertxlref12toxlref.md)，执行失败提供的引用引用的 Excel 2007 工作表中不支持早期版本中的一部分。</span><span class="sxs-lookup"><span data-stu-id="75e69-116">In contrast, conversion the other way from **XLREF12** to **XLREF**, performed by [ConvertXLRef12ToXLRef](convertxlref12toxlref.md), fails if the supplied reference refers to part of an Excel 2007 worksheet that is not supported in earlier versions.</span></span>
  
## <a name="example"></a><span data-ttu-id="75e69-117">示例</span><span class="sxs-lookup"><span data-stu-id="75e69-117">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="75e69-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75e69-118">See also</span></span>



[<span data-ttu-id="75e69-119">Framework 库中的函数</span><span class="sxs-lookup"><span data-stu-id="75e69-119">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

