---
title: xlfGetDef
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
keywords:
- xlfgetdef
localization_priority: Normal
ms.assetid: 68f5edbd-9040-46d3-acd5-dd51ca82f6fa
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 014db553156849d84bd07e0e416f8cb3fefb4e0b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421996"
---
# <a name="xlfgetdef"></a><span data-ttu-id="511a4-104">xlfGetDef</span><span class="sxs-lookup"><span data-stu-id="511a4-104">xlfGetDef</span></span>

<span data-ttu-id="511a4-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="511a4-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="511a4-106">以文本格式返回为工作簿中的特定区域、值或公式定义的名称。</span><span class="sxs-lookup"><span data-stu-id="511a4-106">Returns the name, as text, that is defined for a particular area, value, or formula in a workbook.</span></span> <span data-ttu-id="511a4-107">在Excel中，此值显示在"名称管理器"对话框的"名称"列中，当您单击"公式"选项卡上"定义的名称"部分中的"名称管理器"时，**将显示该对话框**。 使用 **xlfGetDef** 获取与定义对应的名称。</span><span class="sxs-lookup"><span data-stu-id="511a4-107">In Excel, this value is displayed in the **Name** column of the **Name Manager** dialog box, which is displayed when you click **Name Manager** in the **Defined Names** section on the **Formulas** tab. Use **xlfGetDef** to get the name that corresponds to a definition.</span></span> <span data-ttu-id="511a4-108">若要获取名称的定义，请使用 [xlfGetName](xlfgetname.md)。</span><span class="sxs-lookup"><span data-stu-id="511a4-108">To get the definition of a name, use [xlfGetName](xlfgetname.md).</span></span>
  
```cpp
Excel12(xlfGetDef, LPXLOPER12 pxRes, 3, LPXLOPER12 pxDefText, LPXLOPER12 pxDocumentText, LPXLOPER12 pxTypeNum);
```

## <a name="parameters"></a><span data-ttu-id="511a4-109">参数</span><span class="sxs-lookup"><span data-stu-id="511a4-109">Parameters</span></span>

<span data-ttu-id="511a4-110">_pxDefText_ (**xltypeStr**) </span><span class="sxs-lookup"><span data-stu-id="511a4-110">_pxDefText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="511a4-111">可以是您可以定义要引用的名称的任何内容，包括引用、值、对象或公式。</span><span class="sxs-lookup"><span data-stu-id="511a4-111">Can be anything you can define a name to refer to, including a reference, a value, an object, or a formula.</span></span>
  
<span data-ttu-id="511a4-112">引用必须以 R1C1 样式提供，例如  `"R3C5"` 。</span><span class="sxs-lookup"><span data-stu-id="511a4-112">References must be given in R1C1 style, such as  `"R3C5"`.</span></span> <span data-ttu-id="511a4-113">如果 _pxDefText_ 是值或公式，则不需要包括名称管理器对话框中"引用位置"列中 **显示的等号**。 </span><span class="sxs-lookup"><span data-stu-id="511a4-113">If  _pxDefText_ is a value or formula, it is not necessary to include the equal sign that is displayed in the **Refers To** column in the **Name Manager** dialog box.</span></span> <span data-ttu-id="511a4-114">如果  _pxDefText_ 存在多个名称 **，xlfGetDef** 将返回第一个名称。</span><span class="sxs-lookup"><span data-stu-id="511a4-114">If there is more than one name for  _pxDefText_, **xlfGetDef** returns the first name.</span></span> <span data-ttu-id="511a4-115">如果没有名称与  _pxDefText_ 匹配 **，xlfGetDef** 将返回  `#NAME?` 错误值。</span><span class="sxs-lookup"><span data-stu-id="511a4-115">If no name matches  _pxDefText_, **xlfGetDef** returns the  `#NAME?` error value.</span></span> 
  
