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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e113ddbf55e2b4651d578549802c44e2c6413a18
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303848"
---
# <a name="xlgetinst"></a><span data-ttu-id="e2669-104">xlGetInst</span><span class="sxs-lookup"><span data-stu-id="e2669-104">xlGetInst</span></span>

 <span data-ttu-id="e2669-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e2669-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="e2669-106">返回当前正在调用 DLL 的 Microsoft Excel 实例的实例句柄。</span><span class="sxs-lookup"><span data-stu-id="e2669-106">Returns the instance handle of the instance of Microsoft Excel that is currently calling a DLL.</span></span>
  
```cs
Excel4(xlGetInst, LPXLOPER pxRes, 0); /* returns low part only */
Excel12(xlGetInst, LPXLOPER12 pxRes, 0); /* returns full handle */
```

## <a name="parameters"></a><span data-ttu-id="e2669-107">参数</span><span class="sxs-lookup"><span data-stu-id="e2669-107">Parameters</span></span>

<span data-ttu-id="e2669-108">此函数没有参数。</span><span class="sxs-lookup"><span data-stu-id="e2669-108">This function has no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e2669-109">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="e2669-109">Property value/Return value</span></span>

<span data-ttu-id="e2669-110">实例句柄 (**xltypeInt**) 将位于 " **w** " 字段中。</span><span class="sxs-lookup"><span data-stu-id="e2669-110">The instance handle (**xltypeInt**) will be in the **val.w** field.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="e2669-111">注解</span><span class="sxs-lookup"><span data-stu-id="e2669-111">Remarks</span></span>

<span data-ttu-id="e2669-112">此函数可用于区分调用 DLL 的 Excel 的多个运行实例。</span><span class="sxs-lookup"><span data-stu-id="e2669-112">This function can be used to distinguish between multiple running instances of Excel that are calling the DLL.</span></span>
  
<span data-ttu-id="e2669-113">使用[Excel4](excel4-excel12.md)或[Excel4v](excel4v-excel12v.md)调用此函数时, 返回的 XLOPER 整数变量是带符号的16位短整型。这只能包含32位 Windows 句柄的低16位。</span><span class="sxs-lookup"><span data-stu-id="e2669-113">When you are calling this function using [Excel4](excel4-excel12.md) or [Excel4v](excel4v-excel12v.md), the returned XLOPER integer variable is a signed 16-bit short int. This is only capable of containing the low 16 bits of the 32-bit Windows handle.</span></span> <span data-ttu-id="e2669-114">从 Excel 2007 开始, **XLOPER12**的整数变量是一个有符号的32位 int, 因此包含整个句柄, 从而消除了对所有打开的窗口进行迭代的需求。</span><span class="sxs-lookup"><span data-stu-id="e2669-114">Starting in Excel 2007, the integer variable of the **XLOPER12** is a signed 32-bit int and therefore contains the entire handle, removing the need to iterate all open windows.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e2669-115">如果将**xlGetInst**函数与64位版本的 Microsoft Excel 一起使用, 则函数将失败。</span><span class="sxs-lookup"><span data-stu-id="e2669-115">If the **xlGetInst** function is used with the 64-bit version of Microsoft Excel, then the function will fail.</span></span> <span data-ttu-id="e2669-116">这是因为**xltypeInt**值类型的宽度不足以容纳 Excel 在这种情况下返回的64位长句柄。</span><span class="sxs-lookup"><span data-stu-id="e2669-116">This is because the **xltypeInt** value type is not wide enough to hold the 64-bit long handle returned by Excel in this case.</span></span> <span data-ttu-id="e2669-117">为了实现此目的, excel 2010 引入了一个名为[xlGetInstPtr](xlgetinstptr.md)的新函数, 该函数可以使用32位和64位版本的 Excel 来正常运行。</span><span class="sxs-lookup"><span data-stu-id="e2669-117">For this purpose, Excel 2010 introduced a new function named [xlGetInstPtr](xlgetinstptr.md), which runs correctly with both the 32-bit and 64-bit versions of Excel.</span></span> 
  
## <a name="example"></a><span data-ttu-id="e2669-118">示例</span><span class="sxs-lookup"><span data-stu-id="e2669-118">Example</span></span>

<span data-ttu-id="e2669-119">下面的示例将调用它的 excel 的最后一个副本的实例与调用它的 excel 的当前副本进行比较。</span><span class="sxs-lookup"><span data-stu-id="e2669-119">The following example compares the instance of the last copy of Excel that called it to the current copy of Excel that called it.</span></span> <span data-ttu-id="e2669-120">如果它们相同, 则返回 1; 否则返回1。如果不是, 则返回 0;如果函数失败, 则返回-1。</span><span class="sxs-lookup"><span data-stu-id="e2669-120">If they are the same, it returns 1; if not, it returns 0; if the function fails, it returns -1.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="e2669-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2669-121">See also</span></span>



[<span data-ttu-id="e2669-122">xlGetHwnd</span><span class="sxs-lookup"><span data-stu-id="e2669-122">xlGetHwnd</span></span>](xlgethwnd.md)
  
[<span data-ttu-id="e2669-123">xlGetInstPtr</span><span class="sxs-lookup"><span data-stu-id="e2669-123">xlGetInstPtr</span></span>](xlgetinstptr.md)


[<span data-ttu-id="e2669-124">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="e2669-124">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

