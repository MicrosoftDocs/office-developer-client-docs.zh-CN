---
title: xlAddInManagerInfo/xlAddInManagerInfo12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAddInManagerInfo
keywords:
- xladdinmanagerinfo 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 63a73cd2-6479-4233-ad68-93379f940717
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 66d2ac05b9603d6bb587a3898bde2545c1bb844a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303994"
---
# <a name="xladdinmanagerinfoxladdinmanagerinfo12"></a><span data-ttu-id="06e33-104">xlAddInManagerInfo/xlAddInManagerInfo12</span><span class="sxs-lookup"><span data-stu-id="06e33-104">xlAddInManagerInfo/xlAddInManagerInfo12</span></span>

 <span data-ttu-id="06e33-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="06e33-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="06e33-106">在 excel 会话中首次调用外接程序管理器时, 由 Microsoft Excel 调用。</span><span class="sxs-lookup"><span data-stu-id="06e33-106">Called by Microsoft Excel when the Add-in Manager is invoked for the first time in an Excel session.</span></span> <span data-ttu-id="06e33-107">此函数用于向外接程序管理器提供有关外接程序的信息。</span><span class="sxs-lookup"><span data-stu-id="06e33-107">This function is used to provide the Add-In Manager with information about your add-in.</span></span>
  
<span data-ttu-id="06e33-108">如果 XLL 导出了 Excel 2007 及更高版本, 则将首选项中的**xlAddInManagerInfo12**调用**xlAddInManagerInfo** 。</span><span class="sxs-lookup"><span data-stu-id="06e33-108">Excel 2007 and later versions call **xlAddInManagerInfo12** in preference to **xlAddInManagerInfo** if exported by the XLL.</span></span> <span data-ttu-id="06e33-109">**xlAddInManagerInfo12**函数应以与**xlAddInManagerInfo**相同的方式工作, 以避免 XLL 行为中特定于版本的差异。</span><span class="sxs-lookup"><span data-stu-id="06e33-109">The **xlAddInManagerInfo12** function should work in the same way as **xlAddInManagerInfo** to avoid version-specific differences in the behavior of the XLL.</span></span> <span data-ttu-id="06e33-110">Excel 要求**xlAddInManagerInfo12**返回**XLOPER12**数据类型, 而**xlAddInManagerInfo**应返回一个**XLOPER**。</span><span class="sxs-lookup"><span data-stu-id="06e33-110">Excel expects **xlAddInManagerInfo12** to return an **XLOPER12** data type, whereas **xlAddInManagerInfo** should return an **XLOPER**.</span></span>
  
<span data-ttu-id="06e33-111">excel 2007 之前的 excel 版本不会调用**xlAddInManagerInfo12**函数, 因为它们不支持**XLOPER12**。</span><span class="sxs-lookup"><span data-stu-id="06e33-111">The **xlAddInManagerInfo12** function is not called by versions of Excel earlier than Excel 2007, as these do not support the **XLOPER12**.</span></span>
  
<span data-ttu-id="06e33-112">Excel 不需要 XLL 即可实现和导出这两个函数中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="06e33-112">Excel does not require an XLL to implement and export either of these functions.</span></span>
  
```cs
LPXLOPER WINAPI xlAddInManagerInfo(LPXLOPER pxAction);
LPXLOPER12 WINAPI xlAddInManagerInfo12(LPXLOPER12 pxAction);
```

## <a name="parameters"></a><span data-ttu-id="06e33-113">参数</span><span class="sxs-lookup"><span data-stu-id="06e33-113">Parameters</span></span>

 <span data-ttu-id="06e33-114">_pxAction:_ 指向数字**XLOPER/XLOPER12** (**xltypeInt**或**xltypeNum**) 的指针。</span><span class="sxs-lookup"><span data-stu-id="06e33-114">_pxAction:_ A pointer to a numeric **XLOPER/XLOPER12** (**xltypeInt** or **xltypeNum**).</span></span>
  
