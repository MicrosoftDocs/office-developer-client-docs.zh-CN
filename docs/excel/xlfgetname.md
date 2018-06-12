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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 63bfc6e94950a621c2367b2d35d25e3de48b344f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773840"
---
# <a name="xlfgetname"></a><span data-ttu-id="92275-104">xlfGetName</span><span class="sxs-lookup"><span data-stu-id="92275-104">xlfGetName</span></span>

<span data-ttu-id="92275-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92275-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="92275-106">返回的**名称管理器**对话框中，单击**公式**选项卡**定义名称**部分中的**名称管理器**时显示**引用位置**列中显示名称的定义。如果定义中包含的引用，它们可作为 R1C1-样式引用。</span><span class="sxs-lookup"><span data-stu-id="92275-106">Returns the definition of a name as it appears in the **Refers to** column of the **Name Manager** dialog box, which is displayed when you click **Name Manager** in the **Defined Names** section on the **Formulas** tab. If the definition contains references, they are given as R1C1-style references.</span></span> <span data-ttu-id="92275-107">使用**xlfGetName**检查由 name 定义的值。</span><span class="sxs-lookup"><span data-stu-id="92275-107">Use **xlfGetName** to check the value defined by a name.</span></span> <span data-ttu-id="92275-108">若要获取对应于定义的名称，请使用[xlfGetDef](xlfgetdef.md)。</span><span class="sxs-lookup"><span data-stu-id="92275-108">To get the name that corresponds to a definition, use [xlfGetDef](xlfgetdef.md).</span></span>
  
```cpp
Excel12(xlfGetName, LPXLOPER12 pxRes, 2, LPXLOPER12 pxNameText, LPXLOPER12 pxInfoType);
```

## <a name="parameters"></a><span data-ttu-id="92275-109">参数</span><span class="sxs-lookup"><span data-stu-id="92275-109">Parameters</span></span>

<span data-ttu-id="92275-110">_pxNameText_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="92275-110">_pxNameText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="92275-111">可以名称定义了工作表;对活动工作簿，例如上, 定义的名称的外部引用`"!Sales"`;外部引用特定打开工作簿，例如，已定义的名称或`"[Book1]SHEET1!Sales"`。</span><span class="sxs-lookup"><span data-stu-id="92275-111">Can be a name defined on the sheet; an external reference to a name defined on the active workbook, for example,  `"!Sales"`; or an external reference to a name defined on a particular open workbook, for example,  `"[Book1]SHEET1!Sales"`.</span></span>  <span data-ttu-id="92275-112">_pxNameText_也可能是隐藏的名称。</span><span class="sxs-lookup"><span data-stu-id="92275-112">_pxNameText_ can also be a hidden name.</span></span> 
  
<span data-ttu-id="92275-113">_pxInfoType_(**xltypeBool**)</span><span class="sxs-lookup"><span data-stu-id="92275-113">_pxInfoType_ (**xltypeBool**)</span></span>
  
<span data-ttu-id="92275-114">指定要返回的有关名称的信息类型。</span><span class="sxs-lookup"><span data-stu-id="92275-114">Specifies the type of information to return about the name.</span></span> <span data-ttu-id="92275-115">如果**FALSE**或省略，则返回的定义。</span><span class="sxs-lookup"><span data-stu-id="92275-115">If **FALSE** or omitted, the definition is returned.</span></span> <span data-ttu-id="92275-116">如果 **，则返回 TRUE**，则返回**TRUE**如果整个工作簿定义名称，如果为只工作表， **FALSE**定义名称。</span><span class="sxs-lookup"><span data-stu-id="92275-116">If **TRUE**, returns **TRUE** if the name is defined for just the sheet, **FALSE** if the name is defined for the entire workbook.</span></span> 
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="92275-117">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="92275-117">Property value/Return value</span></span>

<span data-ttu-id="92275-118">_pxRes_（**xltypeStr**、 **xltypeBool**或**xltypeErr**）</span><span class="sxs-lookup"><span data-stu-id="92275-118">_pxRes_ (**xltypeStr**, **xltypeBool**, or **xltypeErr**)</span></span>
  
