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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 9a38d5dafd30fda87dda5eadf8fa97ab6e6768a7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413757"
---
# <a name="xlautoadd"></a><span data-ttu-id="94d97-104">xlAutoAdd</span><span class="sxs-lookup"><span data-stu-id="94d97-104">xlAutoAdd</span></span>

 <span data-ttu-id="94d97-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94d97-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="94d97-106">每当用户在 Excel 会话过程中使用外接程序管理器激活 XLL 时, 都会添加 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="94d97-106">Added by Microsoft Excel whenever the user activates the XLL during an Excel session by using the Add-In Manager.</span></span> <span data-ttu-id="94d97-107">当 Excel 启动并加载预安装的加载项时, 不会调用此函数。</span><span class="sxs-lookup"><span data-stu-id="94d97-107">This function is not called when Excel starts up and loads a pre-installed add-in.</span></span>
  
<span data-ttu-id="94d97-108">此函数可用于显示一个自定义对话框, 该对话框告知用户外接程序已激活, 或者读取或写入注册表, 或者检查许可信息 (例如)。</span><span class="sxs-lookup"><span data-stu-id="94d97-108">This function can be used to display a custom dialog box that tells the user that the add-in has been activated, or to read from or write to the registry, or check licensing information, for example.</span></span>
  
<span data-ttu-id="94d97-109">Excel 不需要 XLL 即可实现和导出此函数。</span><span class="sxs-lookup"><span data-stu-id="94d97-109">Excel does not require an XLL to implement and export this function.</span></span>
  
```cs
int WINAPI xlAutoAdd(void);
```

## <a name="parameters"></a><span data-ttu-id="94d97-110">参数</span><span class="sxs-lookup"><span data-stu-id="94d97-110">Parameters</span></span>

<span data-ttu-id="94d97-111">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="94d97-111">This function takes no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="94d97-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="94d97-112">Property value/Return value</span></span>

<span data-ttu-id="94d97-113">此函数的实现应返回1。</span><span class="sxs-lookup"><span data-stu-id="94d97-113">Your implementation of this function should return 1.</span></span> <span data-ttu-id="94d97-114">(**int**)。</span><span class="sxs-lookup"><span data-stu-id="94d97-114">(**int**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="94d97-115">说明</span><span class="sxs-lookup"><span data-stu-id="94d97-115">Remarks</span></span>

<span data-ttu-id="94d97-116">如果 XLL 在加载项管理器添加时需要执行的操作, 请使用此函数。</span><span class="sxs-lookup"><span data-stu-id="94d97-116">Use this function if there is anything your XLL needs to do when it is added by the Add-In Manager.</span></span>
  
## <a name="example"></a><span data-ttu-id="94d97-117">示例</span><span class="sxs-lookup"><span data-stu-id="94d97-117">Example</span></span>

<span data-ttu-id="94d97-118">请`\SAMPLES\EXAMPLE\EXAMPLE.C`参阅`\SAMPLES\GENERIC\GENERIC.C`和, 以了解此函数的示例实现。</span><span class="sxs-lookup"><span data-stu-id="94d97-118">See  `\SAMPLES\EXAMPLE\EXAMPLE.C` and  `\SAMPLES\GENERIC\GENERIC.C` for example implementations of this function.</span></span> <span data-ttu-id="94d97-119">以下代码来自 `\SAMPLES\EXAMPLE\EXAMPLE.C`。</span><span class="sxs-lookup"><span data-stu-id="94d97-119">The following code is from  `\SAMPLES\EXAMPLE\EXAMPLE.C`.</span></span>
  
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

## <a name="see-also"></a><span data-ttu-id="94d97-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94d97-120">See also</span></span>



[<span data-ttu-id="94d97-121">xlAutoRemove</span><span class="sxs-lookup"><span data-stu-id="94d97-121">xlAutoRemove</span></span>](xlautoremove.md)


[<span data-ttu-id="94d97-122">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="94d97-122">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)

