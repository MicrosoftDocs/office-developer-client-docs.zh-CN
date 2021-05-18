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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 66d2ac05b9603d6bb587a3898bde2545c1bb844a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407793"
---
# <a name="xladdinmanagerinfoxladdinmanagerinfo12"></a><span data-ttu-id="8db9e-104">xlAddInManagerInfo/xlAddInManagerInfo12</span><span class="sxs-lookup"><span data-stu-id="8db9e-104">xlAddInManagerInfo/xlAddInManagerInfo12</span></span>

 <span data-ttu-id="8db9e-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8db9e-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="8db9e-106">当Microsoft Excel会话中首次调用加载项管理器时，由 Excel 调用。</span><span class="sxs-lookup"><span data-stu-id="8db9e-106">Called by Microsoft Excel when the Add-in Manager is invoked for the first time in an Excel session.</span></span> <span data-ttu-id="8db9e-107">此函数用于向Add-In管理员提供有关您的外接程序的信息。</span><span class="sxs-lookup"><span data-stu-id="8db9e-107">This function is used to provide the Add-In Manager with information about your add-in.</span></span>
  
<span data-ttu-id="8db9e-108">Excel 2007 及更高版本调用 **xlAddInManagerInfo12，** 如果由 XLL 导出，将优先调用 **xlAddInManagerInfo。**</span><span class="sxs-lookup"><span data-stu-id="8db9e-108">Excel 2007 and later versions call **xlAddInManagerInfo12** in preference to **xlAddInManagerInfo** if exported by the XLL.</span></span> <span data-ttu-id="8db9e-109">**xlAddInManagerInfo12** 函数的运行方式应该与 **xlAddInManagerInfo** 相同，以避免 XLL 行为中特定于版本的差异。</span><span class="sxs-lookup"><span data-stu-id="8db9e-109">The **xlAddInManagerInfo12** function should work in the same way as **xlAddInManagerInfo** to avoid version-specific differences in the behavior of the XLL.</span></span> <span data-ttu-id="8db9e-110">Excel **xlAddInManagerInfo12** 返回 **XLOPER12** 数据类型，而 **xlAddInManagerInfo** 应返回 **XLOPER**。</span><span class="sxs-lookup"><span data-stu-id="8db9e-110">Excel expects **xlAddInManagerInfo12** to return an **XLOPER12** data type, whereas **xlAddInManagerInfo** should return an **XLOPER**.</span></span>
  
<span data-ttu-id="8db9e-111">**xlAddInManagerInfo12** 函数不是由 Excel 2007 Excel之前的版本调用的，这些版本不支持 **XLOPER12**。</span><span class="sxs-lookup"><span data-stu-id="8db9e-111">The **xlAddInManagerInfo12** function is not called by versions of Excel earlier than Excel 2007, as these do not support the **XLOPER12**.</span></span>
  
<span data-ttu-id="8db9e-112">Excel不需要 XLL 来实现和导出其中任一函数。</span><span class="sxs-lookup"><span data-stu-id="8db9e-112">Excel does not require an XLL to implement and export either of these functions.</span></span>
  
```cs
LPXLOPER WINAPI xlAddInManagerInfo(LPXLOPER pxAction);
LPXLOPER12 WINAPI xlAddInManagerInfo12(LPXLOPER12 pxAction);
```

## <a name="parameters"></a><span data-ttu-id="8db9e-113">参数</span><span class="sxs-lookup"><span data-stu-id="8db9e-113">Parameters</span></span>

 <span data-ttu-id="8db9e-114">_pxAction：_ 指向数值 **XLOPER/XLOPER12** (**xltypeInt** 或 **xltypeNum**) 。</span><span class="sxs-lookup"><span data-stu-id="8db9e-114">_pxAction:_ A pointer to a numeric **XLOPER/XLOPER12** (**xltypeInt** or **xltypeNum**).</span></span>
  
<span data-ttu-id="8db9e-115">用户Excel的信息。</span><span class="sxs-lookup"><span data-stu-id="8db9e-115">The information that Excel is asking for.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8db9e-116">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="8db9e-116">Property value/Return value</span></span>

<span data-ttu-id="8db9e-117">如果  _pxAction_ 是数字 1，或可以强制转换为数字 1，则此函数的实现应返回一个字符串，其中包含有关外接程序的一些信息，通常是其名称和版本号。</span><span class="sxs-lookup"><span data-stu-id="8db9e-117">If  _pxAction_ is, or can be coerced to, the number 1, then your implementation of this function should return a string containing some information about the add-in, typically its name and perhaps a version number.</span></span> <span data-ttu-id="8db9e-118">否则，它应返回 #VALUE！。</span><span class="sxs-lookup"><span data-stu-id="8db9e-118">Otherwise it should return #VALUE!.</span></span> 
  
<span data-ttu-id="8db9e-119">如果不返回字符串，则Excel尝试将返回的值转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="8db9e-119">If you do not return a string, Excel tries to convert the returned value to a string.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8db9e-120">备注</span><span class="sxs-lookup"><span data-stu-id="8db9e-120">Remarks</span></span>

<span data-ttu-id="8db9e-121">如果返回的字符串指向动态分配的缓冲区，则必须确保最终释放此缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8db9e-121">If the returned string points to dynamically allocated buffer, you must make sure that this buffer is eventually freed.</span></span> <span data-ttu-id="8db9e-122">如果字符串是由 Excel分配的，则通过设置 **xlbitXLFree 来这样做**。</span><span class="sxs-lookup"><span data-stu-id="8db9e-122">If the string was allocated by Excel, you do this by setting **xlbitXLFree**.</span></span> <span data-ttu-id="8db9e-123">如果字符串是由 DLL 分配的，则通过设置 **xlbitDLLFree** 来实现这一点，如果要返回 **XLOPER** () 或 **xlAutoFree12** (则还必须在 [xlAutoFree](xlautofree-xlautofree12.md)) 中实现。 </span><span class="sxs-lookup"><span data-stu-id="8db9e-123">If the string was allocated by the DLL, you do this by setting **xlbitDLLFree**, and you must also implement in [xlAutoFree](xlautofree-xlautofree12.md) (if you are returning an **XLOPER**) or **xlAutoFree12** (if you are returning an **XLOPER12**).</span></span>
  
## <a name="example"></a><span data-ttu-id="8db9e-124">示例</span><span class="sxs-lookup"><span data-stu-id="8db9e-124">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8db9e-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8db9e-125">See also</span></span>



[<span data-ttu-id="8db9e-126">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="8db9e-126">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)

