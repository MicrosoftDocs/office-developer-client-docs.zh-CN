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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: bf02f71458f2f4d8514f69a6b6f0921b5318303a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406645"
---
# <a name="xlautoopen"></a><span data-ttu-id="6e0da-104">xlAutoOpen</span><span class="sxs-lookup"><span data-stu-id="6e0da-104">xlAutoOpen</span></span>

 <span data-ttu-id="6e0da-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6e0da-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="6e0da-106">必须由每个有效的 XLL 实现和导出的回调函数。</span><span class="sxs-lookup"><span data-stu-id="6e0da-106">Callback function that must be implemented and exported by every valid XLL.</span></span> <span data-ttu-id="6e0da-107">**建议使用 xlAutoOpen** 函数注册 XLL 函数和命令、初始化数据结构、自定义用户界面等。</span><span class="sxs-lookup"><span data-stu-id="6e0da-107">The **xlAutoOpen** function is the recommended place from where to register XLL functions and commands, initialize data structures, customize the user interface, and so on.</span></span> 
  
```cs
int WINAPI xlAutoOpen(void);
```

## <a name="parameters"></a><span data-ttu-id="6e0da-108">参数</span><span class="sxs-lookup"><span data-stu-id="6e0da-108">Parameters</span></span>

<span data-ttu-id="6e0da-109">此函数无需使用任何参数。</span><span class="sxs-lookup"><span data-stu-id="6e0da-109">This function takes no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="6e0da-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="6e0da-110">Property value/Return value</span></span>

<span data-ttu-id="6e0da-111">此函数的实现必须返回 1 (**int**)。</span><span class="sxs-lookup"><span data-stu-id="6e0da-111">Your implementation of this function must return 1 (**int**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="6e0da-112">说明</span><span class="sxs-lookup"><span data-stu-id="6e0da-112">Remarks</span></span>

<span data-ttu-id="6e0da-113">Microsoft Excel **激活 XLL 时调用 xlAutoOpen。**</span><span class="sxs-lookup"><span data-stu-id="6e0da-113">Microsoft Excel calls **xlAutoOpen** whenever the XLL is activated.</span></span> <span data-ttu-id="6e0da-114">在下列情况下将激活 XLL：</span><span class="sxs-lookup"><span data-stu-id="6e0da-114">The XLL is activated in the following situations:</span></span> 
  
- <span data-ttu-id="6e0da-115">在会话会话的Excel，如果它在正常结束的上一Excel会话处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="6e0da-115">At the start of an Excel session if it was active in the last Excel session that ended normally.</span></span>
    
- <span data-ttu-id="6e0da-116">如果在会话期间加载Excel会话。</span><span class="sxs-lookup"><span data-stu-id="6e0da-116">If loaded during an Excel session.</span></span>
    
- <span data-ttu-id="6e0da-117">可以通过多种方式加载 XLL：</span><span class="sxs-lookup"><span data-stu-id="6e0da-117">An XLL can be loaded in several ways:</span></span>
    
- <span data-ttu-id="6e0da-118">选择"**文件**"菜单上的"打开 (，其中 Excel 支持此方法加载 XLL) 。</span><span class="sxs-lookup"><span data-stu-id="6e0da-118">By choosing **Open** on the **File** menu (where the version of Excel supports this method of loading XLLs).</span></span> 
    
- <span data-ttu-id="6e0da-119">使用加载项管理器。</span><span class="sxs-lookup"><span data-stu-id="6e0da-119">Using the Add-In Manager.</span></span>
    
- <span data-ttu-id="6e0da-120">从另一个调用 [xlfRegister](xlfregister-form-1.md) 的 XLL 中，此 DLL 的名称作为唯一参数。</span><span class="sxs-lookup"><span data-stu-id="6e0da-120">From another XLL that calls [xlfRegister](xlfregister-form-1.md) with the name of this DLL as the only argument.</span></span> 
    
- <span data-ttu-id="6e0da-121">从调用 [REGISTER](xlfregister-form-1.md) 的 XLM 宏工作表中，此 DLL 的名称作为唯一参数。</span><span class="sxs-lookup"><span data-stu-id="6e0da-121">From an XLM macro sheet that calls [REGISTER](xlfregister-form-1.md) with the name of this DLL as the only argument.</span></span> 
    
- <span data-ttu-id="6e0da-122">如果在重新激活会话期间停用并重新激活Excel，则重新激活时将调用此函数。</span><span class="sxs-lookup"><span data-stu-id="6e0da-122">If the add-in is deactivated and reactivated during an Excel session, this function is called on reactivation.</span></span>
    
### <a name="example"></a><span data-ttu-id="6e0da-123">示例</span><span class="sxs-lookup"><span data-stu-id="6e0da-123">Example</span></span>

<span data-ttu-id="6e0da-124">请参阅 文件和  `SAMPLES\EXAMPLE\EXAMPLE.C`  `SAMPLES\GENERIC\GENERIC.C` ，有关此函数的示例实现。</span><span class="sxs-lookup"><span data-stu-id="6e0da-124">See the files  `SAMPLES\EXAMPLE\EXAMPLE.C` and  `SAMPLES\GENERIC\GENERIC.C`, and for example implementations of this function.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6e0da-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e0da-125">See also</span></span>



[<span data-ttu-id="6e0da-126">xlAutoClose</span><span class="sxs-lookup"><span data-stu-id="6e0da-126">xlAutoClose</span></span>](xlautoclose.md)
  
[<span data-ttu-id="6e0da-127">xlAutoRegister/xlAutoRegister12</span><span class="sxs-lookup"><span data-stu-id="6e0da-127">xlAutoRegister/xlAutoRegister12</span></span>](xlautoregister-xlautoregister12.md)


[<span data-ttu-id="6e0da-128">加载项管理器和 XLL 接口函数</span><span class="sxs-lookup"><span data-stu-id="6e0da-128">Add-in Manager and XLL Interface Functions</span></span>](add-in-manager-and-xll-interface-functions.md)

