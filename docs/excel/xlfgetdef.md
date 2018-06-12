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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 030c4e501e8a9eb4b6ce29d7fe0e171324b50b5c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773861"
---
# <a name="xlfgetdef"></a><span data-ttu-id="28b82-104">xlfGetDef</span><span class="sxs-lookup"><span data-stu-id="28b82-104">xlfGetDef</span></span>

<span data-ttu-id="28b82-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="28b82-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="28b82-106">返回为文本，为特定区域、 值或公式工作簿中的定义的名称。</span><span class="sxs-lookup"><span data-stu-id="28b82-106">Returns the name, as text, that is defined for a particular area, value, or formula in a workbook.</span></span> <span data-ttu-id="28b82-107">在 Excel 中，此值显示在**名称管理器**对话框中，单击**名称管理器**中使用**xlfGetDef** **公式**选项卡上**定义名称**部分获取时显示的**名称**列对应于定义的名称。</span><span class="sxs-lookup"><span data-stu-id="28b82-107">In Excel, this value is displayed in the **Name** column of the **Name Manager** dialog box, which is displayed when you click **Name Manager** in the **Defined Names** section on the **Formulas** tab. Use **xlfGetDef** to get the name that corresponds to a definition.</span></span> <span data-ttu-id="28b82-108">若要获取的名称定义，请使用[xlfGetName](xlfgetname.md)。</span><span class="sxs-lookup"><span data-stu-id="28b82-108">To get the definition of a name, use [xlfGetName](xlfgetname.md).</span></span>
  
```cpp
Excel12(xlfGetDef, LPXLOPER12 pxRes, 3, LPXLOPER12 pxDefText, LPXLOPER12 pxDocumentText, LPXLOPER12 pxTypeNum);
```

## <a name="parameters"></a><span data-ttu-id="28b82-109">参数</span><span class="sxs-lookup"><span data-stu-id="28b82-109">Parameters</span></span>

<span data-ttu-id="28b82-110">_pxDefText_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="28b82-110">_pxDefText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="28b82-111">可以是任何您可以定义名称来引用，其中包括参考、 值、 对象或公式。</span><span class="sxs-lookup"><span data-stu-id="28b82-111">Can be anything you can define a name to refer to, including a reference, a value, an object, or a formula.</span></span>
  
<span data-ttu-id="28b82-112">引用必须授予以 R1C1 样式，如`"R3C5"`。</span><span class="sxs-lookup"><span data-stu-id="28b82-112">References must be given in R1C1 style, such as  `"R3C5"`.</span></span> <span data-ttu-id="28b82-113">如果值或公式， _pxDefText_ ，不需要包括在**名称管理器**对话框的**引用到**列中显示等号。</span><span class="sxs-lookup"><span data-stu-id="28b82-113">If  _pxDefText_ is a value or formula, it is not necessary to include the equal sign that is displayed in the **Refers To** column in the **Name Manager** dialog box.</span></span> <span data-ttu-id="28b82-114">如果有多个名称_pxDefText_， **xlfGetDef**返回第一个名称。</span><span class="sxs-lookup"><span data-stu-id="28b82-114">If there is more than one name for  _pxDefText_, **xlfGetDef** returns the first name.</span></span> <span data-ttu-id="28b82-115">如果没有名称匹配_pxDefText_， **xlfGetDef**返回`#NAME?`错误值。</span><span class="sxs-lookup"><span data-stu-id="28b82-115">If no name matches  _pxDefText_, **xlfGetDef** returns the  `#NAME?` error value.</span></span> 
  
<span data-ttu-id="28b82-116">_pxDocumentText_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="28b82-116">_pxDocumentText_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="28b82-117">指定工作表的_pxDefText_位于。</span><span class="sxs-lookup"><span data-stu-id="28b82-117">Specifies the sheet that  _pxDefText_ is on.</span></span> <span data-ttu-id="28b82-118">如果省略_pxDocumentText_ ，则假定为活动工作表。</span><span class="sxs-lookup"><span data-stu-id="28b82-118">If  _pxDocumentText_ is omitted, it is assumed to be the active sheet.</span></span> 
  
