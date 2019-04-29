---
title: xlGetHwnd
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlGetHwnd
keywords:
- xlgethwnd 函数 [excel 2007]
localization_priority: Normal
ms.assetid: be33b097-812b-4f5c-81be-4d9673e95b0b
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: ab4ac1bc040ef2ea9bca182624111e03722c5200
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425454"
---
# <a name="xlgethwnd"></a><span data-ttu-id="bce5c-104">xlGetHwnd</span><span class="sxs-lookup"><span data-stu-id="bce5c-104">xlGetHwnd</span></span>

<span data-ttu-id="bce5c-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bce5c-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="bce5c-106">返回顶级 Microsoft Excel 窗口的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="bce5c-106">Returns the window handle of the top-level Microsoft Excel window.</span></span>
  
```cs
Excel4(xlGetHwnd, LPXLOPER pxRes, 0); /* returns low part only */
Excel12(xlGetHwnd, LPXLOPER12 pxRes, 0); /* returns full handle */
```

## <a name="parameters"></a><span data-ttu-id="bce5c-107">参数</span><span class="sxs-lookup"><span data-stu-id="bce5c-107">Parameters</span></span>

<span data-ttu-id="bce5c-108">此函数没有参数。</span><span class="sxs-lookup"><span data-stu-id="bce5c-108">This function has no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="bce5c-109">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="bce5c-109">Property value/Return value</span></span>

<span data-ttu-id="bce5c-110">在 " **w** " 字段中包含窗口句柄 (**xltypeInt**)。</span><span class="sxs-lookup"><span data-stu-id="bce5c-110">Contains the window handle (**xltypeInt**) in the **val.w** field.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="bce5c-111">说明</span><span class="sxs-lookup"><span data-stu-id="bce5c-111">Remarks</span></span>

<span data-ttu-id="bce5c-112">此函数对于编写 Windows API 代码很有用。</span><span class="sxs-lookup"><span data-stu-id="bce5c-112">This function is useful for writing Windows API code.</span></span>
  
<span data-ttu-id="bce5c-113">使用[Excel4](excel4-excel12.md)或[Excel4v](excel4v-excel12v.md)调用此函数时, 返回的 XLOPER 整数变量是带符号的16位短整型。这只能包含32位 Windows 句柄的低16位。</span><span class="sxs-lookup"><span data-stu-id="bce5c-113">When you call this function using [Excel4](excel4-excel12.md) or [Excel4v](excel4v-excel12v.md), the returned XLOPER integer variable is a signed 16-bit short int. This is only capable of containing the low 16 bits of the 32-bit Windows handle.</span></span> <span data-ttu-id="bce5c-114">若要查找高部分, 您的代码必须循环访问所有打开的窗口, 查找低部分的匹配项。</span><span class="sxs-lookup"><span data-stu-id="bce5c-114">To find the high part, your code must iterate through all open windows looking for a match with the low part.</span></span> <span data-ttu-id="bce5c-115">从 Excel 2007 开始, **XLOPER12**的整数变量是一个有符号的32位 int, 因此包含整个句柄, 从而消除了对所有打开的窗口进行迭代的需求。</span><span class="sxs-lookup"><span data-stu-id="bce5c-115">Starting in Excel 2007, the integer variable of the **XLOPER12** is a signed 32-bit int and therefore contains the entire handle, removing the need to iterate all open windows.</span></span> 
  
### <a name="example"></a><span data-ttu-id="bce5c-116">示例</span><span class="sxs-lookup"><span data-stu-id="bce5c-116">Example</span></span>

<span data-ttu-id="bce5c-117">请参阅中`SAMPLES\GENERIC\GENERIC.C`的[fShowDialog 函数](fshowdialog.md)的代码。</span><span class="sxs-lookup"><span data-stu-id="bce5c-117">See the code for the [fShowDialog function](fshowdialog.md) in  `SAMPLES\GENERIC\GENERIC.C`.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bce5c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bce5c-118">See also</span></span>

- [<span data-ttu-id="bce5c-119">xlGetInst</span><span class="sxs-lookup"><span data-stu-id="bce5c-119">xlGetInst</span></span>](xlgetinst.md)
- [<span data-ttu-id="bce5c-120">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="bce5c-120">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

