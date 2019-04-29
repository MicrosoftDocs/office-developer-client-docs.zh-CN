---
title: XLOperToXLOper12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- XLOperToXLOper12
keywords:
- xlopertoxloper12 函数 [excel 2007]
localization_priority: Normal
ms.assetid: b2d4581b-ebf6-4eba-aa95-69a5a9ee8028
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: c881f5d03c732b6594e0750808cfa35a65127ed0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404594"
---
# <a name="xlopertoxloper12"></a><span data-ttu-id="0d757-104">XLOperToXLOper12</span><span class="sxs-lookup"><span data-stu-id="0d757-104">XLOperToXLOper12</span></span>

<span data-ttu-id="0d757-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0d757-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="0d757-106">用于将旧**XLOPER**转换为新**XLOPER12**的转换例程。</span><span class="sxs-lookup"><span data-stu-id="0d757-106">Conversion routine used to convert from the old **XLOPER** to the new **XLOPER12**.</span></span>
  
```cs
BOOL XLOperToXLOper12(LPXLOPER pxloper, LPXLOPER12 pxloper12);
```

## <a name="parameters"></a><span data-ttu-id="0d757-107">参数</span><span class="sxs-lookup"><span data-stu-id="0d757-107">Parameters</span></span>

<span data-ttu-id="0d757-108">_pxloper_(**LPXLOPER**)</span><span class="sxs-lookup"><span data-stu-id="0d757-108">_pxloper_ (**LPXLOPER**)</span></span>
  
<span data-ttu-id="0d757-109">指向要转换的源**XLOPER**的指针。</span><span class="sxs-lookup"><span data-stu-id="0d757-109">Pointer to the source **XLOPER** to be converted.</span></span> 
  
<span data-ttu-id="0d757-110">_pxloper12_(**LPXLOPER12**)</span><span class="sxs-lookup"><span data-stu-id="0d757-110">_pxloper12_ (**LPXLOPER12**)</span></span>
  
<span data-ttu-id="0d757-111">指向目标**XLOPER12**的指针, 以包含转换后的值。</span><span class="sxs-lookup"><span data-stu-id="0d757-111">Pointer to the target **XLOPER12** to contain the converted value.</span></span> 
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="0d757-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="0d757-112">Property value/Return value</span></span>

<span data-ttu-id="0d757-113">如果转换成功,**则为 TRUE** , 否则为**FALSE** 。</span><span class="sxs-lookup"><span data-stu-id="0d757-113">**TRUE** if the conversion succeeded, **FALSE** otherwise.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="0d757-114">说明</span><span class="sxs-lookup"><span data-stu-id="0d757-114">Remarks</span></span>

<span data-ttu-id="0d757-115">根据**XLOPER**的类型, 此函数为转换的值分配一个新的内存缓冲区, 这些值指向目标**XLOPER12**中的。</span><span class="sxs-lookup"><span data-stu-id="0d757-115">Depending on the type of the **XLOPER**, this function allocates a new memory buffer for the converted values, which are pointed to in the target **XLOPER12**.</span></span> <span data-ttu-id="0d757-116">如果转换成功, 则呼叫者负责释放与副本关联的任何内存;可以使用**FreeXLOper12T** , 也可以直接使用**free**执行。</span><span class="sxs-lookup"><span data-stu-id="0d757-116">The caller is responsible for freeing any memory associated with the copy if the conversion is a success; **FreeXLOper12T** can be used, or it can be done directly using **free**.</span></span>
  
<span data-ttu-id="0d757-117">如果转换失败, 则呼叫者无需释放任何内存。</span><span class="sxs-lookup"><span data-stu-id="0d757-117">If the conversion fails, the caller does not need to free any memory.</span></span>
  
<span data-ttu-id="0d757-118">通常情况下, 可以从任何**XLOPER**转换为**XLOPER12** 。</span><span class="sxs-lookup"><span data-stu-id="0d757-118">In general, conversion from any **XLOPER** to an **XLOPER12** is possible.</span></span> <span data-ttu-id="0d757-119">相比之下, 当**XLOPER12**包含的数组或引用过大或字符串太长而无法包含的**XLOPER**时, 从**XLOPER12**到**XLOPER**的转换可能会失败。</span><span class="sxs-lookup"><span data-stu-id="0d757-119">In contrast, conversion from an **XLOPER12** to an **XLOPER** can fail when the **XLOPER12** contains an array or reference that is too large or a string that is too long for the **XLOPER** to contain.</span></span> 
  
<span data-ttu-id="0d757-120">**XLOPER**ASCII 字节字符串将以与区域设置相关的方式转换为**XLOPER12** Unicode 宽字符字符串。</span><span class="sxs-lookup"><span data-stu-id="0d757-120">**XLOPER** ASCII byte strings are converted to **XLOPER12** Unicode wide-character strings in a way that is locale-dependent.</span></span> 
  
### <a name="example"></a><span data-ttu-id="0d757-121">示例</span><span class="sxs-lookup"><span data-stu-id="0d757-121">Example</span></span>

<span data-ttu-id="0d757-122">有关此函数`\SAMPLES\FRAMEWRK\FRAMEWRK.C`的代码, 请参阅文件。</span><span class="sxs-lookup"><span data-stu-id="0d757-122">See the file  `\SAMPLES\FRAMEWRK\FRAMEWRK.C` for the code for this function.</span></span> 
  