<span data-ttu-id="28b82-119">_pxTypeNum_(**xltypeNum**)</span><span class="sxs-lookup"><span data-stu-id="28b82-119">_pxTypeNum_ (**xltypeNum**)</span></span>
  
<span data-ttu-id="28b82-120">介于 1 到 3 指定返回哪些类型的名称。</span><span class="sxs-lookup"><span data-stu-id="28b82-120">A number from 1 to 3 specifying which types of names are returned.</span></span>
  
|<span data-ttu-id="28b82-121">**_pxTypeNum_**</span><span class="sxs-lookup"><span data-stu-id="28b82-121">**_pxTypeNum_**</span></span>|<span data-ttu-id="28b82-122">**返回**</span><span class="sxs-lookup"><span data-stu-id="28b82-122">**Returns**</span></span>|
|:-----|:-----|
|<span data-ttu-id="28b82-123">1 或省略</span><span class="sxs-lookup"><span data-stu-id="28b82-123">1 or omitted</span></span>  <br/> |<span data-ttu-id="28b82-124">普通的名称。</span><span class="sxs-lookup"><span data-stu-id="28b82-124">Normal names only.</span></span>  <br/> |
|<span data-ttu-id="28b82-125">2</span><span class="sxs-lookup"><span data-stu-id="28b82-125">2</span></span>  <br/> |<span data-ttu-id="28b82-126">隐藏的名称。</span><span class="sxs-lookup"><span data-stu-id="28b82-126">Hidden names only.</span></span>  <br/> |
|<span data-ttu-id="28b82-127">3</span><span class="sxs-lookup"><span data-stu-id="28b82-127">3</span></span>  <br/> |<span data-ttu-id="28b82-128">所有名称。</span><span class="sxs-lookup"><span data-stu-id="28b82-128">All names.</span></span>  <br/> |
   
## <a name="property-valuereturn-value"></a><span data-ttu-id="28b82-129">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="28b82-129">Property value/Return value</span></span>

 <span data-ttu-id="28b82-130">_pxRes_（**xltypeStr**或**xltypeErr**）</span><span class="sxs-lookup"><span data-stu-id="28b82-130">_pxRes_ (**xltypeStr** or **xltypeErr**)</span></span>
  
<span data-ttu-id="28b82-131">返回与指定的定义关联的名称。</span><span class="sxs-lookup"><span data-stu-id="28b82-131">Returns the name associated with the specified definition.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="28b82-132">备注</span><span class="sxs-lookup"><span data-stu-id="28b82-132">Remarks</span></span>

<span data-ttu-id="28b82-133">下表列出了通过调用**xlfGetDef**用指定的参数返回的值的四个示例。</span><span class="sxs-lookup"><span data-stu-id="28b82-133">The following table lists four examples of the values returned by a call to **xlfGetDef** with the specified arguments.</span></span> 
  
