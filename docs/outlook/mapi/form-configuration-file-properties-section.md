---
title: 表单配置文件 [Properties] 节
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
# <a name="form-configuration-file-properties-section"></a><span data-ttu-id="f959a-103">表单配置文件 [Properties] 节</span><span class="sxs-lookup"><span data-stu-id="f959a-103">Form Configuration File [Properties] Section</span></span>

  
  
<span data-ttu-id="f959a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f959a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f959a-105">**[Properties]** 节列出了表单使用和发布的完整属性集;即，它在自定义邮件中创建的属性，MAPI 客户端应用程序可在显示列、筛选内容表、设置搜索结果文件夹等时使用这些属性。</span><span class="sxs-lookup"><span data-stu-id="f959a-105">The **[Properties]** section lists the complete set of properties that the form uses and publishes; that is, the properties it creates in its custom messages that MAPI client applications can use when displaying columns, filtering contents tables, setting up search-results folders, and so on.</span></span> <span data-ttu-id="f959a-106">此属性列表中的每个条目引用一个后续 **[Property。**</span><span class="sxs-lookup"><span data-stu-id="f959a-106">Each entry in this property list references a subsequent **[Property.**</span></span> <span data-ttu-id="f959a-107">_string_ **]** 部分，如下所示。</span><span class="sxs-lookup"><span data-stu-id="f959a-107">_string_ **]** section as shown following.</span></span> 
  
 <span data-ttu-id="f959a-108">**[Properties]**</span><span class="sxs-lookup"><span data-stu-id="f959a-108">**[Properties]**</span></span>
  
 <span data-ttu-id="f959a-109">**属性。**</span><span class="sxs-lookup"><span data-stu-id="f959a-109">**Property.**</span></span> <span data-ttu-id="f959a-110">_string_  =  _string_</span><span class="sxs-lookup"><span data-stu-id="f959a-110">_string_ =  _string_</span></span>
  
<span data-ttu-id="f959a-111">[ **属性的格式。**</span><span class="sxs-lookup"><span data-stu-id="f959a-111">The format of a [ **Property.**</span></span> <span data-ttu-id="f959a-112">_string_]section 为：</span><span class="sxs-lookup"><span data-stu-id="f959a-112">_string_] section is:</span></span> 
  
 <span data-ttu-id="f959a-113">**[属性。**</span><span class="sxs-lookup"><span data-stu-id="f959a-113">**[Property.**</span></span> <span data-ttu-id="f959a-114">_string_ **]**</span><span class="sxs-lookup"><span data-stu-id="f959a-114">_string_ **]**</span></span>
  
 <span data-ttu-id="f959a-115">**类型**  =  _integer_</span><span class="sxs-lookup"><span data-stu-id="f959a-115">**Type** =  _integer_</span></span>
  
 <span data-ttu-id="f959a-116">**NmidPropset**  =  _guid_</span><span class="sxs-lookup"><span data-stu-id="f959a-116">**NmidPropset** =  _guid_</span></span>
  
 <span data-ttu-id="f959a-117">**NmidString**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="f959a-117">**NmidString** =  _string_</span></span>
  
 <span data-ttu-id="f959a-118">**NmidInteger**  =  _integer_</span><span class="sxs-lookup"><span data-stu-id="f959a-118">**NmidInteger** =  _integer_</span></span>
  
 <span data-ttu-id="f959a-119">**DisplayName**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="f959a-119">**DisplayName** =  _string_</span></span>
  
 <span data-ttu-id="f959a-120">**Flags**  =  _integer_</span><span class="sxs-lookup"><span data-stu-id="f959a-120">**Flags** =  _integer_</span></span>
  
 <span data-ttu-id="f959a-121">**SpecialType** = 0|1</span><span class="sxs-lookup"><span data-stu-id="f959a-121">**SpecialType** = 0|1</span></span> 
  
 <span data-ttu-id="f959a-122">**Enum1**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="f959a-122">**Enum1** =  _string_</span></span>
  