<span data-ttu-id="511a4-116">_pxDocumentText_ (**xltypeStr**) </span><span class="sxs-lookup"><span data-stu-id="511a4-116">_pxDocumentText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="511a4-117">指定  _pxDefText_ 位于的工作表。</span><span class="sxs-lookup"><span data-stu-id="511a4-117">Specifies the sheet that  _pxDefText_ is on.</span></span> <span data-ttu-id="511a4-118">如果  _省略 pxDocumentText，_ 则假定它是活动工作表。</span><span class="sxs-lookup"><span data-stu-id="511a4-118">If  _pxDocumentText_ is omitted, it is assumed to be the active sheet.</span></span> 
  
<span data-ttu-id="511a4-119">_pxTypeNum_ (**xltypeNum**) </span><span class="sxs-lookup"><span data-stu-id="511a4-119">_pxTypeNum_ (**xltypeNum**)</span></span>
  
<span data-ttu-id="511a4-120">一个 1 到 3 个数字，用于指定返回的名称类型。</span><span class="sxs-lookup"><span data-stu-id="511a4-120">A number from 1 to 3 specifying which types of names are returned.</span></span>
  
|<span data-ttu-id="511a4-121">**_pxTypeNum_**</span><span class="sxs-lookup"><span data-stu-id="511a4-121">**_pxTypeNum_**</span></span>|<span data-ttu-id="511a4-122">**返回**</span><span class="sxs-lookup"><span data-stu-id="511a4-122">**Returns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="511a4-123">1 或省略</span><span class="sxs-lookup"><span data-stu-id="511a4-123">1 or omitted</span></span>  <br/> |<span data-ttu-id="511a4-124">仅普通名称。</span><span class="sxs-lookup"><span data-stu-id="511a4-124">Normal names only.</span></span>  <br/> |
|<span data-ttu-id="511a4-125">2</span><span class="sxs-lookup"><span data-stu-id="511a4-125">2</span></span>  <br/> |<span data-ttu-id="511a4-126">仅隐藏名称。</span><span class="sxs-lookup"><span data-stu-id="511a4-126">Hidden names only.</span></span>  <br/> |
|<span data-ttu-id="511a4-127">3</span><span class="sxs-lookup"><span data-stu-id="511a4-127">3</span></span>  <br/> |<span data-ttu-id="511a4-128">所有名称。</span><span class="sxs-lookup"><span data-stu-id="511a4-128">All names.</span></span>  <br/> |
   
## <a name="property-valuereturn-value"></a><span data-ttu-id="511a4-129">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="511a4-129">Property value/Return value</span></span>

 <span data-ttu-id="511a4-130">_pxRes_ (**xltypeStr** 或 **xltypeErr)**</span><span class="sxs-lookup"><span data-stu-id="511a4-130">_pxRes_ (**xltypeStr** or **xltypeErr**)</span></span>
  
<span data-ttu-id="511a4-131">返回与指定定义关联的名称。</span><span class="sxs-lookup"><span data-stu-id="511a4-131">Returns the name associated with the specified definition.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="511a4-132">备注</span><span class="sxs-lookup"><span data-stu-id="511a4-132">Remarks</span></span>

<span data-ttu-id="511a4-133">下表列出了使用指定参数调用 **xlfGetDef** 返回的四个值示例。</span><span class="sxs-lookup"><span data-stu-id="511a4-133">The following table lists four examples of the values returned by a call to **xlfGetDef** with the specified arguments.</span></span> 
  
