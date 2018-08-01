---
title: xlAutoOpen
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAutoOpen
keywords:
- xlautoopen 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 748cecb6-61d0-496b-a1a4-a73d22eb29e2
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: bf64841cbd75e25443abe5cfc7d3d7419757e245
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773826"
---
# <a name="xlautoopen"></a><span data-ttu-id="f5b83-104">xlAutoOpen</span><span class="sxs-lookup"><span data-stu-id="f5b83-104">xlAutoOpen</span></span>

 <span data-ttu-id="f5b83-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f5b83-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="f5b83-106">必须实现和每个有效 XLL 导出的回调函数。</span><span class="sxs-lookup"><span data-stu-id="f5b83-106">Callback function that must be implemented and exported by every valid XLL.</span></span> <span data-ttu-id="f5b83-107">**XlAutoOpen**函数是从何处到注册 XLL 函数和命令的建议的位置、 初始化数据结构、 自定义用户界面，等等。</span><span class="sxs-lookup"><span data-stu-id="f5b83-107">The **xlAutoOpen** function is the recommended place from where to register XLL functions and commands, initialize data structures, customize the user interface, and so on.</span></span> 
  
```cs
int WINAPI xlAutoOpen(void);
```

## <a name="parameters"></a><span data-ttu-id="f5b83-108">参数</span><span class="sxs-lookup"><span data-stu-id="f5b83-108">Parameters</span></span>

<span data-ttu-id="f5b83-109">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="f5b83-109">This function takes no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f5b83-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="f5b83-110">Property value/Return value</span></span>

<span data-ttu-id="f5b83-111">此函数的实现必须返回 1 (**int**)。</span><span class="sxs-lookup"><span data-stu-id="f5b83-111">Your implementation of this function must return 1 (**int**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="f5b83-112">说明</span><span class="sxs-lookup"><span data-stu-id="f5b83-112">Remarks</span></span>

<span data-ttu-id="f5b83-113">Microsoft Excel 每当激活 XLL 调用**xlAutoOpen** 。</span><span class="sxs-lookup"><span data-stu-id="f5b83-113">Microsoft Excel calls **xlAutoOpen** whenever the XLL is activated.</span></span> <span data-ttu-id="f5b83-114">XLL 激活在下列情况下：</span><span class="sxs-lookup"><span data-stu-id="f5b83-114">The XLL is activated in the following situations:</span></span> 
  
- <span data-ttu-id="f5b83-115">如果活动通常结束最后一个 Excel 会话中的 Excel 会话开头。</span><span class="sxs-lookup"><span data-stu-id="f5b83-115">At the start of an Excel session if it was active in the last Excel session that ended normally.</span></span>
    
- <span data-ttu-id="f5b83-116">如果加载 Excel 会话过程中。</span><span class="sxs-lookup"><span data-stu-id="f5b83-116">If loaded during an Excel session.</span></span>
    
- <span data-ttu-id="f5b83-117">以下几种方式，可加载 XLL:</span><span class="sxs-lookup"><span data-stu-id="f5b83-117">An XLL can be loaded in several ways:</span></span>
    
- <span data-ttu-id="f5b83-118">通过在**文件**菜单 （其中的 Excel 版本支持此方法的加载 xll （英文）） 中选择**打开**。</span><span class="sxs-lookup"><span data-stu-id="f5b83-118">By choosing **Open** on the **File** menu (where the version of Excel supports this method of loading XLLs).</span></span> 
    
- <span data-ttu-id="f5b83-119">使用加载项管理器。</span><span class="sxs-lookup"><span data-stu-id="f5b83-119">Using the Add-In Manager.</span></span>
    
- <span data-ttu-id="f5b83-120">从另一个 XLL 调用[xlfRegister](xlfregister-form-1.md)与此 DLL 作为唯一参数的名称。</span><span class="sxs-lookup"><span data-stu-id="f5b83-120">From another XLL that calls [xlfRegister](xlfregister-form-1.md) with the name of this DLL as the only argument.</span></span> 
    
- <span data-ttu-id="f5b83-121">从 XLM 宏工作表的调用[注册](xlfregister-form-1.md)的此 DLL 名称作为唯一的参数。</span><span class="sxs-lookup"><span data-stu-id="f5b83-121">From an XLM macro sheet that calls [REGISTER](xlfregister-form-1.md) with the name of this DLL as the only argument.</span></span> 
    
- <span data-ttu-id="f5b83-122">外接程序是停用和重新激活 Excel 会话期间，如果是在重新激活上调用此函数。</span><span class="sxs-lookup"><span data-stu-id="f5b83-122">If the add-in is deactivated and reactivated during an Excel session, this function is called on reactivation.</span></span>
    
### <a name="example"></a><span data-ttu-id="f5b83-123">示例</span><span class="sxs-lookup"><span data-stu-id="f5b83-123">Example</span></span>

<span data-ttu-id="f5b83-124">请参阅文件`SAMPLES\EXAMPLE\EXAMPLE.C`和`SAMPLES\GENERIC\GENERIC.C`，和例如实现此函数。</span><span class="sxs-lookup"><span data-stu-id="f5b83-124">See the files  `SAMPLES\EXAMPLE\EXAMPLE.C` and  `SAMPLES\GENERIC\GENERIC.C`, and for example implementations of this function.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f5b83-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5b83-125">See also</span></span>



[<span data-ttu-id="f5b83-126">xlAutoClose</span><span class="sxs-lookup"><span data-stu-id="f5b83-126">xlAutoClose</span></span>](xlautoclose.md)
  
[<span data-ttu-id="f5b83-127">xlAutoRegister/xlAutoRegister12</span><span class="sxs-lookup"><span data-stu-id="f5b83-127">xlAutoRegister/xlAutoRegister12</span></span>](xlautoregister-xlautoregister12.md)


[<span data-ttu-id="f5b83-128">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="f5b83-128">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)

