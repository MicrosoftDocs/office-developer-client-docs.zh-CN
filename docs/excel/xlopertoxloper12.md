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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 76c78e5a2ad62b1a3d1aa23748b10e49e07f6543
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773877"
---
# <a name="xlopertoxloper12"></a><span data-ttu-id="7a48a-104">XLOperToXLOper12</span><span class="sxs-lookup"><span data-stu-id="7a48a-104">XLOperToXLOper12</span></span>

<span data-ttu-id="7a48a-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7a48a-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="7a48a-106">用于从旧**XLOPER**转换为新**XLOPER12**转换例程。</span><span class="sxs-lookup"><span data-stu-id="7a48a-106">Conversion routine used to convert from the old **XLOPER** to the new **XLOPER12**.</span></span>
  
```cs
BOOL XLOperToXLOper12(LPXLOPER pxloper, LPXLOPER12 pxloper12);
```

## <a name="parameters"></a><span data-ttu-id="7a48a-107">参数</span><span class="sxs-lookup"><span data-stu-id="7a48a-107">Parameters</span></span>

<span data-ttu-id="7a48a-108">_pxloper_(**LPXLOPER**)</span><span class="sxs-lookup"><span data-stu-id="7a48a-108">_pxloper_ (**LPXLOPER**)</span></span>
  
<span data-ttu-id="7a48a-109">对源**XLOPER**要转换的指针。</span><span class="sxs-lookup"><span data-stu-id="7a48a-109">Pointer to the source **XLOPER** to be converted.</span></span> 
  
<span data-ttu-id="7a48a-110">_pxloper12_(**LPXLOPER12**)</span><span class="sxs-lookup"><span data-stu-id="7a48a-110">_pxloper12_ (**LPXLOPER12**)</span></span>
  
<span data-ttu-id="7a48a-111">指向目标**XLOPER12**包含转换的值。</span><span class="sxs-lookup"><span data-stu-id="7a48a-111">Pointer to the target **XLOPER12** to contain the converted value.</span></span> 
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7a48a-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="7a48a-112">Property value/Return value</span></span>

<span data-ttu-id="7a48a-113">如果为**TRUE**转换成功， **FALSE**否则。</span><span class="sxs-lookup"><span data-stu-id="7a48a-113">**TRUE** if the conversion succeeded, **FALSE** otherwise.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="7a48a-114">说明</span><span class="sxs-lookup"><span data-stu-id="7a48a-114">Remarks</span></span>

<span data-ttu-id="7a48a-115">根据**XLOPER**类型，此函数为转换后的值，指向目标**XLOPER12**中分配新内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="7a48a-115">Depending on the type of the **XLOPER**, this function allocates a new memory buffer for the converted values, which are pointed to in the target **XLOPER12**.</span></span> <span data-ttu-id="7a48a-116">呼叫者负责释放转换为成功; 如果与副本关联任何内存可以使用**FreeXLOper12T** ，或直接使用**免费**即可完成。</span><span class="sxs-lookup"><span data-stu-id="7a48a-116">The caller is responsible for freeing any memory associated with the copy if the conversion is a success; **FreeXLOper12T** can be used, or it can be done directly using **free**.</span></span>
  
<span data-ttu-id="7a48a-117">如果转换失败，则不需要释放的任何内存呼叫者。</span><span class="sxs-lookup"><span data-stu-id="7a48a-117">If the conversion fails, the caller does not need to free any memory.</span></span>
  
<span data-ttu-id="7a48a-118">一般情况下，从任何**XLOPER**转换为**XLOPER12**时可能。</span><span class="sxs-lookup"><span data-stu-id="7a48a-118">In general, conversion from any **XLOPER** to an **XLOPER12** is possible.</span></span> <span data-ttu-id="7a48a-119">相比之下，从**XLOPER12**到**XLOPER**转换可能会失败时**XLOPER12**包含数组或引用太大或对于**XLOPER**包含太长字符串。</span><span class="sxs-lookup"><span data-stu-id="7a48a-119">In contrast, conversion from an **XLOPER12** to an **XLOPER** can fail when the **XLOPER12** contains an array or reference that is too large or a string that is too long for the **XLOPER** to contain.</span></span> 
  
<span data-ttu-id="7a48a-120">**XLOPER**ASCII 字节字符串转换为**XLOPER12** Unicode 宽字符字符串是区域设置相关的方式。</span><span class="sxs-lookup"><span data-stu-id="7a48a-120">**XLOPER** ASCII byte strings are converted to **XLOPER12** Unicode wide-character strings in a way that is locale-dependent.</span></span> 
  
### <a name="example"></a><span data-ttu-id="7a48a-121">示例</span><span class="sxs-lookup"><span data-stu-id="7a48a-121">Example</span></span>

<span data-ttu-id="7a48a-122">请参阅文件`\SAMPLES\FRAMEWRK\FRAMEWRK.C`的此函数的代码。</span><span class="sxs-lookup"><span data-stu-id="7a48a-122">See the file  `\SAMPLES\FRAMEWRK\FRAMEWRK.C` for the code for this function.</span></span> 
  

