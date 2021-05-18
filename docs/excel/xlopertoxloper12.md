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
# <a name="xlopertoxloper12"></a><span data-ttu-id="c95b3-104">XLOperToXLOper12</span><span class="sxs-lookup"><span data-stu-id="c95b3-104">XLOperToXLOper12</span></span>

<span data-ttu-id="c95b3-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c95b3-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="c95b3-106">用于从旧 **XLOPER** 转换到新 **XLOPER12** 的转换例程。</span><span class="sxs-lookup"><span data-stu-id="c95b3-106">Conversion routine used to convert from the old **XLOPER** to the new **XLOPER12**.</span></span>
  
```cs
BOOL XLOperToXLOper12(LPXLOPER pxloper, LPXLOPER12 pxloper12);
```

## <a name="parameters"></a><span data-ttu-id="c95b3-107">参数</span><span class="sxs-lookup"><span data-stu-id="c95b3-107">Parameters</span></span>

<span data-ttu-id="c95b3-108">_pxloper_ (**LPXLOPER**) </span><span class="sxs-lookup"><span data-stu-id="c95b3-108">_pxloper_ (**LPXLOPER**)</span></span>
  
<span data-ttu-id="c95b3-109">指向要转换的 **源 XLOPER** 的指针。</span><span class="sxs-lookup"><span data-stu-id="c95b3-109">Pointer to the source **XLOPER** to be converted.</span></span> 
  
<span data-ttu-id="c95b3-110">_pxloper12_ (**LPXLOPER12**) </span><span class="sxs-lookup"><span data-stu-id="c95b3-110">_pxloper12_ (**LPXLOPER12**)</span></span>
  
<span data-ttu-id="c95b3-111">指向目标 **XLOPER12 的指针，** 以包含转换后的值。</span><span class="sxs-lookup"><span data-stu-id="c95b3-111">Pointer to the target **XLOPER12** to contain the converted value.</span></span> 
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c95b3-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="c95b3-112">Property value/Return value</span></span>

<span data-ttu-id="c95b3-113">如果转换成功，则其为 **TRUE;** 否则为 **FALSE。**</span><span class="sxs-lookup"><span data-stu-id="c95b3-113">**TRUE** if the conversion succeeded, **FALSE** otherwise.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="c95b3-114">备注</span><span class="sxs-lookup"><span data-stu-id="c95b3-114">Remarks</span></span>

<span data-ttu-id="c95b3-115">根据 **XLOPER** 的类型，此函数为目标 **XLOPER12** 中指向的转换值分配新的内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c95b3-115">Depending on the type of the **XLOPER**, this function allocates a new memory buffer for the converted values, which are pointed to in the target **XLOPER12**.</span></span> <span data-ttu-id="c95b3-116">如果转换成功，调用方负责释放与副本关联的任何内存; **可以使用 FreeXLOper12T，** 也可以直接使用免费 **完成**。</span><span class="sxs-lookup"><span data-stu-id="c95b3-116">The caller is responsible for freeing any memory associated with the copy if the conversion is a success; **FreeXLOper12T** can be used, or it can be done directly using **free**.</span></span>
  
<span data-ttu-id="c95b3-117">如果转换失败，则调用方无需释放任何内存。</span><span class="sxs-lookup"><span data-stu-id="c95b3-117">If the conversion fails, the caller does not need to free any memory.</span></span>
  
<span data-ttu-id="c95b3-118">通常，从任何 **XLOPER 到** **XLOPER12** 的转换都是可能的。</span><span class="sxs-lookup"><span data-stu-id="c95b3-118">In general, conversion from any **XLOPER** to an **XLOPER12** is possible.</span></span> <span data-ttu-id="c95b3-119">相比之下，当 XLOPER12 包含的数组或引用过大或字符串太长 **，XLOPER** 无法包含时，从 **XLOPER12** 转换到 **XLOPER** 可能会失败。</span><span class="sxs-lookup"><span data-stu-id="c95b3-119">In contrast, conversion from an **XLOPER12** to an **XLOPER** can fail when the **XLOPER12** contains an array or reference that is too large or a string that is too long for the **XLOPER** to contain.</span></span> 
  
<span data-ttu-id="c95b3-120">**XLOPER** ASCII 字节字符串以依赖于区域设置的方式转换为 **XLOPER12** Unicode 宽字符字符串。</span><span class="sxs-lookup"><span data-stu-id="c95b3-120">**XLOPER** ASCII byte strings are converted to **XLOPER12** Unicode wide-character strings in a way that is locale-dependent.</span></span> 
  
### <a name="example"></a><span data-ttu-id="c95b3-121">示例</span><span class="sxs-lookup"><span data-stu-id="c95b3-121">Example</span></span>

<span data-ttu-id="c95b3-122">有关此  `\SAMPLES\FRAMEWRK\FRAMEWRK.C` 函数的代码，请参阅 文件。</span><span class="sxs-lookup"><span data-stu-id="c95b3-122">See the file  `\SAMPLES\FRAMEWRK\FRAMEWRK.C` for the code for this function.</span></span> 
  

