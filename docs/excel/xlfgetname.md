---
title: xlfGetName
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
keywords:
- xlfgetname
localization_priority: Normal
ms.assetid: 65780435-aaa2-47af-b44f-07be7aa769ee
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: fdee0146ae2199097828e98abb96ffe43a64fc80
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436627"
---
# <a name="xlfgetname"></a><span data-ttu-id="5a0ad-104">xlfGetName</span><span class="sxs-lookup"><span data-stu-id="5a0ad-104">xlfGetName</span></span>

<span data-ttu-id="5a0ad-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5a0ad-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="5a0ad-106">返回名称显示在 "**名称管理器**" 对话框 (在 "**公式**" 选项卡上 "**定义的名称**" 部分中单击 "**名称管理器**" 时显示) 中的 "**引用**" 列中显示的名称定义。如果定义中包含引用, 则将它们作为 R1C1 样式的引用提供。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-106">Returns the definition of a name as it appears in the **Refers to** column of the **Name Manager** dialog box, which is displayed when you click **Name Manager** in the **Defined Names** section on the **Formulas** tab. If the definition contains references, they are given as R1C1-style references.</span></span> <span data-ttu-id="5a0ad-107">使用**xlfGetName**检查名称定义的值。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-107">Use **xlfGetName** to check the value defined by a name.</span></span> <span data-ttu-id="5a0ad-108">若要获取与定义对应的名称, 请使用[xlfGetDef](xlfgetdef.md)。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-108">To get the name that corresponds to a definition, use [xlfGetDef](xlfgetdef.md).</span></span>
  
```cpp
Excel12(xlfGetName, LPXLOPER12 pxRes, 2, LPXLOPER12 pxNameText, LPXLOPER12 pxInfoType);
```

## <a name="parameters"></a><span data-ttu-id="5a0ad-109">参数</span><span class="sxs-lookup"><span data-stu-id="5a0ad-109">Parameters</span></span>

<span data-ttu-id="5a0ad-110">_pxNameText_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="5a0ad-110">_pxNameText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="5a0ad-111">可以是在工作表上定义的名称;对在活动工作簿上定义的名称的外部引用, 例如`"!Sales"`;或对在特定打开的工作簿上定义的名称的外部引用, 例如`"[Book1]SHEET1!Sales"`。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-111">Can be a name defined on the sheet; an external reference to a name defined on the active workbook, for example,  `"!Sales"`; or an external reference to a name defined on a particular open workbook, for example,  `"[Book1]SHEET1!Sales"`.</span></span>  <span data-ttu-id="5a0ad-112">_pxNameText_也可以是一个隐藏的名称。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-112">_pxNameText_ can also be a hidden name.</span></span> 
  
<span data-ttu-id="5a0ad-113">_pxInfoType_(**xltypeBool**)</span><span class="sxs-lookup"><span data-stu-id="5a0ad-113">_pxInfoType_ (**xltypeBool**)</span></span>
  
<span data-ttu-id="5a0ad-114">指定要返回的有关名称的信息类型。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-114">Specifies the type of information to return about the name.</span></span> <span data-ttu-id="5a0ad-115">如果**为 FALSE**或省略, 则返回定义。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-115">If **FALSE** or omitted, the definition is returned.</span></span> <span data-ttu-id="5a0ad-116">如果**为 true**, 则如果只为工作表定义名称, 则返回**true** ; 如果为整个工作簿定义了名称, 则返回**FALSE** 。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-116">If **TRUE**, returns **TRUE** if the name is defined for just the sheet, **FALSE** if the name is defined for the entire workbook.</span></span> 
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5a0ad-117">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="5a0ad-117">Property value/Return value</span></span>

<span data-ttu-id="5a0ad-118">_pxRes_(**xltypeStr**、 **xltypeBool**或**xltypeErr**)</span><span class="sxs-lookup"><span data-stu-id="5a0ad-118">_pxRes_ (**xltypeStr**, **xltypeBool**, or **xltypeErr**)</span></span>
  