<span data-ttu-id="f959a-123">每个 **[属性。**</span><span class="sxs-lookup"><span data-stu-id="f959a-123">Each **[Property.**</span></span> <span data-ttu-id="f959a-124">_string_ **]** 节描述单个属性。</span><span class="sxs-lookup"><span data-stu-id="f959a-124">_string_ **]** section describes a single property.</span></span> <span data-ttu-id="f959a-125">**Type** 条目指定属性的 MAPI 属性类型， (PT_I4) 3 个属性类型。</span><span class="sxs-lookup"><span data-stu-id="f959a-125">The **Type** entry specifies the MAPI property type, for example 3 (PT_I4), of the property.</span></span> <span data-ttu-id="f959a-126">**NmidPropset** 项是可选的;**NmidPropset** 条目与 **NmidString** 条目或 **NmidInteger** 条目一起提供属性的名称。</span><span class="sxs-lookup"><span data-stu-id="f959a-126">The **NmidPropset** entry is optional; together with either the **NmidString** entry or the **NmidInteger** entry, the **NmidPropset** entry gives the name of the property.</span></span> <span data-ttu-id="f959a-127">**NmidString** 提供属性的名称， **而 NmidInteger** 提供属性的标识符。</span><span class="sxs-lookup"><span data-stu-id="f959a-127">**NmidString** gives the name of the property, while **NmidInteger** gives the identifier of the property.</span></span> <span data-ttu-id="f959a-128">**NmidString** 和 **NmidInteger** 相互排斥。</span><span class="sxs-lookup"><span data-stu-id="f959a-128">**NmidString** and **NmidInteger** are mutually exclusive.</span></span> 
  
<span data-ttu-id="f959a-129">如果设置， **则 NmidPropset** 应包含属性集的名称;如果不存在，则根据以下规则将 **NmidPropset** 设置为默认值：如果存在 **NmidInteger** 且其值小于 0x8000，则 **NmidPropset** 设置为 PS_MAPI。</span><span class="sxs-lookup"><span data-stu-id="f959a-129">If set, **NmidPropset** should contain the name of the property set; if absent, **NmidPropset** is set to a default based on the following rule: If **NmidInteger** is present and its value is less than 0x8000, **NmidPropset** is set to PS_MAPI.</span></span> <span data-ttu-id="f959a-130">如果 **NmidInteger** 的值设置为大于 0x8000 的整数，或者如果不存在， **则 NmidPropset** 设置为 PS_PUBLIC_STRINGS。</span><span class="sxs-lookup"><span data-stu-id="f959a-130">If the value of **NmidInteger** is set to an integer greater than 0x8000, or if it is absent, **NmidPropset** is set to PS_PUBLIC_STRINGS.</span></span> 
  
<span data-ttu-id="f959a-131">**DisplayName** 条目包含属性的标签。</span><span class="sxs-lookup"><span data-stu-id="f959a-131">The **DisplayName** entry contains the label for the property.</span></span> <span data-ttu-id="f959a-132">**SpecialType** 项（如果存在）和非零值表示此属性是特殊属性。</span><span class="sxs-lookup"><span data-stu-id="f959a-132">The **SpecialType** entry, if present and nonzero indicates that this property is a special property.</span></span> <span data-ttu-id="f959a-133">目前，唯一定义的特殊属性类型是 **SpecialType** = 1，它指示字符串枚举属性。</span><span class="sxs-lookup"><span data-stu-id="f959a-133">At present, the only special property type defined is **SpecialType** = 1, which indicates string enumerated properties.</span></span> <span data-ttu-id="f959a-134">如果 **SpecialType** 设置为 1，Enum1 条目将引用 **[Enum1。** </span><span class="sxs-lookup"><span data-stu-id="f959a-134">If **SpecialType** is set to 1, the **Enum1** entry references the **[Enum1.**</span></span> <span data-ttu-id="f959a-135">_string_ **]** section.</span><span class="sxs-lookup"><span data-stu-id="f959a-135">_string_ **]** section.</span></span> 
  
<span data-ttu-id="f959a-136">下面是 **[Properties] 部分** 和 **[Properties** 的示例。</span><span class="sxs-lookup"><span data-stu-id="f959a-136">Following is an example of a **[Properties]** section and a **[Properties.**</span></span> <span data-ttu-id="f959a-137">_string_ **]** section.</span><span class="sxs-lookup"><span data-stu-id="f959a-137">_string_ **]** section.</span></span> 
  
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

