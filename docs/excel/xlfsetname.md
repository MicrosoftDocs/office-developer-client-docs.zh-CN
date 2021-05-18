---
title: xlfSetName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfSetName
keywords:
- xlfsetname 函数 [excel 2007]
localization_priority: Normal
ms.assetid: ea7fd713-7c1b-4648-a609-3334f595c61a
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e6327ccf2cd18e42c3ef9abe538e6f669e498352
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404258"
---
# <a name="xlfsetname"></a><span data-ttu-id="b1a3e-104">xlfSetName</span><span class="sxs-lookup"><span data-stu-id="b1a3e-104">xlfSetName</span></span>

<span data-ttu-id="b1a3e-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b1a3e-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="b1a3e-106">用于创建和删除与 DLL 关联的已定义名称。</span><span class="sxs-lookup"><span data-stu-id="b1a3e-106">Used to create and delete defined names associated with the DLL.</span></span>
  
```cs
Excel12(xlfSetName, LPXLOPER12 pxRes, 2, LPXLOPER12 pxNameText, LPXLOPER12 pxNameDefinition);
```

## <a name="parameters"></a><span data-ttu-id="b1a3e-107">参数</span><span class="sxs-lookup"><span data-stu-id="b1a3e-107">Parameters</span></span>

<span data-ttu-id="b1a3e-108">_pxNameText_ (**xltypeStr**) </span><span class="sxs-lookup"><span data-stu-id="b1a3e-108">_pxNameText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="b1a3e-109">区域的名称，它应符合对有效名称Microsoft Excel的常规限制。</span><span class="sxs-lookup"><span data-stu-id="b1a3e-109">The name of the range, which should conform to the usual limitations in Microsoft Excel on valid names.</span></span>
  
<span data-ttu-id="b1a3e-110">_pxNameDefinition_ **(xltypeStr**、 **xltypeNum**、 **xltypeBool**、 **xltypeErr**、 **xltypeMulti**、 **xltypeSRef**、 **xltypeRef** 或 **xltypeInt**) </span><span class="sxs-lookup"><span data-stu-id="b1a3e-110">_pxNameDefinition_ (**xltypeStr**, **xltypeNum**, **xltypeBool**, **xltypeErr**, **xltypeMulti**, **xltypeSRef**, **xltypeRef**, or **xltypeInt**)</span></span>
  
<span data-ttu-id="b1a3e-111"> (可选) 。</span><span class="sxs-lookup"><span data-stu-id="b1a3e-111">(Optional).</span></span> <span data-ttu-id="b1a3e-112">_pxNameText_ 定义为的值、值集、单元格或单元格区域。</span><span class="sxs-lookup"><span data-stu-id="b1a3e-112">The value, set of values, cell, or range of cells that  _pxNameText_ is defined as.</span></span> <span data-ttu-id="b1a3e-113">如果省略，将删除该名称。</span><span class="sxs-lookup"><span data-stu-id="b1a3e-113">If omitted, the name is deleted.</span></span> 
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b1a3e-114">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="b1a3e-114">Property value/Return value</span></span>

<span data-ttu-id="b1a3e-115">_pxRes_ (**xltypeBool** 或 **xltypeErr)**</span><span class="sxs-lookup"><span data-stu-id="b1a3e-115">_pxRes_ (**xltypeBool** or **xltypeErr**)</span></span>
  
<span data-ttu-id="b1a3e-116">如果操作成功，则其为 TRUE;如果无法创建或删除名称，则其为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="b1a3e-116">TRUE if the operation succeeded or FALSE if the name could not be created or deleted.</span></span> <span data-ttu-id="b1a3e-117">返回#VALUE！</span><span class="sxs-lookup"><span data-stu-id="b1a3e-117">Returns #VALUE!</span></span> <span data-ttu-id="b1a3e-118">如果一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="b1a3e-118">if one or more of the arguments was invalid.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b1a3e-119">备注</span><span class="sxs-lookup"><span data-stu-id="b1a3e-119">Remarks</span></span>

<span data-ttu-id="b1a3e-120">使用 **xlfRegister** 和有效的 _pxFunctionText_ 参数注册函数或命令时，Excel创建与 DLL 资源关联的名称。</span><span class="sxs-lookup"><span data-stu-id="b1a3e-120">When a function or command is registered using **xlfRegister** with a valid  _pxFunctionText_ argument, Excel creates a name associated with the DLL resource.</span></span> <span data-ttu-id="b1a3e-121">卸载 DLL 时，应该使用 [xlfSetName](xlfsetname.md)函数删除此类名称。</span><span class="sxs-lookup"><span data-stu-id="b1a3e-121">When your DLL is being unloaded, such names should be deleted using the [xlfSetName function](xlfsetname.md).</span></span> <span data-ttu-id="b1a3e-122">但是，由于此删除操作中Excel问题，此删除操作将失败。</span><span class="sxs-lookup"><span data-stu-id="b1a3e-122">However, due to a known issue in Excel, this deletion operation fails.</span></span> <span data-ttu-id="b1a3e-123">有关详细信息，请参阅 [Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。</span><span class="sxs-lookup"><span data-stu-id="b1a3e-123">For more information, see [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
### <a name="example"></a><span data-ttu-id="b1a3e-124">示例</span><span class="sxs-lookup"><span data-stu-id="b1a3e-124">Example</span></span>

<span data-ttu-id="b1a3e-125">请参阅 中的 **xlAutoClose** 函数的代码  `\SAMPLES\GENERIC\GENERIC.C` 。</span><span class="sxs-lookup"><span data-stu-id="b1a3e-125">See the code for the **xlAutoClose** function in  `\SAMPLES\GENERIC\GENERIC.C`.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b1a3e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1a3e-126">See also</span></span>

- [<span data-ttu-id="b1a3e-127">实用的基本 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="b1a3e-127">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

