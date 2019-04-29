---
title: 表单配置文件 [Properties] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f31a08ce-3a56-4c90-9502-5bcb09d8d80f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 86d2257b821622094ff8d5ad3a5d7b1bfc74942b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421289"
---
# <a name="form-configuration-file-properties-section"></a><span data-ttu-id="d837f-103">表单配置文件 [Properties] 部分</span><span class="sxs-lookup"><span data-stu-id="d837f-103">Form Configuration File [Properties] Section</span></span>

  
  
<span data-ttu-id="d837f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d837f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d837f-105">**[Properties]** 部分列出了表单使用和发布的完整属性集;即, 它在自定义邮件中创建的属性, MAPI 客户端应用程序可以在显示列、筛选内容表、设置搜索结果文件夹等时使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="d837f-105">The **[Properties]** section lists the complete set of properties that the form uses and publishes; that is, the properties it creates in its custom messages that MAPI client applications can use when displaying columns, filtering contents tables, setting up search-results folders, and so on.</span></span> <span data-ttu-id="d837f-106">此属性列表中的每个条目都引用一个后续的 **[属性。**</span><span class="sxs-lookup"><span data-stu-id="d837f-106">Each entry in this property list references a subsequent **[Property.**</span></span> <span data-ttu-id="d837f-107">_string_\*\*\*\* "一节, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="d837f-107">_string_ **]** section as shown following.</span></span> 
  
 <span data-ttu-id="d837f-108">**属性**</span><span class="sxs-lookup"><span data-stu-id="d837f-108">**[Properties]**</span></span>
  
 <span data-ttu-id="d837f-109">**财产.**</span><span class="sxs-lookup"><span data-stu-id="d837f-109">**Property.**</span></span> <span data-ttu-id="d837f-110">_字符串_ =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="d837f-110">_string_ =  _string_</span></span>
  
<span data-ttu-id="d837f-111">[属性的格式 **。**</span><span class="sxs-lookup"><span data-stu-id="d837f-111">The format of a [ **Property.**</span></span> <span data-ttu-id="d837f-112">_string_]部分为:</span><span class="sxs-lookup"><span data-stu-id="d837f-112">_string_] section is:</span></span> 
  
 <span data-ttu-id="d837f-113">**财产.**</span><span class="sxs-lookup"><span data-stu-id="d837f-113">**[Property.**</span></span> <span data-ttu-id="d837f-114">_string_**]**</span><span class="sxs-lookup"><span data-stu-id="d837f-114">_string_ **]**</span></span>
  
 <span data-ttu-id="d837f-115">**类型** =  _integer_</span><span class="sxs-lookup"><span data-stu-id="d837f-115">**Type** =  _integer_</span></span>
  
 <span data-ttu-id="d837f-116">**NmidPropset** =  _guid_</span><span class="sxs-lookup"><span data-stu-id="d837f-116">**NmidPropset** =  _guid_</span></span>
  
 <span data-ttu-id="d837f-117">**NmidString** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="d837f-117">**NmidString** =  _string_</span></span>
  
 <span data-ttu-id="d837f-118">**NmidInteger** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="d837f-118">**NmidInteger** =  _integer_</span></span>
  
 <span data-ttu-id="d837f-119">**DisplayName** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="d837f-119">**DisplayName** =  _string_</span></span>
  
 <span data-ttu-id="d837f-120">**Flags** =  _integer_</span><span class="sxs-lookup"><span data-stu-id="d837f-120">**Flags** =  _integer_</span></span>
  
 <span data-ttu-id="d837f-121">**SpecialType** = 0 | 1</span><span class="sxs-lookup"><span data-stu-id="d837f-121">**SpecialType** = 0|1</span></span> 
  
 <span data-ttu-id="d837f-122">**Enum1** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="d837f-122">**Enum1** =  _string_</span></span>
  
<span data-ttu-id="d837f-123">每个 **[属性。**</span><span class="sxs-lookup"><span data-stu-id="d837f-123">Each **[Property.**</span></span> <span data-ttu-id="d837f-124">_string_**]** 部分介绍了单个属性。</span><span class="sxs-lookup"><span data-stu-id="d837f-124">_string_ **]** section describes a single property.</span></span> <span data-ttu-id="d837f-125">**类型**条目指定了该属性的 MAPI 属性类型 (例如, 3 (PT_I4))。</span><span class="sxs-lookup"><span data-stu-id="d837f-125">The **Type** entry specifies the MAPI property type, for example 3 (PT_I4), of the property.</span></span> <span data-ttu-id="d837f-126">**NmidPropset**条目是可选的;**NmidString**项或**NmidInteger**项一起使用时, **NmidPropset**项将提供属性的名称。</span><span class="sxs-lookup"><span data-stu-id="d837f-126">The **NmidPropset** entry is optional; together with either the **NmidString** entry or the **NmidInteger** entry, the **NmidPropset** entry gives the name of the property.</span></span> <span data-ttu-id="d837f-127">**NmidString**提供属性的名称, 而**NmidInteger**将提供属性的标识符。</span><span class="sxs-lookup"><span data-stu-id="d837f-127">**NmidString** gives the name of the property, while **NmidInteger** gives the identifier of the property.</span></span> <span data-ttu-id="d837f-128">**NmidString**和**NmidInteger**是相互排斥的。</span><span class="sxs-lookup"><span data-stu-id="d837f-128">**NmidString** and **NmidInteger** are mutually exclusive.</span></span> 
  
<span data-ttu-id="d837f-129">如果设置, 则**NmidPropset**应包含属性集的名称;如果不存在, 则根据以下规则将**NmidPropset**设置为默认值: 如果存在**NmidInteger**且其值小于 0x8000, 则将**NmidPropset**设置为 PS_MAPI。</span><span class="sxs-lookup"><span data-stu-id="d837f-129">If set, **NmidPropset** should contain the name of the property set; if absent, **NmidPropset** is set to a default based on the following rule: If **NmidInteger** is present and its value is less than 0x8000, **NmidPropset** is set to PS_MAPI.</span></span> <span data-ttu-id="d837f-130">如果**NmidInteger**的值设置为大于0x8000 的整数, 或者如果不存在, 则**NmidPropset**设置为 PS_PUBLIC_STRINGS。</span><span class="sxs-lookup"><span data-stu-id="d837f-130">If the value of **NmidInteger** is set to an integer greater than 0x8000, or if it is absent, **NmidPropset** is set to PS_PUBLIC_STRINGS.</span></span> 
  
<span data-ttu-id="d837f-131">**DisplayName**项包含属性的标签。</span><span class="sxs-lookup"><span data-stu-id="d837f-131">The **DisplayName** entry contains the label for the property.</span></span> <span data-ttu-id="d837f-132">**SpecialType**条目 (如果存在) 和非零表示此属性是特殊属性。</span><span class="sxs-lookup"><span data-stu-id="d837f-132">The **SpecialType** entry, if present and nonzero indicates that this property is a special property.</span></span> <span data-ttu-id="d837f-133">目前, 唯一定义的特殊属性类型是**SpecialType** = 1, 它表示字符串枚举属性。</span><span class="sxs-lookup"><span data-stu-id="d837f-133">At present, the only special property type defined is **SpecialType** = 1, which indicates string enumerated properties.</span></span> <span data-ttu-id="d837f-134">如果将**SpecialType**设置为 1, 则**Enum1**项将引用 **[Enum1。**</span><span class="sxs-lookup"><span data-stu-id="d837f-134">If **SpecialType** is set to 1, the **Enum1** entry references the **[Enum1.**</span></span> <span data-ttu-id="d837f-135">_string_**]** 部分。</span><span class="sxs-lookup"><span data-stu-id="d837f-135">_string_ **]** section.</span></span> 
  
<span data-ttu-id="d837f-136">以下是 **[properties]** 节和 **[properties** ] 的示例。</span><span class="sxs-lookup"><span data-stu-id="d837f-136">Following is an example of a **[Properties]** section and a **[Properties.**</span></span> <span data-ttu-id="d837f-137">_string_**]** 部分。</span><span class="sxs-lookup"><span data-stu-id="d837f-137">_string_ **]** section.</span></span> 
  