<span data-ttu-id="f959a-138">前 **一示例引用的 Enum1** 条目引用后续 **[Enum1。**</span><span class="sxs-lookup"><span data-stu-id="f959a-138">The **Enum1** entry in the preceeding example references to a subsequent **[Enum1.**</span></span> <span data-ttu-id="f959a-139">_string_ **]** 描述特定类型枚举的部分。</span><span class="sxs-lookup"><span data-stu-id="f959a-139">_string_ **]** section describing an enumeration of a particular type.</span></span> <span data-ttu-id="f959a-140">此类枚举将关联 [Property] 中的第一 **个属性。**</span><span class="sxs-lookup"><span data-stu-id="f959a-140">Such an enumeration associates the first property in the **[Property.**</span></span> <span data-ttu-id="f959a-141">_string_ **]** section with an integer property， called the index.</span><span class="sxs-lookup"><span data-stu-id="f959a-141">_string_ **]** section with an integer property, called the index.</span></span> <span data-ttu-id="f959a-142">此类枚举还包含显示索引对可以假定的可能值的列表。</span><span class="sxs-lookup"><span data-stu-id="f959a-142">Such an enumeration also contains a list of the possible values that the display-index pair can assume.</span></span> <span data-ttu-id="f959a-143">不必为枚举指定属性类型，因为根据定义 **，Enum1** 项始终具有PT_I4类型。</span><span class="sxs-lookup"><span data-stu-id="f959a-143">Specifying a property type for the enumeration is unnecessary because by definition an **Enum1** entry always has the PT_I4 type.</span></span> <span data-ttu-id="f959a-144">**[Enum1 的格式。**</span><span class="sxs-lookup"><span data-stu-id="f959a-144">The format for the **[Enum1.**</span></span> <span data-ttu-id="f959a-145">_string_ **]** section is：</span><span class="sxs-lookup"><span data-stu-id="f959a-145">_string_ **]** section is:</span></span> 
  
 <span data-ttu-id="f959a-146">**[Enum1。**</span><span class="sxs-lookup"><span data-stu-id="f959a-146">**[Enum1.**</span></span> <span data-ttu-id="f959a-147">_string_ **]**</span><span class="sxs-lookup"><span data-stu-id="f959a-147">_string_ **]**</span></span>
  
 <span data-ttu-id="f959a-148">**NmidPropset**  =  _guid_</span><span class="sxs-lookup"><span data-stu-id="f959a-148">**NmidPropset** =  _guid_</span></span>
  
 <span data-ttu-id="f959a-149">**NmidString**  =  _string_</span><span class="sxs-lookup"><span data-stu-id="f959a-149">**NmidString** =  _string_</span></span>
  
 <span data-ttu-id="f959a-150">**NmidInteger**  =  _integer_</span><span class="sxs-lookup"><span data-stu-id="f959a-150">**NmidInteger** =  _integer_</span></span>
  
 <span data-ttu-id="f959a-151">**EnumCount**  =  _integer_</span><span class="sxs-lookup"><span data-stu-id="f959a-151">**EnumCount** =  _integer_</span></span>
  
 <span data-ttu-id="f959a-152">**Val.**</span><span class="sxs-lookup"><span data-stu-id="f959a-152">**Val.**</span></span> <span data-ttu-id="f959a-153">_整数_ **。显示**  =   _字符串_</span><span class="sxs-lookup"><span data-stu-id="f959a-153">_integer_ **.Display** =  _string_</span></span>
  
 <span data-ttu-id="f959a-154">**Val.**</span><span class="sxs-lookup"><span data-stu-id="f959a-154">**Val.**</span></span> <span data-ttu-id="f959a-155">_整数_ **。索引**  =   _整数_</span><span class="sxs-lookup"><span data-stu-id="f959a-155">_integer_ **.Index** =  _integer_</span></span>
  
<span data-ttu-id="f959a-156">下面是名为 Fire Hazard 的枚举属性的示例属性定义，其可能值为 Low、Medium 和 High。</span><span class="sxs-lookup"><span data-stu-id="f959a-156">The following is an example property definition for an enumerated property named Fire Hazard with possible values of Low, Medium, and High.</span></span>
  
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

 <span data-ttu-id="f959a-157">**[Enum1。**</span><span class="sxs-lookup"><span data-stu-id="f959a-157">**[Enum1.**</span></span> <span data-ttu-id="f959a-158">_string_ **]** sections can be used by applications for two purposes： to speed up the filtering of properties by using the index instead of the string and to sort by a different order than the alphanumeric order of the string values.</span><span class="sxs-lookup"><span data-stu-id="f959a-158">_string_ **]** sections can be used by applications for two purposes: to speed up the filtering of properties by using the index instead of the string and to sort by a different order than the alphanumeric order of the string values.</span></span> <span data-ttu-id="f959a-159">例如，可以基于低-中-高顺序而不是基于高-中-低顺序进行排序。</span><span class="sxs-lookup"><span data-stu-id="f959a-159">For example, sorting could be done based on Low-Medium-High order instead of High-Medium-Low order.</span></span> 
  