|<span data-ttu-id="511a4-134">**中定义Excel**</span><span class="sxs-lookup"><span data-stu-id="511a4-134">**Name defined in Excel**</span></span>|<span data-ttu-id="511a4-135">**_pxDefText_**</span><span class="sxs-lookup"><span data-stu-id="511a4-135">**_pxDefText_**</span></span>|<span data-ttu-id="511a4-136">**_pxDocumentText_**</span><span class="sxs-lookup"><span data-stu-id="511a4-136">**_pxDocumentText_**</span></span>|<span data-ttu-id="511a4-137">**_pxTypeNum_**</span><span class="sxs-lookup"><span data-stu-id="511a4-137">**_pxTypeNum_**</span></span>|<span data-ttu-id="511a4-138">**返回的值**</span><span class="sxs-lookup"><span data-stu-id="511a4-138">**Value Returned**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="511a4-139">Sheet4 中的指定区域名为 Sales。</span><span class="sxs-lookup"><span data-stu-id="511a4-139">The specified range in Sheet4 is named Sales.</span></span>  <br/> |<span data-ttu-id="511a4-140">"R2C2：R9C6"</span><span class="sxs-lookup"><span data-stu-id="511a4-140">"R2C2:R9C6"</span></span>  <br/> |<span data-ttu-id="511a4-141">"Sheet4"</span><span class="sxs-lookup"><span data-stu-id="511a4-141">"Sheet4"</span></span>  <br/> |<span data-ttu-id="511a4-142">\<省略\></span><span class="sxs-lookup"><span data-stu-id="511a4-142">\<omitted\></span></span>  <br/> |<span data-ttu-id="511a4-143">"Sales"</span><span class="sxs-lookup"><span data-stu-id="511a4-143">"Sales"</span></span>  <br/> |
|<span data-ttu-id="511a4-144">Sheet4 中的值 100 定义为 Constant。</span><span class="sxs-lookup"><span data-stu-id="511a4-144">The value 100 in Sheet4 is defined as Constant.</span></span>  <br/> |<span data-ttu-id="511a4-145">"100"</span><span class="sxs-lookup"><span data-stu-id="511a4-145">"100"</span></span>  <br/> |<span data-ttu-id="511a4-146">"Sheet4"</span><span class="sxs-lookup"><span data-stu-id="511a4-146">"Sheet4"</span></span>  <br/> |<span data-ttu-id="511a4-147">\<省略\></span><span class="sxs-lookup"><span data-stu-id="511a4-147">\<omitted\></span></span>  <br/> |<span data-ttu-id="511a4-148">"Constant"</span><span class="sxs-lookup"><span data-stu-id="511a4-148">"Constant"</span></span>  <br/> |
|<span data-ttu-id="511a4-149">Sheet4 中的指定公式名为 SumTotal。</span><span class="sxs-lookup"><span data-stu-id="511a4-149">The specified formula in Sheet4 is named SumTotal.</span></span>  <br/> |<span data-ttu-id="511a4-150">"SUM (R1C1：R10C1) "</span><span class="sxs-lookup"><span data-stu-id="511a4-150">"SUM(R1C1:R10C1)"</span></span>  <br/> |<span data-ttu-id="511a4-151">"Sheet4"</span><span class="sxs-lookup"><span data-stu-id="511a4-151">"Sheet4"</span></span>  <br/> |<span data-ttu-id="511a4-152">\<省略\></span><span class="sxs-lookup"><span data-stu-id="511a4-152">\<omitted\></span></span>  <br/> |<span data-ttu-id="511a4-153">"SumTotal"</span><span class="sxs-lookup"><span data-stu-id="511a4-153">"SumTotal"</span></span>  <br/> |
|<span data-ttu-id="511a4-154">3 定义为活动工作表上的隐藏名称 Counter。</span><span class="sxs-lookup"><span data-stu-id="511a4-154">3 is defined as the hidden name Counter on the active sheet.</span></span>  <br/> |<span data-ttu-id="511a4-155">"3"</span><span class="sxs-lookup"><span data-stu-id="511a4-155">"3"</span></span>  <br/> |<span data-ttu-id="511a4-156">\<省略\></span><span class="sxs-lookup"><span data-stu-id="511a4-156">\<omitted\></span></span>  <br/> |<span data-ttu-id="511a4-157">2</span><span class="sxs-lookup"><span data-stu-id="511a4-157">2</span></span>  <br/> |<span data-ttu-id="511a4-158">"Counter"</span><span class="sxs-lookup"><span data-stu-id="511a4-158">"Counter"</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="511a4-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="511a4-159">See also</span></span>

- [<span data-ttu-id="511a4-160">xlfGetName</span><span class="sxs-lookup"><span data-stu-id="511a4-160">xlfGetName</span></span>](xlfgetname.md)
- [<span data-ttu-id="511a4-161">实用的基本 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="511a4-161">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

