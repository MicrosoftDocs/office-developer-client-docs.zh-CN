---
title: xlAutoRemove
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAutoRemove
keywords:
- xlautoremove 函数 [excel 2007]
localization_priority: Normal
ms.assetid: fff0de4d-605d-49e6-a5be-a000410c09d8
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: af8bd2d44883b1820be42b82d4fe4794fa29caab
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425475"
---
# <a name="xlautoremove"></a><span data-ttu-id="c6848-104">xlAutoRemove</span><span class="sxs-lookup"><span data-stu-id="c6848-104">xlAutoRemove</span></span>

 <span data-ttu-id="c6848-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c6848-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="c6848-106">当用户使用外接程序管理器在 excel 会话期间停用 XLL 时, 由 Microsoft Excel 调用。</span><span class="sxs-lookup"><span data-stu-id="c6848-106">Called by Microsoft Excel whenever the user deactivates the XLL during an Excel session by using the Add-In Manager.</span></span> <span data-ttu-id="c6848-107">如果在已安装加载项的情况下 Excel 会话正常或异常关闭，则不会调用此函数。</span><span class="sxs-lookup"><span data-stu-id="c6848-107">This function is not called when an Excel session closes, normally or abnormally, with the add-in installed.</span></span>
  
<span data-ttu-id="c6848-108">此函数可用于显示一个自定义对话框, 告诉用户外接程序已停用, 或者读取或写入注册表, 例如。</span><span class="sxs-lookup"><span data-stu-id="c6848-108">This function can be used to display a custom dialog box telling the user that the add-in has been deactivated, or to read from or write to the registry, for example.</span></span>
  
<span data-ttu-id="c6848-109">Excel 不需要 XLL 即可实现和导出此函数。</span><span class="sxs-lookup"><span data-stu-id="c6848-109">Excel does not require an XLL to implement and export this function.</span></span> 
  
```cs
int WINAPI xlAutoRemove(void);
```

## <a name="parameters"></a><span data-ttu-id="c6848-110">参数</span><span class="sxs-lookup"><span data-stu-id="c6848-110">Parameters</span></span>

<span data-ttu-id="c6848-111">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="c6848-111">This function takes no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c6848-112">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="c6848-112">Property value/Return value</span></span>

<span data-ttu-id="c6848-113">此函数的实现必须返回 1 (**int**)。</span><span class="sxs-lookup"><span data-stu-id="c6848-113">Your implementation of this function must return 1 (**int**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c6848-114">说明</span><span class="sxs-lookup"><span data-stu-id="c6848-114">Remarks</span></span>

<span data-ttu-id="c6848-115">如果您的 XLL 需要在加载项管理器删除任何任务时完成任何任务, 请使用此函数。</span><span class="sxs-lookup"><span data-stu-id="c6848-115">Use this function if your XLL needs to complete any task when it is removed by the Add-In Manager.</span></span>
  
## <a name="example"></a><span data-ttu-id="c6848-116">示例</span><span class="sxs-lookup"><span data-stu-id="c6848-116">Example</span></span>

<span data-ttu-id="c6848-117">查看文件 `\SAMPLES\EXAMPLE\EXAMPLE.C` 和 `\SAMPLES\GENERIC\GENERIC.C`，了解此函数的示例实现。</span><span class="sxs-lookup"><span data-stu-id="c6848-117">See the files  `\SAMPLES\EXAMPLE\EXAMPLE.C` and  `\SAMPLES\GENERIC\GENERIC.C` for example implementations of this function.</span></span> <span data-ttu-id="c6848-118">以下代码来自 `\SAMPLES\EXAMPLE\EXAMPLE.C`。</span><span class="sxs-lookup"><span data-stu-id="c6848-118">The following code is from  `\SAMPLES\EXAMPLE\EXAMPLE.C`.</span></span>
  
```cs
int WINAPI xlAutoRemove(void)
{
/* Display a dialog box indicating that the XLL was successfully removed */
   Excel12f(xlcAlert, 0, 2,
      TempStr12(L"Thank you for removing Example.XLL!"),
      TempInt12(2));
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="c6848-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6848-119">See also</span></span>



[<span data-ttu-id="c6848-120">xlAutoAdd</span><span class="sxs-lookup"><span data-stu-id="c6848-120">xlAutoAdd</span></span>](xlautoadd.md)


[<span data-ttu-id="c6848-121">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="c6848-121">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)