```cpp
[Properties]
Property.1 = Fire Hazard
Property.2 = Safe
[Property.Fire Hazard]
Type = 1
NmidPropSet = {E47F4480-8400-101B-934D-04021C007002]
NmidString = FireHazard
DisplayName = Fire Hazard
SpecialType = 1
Enum1 = HazardEnum

```

<span data-ttu-id="d837f-138">前面的示例中的**Enum1**条目引用了随后的 **[Enum1。**</span><span class="sxs-lookup"><span data-stu-id="d837f-138">The **Enum1** entry in the preceeding example references to a subsequent **[Enum1.**</span></span> <span data-ttu-id="d837f-139">_string_\*\*\*\* "一节描述特定类型的枚举。</span><span class="sxs-lookup"><span data-stu-id="d837f-139">_string_ **]** section describing an enumeration of a particular type.</span></span> <span data-ttu-id="d837f-140">这样的枚举将关联 **[属性**中的第一个属性。</span><span class="sxs-lookup"><span data-stu-id="d837f-140">Such an enumeration associates the first property in the **[Property.**</span></span> <span data-ttu-id="d837f-141">_string_\*\*\*\* 包含 integer 属性 (称为 index) 的节。</span><span class="sxs-lookup"><span data-stu-id="d837f-141">_string_ **]** section with an integer property, called the index.</span></span> <span data-ttu-id="d837f-142">此类枚举还包含显示索引对可以假设的可能值的列表。</span><span class="sxs-lookup"><span data-stu-id="d837f-142">Such an enumeration also contains a list of the possible values that the display-index pair can assume.</span></span> <span data-ttu-id="d837f-143">为枚举指定属性类型是不必要的, 因为根据定义, **Enum1**条目始终具有 PT_I4 类型。</span><span class="sxs-lookup"><span data-stu-id="d837f-143">Specifying a property type for the enumeration is unnecessary because by definition an **Enum1** entry always has the PT_I4 type.</span></span> <span data-ttu-id="d837f-144">**[Enum1.**</span><span class="sxs-lookup"><span data-stu-id="d837f-144">The format for the **[Enum1.**</span></span> <span data-ttu-id="d837f-145">_string_**]** 部分为:</span><span class="sxs-lookup"><span data-stu-id="d837f-145">_string_ **]** section is:</span></span> 
  
 <span data-ttu-id="d837f-146">**[Enum1。**</span><span class="sxs-lookup"><span data-stu-id="d837f-146">**[Enum1.**</span></span> <span data-ttu-id="d837f-147">_string_**]**</span><span class="sxs-lookup"><span data-stu-id="d837f-147">_string_ **]**</span></span>
  
 <span data-ttu-id="d837f-148">**NmidPropset** =  _guid_</span><span class="sxs-lookup"><span data-stu-id="d837f-148">**NmidPropset** =  _guid_</span></span>
  
 <span data-ttu-id="d837f-149">**NmidString** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="d837f-149">**NmidString** =  _string_</span></span>
  
 <span data-ttu-id="d837f-150">**NmidInteger** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="d837f-150">**NmidInteger** =  _integer_</span></span>
  
 <span data-ttu-id="d837f-151">**EnumCount** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="d837f-151">**EnumCount** =  _integer_</span></span>
  
 <span data-ttu-id="d837f-152">**初始值.**</span><span class="sxs-lookup"><span data-stu-id="d837f-152">**Val.**</span></span> <span data-ttu-id="d837f-153">_integer_**.显示** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="d837f-153">_integer_ **.Display** =  _string_</span></span>
  
 <span data-ttu-id="d837f-154">**初始值.**</span><span class="sxs-lookup"><span data-stu-id="d837f-154">**Val.**</span></span> <span data-ttu-id="d837f-155">_integer_**.索引** =  _integer_</span><span class="sxs-lookup"><span data-stu-id="d837f-155">_integer_ **.Index** =  _integer_</span></span>
  
<span data-ttu-id="d837f-156">以下是名为火灾危险的枚举属性的示例属性定义, 其可能值为低、中和高。</span><span class="sxs-lookup"><span data-stu-id="d837f-156">The following is an example property definition for an enumerated property named Fire Hazard with possible values of Low, Medium, and High.</span></span>
  
```cpp
[Properties]
Property1 = Fire Hazard
[Enum1.HazardEnum]
IdxNmidPropset={E47F4480-8400-101B-934D-04021C007002]
IdxNmidString=FireHazardEnum
EnumCount = 3
Val.1.Display = Low
Val.1.Index = 1
Val.2.Display = Medium
Val.2.Index = 2
Val.3.Display = High
Val.3.Index = 3

```

 <span data-ttu-id="d837f-157">**[Enum1。**</span><span class="sxs-lookup"><span data-stu-id="d837f-157">**[Enum1.**</span></span> <span data-ttu-id="d837f-158">_string_**]** 可由应用程序用于两个部分: 通过使用索引而不是字符串来加快对属性的筛选, 并按与字符串值的字母数字顺序不同的顺序进行排序。</span><span class="sxs-lookup"><span data-stu-id="d837f-158">_string_ **]** sections can be used by applications for two purposes: to speed up the filtering of properties by using the index instead of the string and to sort by a different order than the alphanumeric order of the string values.</span></span> <span data-ttu-id="d837f-159">例如, 可以根据低标准高订单 (而不是高中低订单) 执行排序。</span><span class="sxs-lookup"><span data-stu-id="d837f-159">For example, sorting could be done based on Low-Medium-High order instead of High-Medium-Low order.</span></span> 
  

