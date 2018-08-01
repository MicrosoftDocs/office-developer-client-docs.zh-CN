---
title: XLOper12ToXLOper
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- XLOper12ToXLOper
keywords:
- xloper12toxloper 函数 [excel 2007]
localization_priority: Normal
ms.assetid: b46f87c4-778b-4502-be57-c3725f73a644
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 2c06102699db8810da803ecc0ddfa30375fcc125
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773862"
---
# <a name="xloper12toxloper"></a><span data-ttu-id="87671-104">XLOper12ToXLOper</span><span class="sxs-lookup"><span data-stu-id="87671-104">XLOper12ToXLOper</span></span>

<span data-ttu-id="87671-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="87671-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="87671-106">用于从新**XLOPER12**转换为旧**XLOPER**转换例程。</span><span class="sxs-lookup"><span data-stu-id="87671-106">Conversion routine used to convert from the new **XLOPER12** to the old **XLOPER**.</span></span>
  
```cs
BOOL XLOper12ToXLOper(LPXLOPER12 pxloper12, LPXLOPER pxloper);
```

## <a name="parameters"></a><span data-ttu-id="87671-107">参数</span><span class="sxs-lookup"><span data-stu-id="87671-107">Parameters</span></span>

<span data-ttu-id="87671-108">_pxloper12_(**LPXLOPER12**)</span><span class="sxs-lookup"><span data-stu-id="87671-108">_pxloper12_ (**LPXLOPER12**)</span></span>
  
<span data-ttu-id="87671-109">对源**XLOPER12**要转换的指针。</span><span class="sxs-lookup"><span data-stu-id="87671-109">Pointer to the source **XLOPER12** to be converted.</span></span> 
  
<span data-ttu-id="87671-110">_pxloper_(**LPXLOPER**)</span><span class="sxs-lookup"><span data-stu-id="87671-110">_pxloper_ (**LPXLOPER**)</span></span>
  
<span data-ttu-id="87671-111">指向目标**XLOPER**包含转换的值。</span><span class="sxs-lookup"><span data-stu-id="87671-111">Pointer to the target **XLOPER** to contain the converted value.</span></span> 
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="87671-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="87671-112">Property value/Return value</span></span>

<span data-ttu-id="87671-113">如果为**TRUE**转换成功， **FALSE**否则。</span><span class="sxs-lookup"><span data-stu-id="87671-113">**TRUE** if the conversion succeeded, **FALSE** otherwise.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="87671-114">说明</span><span class="sxs-lookup"><span data-stu-id="87671-114">Remarks</span></span>

<span data-ttu-id="87671-115">根据**XLOPER12**类型，此函数为转换后的值，指向目标**XLOPER**中分配新内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="87671-115">Depending on the type of the **XLOPER12**, this function allocates a new memory buffer for the converted values, which are pointed to in the target **XLOPER**.</span></span> <span data-ttu-id="87671-116">呼叫者负责释放转换为成功; 如果与副本关联任何内存可**FreeXLOperT** ，也可直接通过使用**免费**。</span><span class="sxs-lookup"><span data-stu-id="87671-116">The caller is responsible for freeing any memory associated with the copy if the conversion is a success; **FreeXLOperT** can be used, or it can be done directly by using **free**.</span></span>
  
<span data-ttu-id="87671-117">如果转换失败，则不需要释放的任何内存呼叫者。</span><span class="sxs-lookup"><span data-stu-id="87671-117">If the conversion fails, the caller does not need to free any memory.</span></span>
  
<span data-ttu-id="87671-118">**XLOPER12**包含数组或引用太大或对于**XLOPER**包含太长字符串时，从**XLOPER12**到**XLOPER**转换可能会失败。</span><span class="sxs-lookup"><span data-stu-id="87671-118">Conversion from an **XLOPER12** to an **XLOPER** can fail when the **XLOPER12** contains an array or reference that is too large or a string that is too long for the **XLOPER** to contain.</span></span> 
  
<span data-ttu-id="87671-119">**XLOPER12**Unicode 宽字符的字符串转换为的方式，它是区域设置相关的**XLOPER** ASCII 字节字符串。</span><span class="sxs-lookup"><span data-stu-id="87671-119">**XLOPER12** Unicode wide-character strings are converted to **XLOPER** ASCII byte strings in a way that is locale-dependent.</span></span> 
  
<span data-ttu-id="87671-120">**XLOPER12** **xltypeInt**是 32 位有符号的整数，而**XLOPER** **xltypeInt**是一个 16 位有符号的整数。</span><span class="sxs-lookup"><span data-stu-id="87671-120">The **XLOPER12** **xltypeInt** is a 32-bit signed integer, whereas the **XLOPER** **xltypeInt** is a 16-bit signed integer.</span></span> <span data-ttu-id="87671-121">时提供的**XLOPER12**整数超出**XLOPER**整数的限制，整数转换为 8 字节 double，并返回类型**xltypeNum** **XLOPER** 。</span><span class="sxs-lookup"><span data-stu-id="87671-121">When a supplied **XLOPER12** integer exceeds the limit of an **XLOPER** integer, the integer is converted to an 8-byte double and returned in an **XLOPER** of type **xltypeNum**.</span></span> <span data-ttu-id="87671-122">这是唯一的转换**XLOPER**类型更改顺序此函数的情况。</span><span class="sxs-lookup"><span data-stu-id="87671-122">This is the only case in which this function changes the type of the converted **XLOPER**.</span></span>
  
### <a name="example"></a><span data-ttu-id="87671-123">示例</span><span class="sxs-lookup"><span data-stu-id="87671-123">Example</span></span>

<span data-ttu-id="87671-124">请参阅文件`\SAMPLES\FRAMEWRK\FRAMEWRK.C`的此函数的代码。</span><span class="sxs-lookup"><span data-stu-id="87671-124">See the file  `\SAMPLES\FRAMEWRK\FRAMEWRK.C` for the code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="87671-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87671-125">See also</span></span>

- [<span data-ttu-id="87671-126">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="87671-126">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

