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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 48ce927f6bcb328a90779948a660cf9d0b460205
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773841"
---
# <a name="xlfsetname"></a><span data-ttu-id="15fa5-104">xlfSetName</span><span class="sxs-lookup"><span data-stu-id="15fa5-104">xlfSetName</span></span>

<span data-ttu-id="15fa5-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="15fa5-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="15fa5-106">用于创建和删除已定义的名称 DLL 相关联。</span><span class="sxs-lookup"><span data-stu-id="15fa5-106">Used to create and delete defined names associated with the DLL.</span></span>
  
```cs
Excel12(xlfSetName, LPXLOPER12 pxRes, 2, LPXLOPER12 pxNameText, LPXLOPER12 pxNameDefinition);
```

## <a name="parameters"></a><span data-ttu-id="15fa5-107">参数</span><span class="sxs-lookup"><span data-stu-id="15fa5-107">Parameters</span></span>

<span data-ttu-id="15fa5-108">_pxNameText_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="15fa5-108">_pxNameText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="15fa5-109">有效的名称通常限制在 Microsoft Excel 中应符合范围的名称。</span><span class="sxs-lookup"><span data-stu-id="15fa5-109">The name of the range, which should conform to the usual limitations in Microsoft Excel on valid names.</span></span>
  
<span data-ttu-id="15fa5-110">_pxNameDefinition_（**xltypeStr**、 **xltypeNum**、 **xltypeBool**、 **xltypeErr**、 **xltypeMulti**、 **xltypeSRef**、 **xltypeRef**或**xltypeInt**）</span><span class="sxs-lookup"><span data-stu-id="15fa5-110">_pxNameDefinition_ (**xltypeStr**, **xltypeNum**, **xltypeBool**, **xltypeErr**, **xltypeMulti**, **xltypeSRef**, **xltypeRef**, or **xltypeInt**)</span></span>
  
<span data-ttu-id="15fa5-111">（可选）。</span><span class="sxs-lookup"><span data-stu-id="15fa5-111">(Optional).</span></span> <span data-ttu-id="15fa5-112">值、 值、 单元格或单元格区域的设置的_pxNameText_被定义为。</span><span class="sxs-lookup"><span data-stu-id="15fa5-112">The value, set of values, cell, or range of cells that  _pxNameText_ is defined as.</span></span> <span data-ttu-id="15fa5-113">如果省略，则删除名称。</span><span class="sxs-lookup"><span data-stu-id="15fa5-113">If omitted, the name is deleted.</span></span> 
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="15fa5-114">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="15fa5-114">Property value/Return value</span></span>

<span data-ttu-id="15fa5-115">_pxRes_（**xltypeBool**或**xltypeErr**）</span><span class="sxs-lookup"><span data-stu-id="15fa5-115">_pxRes_ (**xltypeBool** or **xltypeErr**)</span></span>
  
<span data-ttu-id="15fa5-116">如果操作成功，则返回 TRUE 或 FALSE，如果无法创建或删除名称。</span><span class="sxs-lookup"><span data-stu-id="15fa5-116">TRUE if the operation succeeded or FALSE if the name could not be created or deleted.</span></span> <span data-ttu-id="15fa5-117">返回 #VALUE ！</span><span class="sxs-lookup"><span data-stu-id="15fa5-117">Returns #VALUE!</span></span> <span data-ttu-id="15fa5-118">如果一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="15fa5-118">if one or more of the arguments was invalid.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="15fa5-119">备注</span><span class="sxs-lookup"><span data-stu-id="15fa5-119">Remarks</span></span>

<span data-ttu-id="15fa5-120">使用有效_pxFunctionText_参数**xlfRegister**注册函数或命令，Excel 将新建关联的 DLL 资源的名称。</span><span class="sxs-lookup"><span data-stu-id="15fa5-120">When a function or command is registered using **xlfRegister** with a valid  _pxFunctionText_ argument, Excel creates a name associated with the DLL resource.</span></span> <span data-ttu-id="15fa5-121">当正在卸载 DLL 时，应使用[xlfSetName 函数](xlfsetname.md)删除此类名称。</span><span class="sxs-lookup"><span data-stu-id="15fa5-121">When your DLL is being unloaded, such names should be deleted using the [xlfSetName function](xlfsetname.md).</span></span> <span data-ttu-id="15fa5-122">但是，由于在 Excel 中的已知问题，此删除操作失败。</span><span class="sxs-lookup"><span data-stu-id="15fa5-122">However, due to a known issue in Excel, this deletion operation fails.</span></span> <span data-ttu-id="15fa5-123">有关详细信息，请参阅[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)。</span><span class="sxs-lookup"><span data-stu-id="15fa5-123">For more information, see [Known Issues in Excel XLL Development](known-issues-in-excel-xll-development.md).</span></span>
  
### <a name="example"></a><span data-ttu-id="15fa5-124">示例</span><span class="sxs-lookup"><span data-stu-id="15fa5-124">Example</span></span>

<span data-ttu-id="15fa5-125">请参阅**xlAutoClose**函数中的代码`\SAMPLES\GENERIC\GENERIC.C`。</span><span class="sxs-lookup"><span data-stu-id="15fa5-125">See the code for the **xlAutoClose** function in  `\SAMPLES\GENERIC\GENERIC.C`.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="15fa5-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15fa5-126">See also</span></span>

- [<span data-ttu-id="15fa5-127">关键及有用的 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="15fa5-127">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

