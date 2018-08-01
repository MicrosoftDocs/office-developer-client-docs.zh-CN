---
title: 表单配置文件 [属性] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f31a08ce-3a56-4c90-9502-5bcb09d8d80f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f582322c8ba2ffa0369792e531adf1ec4ccb3e28
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774984"
---
# <a name="form-configuration-file-properties-section"></a><span data-ttu-id="02509-103">表单配置文件 [属性] 部分</span><span class="sxs-lookup"><span data-stu-id="02509-103">Form Configuration File [Properties] Section</span></span>

  
  
<span data-ttu-id="02509-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="02509-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="02509-105">**属性**部分列出的窗体使用并发布; 属性的完整集合即，它会在创建其自定义消息的 MAPI 客户端应用程序的属性可显示列筛选内容表，设置搜索结果文件夹时使用，依此类推。</span><span class="sxs-lookup"><span data-stu-id="02509-105">The **[Properties]** section lists the complete set of properties that the form uses and publishes; that is, the properties it creates in its custom messages that MAPI client applications can use when displaying columns, filtering contents tables, setting up search-results folders, and so on.</span></span> <span data-ttu-id="02509-106">此属性列表中的每个条目引用后续 **[属性。**</span><span class="sxs-lookup"><span data-stu-id="02509-106">Each entry in this property list references a subsequent **[Property.**</span></span> <span data-ttu-id="02509-107">_字符串_**]** 部分如下所示。</span><span class="sxs-lookup"><span data-stu-id="02509-107">_string_ **]** section as shown following.</span></span> 
  
 <span data-ttu-id="02509-108">**[属性]**</span><span class="sxs-lookup"><span data-stu-id="02509-108">**[Properties]**</span></span>
  
 <span data-ttu-id="02509-109">**属性。**</span><span class="sxs-lookup"><span data-stu-id="02509-109">**Property.**</span></span> <span data-ttu-id="02509-110">_字符串_ =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="02509-110">_string_ =  _string_</span></span>
  
<span data-ttu-id="02509-111">格式 [**属性。**</span><span class="sxs-lookup"><span data-stu-id="02509-111">The format of a [ **Property.**</span></span> <span data-ttu-id="02509-112">_字符串_]部分是：</span><span class="sxs-lookup"><span data-stu-id="02509-112">_string_] section is:</span></span> 
  
 <span data-ttu-id="02509-113">**[属性。**</span><span class="sxs-lookup"><span data-stu-id="02509-113">**[Property.**</span></span> <span data-ttu-id="02509-114">_字符串_**]**</span><span class="sxs-lookup"><span data-stu-id="02509-114">_string_ **]**</span></span>
  
 <span data-ttu-id="02509-115">**类型** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="02509-115">**Type** =  _integer_</span></span>
  
 <span data-ttu-id="02509-116">**NmidPropset** =  _guid_</span><span class="sxs-lookup"><span data-stu-id="02509-116">**NmidPropset** =  _guid_</span></span>
  
 <span data-ttu-id="02509-117">**NmidString** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="02509-117">**NmidString** =  _string_</span></span>
  
 <span data-ttu-id="02509-118">**NmidInteger** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="02509-118">**NmidInteger** =  _integer_</span></span>
  
 <span data-ttu-id="02509-119">**DisplayName** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="02509-119">**DisplayName** =  _string_</span></span>
  
 <span data-ttu-id="02509-120">**Flags** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="02509-120">**Flags** =  _integer_</span></span>
  
 <span data-ttu-id="02509-121">**SpecialType** = 0 | 1</span><span class="sxs-lookup"><span data-stu-id="02509-121">**SpecialType** = 0|1</span></span> 
  
 <span data-ttu-id="02509-122">**1>** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="02509-122">**Enum1** =  _string_</span></span>
  
