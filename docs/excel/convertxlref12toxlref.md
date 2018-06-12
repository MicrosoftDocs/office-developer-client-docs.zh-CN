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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 826428edb57eba9e17d601164aa8b4b797fc8929
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773639"
---
# <a name="convertxlref12toxlref"></a><span data-ttu-id="0bded-104">ConvertXLRef12ToXLRef</span><span class="sxs-lookup"><span data-stu-id="0bded-104">ConvertXLRef12ToXLRef</span></span>

<span data-ttu-id="0bded-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0bded-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="0bded-106">尝试**XLREF12**转换**XLREF**。</span><span class="sxs-lookup"><span data-stu-id="0bded-106">Tries to convert an **XLREF12** into an **XLREF**.</span></span>
  
```cs
BOOL ConvertXLRefToXLRef12(LPXLREF12 pxRef12, LPXLREF pxRef);
```

## <a name="parameters"></a><span data-ttu-id="0bded-107">参数</span><span class="sxs-lookup"><span data-stu-id="0bded-107">Parameters</span></span>

 <span data-ttu-id="0bded-108">_pxRef12_(**LPXLREF12**)</span><span class="sxs-lookup"><span data-stu-id="0bded-108">_pxRef12_ (**LPXLREF12**)</span></span>
  
<span data-ttu-id="0bded-109">指向源引用结构。</span><span class="sxs-lookup"><span data-stu-id="0bded-109">Pointer to the source reference structure.</span></span>
  
 <span data-ttu-id="0bded-110">_pxRef_(**LPXLREF**)</span><span class="sxs-lookup"><span data-stu-id="0bded-110">_pxRef_ (**LPXLREF**)</span></span>
  
<span data-ttu-id="0bded-111">转换后的值是放置到其中的目标引用结构的指针。</span><span class="sxs-lookup"><span data-stu-id="0bded-111">Pointer to the target reference structure into which the converted value is to be placed.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="0bded-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="0bded-112">Property value/Return value</span></span>

 <span data-ttu-id="0bded-113">如果为**TRUE**转换成功， **FALSE**否则。</span><span class="sxs-lookup"><span data-stu-id="0bded-113">**TRUE** if the conversion succeeded, **FALSE** otherwise.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="0bded-114">备注</span><span class="sxs-lookup"><span data-stu-id="0bded-114">Remarks</span></span>

<span data-ttu-id="0bded-115">如果提供的引用是指不支持早期版本中的 Excel 2007 工作表部分，从**XLREF12**到**XLREF**的转换失败。</span><span class="sxs-lookup"><span data-stu-id="0bded-115">The conversion from **XLREF12** to **XLREF** fails if the supplied reference refers to part of a Excel 2007 worksheet that is not supported in earlier versions.</span></span> 
  
## <a name="example"></a><span data-ttu-id="0bded-116">示例</span><span class="sxs-lookup"><span data-stu-id="0bded-116">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0bded-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bded-117">See also</span></span>



[<span data-ttu-id="0bded-118">Framework 库中的函数</span><span class="sxs-lookup"><span data-stu-id="0bded-118">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

