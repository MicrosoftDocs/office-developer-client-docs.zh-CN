---
title: xlGetInstPtr
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a166f39c-f10b-4e56-8b5d-e6a54ee08c8f
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: fd4b4ad5bf52f29384ef7e0ba738c350189f471e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310050"
---
# <a name="xlgetinstptr"></a><span data-ttu-id="08cbf-103">xlGetInstPtr</span><span class="sxs-lookup"><span data-stu-id="08cbf-103">xlGetInstPtr</span></span>

<span data-ttu-id="08cbf-104">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="08cbf-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="08cbf-105">返回当前正在调用 DLL 的 Microsoft Excel 实例的实例句柄。</span><span class="sxs-lookup"><span data-stu-id="08cbf-105">Returns the instance handle of the instance of Microsoft Excel that is currently calling a DLL.</span></span>
  
```cs
Excel4(xlGetInstPtr, LPXLOPER pxRes, 0);Excel12(xlGetInstPtr, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a><span data-ttu-id="08cbf-106">参数</span><span class="sxs-lookup"><span data-stu-id="08cbf-106">Parameters</span></span>

<span data-ttu-id="08cbf-107">此函数没有参数。</span><span class="sxs-lookup"><span data-stu-id="08cbf-107">This function has no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="08cbf-108">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="08cbf-108">Property value/Return value</span></span>

<span data-ttu-id="08cbf-109">实例句柄 (**xltypeBigData**) 将位于**bigdata**字段中。</span><span class="sxs-lookup"><span data-stu-id="08cbf-109">The instance handle (**xltypeBigData**) will be in the **val.bigdata.h.hdata** field.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="08cbf-110">注解</span><span class="sxs-lookup"><span data-stu-id="08cbf-110">Remarks</span></span>

<span data-ttu-id="08cbf-111">此函数可用于区分调用 DLL 的 Excel 的多个运行实例。</span><span class="sxs-lookup"><span data-stu-id="08cbf-111">This function can be used to distinguish between multiple running instances of Excel that are calling the DLL.</span></span>
  
<span data-ttu-id="08cbf-112">此函数将返回包含32位和64位版本的 Excel 的正确值。</span><span class="sxs-lookup"><span data-stu-id="08cbf-112">This function returns a correct value with both 32-bit and 64-bit versions of Excel.</span></span> <span data-ttu-id="08cbf-113">它在 excel 2010 中引入, 作为[xlGetInst](xlgetinst.md)函数的扩展, 它只能在32位版本的 Excel 中正常运行。</span><span class="sxs-lookup"><span data-stu-id="08cbf-113">It was introduced in Excel 2010 as an extension to the [xlGetInst](xlgetinst.md) function, which works correctly only with 32-bit versions of Excel.</span></span> 
  
<span data-ttu-id="08cbf-114">在使用 API 回调函数的[Excel4 和 Excel12](excel4-excel12.md)种类的情况调用此函数时, 该函数将正常运行, 因为**XLOPER**和**XLOPER12**都具有支持**xltypeBigData**值的相同结构类型.</span><span class="sxs-lookup"><span data-stu-id="08cbf-114">This function works correctly when it is called by using both the [Excel4 and Excel12](excel4-excel12.md) varieties of the API callback functions, because both **XLOPER** and **XLOPER12** have the same structure that supports the **xltypeBigData** value type.</span></span> 
  
## <a name="example"></a><span data-ttu-id="08cbf-115">示例</span><span class="sxs-lookup"><span data-stu-id="08cbf-115">Example</span></span>

<span data-ttu-id="08cbf-116">下面的示例将调用它的 excel 的最后一个副本的实例与调用它的 excel 的当前副本进行比较。</span><span class="sxs-lookup"><span data-stu-id="08cbf-116">The following example compares the instance of the last copy of Excel that called it to the current copy of Excel that called it.</span></span> <span data-ttu-id="08cbf-117">如果它们相同, 则返回 1; 否则返回1。如果不是, 则返回 0;如果函数失败, 则返回-1。</span><span class="sxs-lookup"><span data-stu-id="08cbf-117">If they are the same, it returns 1; if not, it returns 0; if the function fails, it returns -1.</span></span> <span data-ttu-id="08cbf-118">此示例适用于32位和64位版本的 Excel。</span><span class="sxs-lookup"><span data-stu-id="08cbf-118">This sample works with both 32-bit and 64-bit versions of Excel.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="08cbf-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08cbf-119">See also</span></span>

- [<span data-ttu-id="08cbf-120">xlGetHwnd</span><span class="sxs-lookup"><span data-stu-id="08cbf-120">xlGetHwnd</span></span>](xlgethwnd.md)
- [<span data-ttu-id="08cbf-121">xlGetInst</span><span class="sxs-lookup"><span data-stu-id="08cbf-121">xlGetInst</span></span>](xlgetinst.md)
- [<span data-ttu-id="08cbf-122">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="08cbf-122">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