<span data-ttu-id="02509-123">每个 **[属性。**</span><span class="sxs-lookup"><span data-stu-id="02509-123">Each **[Property.**</span></span> <span data-ttu-id="02509-124">_字符串_**]** 部分介绍单个属性。</span><span class="sxs-lookup"><span data-stu-id="02509-124">_string_ **]** section describes a single property.</span></span> <span data-ttu-id="02509-125">该**类型**条目指定 MAPI 属性类型，例如 3 (PT_I4) 的属性。</span><span class="sxs-lookup"><span data-stu-id="02509-125">The **Type** entry specifies the MAPI property type, for example 3 (PT_I4), of the property.</span></span> <span data-ttu-id="02509-126">**NmidPropset**条目是可选的。**NmidString**条目或**NmidInteger**条目，以及**NmidPropset**条目提供属性的名称。</span><span class="sxs-lookup"><span data-stu-id="02509-126">The **NmidPropset** entry is optional; together with either the **NmidString** entry or the **NmidInteger** entry, the **NmidPropset** entry gives the name of the property.</span></span> <span data-ttu-id="02509-127">**NmidString**提供属性的名称，而**NmidInteger**提供属性的标识符。</span><span class="sxs-lookup"><span data-stu-id="02509-127">**NmidString** gives the name of the property, while **NmidInteger** gives the identifier of the property.</span></span> <span data-ttu-id="02509-128">**NmidString**和**NmidInteger**互斥。</span><span class="sxs-lookup"><span data-stu-id="02509-128">**NmidString** and **NmidInteger** are mutually exclusive.</span></span> 
  
<span data-ttu-id="02509-129">如果设置， **NmidPropset**应包含的属性集; 名称如果不存在， **NmidPropset**设置为默认的基于以下规则： 如果**NmidInteger**存在且其值为小于 0x8000， **NmidPropset**将设置为 PS_MAPI。</span><span class="sxs-lookup"><span data-stu-id="02509-129">If set, **NmidPropset** should contain the name of the property set; if absent, **NmidPropset** is set to a default based on the following rule: If **NmidInteger** is present and its value is less than 0x8000, **NmidPropset** is set to PS_MAPI.</span></span> <span data-ttu-id="02509-130">如果**NmidInteger**的值设置为一个整数值大于 0x8000，或不存在， **NmidPropset**设置为 PS_PUBLIC_STRINGS。</span><span class="sxs-lookup"><span data-stu-id="02509-130">If the value of **NmidInteger** is set to an integer greater than 0x8000, or if it is absent, **NmidPropset** is set to PS_PUBLIC_STRINGS.</span></span> 
  
<span data-ttu-id="02509-131">**DisplayName**条目包含属性的标签。</span><span class="sxs-lookup"><span data-stu-id="02509-131">The **DisplayName** entry contains the label for the property.</span></span> <span data-ttu-id="02509-132">**SpecialType**条目，是否存在且非零值指示此属性是一个特殊的属性。</span><span class="sxs-lookup"><span data-stu-id="02509-132">The **SpecialType** entry, if present and nonzero indicates that this property is a special property.</span></span> <span data-ttu-id="02509-133">目前，仅特殊属性类型定义为**SpecialType** = 1，这表示字符串枚举属性。</span><span class="sxs-lookup"><span data-stu-id="02509-133">At present, the only special property type defined is **SpecialType** = 1, which indicates string enumerated properties.</span></span> <span data-ttu-id="02509-134">如果**SpecialType**设置为 1， **1>** 条目引用 **[1>。**</span><span class="sxs-lookup"><span data-stu-id="02509-134">If **SpecialType** is set to 1, the **Enum1** entry references the **[Enum1.**</span></span> <span data-ttu-id="02509-135">_字符串_**]** 部分。</span><span class="sxs-lookup"><span data-stu-id="02509-135">_string_ **]** section.</span></span> 
  
<span data-ttu-id="02509-136">以下是**属性**部分的示例和 **[属性。**</span><span class="sxs-lookup"><span data-stu-id="02509-136">Following is an example of a **[Properties]** section and a **[Properties.**</span></span> <span data-ttu-id="02509-137">_字符串_**]** 部分。</span><span class="sxs-lookup"><span data-stu-id="02509-137">_string_ **]** section.</span></span> 
  
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