<span data-ttu-id="5a0ad-119">根据为_pxInfoType_传递的值, 返回指定名称 (**xltypeStr**) 的定义, 或者**TRUE**或**FALSE** (**xltypeBool**)。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-119">Depending on the value passed for  _pxInfoType_, returns the definition of the specified name (**xltypeStr**), or **TRUE** or **FALSE** (**xltypeBool**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5a0ad-120">说明</span><span class="sxs-lookup"><span data-stu-id="5a0ad-120">Remarks</span></span>

<span data-ttu-id="5a0ad-121">如果已在 "**保护工作表**" 对话框中选中 "**保护工作表和锁定的单元格内容**" 复选框, 以保护包含该名称的`#N/A`工作簿, 则**xlfGetName**将返回错误值。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-121">If the **Protect worksheet and contents of locked cells** check box has been selected in the **Protect Sheet** dialog box to protect the workbook containing the name, **xlfGetName** returns the  `#N/A` error value.</span></span> <span data-ttu-id="5a0ad-122">若要查看**保护工作表**对话框, 请单击 "**审阅**" 选项卡的 "**更改**" 部分中的 "**保护工作表**"。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-122">To see the **Protect Sheet** dialog box, click **Protect Sheet** in the **Changes** section of the **Review** tab.</span></span> 
  
<span data-ttu-id="5a0ad-123">下表列出了使用指定的_pxNameText_参数调用**xlfGetDef**时返回的值的三个示例。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-123">The following table lists three examples of the values returned by a call to **xlfGetDef** with the specified  _pxNameText_ argument.</span></span> 
  
|<span data-ttu-id="5a0ad-124">**Excel 中的定义**</span><span class="sxs-lookup"><span data-stu-id="5a0ad-124">**Definition in Excel**</span></span>|<span data-ttu-id="5a0ad-125">**_pxNameText_**</span><span class="sxs-lookup"><span data-stu-id="5a0ad-125">**_pxNameText_**</span></span>|<span data-ttu-id="5a0ad-126">**返回的值**</span><span class="sxs-lookup"><span data-stu-id="5a0ad-126">**Value Returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5a0ad-127">工作表上的名称 Sales 定义为数字523。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-127">The name Sales on a sheet is defined as the number 523.</span></span>  <br/> |<span data-ttu-id="5a0ad-128">销售</span><span class="sxs-lookup"><span data-stu-id="5a0ad-128">"Sales"</span></span>  <br/> |<span data-ttu-id="5a0ad-129">"= 523"</span><span class="sxs-lookup"><span data-stu-id="5a0ad-129">"=523"</span></span>  <br/> |
|<span data-ttu-id="5a0ad-130">活动工作表上的名称利润定义为公式 = Sales-成本。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-130">The name Profit on the active sheet is defined as the formula =Sales-Costs.</span></span>  <br/> |<span data-ttu-id="5a0ad-131">"!盈利</span><span class="sxs-lookup"><span data-stu-id="5a0ad-131">"!Profit"</span></span>  <br/> |<span data-ttu-id="5a0ad-132">"= 销售-成本"</span><span class="sxs-lookup"><span data-stu-id="5a0ad-132">"=Sales-Costs"</span></span>  <br/> |
|<span data-ttu-id="5a0ad-133">活动工作表上的名称数据库定义为区域 A1: F500。</span><span class="sxs-lookup"><span data-stu-id="5a0ad-133">The name Database on the active sheet is defined as the range A1:F500.</span></span>  <br/> |<span data-ttu-id="5a0ad-134">"!数据库</span><span class="sxs-lookup"><span data-stu-id="5a0ad-134">"!Database"</span></span>  <br/> |<span data-ttu-id="5a0ad-135">"= R1C1: R500C6"</span><span class="sxs-lookup"><span data-stu-id="5a0ad-135">"=R1C1:R500C6"</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5a0ad-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a0ad-136">See also</span></span>

- [<span data-ttu-id="5a0ad-137">xlfGetDef</span><span class="sxs-lookup"><span data-stu-id="5a0ad-137">xlfGetDef</span></span>](xlfgetdef.md)
- [<span data-ttu-id="5a0ad-138">实用的基本 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="5a0ad-138">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

