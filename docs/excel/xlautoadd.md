---
title: xlAutoAdd
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAutoAdd
keywords:
- xlautoadd 函数 [excel 2007]
localization_priority: Normal
ms.assetid: c69299af-a28a-44d9-be10-9c9fb92e21f2
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: ae0b4ae2d5f5fc58c3e18ffa9d79ec4128cb4639
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773825"
---
# <a name="xlautoadd"></a><span data-ttu-id="5d100-104">xlAutoAdd</span><span class="sxs-lookup"><span data-stu-id="5d100-104">xlAutoAdd</span></span>

 <span data-ttu-id="5d100-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5d100-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="5d100-106">添加 Microsoft excel 每当用户激活 Excel 会话期间 XLL 使用加载项管理器。</span><span class="sxs-lookup"><span data-stu-id="5d100-106">Added by Microsoft Excel whenever the user activates the XLL during an Excel session by using the Add-In Manager.</span></span> <span data-ttu-id="5d100-107">Excel 启动和加载预安装的加载项时，不会调用此函数。</span><span class="sxs-lookup"><span data-stu-id="5d100-107">This function is not called when Excel starts up and loads a pre-installed add-in.</span></span>
  
<span data-ttu-id="5d100-108">可以使用此函数以显示自定义对话框中，告知用户的外接程序已被激活，或要读取或写入注册表，例如检查许可信息。</span><span class="sxs-lookup"><span data-stu-id="5d100-108">This function can be used to display a custom dialog box that tells the user that the add-in has been activated, or to read from or write to the registry, or check licensing information, for example.</span></span>
  
<span data-ttu-id="5d100-109">Excel 不需要 XLL 实施和导出此函数。</span><span class="sxs-lookup"><span data-stu-id="5d100-109">Excel does not require an XLL to implement and export this function.</span></span>
  
```cs
int WINAPI xlAutoAdd(void);
```

## <a name="parameters"></a><span data-ttu-id="5d100-110">参数</span><span class="sxs-lookup"><span data-stu-id="5d100-110">Parameters</span></span>

<span data-ttu-id="5d100-111">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="5d100-111">This function takes no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5d100-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="5d100-112">Property value/Return value</span></span>

<span data-ttu-id="5d100-113">此函数的实现应返回 1。</span><span class="sxs-lookup"><span data-stu-id="5d100-113">Your implementation of this function should return 1.</span></span> <span data-ttu-id="5d100-114">(**int**)。</span><span class="sxs-lookup"><span data-stu-id="5d100-114">(**int**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5d100-115">说明</span><span class="sxs-lookup"><span data-stu-id="5d100-115">Remarks</span></span>

<span data-ttu-id="5d100-116">如果没有任何您 XLL 需要执行添加由加载项管理器时，请使用此函数。</span><span class="sxs-lookup"><span data-stu-id="5d100-116">Use this function if there is anything your XLL needs to do when it is added by the Add-In Manager.</span></span>
  
## <a name="example"></a><span data-ttu-id="5d100-117">示例</span><span class="sxs-lookup"><span data-stu-id="5d100-117">Example</span></span>

<span data-ttu-id="5d100-118">请参阅`\SAMPLES\EXAMPLE\EXAMPLE.C`和`\SAMPLES\GENERIC\GENERIC.C`，例如此函数的实现。</span><span class="sxs-lookup"><span data-stu-id="5d100-118">See  `\SAMPLES\EXAMPLE\EXAMPLE.C` and  `\SAMPLES\GENERIC\GENERIC.C` for example implementations of this function.</span></span> <span data-ttu-id="5d100-119">以下代码来自 `\SAMPLES\EXAMPLE\EXAMPLE.C`。</span><span class="sxs-lookup"><span data-stu-id="5d100-119">The following code is from  `\SAMPLES\EXAMPLE\EXAMPLE.C`.</span></span>
  
```cs
int WINAPI xlAutoAdd(void)
{
    XCHAR szBuf[255];
    wsprintfW((LPWSTR)szBuf, L"Thank you for adding Example.XLL\n"
            L"build date %hs, time %hs",__DATE__, __TIME__);
/* Display a dialog indicating that the XLL was successfully added */
    Excel12f(xlcAlert, 0, 2, TempStr12(szBuf), TempInt12(2));
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="5d100-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d100-120">See also</span></span>



[<span data-ttu-id="5d100-121">xlAutoRemove</span><span class="sxs-lookup"><span data-stu-id="5d100-121">xlAutoRemove</span></span>](xlautoremove.md)


[<span data-ttu-id="5d100-122">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="5d100-122">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)