<span data-ttu-id="02509-138">对后续的前一示例引用中的**1>** 条目 **[1>。**</span><span class="sxs-lookup"><span data-stu-id="02509-138">The **Enum1** entry in the preceeding example references to a subsequent **[Enum1.**</span></span> <span data-ttu-id="02509-139">_字符串_**]** 部分描述特定类型的枚举。</span><span class="sxs-lookup"><span data-stu-id="02509-139">_string_ **]** section describing an enumeration of a particular type.</span></span> <span data-ttu-id="02509-140">此类枚举将关联中的第一个属性 **[属性。**</span><span class="sxs-lookup"><span data-stu-id="02509-140">Such an enumeration associates the first property in the **[Property.**</span></span> <span data-ttu-id="02509-141">_字符串_**]** 部分，包含一个整数属性，称为索引。</span><span class="sxs-lookup"><span data-stu-id="02509-141">_string_ **]** section with an integer property, called the index.</span></span> <span data-ttu-id="02509-142">此类枚举还包含一组显示索引对可以假定的可能值。</span><span class="sxs-lookup"><span data-stu-id="02509-142">Such an enumeration also contains a list of the possible values that the display-index pair can assume.</span></span> <span data-ttu-id="02509-143">指定枚举的属性类型是不必要的因为根据定义**1>** 条目始终 PT_I4 类型。</span><span class="sxs-lookup"><span data-stu-id="02509-143">Specifying a property type for the enumeration is unnecessary because by definition an **Enum1** entry always has the PT_I4 type.</span></span> <span data-ttu-id="02509-144">格式为 **[1>。**</span><span class="sxs-lookup"><span data-stu-id="02509-144">The format for the **[Enum1.**</span></span> <span data-ttu-id="02509-145">_字符串_**]** 部分是：</span><span class="sxs-lookup"><span data-stu-id="02509-145">_string_ **]** section is:</span></span> 
  
 <span data-ttu-id="02509-146">**[1>。**</span><span class="sxs-lookup"><span data-stu-id="02509-146">**[Enum1.**</span></span> <span data-ttu-id="02509-147">_字符串_**]**</span><span class="sxs-lookup"><span data-stu-id="02509-147">_string_ **]**</span></span>
  
 <span data-ttu-id="02509-148">**NmidPropset** =  _guid_</span><span class="sxs-lookup"><span data-stu-id="02509-148">**NmidPropset** =  _guid_</span></span>
  
 <span data-ttu-id="02509-149">**NmidString** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="02509-149">**NmidString** =  _string_</span></span>
  
 <span data-ttu-id="02509-150">**NmidInteger** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="02509-150">**NmidInteger** =  _integer_</span></span>
  
 <span data-ttu-id="02509-151">**EnumCount** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="02509-151">**EnumCount** =  _integer_</span></span>
  
 <span data-ttu-id="02509-152">**Val。**</span><span class="sxs-lookup"><span data-stu-id="02509-152">**Val.**</span></span> <span data-ttu-id="02509-153">_整数_**.显示** =  _字符串_</span><span class="sxs-lookup"><span data-stu-id="02509-153">_integer_ **.Display** =  _string_</span></span>
  
 <span data-ttu-id="02509-154">**Val。**</span><span class="sxs-lookup"><span data-stu-id="02509-154">**Val.**</span></span> <span data-ttu-id="02509-155">_整数_**.索引** =  _整数_</span><span class="sxs-lookup"><span data-stu-id="02509-155">_integer_ **.Index** =  _integer_</span></span>
  
<span data-ttu-id="02509-156">以下是名为火灾危险的低、 中型和高的可能值是枚举属性定义示例属性。</span><span class="sxs-lookup"><span data-stu-id="02509-156">The following is an example property definition for an enumerated property named Fire Hazard with possible values of Low, Medium, and High.</span></span>
  
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

 <span data-ttu-id="02509-157">**[1>。**</span><span class="sxs-lookup"><span data-stu-id="02509-157">**[Enum1.**</span></span> <span data-ttu-id="02509-158">_字符串_**]** 部分可用于应用程序通过两种用途： 加快使用而非字符串索引筛选属性并由不同的顺序比字符串值的字母顺序排序。</span><span class="sxs-lookup"><span data-stu-id="02509-158">_string_ **]** sections can be used by applications for two purposes: to speed up the filtering of properties by using the index instead of the string and to sort by a different order than the alphanumeric order of the string values.</span></span> <span data-ttu-id="02509-159">例如，排序能根据低-中的高顺序而不是高-中低顺序。</span><span class="sxs-lookup"><span data-stu-id="02509-159">For example, sorting could be done based on Low-Medium-High order instead of High-Medium-Low order.</span></span> 
  