|<span data-ttu-id="28b82-134">**在 Excel 中定义的名称**</span><span class="sxs-lookup"><span data-stu-id="28b82-134">**Name defined in Excel**</span></span>|<span data-ttu-id="28b82-135">**_pxDefText_**</span><span class="sxs-lookup"><span data-stu-id="28b82-135">**_pxDefText_**</span></span>|<span data-ttu-id="28b82-136">**_pxDocumentText_**</span><span class="sxs-lookup"><span data-stu-id="28b82-136">**_pxDocumentText_**</span></span>|<span data-ttu-id="28b82-137">**_pxTypeNum_**</span><span class="sxs-lookup"><span data-stu-id="28b82-137">**_pxTypeNum_**</span></span>|<span data-ttu-id="28b82-138">**返回值**</span><span class="sxs-lookup"><span data-stu-id="28b82-138">**Value Returned**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="28b82-139">Sheet4 中的指定的范围名为 Sales。</span><span class="sxs-lookup"><span data-stu-id="28b82-139">The specified range in Sheet4 is named Sales.</span></span>  <br/> |<span data-ttu-id="28b82-140">"R2C2:R9C6"</span><span class="sxs-lookup"><span data-stu-id="28b82-140">"R2C2:R9C6"</span></span>  <br/> |<span data-ttu-id="28b82-141">"Sheet4"</span><span class="sxs-lookup"><span data-stu-id="28b82-141">"Sheet4"</span></span>  <br/> |<span data-ttu-id="28b82-142">\<省略\></span><span class="sxs-lookup"><span data-stu-id="28b82-142">\<omitted\></span></span>  <br/> |<span data-ttu-id="28b82-143">"Sales"</span><span class="sxs-lookup"><span data-stu-id="28b82-143">"Sales"</span></span>  <br/> |
|<span data-ttu-id="28b82-144">Sheet4 中的值 100 被定义为常量。</span><span class="sxs-lookup"><span data-stu-id="28b82-144">The value 100 in Sheet4 is defined as Constant.</span></span>  <br/> |<span data-ttu-id="28b82-145">"100"</span><span class="sxs-lookup"><span data-stu-id="28b82-145">"100"</span></span>  <br/> |<span data-ttu-id="28b82-146">"Sheet4"</span><span class="sxs-lookup"><span data-stu-id="28b82-146">"Sheet4"</span></span>  <br/> |<span data-ttu-id="28b82-147">\<省略\></span><span class="sxs-lookup"><span data-stu-id="28b82-147">\<omitted\></span></span>  <br/> |<span data-ttu-id="28b82-148">"常量"</span><span class="sxs-lookup"><span data-stu-id="28b82-148">"Constant"</span></span>  <br/> |
|<span data-ttu-id="28b82-149">SumTotal 名为 Sheet4 中指定的公式。</span><span class="sxs-lookup"><span data-stu-id="28b82-149">The specified formula in Sheet4 is named SumTotal.</span></span>  <br/> |<span data-ttu-id="28b82-150">"SUM(R1C1:R10C1)"</span><span class="sxs-lookup"><span data-stu-id="28b82-150">"SUM(R1C1:R10C1)"</span></span>  <br/> |<span data-ttu-id="28b82-151">"Sheet4"</span><span class="sxs-lookup"><span data-stu-id="28b82-151">"Sheet4"</span></span>  <br/> |<span data-ttu-id="28b82-152">\<省略\></span><span class="sxs-lookup"><span data-stu-id="28b82-152">\<omitted\></span></span>  <br/> |<span data-ttu-id="28b82-153">"SumTotal"</span><span class="sxs-lookup"><span data-stu-id="28b82-153">"SumTotal"</span></span>  <br/> |
|<span data-ttu-id="28b82-154">3 被定义为活动工作表上的隐藏名称计数器。</span><span class="sxs-lookup"><span data-stu-id="28b82-154">3 is defined as the hidden name Counter on the active sheet.</span></span>  <br/> |<span data-ttu-id="28b82-155">"3"</span><span class="sxs-lookup"><span data-stu-id="28b82-155">"3"</span></span>  <br/> |<span data-ttu-id="28b82-156">\<省略\></span><span class="sxs-lookup"><span data-stu-id="28b82-156">\<omitted\></span></span>  <br/> |<span data-ttu-id="28b82-157">2</span><span class="sxs-lookup"><span data-stu-id="28b82-157">2</span></span>  <br/> |<span data-ttu-id="28b82-158">"计数器"</span><span class="sxs-lookup"><span data-stu-id="28b82-158">"Counter"</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="28b82-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28b82-159">See also</span></span>

- [<span data-ttu-id="28b82-160">xlfGetName</span><span class="sxs-lookup"><span data-stu-id="28b82-160">xlfGetName</span></span>](xlfgetname.md)
- [<span data-ttu-id="28b82-161">关键及有用的 C API XLM 函数</span><span class="sxs-lookup"><span data-stu-id="28b82-161">Essential and Useful C API XLM Functions</span></span>](essential-and-useful-c-api-xlm-functions.md)

