---
title: xlGetInstPtr
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a166f39c-f10b-4e56-8b5d-e6a54ee08c8f
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 7cc07093e5db335d01fe85527746594d34d4d938
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773863"
---
# <a name="xlgetinstptr"></a><span data-ttu-id="a11c9-103">xlGetInstPtr</span><span class="sxs-lookup"><span data-stu-id="a11c9-103">xlGetInstPtr</span></span>

<span data-ttu-id="a11c9-104">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a11c9-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="a11c9-105">返回当前正在呼叫 DLL 的 Microsoft Excel 实例的实例句柄。</span><span class="sxs-lookup"><span data-stu-id="a11c9-105">Returns the instance handle of the instance of Microsoft Excel that is currently calling a DLL.</span></span>
  
```cs
Excel4(xlGetInstPtr, LPXLOPER pxRes, 0);Excel12(xlGetInstPtr, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a><span data-ttu-id="a11c9-106">参数</span><span class="sxs-lookup"><span data-stu-id="a11c9-106">Parameters</span></span>

<span data-ttu-id="a11c9-107">此函数具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="a11c9-107">This function has no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a11c9-108">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="a11c9-108">Property value/Return value</span></span>

<span data-ttu-id="a11c9-109">在**val.bigdata.h.hdata**字段将实例句柄 (**xltypeBigData**)。</span><span class="sxs-lookup"><span data-stu-id="a11c9-109">The instance handle (**xltypeBigData**) will be in the **val.bigdata.h.hdata** field.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="a11c9-110">说明</span><span class="sxs-lookup"><span data-stu-id="a11c9-110">Remarks</span></span>

<span data-ttu-id="a11c9-111">用于区分多个运行实例 Excel 的 DLL 调用此函数。</span><span class="sxs-lookup"><span data-stu-id="a11c9-111">This function can be used to distinguish between multiple running instances of Excel that are calling the DLL.</span></span>
  
<span data-ttu-id="a11c9-112">此函数返回与 32 位和 64 位版本的 Excel 的正确值。</span><span class="sxs-lookup"><span data-stu-id="a11c9-112">This function returns a correct value with both 32-bit and 64-bit versions of Excel.</span></span> <span data-ttu-id="a11c9-113">它引入了 Excel 2010 中作为扩展到[xlGetInst](xlgetinst.md)函数，仅与 32 位版本的 Excel 一起正常运行。</span><span class="sxs-lookup"><span data-stu-id="a11c9-113">It was introduced in Excel 2010 as an extension to the [xlGetInst](xlgetinst.md) function, which works correctly only with 32-bit versions of Excel.</span></span> 
  
<span data-ttu-id="a11c9-114">因为**XLOPER**和**XLOPER12**具有相同的结构支持**xltypeBigData**值使用的 API 回调函数中， [Excel4 和 Excel12](excel4-excel12.md)类别调用时此函数的运行正常类型。</span><span class="sxs-lookup"><span data-stu-id="a11c9-114">This function works correctly when it is called by using both the [Excel4 and Excel12](excel4-excel12.md) varieties of the API callback functions, because both **XLOPER** and **XLOPER12** have the same structure that supports the **xltypeBigData** value type.</span></span> 
  
## <a name="example"></a><span data-ttu-id="a11c9-115">示例</span><span class="sxs-lookup"><span data-stu-id="a11c9-115">Example</span></span>

<span data-ttu-id="a11c9-116">下面的示例将实例调用于调用它的 Excel 的当前副本的 Excel 的最后一个副本进行比较。</span><span class="sxs-lookup"><span data-stu-id="a11c9-116">The following example compares the instance of the last copy of Excel that called it to the current copy of Excel that called it.</span></span> <span data-ttu-id="a11c9-117">如果它们是相同的则将返回 1;如果没有，则返回 0;如果函数失败，则返回-1。</span><span class="sxs-lookup"><span data-stu-id="a11c9-117">If they are the same, it returns 1; if not, it returns 0; if the function fails, it returns -1.</span></span> <span data-ttu-id="a11c9-118">此示例使用 32 位和 64 位版本的 Excel 工作正常。</span><span class="sxs-lookup"><span data-stu-id="a11c9-118">This sample works with both 32-bit and 64-bit versions of Excel.</span></span>
  
`\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlGetInstPtrExample(void)
{
    XLOPER12 xRes;
    static HANDLE hOld = 0;
    short iRet;
    if (Excel12(xlGetInstPtr, &xRes, 0) != xlretSuccess)
    iRet = -1;
    else
    {
    HANDLE hNew;
    hNew =  xRes.val.bigdata.h.hdata;
    if (hNew != hOld)
    iRet = 0;
    else
    iRet = 1;
    hOld = hNew;
    }
    return iRet;
}
```

## <a name="see-also"></a><span data-ttu-id="a11c9-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a11c9-119">See also</span></span>

- [<span data-ttu-id="a11c9-120">xlGetHwnd</span><span class="sxs-lookup"><span data-stu-id="a11c9-120">xlGetHwnd</span></span>](xlgethwnd.md)
- [<span data-ttu-id="a11c9-121">xlGetInst</span><span class="sxs-lookup"><span data-stu-id="a11c9-121">xlGetInst</span></span>](xlgetinst.md)
- [<span data-ttu-id="a11c9-122">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="a11c9-122">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