<span data-ttu-id="06e33-115">Excel 所要求的信息。</span><span class="sxs-lookup"><span data-stu-id="06e33-115">The information that Excel is asking for.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="06e33-116">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="06e33-116">Property value/Return value</span></span>

<span data-ttu-id="06e33-117">如果_pxAction_为或可以强制为数字 1, 则此函数的实现应返回一个字符串, 其中包含有关外接程序的一些信息, 通常是它的名称, 也可能是版本号。</span><span class="sxs-lookup"><span data-stu-id="06e33-117">If  _pxAction_ is, or can be coerced to, the number 1, then your implementation of this function should return a string containing some information about the add-in, typically its name and perhaps a version number.</span></span> <span data-ttu-id="06e33-118">否则, 它应返回 #VALUE!。</span><span class="sxs-lookup"><span data-stu-id="06e33-118">Otherwise it should return #VALUE!.</span></span> 
  
<span data-ttu-id="06e33-119">如果不返回字符串, Excel 将尝试将返回的值转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="06e33-119">If you do not return a string, Excel tries to convert the returned value to a string.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="06e33-120">注解</span><span class="sxs-lookup"><span data-stu-id="06e33-120">Remarks</span></span>

<span data-ttu-id="06e33-121">如果返回的字符串指向动态分配的缓冲区, 则必须确保最终释放此缓冲区。</span><span class="sxs-lookup"><span data-stu-id="06e33-121">If the returned string points to dynamically allocated buffer, you must make sure that this buffer is eventually freed.</span></span> <span data-ttu-id="06e33-122">如果该字符串是由 Excel 分配的, 则可以通过设置**xlbitXLFree**来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="06e33-122">If the string was allocated by Excel, you do this by setting **xlbitXLFree**.</span></span> <span data-ttu-id="06e33-123">如果该字符串是由 DLL 分配的, 则可以通过设置**xlbitDLLFree**来执行此操作, 此外, 还必须在[xlAutoFree](xlautofree-xlautofree12.md)中实现 (如果要返回**XLOPER**) 或**xlAutoFree12** (如果要返回**XLOPER12**)。</span><span class="sxs-lookup"><span data-stu-id="06e33-123">If the string was allocated by the DLL, you do this by setting **xlbitDLLFree**, and you must also implement in [xlAutoFree](xlautofree-xlautofree12.md) (if you are returning an **XLOPER**) or **xlAutoFree12** (if you are returning an **XLOPER12**).</span></span>
  
## <a name="example"></a><span data-ttu-id="06e33-124">示例</span><span class="sxs-lookup"><span data-stu-id="06e33-124">Example</span></span>

 `\SAMPLES\GENERIC\GENERIC.C`
  
```cs
LPXLOPER12 WINAPI xlAddInManagerInfo12(LPXLOPER12 xAction)
{
    static XLOPER12 xInfo, xIntAction;
/*
** This code coerces the passed-in value to an integer. This is how the
** code determines what is being requested. If it receives a 1, it returns a
** string representing the long name. If it receives anything else, it
** returns a #VALUE! error.
*/
    Excel12f(xlCoerce, &xIntAction, 2, xAction, TempInt12(xltypeInt));
    if(xIntAction.val.w == 1) 
    {
        xInfo.xltype = xltypeStr;
        xInfo.val.str = L"\026Example Standalone DLL";
    }
    else 
    {
        xInfo.xltype = xltypeErr;
        xInfo.val.err = xlerrValue;
    }
// Word of caution - returning static XLOPERs/XLOPER12s is not thread safe
// for UDFs declared as thread safe. Use alternate memory allocation mechanisms.
    return (LPXLOPER12)&xInfo;
} 

```

## <a name="see-also"></a><span data-ttu-id="06e33-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06e33-125">See also</span></span>



[<span data-ttu-id="06e33-126">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="06e33-126">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)