<span data-ttu-id="92275-119">根据为_pxInfoType_传递的值，将返回指定的名称 (**xltypeStr**)，或**TRUE**或**FALSE** (**xltypeBool**) 的定义。</span><span class="sxs-lookup"><span data-stu-id="92275-119">Depending on the value passed for  _pxInfoType_, returns the definition of the specified name (**xltypeStr**), or **TRUE** or **FALSE** (**xltypeBool**).</span></span>
  
## <a name="remarks"></a><span data-ttu-id="92275-120">备注</span><span class="sxs-lookup"><span data-stu-id="92275-120">Remarks</span></span>

<span data-ttu-id="92275-121">如果**保护工作表和锁定的单元格的内容**复选框已选择了**保护工作表**对话框中来保护包含名称的工作簿**xlfGetName**返回`#N/A`错误值。</span><span class="sxs-lookup"><span data-stu-id="92275-121">If the **Protect worksheet and contents of locked cells** check box has been selected in the **Protect Sheet** dialog box to protect the workbook containing the name, **xlfGetName** returns the  `#N/A` error value.</span></span> <span data-ttu-id="92275-122">若要查看**保护工作表**对话框中，单击**保护工作表**的**更改**部分的**审阅**选项卡。</span><span class="sxs-lookup"><span data-stu-id="92275-122">To see the **Protect Sheet** dialog box, click **Protect Sheet** in the **Changes** section of the **Review** tab.</span></span> 
  
<span data-ttu-id="92275-123">下表列出了通过调用**xlfGetDef**指定的_pxNameText_参数返回的值的三个示例。</span><span class="sxs-lookup"><span data-stu-id="92275-123">The following table lists three examples of the values returned by a call to **xlfGetDef** with the specified  _pxNameText_ argument.</span></span> 
  
|<span data-ttu-id="92275-124">**在 Excel 中的定义**</span><span class="sxs-lookup"><span data-stu-id="92275-124">**Definition in Excel**</span></span>|<span data-ttu-id="92275-125">**_pxNameText_**</span><span class="sxs-lookup"><span data-stu-id="92275-125">**_pxNameText_**</span></span>|<span data-ttu-id="92275-126">**返回值**</span><span class="sxs-lookup"><span data-stu-id="92275-126">**Value Returned**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="92275-127">工作表上的名称销售被定义为 523 的号码。</span><span class="sxs-lookup"><span data-stu-id="92275-127">The name Sales on a sheet is defined as the number 523.</span></span>  <br/> |<span data-ttu-id="92275-128">"Sales"</span><span class="sxs-lookup"><span data-stu-id="92275-128">"Sales"</span></span>  <br/> |<span data-ttu-id="92275-129">"= 523"</span><span class="sxs-lookup"><span data-stu-id="92275-129">"=523"</span></span>  <br/> |
|<span data-ttu-id="92275-130">活动工作表的名称利润定义为公式 = 销售成本。</span><span class="sxs-lookup"><span data-stu-id="92275-130">The name Profit on the active sheet is defined as the formula =Sales-Costs.</span></span>  <br/> |<span data-ttu-id="92275-131">"!利润"</span><span class="sxs-lookup"><span data-stu-id="92275-131">"!Profit"</span></span>  <br/> |<span data-ttu-id="92275-132">"= 销售成本"</span><span class="sxs-lookup"><span data-stu-id="92275-132">"=Sales-Costs"</span></span>  <br/> |
|<span data-ttu-id="92275-133">在活动工作表上的数据库名称定义为 A1:F500 的范围。</span><span class="sxs-lookup"><span data-stu-id="92275-133">The name Database on the active sheet is defined as the range A1:F500.</span></span>  <br/> |<span data-ttu-id="92275-134">"!数据库"</span><span class="sxs-lookup"><span data-stu-id="92275-134">"!Database"</span></span>  <br/> |<span data-ttu-id="92275-135">"= R1C1:R500C6"</span><span class="sxs-lookup"><span data-stu-id="92275-135">"=R1C1:R500C6"</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="92275-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92275-136">See also</span></span>

- [<span data-ttu-id="92275-137">xlfGetDef</span><span class="sxs-lookup"><span data-stu-id="92275-137">xlfGetDef</span></span>](xlfgetdef.md)
- [<span data-ttu-id="92275-138">关键及有用的 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="92275-138">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

