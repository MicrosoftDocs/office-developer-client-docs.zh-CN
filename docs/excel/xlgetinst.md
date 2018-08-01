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
ms.openlocfilehash: 9484f7bbc1f5e0fc5b0def17f2ce79ef226dcd17
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773851"
---
# <a name="xlgetinst"></a><span data-ttu-id="44106-104">xlGetInst</span><span class="sxs-lookup"><span data-stu-id="44106-104">xlGetInst</span></span>

 <span data-ttu-id="44106-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="44106-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="44106-106">返回当前正在呼叫 DLL 的 Microsoft Excel 实例的实例句柄。</span><span class="sxs-lookup"><span data-stu-id="44106-106">Returns the instance handle of the instance of Microsoft Excel that is currently calling a DLL.</span></span>
  
```cs
Excel4(xlGetInst, LPXLOPER pxRes, 0); /* returns low part only */
Excel12(xlGetInst, LPXLOPER12 pxRes, 0); /* returns full handle */
```

## <a name="parameters"></a><span data-ttu-id="44106-107">参数</span><span class="sxs-lookup"><span data-stu-id="44106-107">Parameters</span></span>

<span data-ttu-id="44106-108">此函数具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="44106-108">This function has no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="44106-109">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="44106-109">Property value/Return value</span></span>

<span data-ttu-id="44106-110">在**val.w**字段将实例句柄 (**xltypeInt**)。</span><span class="sxs-lookup"><span data-stu-id="44106-110">The instance handle (**xltypeInt**) will be in the **val.w** field.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="44106-111">说明</span><span class="sxs-lookup"><span data-stu-id="44106-111">Remarks</span></span>

<span data-ttu-id="44106-112">用于区分多个运行实例 Excel 的 DLL 调用此函数。</span><span class="sxs-lookup"><span data-stu-id="44106-112">This function can be used to distinguish between multiple running instances of Excel that are calling the DLL.</span></span>
  
<span data-ttu-id="44106-113">返回的 XLOPER integer 变量时要调用此函数使用[Excel4](excel4-excel12.md)或[Excel4v](excel4v-excel12v.md)，为签名的 16 位短 int。这是只可以包含低 16 位的 32 位 Windows 句柄。</span><span class="sxs-lookup"><span data-stu-id="44106-113">When you are calling this function using [Excel4](excel4-excel12.md) or [Excel4v](excel4v-excel12v.md), the returned XLOPER integer variable is a signed 16-bit short int. This is only capable of containing the low 16 bits of the 32-bit Windows handle.</span></span> <span data-ttu-id="44106-114">从 Excel 2007 开始， **XLOPER12**整数变量是带符号的 32 位 int 和因此包含整个窗口的句，而不必循环访问所有打开的窗口。</span><span class="sxs-lookup"><span data-stu-id="44106-114">Starting in Excel 2007, the integer variable of the **XLOPER12** is a signed 32-bit int and therefore contains the entire handle, removing the need to iterate all open windows.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="44106-115">如果与 64 位版本的 Microsoft Excel 使用**xlGetInst**函数，则将失败函数。</span><span class="sxs-lookup"><span data-stu-id="44106-115">If the **xlGetInst** function is used with the 64-bit version of Microsoft Excel, then the function will fail.</span></span> <span data-ttu-id="44106-116">这是因为**xltypeInt**值类型不宽到足以容纳在这种情况下返回 Excel 的 64 位长句柄。</span><span class="sxs-lookup"><span data-stu-id="44106-116">This is because the **xltypeInt** value type is not wide enough to hold the 64-bit long handle returned by Excel in this case.</span></span> <span data-ttu-id="44106-117">为此，Excel 2010 引入了新的函数名为[xlGetInstPtr](xlgetinstptr.md)，与 Excel 的 32 位和 64 位版本正确运行。</span><span class="sxs-lookup"><span data-stu-id="44106-117">For this purpose, Excel 2010 introduced a new function named [xlGetInstPtr](xlgetinstptr.md), which runs correctly with both the 32-bit and 64-bit versions of Excel.</span></span> 
  
## <a name="example"></a><span data-ttu-id="44106-118">示例</span><span class="sxs-lookup"><span data-stu-id="44106-118">Example</span></span>

<span data-ttu-id="44106-119">下面的示例将实例调用于调用它的 Excel 的当前副本的 Excel 的最后一个副本进行比较。</span><span class="sxs-lookup"><span data-stu-id="44106-119">The following example compares the instance of the last copy of Excel that called it to the current copy of Excel that called it.</span></span> <span data-ttu-id="44106-120">如果它们是相同的则将返回 1;如果没有，则返回 0;如果函数失败，则返回-1。</span><span class="sxs-lookup"><span data-stu-id="44106-120">If they are the same, it returns 1; if not, it returns 0; if the function fails, it returns -1.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="44106-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44106-121">See also</span></span>



[<span data-ttu-id="44106-122">xlGetHwnd</span><span class="sxs-lookup"><span data-stu-id="44106-122">xlGetHwnd</span></span>](xlgethwnd.md)
  
[<span data-ttu-id="44106-123">xlGetInstPtr</span><span class="sxs-lookup"><span data-stu-id="44106-123">xlGetInstPtr</span></span>](xlgetinstptr.md)


[<span data-ttu-id="44106-124">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="44106-124">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

