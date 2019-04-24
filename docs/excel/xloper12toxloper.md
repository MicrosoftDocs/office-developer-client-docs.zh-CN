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
ms.openlocfilehash: 148353dcec1cc051aa44d18c0a081b6623e3759a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310071"
---
# <a name="xloper12toxloper"></a><span data-ttu-id="5b14d-104">XLOper12ToXLOper</span><span class="sxs-lookup"><span data-stu-id="5b14d-104">XLOper12ToXLOper</span></span>

<span data-ttu-id="5b14d-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5b14d-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="5b14d-106">用于将新**XLOPER12**转换为旧**XLOPER**的转换例程。</span><span class="sxs-lookup"><span data-stu-id="5b14d-106">Conversion routine used to convert from the new **XLOPER12** to the old **XLOPER**.</span></span>
  
```cs
BOOL XLOper12ToXLOper(LPXLOPER12 pxloper12, LPXLOPER pxloper);
```

## <a name="parameters"></a><span data-ttu-id="5b14d-107">参数</span><span class="sxs-lookup"><span data-stu-id="5b14d-107">Parameters</span></span>

<span data-ttu-id="5b14d-108">_pxloper12_(**LPXLOPER12**)</span><span class="sxs-lookup"><span data-stu-id="5b14d-108">_pxloper12_ (**LPXLOPER12**)</span></span>
  
<span data-ttu-id="5b14d-109">指向要转换的源**XLOPER12**的指针。</span><span class="sxs-lookup"><span data-stu-id="5b14d-109">Pointer to the source **XLOPER12** to be converted.</span></span> 
  
<span data-ttu-id="5b14d-110">_pxloper_(**LPXLOPER**)</span><span class="sxs-lookup"><span data-stu-id="5b14d-110">_pxloper_ (**LPXLOPER**)</span></span>
  
<span data-ttu-id="5b14d-111">指向目标**XLOPER**的指针, 以包含转换后的值。</span><span class="sxs-lookup"><span data-stu-id="5b14d-111">Pointer to the target **XLOPER** to contain the converted value.</span></span> 
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5b14d-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="5b14d-112">Property value/Return value</span></span>

<span data-ttu-id="5b14d-113">如果转换成功,**则为 TRUE** , 否则为**FALSE** 。</span><span class="sxs-lookup"><span data-stu-id="5b14d-113">**TRUE** if the conversion succeeded, **FALSE** otherwise.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="5b14d-114">注解</span><span class="sxs-lookup"><span data-stu-id="5b14d-114">Remarks</span></span>

<span data-ttu-id="5b14d-115">根据**XLOPER12**的类型, 此函数为转换的值分配一个新的内存缓冲区, 这些值指向目标**XLOPER**中的。</span><span class="sxs-lookup"><span data-stu-id="5b14d-115">Depending on the type of the **XLOPER12**, this function allocates a new memory buffer for the converted values, which are pointed to in the target **XLOPER**.</span></span> <span data-ttu-id="5b14d-116">如果转换成功, 则呼叫者负责释放与副本关联的任何内存;可以使用**FreeXLOperT** , 也可以通过使用**free**直接完成。</span><span class="sxs-lookup"><span data-stu-id="5b14d-116">The caller is responsible for freeing any memory associated with the copy if the conversion is a success; **FreeXLOperT** can be used, or it can be done directly by using **free**.</span></span>
  
<span data-ttu-id="5b14d-117">如果转换失败, 则呼叫者无需释放任何内存。</span><span class="sxs-lookup"><span data-stu-id="5b14d-117">If the conversion fails, the caller does not need to free any memory.</span></span>
  
<span data-ttu-id="5b14d-118">当**XLOPER12**包含的数组或引用太大或字符串太长而无法包含的**XLOPER**时, 从**XLOPER12**到**XLOPER**的转换可能会失败。</span><span class="sxs-lookup"><span data-stu-id="5b14d-118">Conversion from an **XLOPER12** to an **XLOPER** can fail when the **XLOPER12** contains an array or reference that is too large or a string that is too long for the **XLOPER** to contain.</span></span> 
  
<span data-ttu-id="5b14d-119">**XLOPER12**Unicode 宽字符字符串将以与区域设置相关的方式转换为**XLOPER** ASCII 字节字符串。</span><span class="sxs-lookup"><span data-stu-id="5b14d-119">**XLOPER12** Unicode wide-character strings are converted to **XLOPER** ASCII byte strings in a way that is locale-dependent.</span></span> 
  
<span data-ttu-id="5b14d-120">**XLOPER12** **xltypeInt**是一个32位带符号整数, 而**XLOPER** **xltypeInt**是一个16位带符号整数。</span><span class="sxs-lookup"><span data-stu-id="5b14d-120">The **XLOPER12** **xltypeInt** is a 32-bit signed integer, whereas the **XLOPER** **xltypeInt** is a 16-bit signed integer.</span></span> <span data-ttu-id="5b14d-121">当提供的**XLOPER12**整数超过**XLOPER**整数的限制时, 该整数将转换为8字节双精度, 并在类型**xltypeNum**的**XLOPER**中返回。</span><span class="sxs-lookup"><span data-stu-id="5b14d-121">When a supplied **XLOPER12** integer exceeds the limit of an **XLOPER** integer, the integer is converted to an 8-byte double and returned in an **XLOPER** of type **xltypeNum**.</span></span> <span data-ttu-id="5b14d-122">在这种情况下, 此函数将更改已转换的**XLOPER**的类型。</span><span class="sxs-lookup"><span data-stu-id="5b14d-122">This is the only case in which this function changes the type of the converted **XLOPER**.</span></span>
  
### <a name="example"></a><span data-ttu-id="5b14d-123">示例</span><span class="sxs-lookup"><span data-stu-id="5b14d-123">Example</span></span>

<span data-ttu-id="5b14d-124">有关此函数`\SAMPLES\FRAMEWRK\FRAMEWRK.C`的代码, 请参阅文件。</span><span class="sxs-lookup"><span data-stu-id="5b14d-124">See the file  `\SAMPLES\FRAMEWRK\FRAMEWRK.C` for the code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5b14d-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b14d-125">See also</span></span>

- [<span data-ttu-id="5b14d-126">框架库中的函数</span><span class="sxs-lookup"><span data-stu-id="5b14d-126">Functions in the Framework Library</span></span>](functions-in-the-framework-library.md)

