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
ms.openlocfilehash: e42cca809c4426ddf9a98b3b275d08490d31c8db
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773819"
---
# <a name="xladdinmanagerinfoxladdinmanagerinfo12"></a><span data-ttu-id="1de20-104">xlAddInManagerInfo/xlAddInManagerInfo12</span><span class="sxs-lookup"><span data-stu-id="1de20-104">xlAddInManagerInfo/xlAddInManagerInfo12</span></span>

 <span data-ttu-id="1de20-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1de20-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="1de20-106">由 Microsoft Excel 加载项管理器调用 Excel 会话中第一次时调用。</span><span class="sxs-lookup"><span data-stu-id="1de20-106">Called by Microsoft Excel when the Add-in Manager is invoked for the first time in an Excel session.</span></span> <span data-ttu-id="1de20-107">此函数用于外接程序经理提供有关加载项的信息。</span><span class="sxs-lookup"><span data-stu-id="1de20-107">This function is used to provide the Add-In Manager with information about your add-in.</span></span>
  
<span data-ttu-id="1de20-108">如果导出 XLL，Excel 2007 和更高版本调用**xlAddInManagerInfo12**优先于**xlAddInManagerInfo** 。</span><span class="sxs-lookup"><span data-stu-id="1de20-108">Excel 2007 and later versions call **xlAddInManagerInfo12** in preference to **xlAddInManagerInfo** if exported by the XLL.</span></span> <span data-ttu-id="1de20-109">**XlAddInManagerInfo12**函数应从事方式相同**xlAddInManagerInfo**以避免 XLL 的行为的特定于版本的差异。</span><span class="sxs-lookup"><span data-stu-id="1de20-109">The **xlAddInManagerInfo12** function should work in the same way as **xlAddInManagerInfo** to avoid version-specific differences in the behavior of the XLL.</span></span> <span data-ttu-id="1de20-110">Excel 希望**xlAddInManagerInfo12**返回**XLOPER12**数据类型，而**xlAddInManagerInfo**应返回**XLOPER**。</span><span class="sxs-lookup"><span data-stu-id="1de20-110">Excel expects **xlAddInManagerInfo12** to return an **XLOPER12** data type, whereas **xlAddInManagerInfo** should return an **XLOPER**.</span></span>
  
<span data-ttu-id="1de20-111">因为这些不支持**XLOPER12**早于 Excel 2007 版本的 Excel 不调用**xlAddInManagerInfo12**函数。</span><span class="sxs-lookup"><span data-stu-id="1de20-111">The **xlAddInManagerInfo12** function is not called by versions of Excel earlier than Excel 2007, as these do not support the **XLOPER12**.</span></span>
  
<span data-ttu-id="1de20-112">Excel 不需要 XLL 实施和导出其中任一函数。</span><span class="sxs-lookup"><span data-stu-id="1de20-112">Excel does not require an XLL to implement and export either of these functions.</span></span>
  
```cs
LPXLOPER WINAPI xlAddInManagerInfo(LPXLOPER pxAction);
LPXLOPER12 WINAPI xlAddInManagerInfo12(LPXLOPER12 pxAction);
```

## <a name="parameters"></a><span data-ttu-id="1de20-113">参数</span><span class="sxs-lookup"><span data-stu-id="1de20-113">Parameters</span></span>

 <span data-ttu-id="1de20-114">_pxAction:_ 指向 （**xltypeInt**或**xltypeNum**） 数字**XLOPER/XLOPER12**的指针。</span><span class="sxs-lookup"><span data-stu-id="1de20-114">_pxAction:_ A pointer to a numeric **XLOPER/XLOPER12** (**xltypeInt** or **xltypeNum**).</span></span>
  
<span data-ttu-id="1de20-115">Excel 要求的信息。</span><span class="sxs-lookup"><span data-stu-id="1de20-115">The information that Excel is asking for.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1de20-116">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="1de20-116">Property value/Return value</span></span>

<span data-ttu-id="1de20-117">如果_pxAction_ ，或可以强制为，数字 1，此函数的实现应返回包含一些有关外接程序、 通常其名称和可能的版本号的字符串。</span><span class="sxs-lookup"><span data-stu-id="1de20-117">If  _pxAction_ is, or can be coerced to, the number 1, then your implementation of this function should return a string containing some information about the add-in, typically its name and perhaps a version number.</span></span> <span data-ttu-id="1de20-118">否则，它应返回 #VALUE ！。</span><span class="sxs-lookup"><span data-stu-id="1de20-118">Otherwise it should return #VALUE!.</span></span> 
  
<span data-ttu-id="1de20-119">如果不返回一个字符串，Excel 会尝试将返回的值转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="1de20-119">If you do not return a string, Excel tries to convert the returned value to a string.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1de20-120">说明</span><span class="sxs-lookup"><span data-stu-id="1de20-120">Remarks</span></span>

<span data-ttu-id="1de20-121">如果返回的字符串指向动态分配缓冲区，您必须确保最终释放的此缓冲区。</span><span class="sxs-lookup"><span data-stu-id="1de20-121">If the returned string points to dynamically allocated buffer, you must make sure that this buffer is eventually freed.</span></span> <span data-ttu-id="1de20-122">如果该字符串由 Excel 分配，您需要执行此操作通过设置**xlbitXLFree**。</span><span class="sxs-lookup"><span data-stu-id="1de20-122">If the string was allocated by Excel, you do this by setting **xlbitXLFree**.</span></span> <span data-ttu-id="1de20-123">如果字符串已分配 DLL，设置**xlbitDLLFree**，通过实现此目的，您还必须实现[xlAutoFree](xlautofree-xlautofree12.md) （如果您返回**XLOPER**） 或**xlAutoFree12**中 （如果您返回**XLOPER12**）。</span><span class="sxs-lookup"><span data-stu-id="1de20-123">If the string was allocated by the DLL, you do this by setting **xlbitDLLFree**, and you must also implement in [xlAutoFree](xlautofree-xlautofree12.md) (if you are returning an **XLOPER**) or **xlAutoFree12** (if you are returning an **XLOPER12**).</span></span>
  
## <a name="example"></a><span data-ttu-id="1de20-124">示例</span><span class="sxs-lookup"><span data-stu-id="1de20-124">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1de20-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1de20-125">See also</span></span>



[<span data-ttu-id="1de20-126">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="1de20-126">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)

