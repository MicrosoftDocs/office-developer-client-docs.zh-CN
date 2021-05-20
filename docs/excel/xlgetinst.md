---
title: xlGetInst
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlGetInst
keywords:
- xlgetinst 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 631a8f4e-ea7c-4743-9ee1-b2233fd7d98d
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e113ddbf55e2b4651d578549802c44e2c6413a18
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428128"
---
# <a name="xlgetinst"></a><span data-ttu-id="ef8e8-104">xlGetInst</span><span class="sxs-lookup"><span data-stu-id="ef8e8-104">xlGetInst</span></span>

 <span data-ttu-id="ef8e8-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ef8e8-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="ef8e8-106">返回当前调用 DLL Microsoft Excel实例的实例句柄。</span><span class="sxs-lookup"><span data-stu-id="ef8e8-106">Returns the instance handle of the instance of Microsoft Excel that is currently calling a DLL.</span></span>
  
```cs
Excel4(xlGetInst, LPXLOPER pxRes, 0); /* returns low part only */
Excel12(xlGetInst, LPXLOPER12 pxRes, 0); /* returns full handle */
```

## <a name="parameters"></a><span data-ttu-id="ef8e8-107">参数</span><span class="sxs-lookup"><span data-stu-id="ef8e8-107">Parameters</span></span>

<span data-ttu-id="ef8e8-108">此函数没有参数。</span><span class="sxs-lookup"><span data-stu-id="ef8e8-108">This function has no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ef8e8-109">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="ef8e8-109">Property value/Return value</span></span>

<span data-ttu-id="ef8e8-110">**xltypeInt (将**) **val.w** 字段中。</span><span class="sxs-lookup"><span data-stu-id="ef8e8-110">The instance handle (**xltypeInt**) will be in the **val.w** field.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="ef8e8-111">备注</span><span class="sxs-lookup"><span data-stu-id="ef8e8-111">Remarks</span></span>

<span data-ttu-id="ef8e8-112">此函数可用于区分调用 DLL 的 Excel实例。</span><span class="sxs-lookup"><span data-stu-id="ef8e8-112">This function can be used to distinguish between multiple running instances of Excel that are calling the DLL.</span></span>
  
<span data-ttu-id="ef8e8-113">使用 Excel4 或[Excel4v](excel4-excel12.md)调用此函数时，返回的 XLOPER 整数变量是一个有符号的 16 位短整型整数。 [](excel4v-excel12v.md)这只能包含 32 位句柄的低 16 Windows位。</span><span class="sxs-lookup"><span data-stu-id="ef8e8-113">When you are calling this function using [Excel4](excel4-excel12.md) or [Excel4v](excel4v-excel12v.md), the returned XLOPER integer variable is a signed 16-bit short int. This is only capable of containing the low 16 bits of the 32-bit Windows handle.</span></span> <span data-ttu-id="ef8e8-114">从 Excel 2007 开始 **，XLOPER12** 的整数变量是一个已签名的 32 位 int，因此包含整个句柄，无需重新访问所有打开的窗口。</span><span class="sxs-lookup"><span data-stu-id="ef8e8-114">Starting in Excel 2007, the integer variable of the **XLOPER12** is a signed 32-bit int and therefore contains the entire handle, removing the need to iterate all open windows.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ef8e8-115">如果 **xlGetInst** 函数与 64 位版本的 Microsoft Excel一起使用，该函数将失败。</span><span class="sxs-lookup"><span data-stu-id="ef8e8-115">If the **xlGetInst** function is used with the 64-bit version of Microsoft Excel, then the function will fail.</span></span> <span data-ttu-id="ef8e8-116">这是因为 **xltypeInt** 值类型不够宽，无法容纳由 Excel返回的 64 位长句柄。</span><span class="sxs-lookup"><span data-stu-id="ef8e8-116">This is because the **xltypeInt** value type is not wide enough to hold the 64-bit long handle returned by Excel in this case.</span></span> <span data-ttu-id="ef8e8-117">为此，Excel 2010 引入了名为[xlGetInstPtr](xlgetinstptr.md)的新函数，该函数在 32 位和 64 位版本的 Excel 中均正常运行。</span><span class="sxs-lookup"><span data-stu-id="ef8e8-117">For this purpose, Excel 2010 introduced a new function named [xlGetInstPtr](xlgetinstptr.md), which runs correctly with both the 32-bit and 64-bit versions of Excel.</span></span> 
  
## <a name="example"></a><span data-ttu-id="ef8e8-118">示例</span><span class="sxs-lookup"><span data-stu-id="ef8e8-118">Example</span></span>

<span data-ttu-id="ef8e8-119">下面的示例将最后一个调用该副本的 Excel 实例与调用它的Excel副本进行比较。</span><span class="sxs-lookup"><span data-stu-id="ef8e8-119">The following example compares the instance of the last copy of Excel that called it to the current copy of Excel that called it.</span></span> <span data-ttu-id="ef8e8-120">如果二者相同，则返回 1;如果没有，则返回 0;如果函数失败，则返回 -1。</span><span class="sxs-lookup"><span data-stu-id="ef8e8-120">If they are the same, it returns 1; if not, it returns 0; if the function fails, it returns -1.</span></span>
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlGetInstExample(void)
{
    XLOPER12 xRes;
    static HANDLE hOld = 0;
    short iRet;
    if (Excel12(xlGetInst, &xRes, 0) != xlretSuccess)
        iRet = -1;
    else
    {
    HANDLE hNew;
    hNew = (HANDLE)xRes.val.w;
    if (hNew != hOld)
            iRet = 0;
    else
            iRet = 1;
    hOld = hNew;
    }
    return iRet;
}
```

## <a name="see-also"></a><span data-ttu-id="ef8e8-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef8e8-121">See also</span></span>



[<span data-ttu-id="ef8e8-122">xlGetHwnd</span><span class="sxs-lookup"><span data-stu-id="ef8e8-122">xlGetHwnd</span></span>](xlgethwnd.md)
  
[<span data-ttu-id="ef8e8-123">xlGetInstPtr</span><span class="sxs-lookup"><span data-stu-id="ef8e8-123">xlGetInstPtr</span></span>](xlgetinstptr.md)


[<span data-ttu-id="ef8e8-124">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="ef8e8-124">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

