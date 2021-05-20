---
title: 'forecastType complexType (Outlook天气信息架构) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6301d6b6-34fa-af8d-e682-605d35cfdf47
description: 定义有关位置的天气预报条件的参数。
ms.openlocfilehash: e799ebbea72daa1788aedbdcadbc523b5e4dff0d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540950"
---
# <a name="forecasttype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="507ef-103">forecastType complexType (Outlook天气信息架构) </span><span class="sxs-lookup"><span data-stu-id="507ef-103">forecastType complexType (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="507ef-104">定义有关位置的天气预报条件的参数。</span><span class="sxs-lookup"><span data-stu-id="507ef-104">Defines the parameters about the forecast weather conditions of a location.</span></span>
  
## <a name="type-information"></a><span data-ttu-id="507ef-105">类型信息</span><span class="sxs-lookup"><span data-stu-id="507ef-105">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="507ef-106">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="507ef-106">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="507ef-107">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="507ef-107">**Schema file**</span></span> <br/> |<span data-ttu-id="507ef-108">getweatherinfo.xsd</span><span class="sxs-lookup"><span data-stu-id="507ef-108">getweatherinfo.xsd</span></span>  <br/> |
|<span data-ttu-id="507ef-109">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="507ef-109">**Extension base**</span></span> <br/> |<span data-ttu-id="507ef-110">无</span><span class="sxs-lookup"><span data-stu-id="507ef-110">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="507ef-111">定义</span><span class="sxs-lookup"><span data-stu-id="507ef-111">Definition</span></span>

```XML
       <xs:complexType name="forecastType">
     <xs:attribute name="shortday"   type="xs:string"      use="required"     />
     <xs:attribute name="day"   type="xs:string"      use="required"     />
     <xs:attribute name="date"   type="xs:date"      use="required"     />
     <xs:attribute name="precip"   type="xs:integer"      use="required"     />
     <xs:attribute name="skytextday"   type="xs:string"      use="required"     />
     <xs:attribute name="skycodeday"   type="xs:integer"      use="required"     />
     <xs:attribute name="high"   type="xs:integer"      use="required"     />
     <xs:attribute name="low"   type="xs:integer"      use="required"     />
       </xs:complexType>

```

## <a name="elements-and-attributes"></a><span data-ttu-id="507ef-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="507ef-112">Elements and attributes</span></span>

<span data-ttu-id="507ef-113">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="507ef-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="507ef-114">子元素</span><span class="sxs-lookup"><span data-stu-id="507ef-114">Child elements</span></span>

<span data-ttu-id="507ef-115">无。</span><span class="sxs-lookup"><span data-stu-id="507ef-115">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="507ef-116">属性</span><span class="sxs-lookup"><span data-stu-id="507ef-116">Attributes</span></span>

|<span data-ttu-id="507ef-117">**属性**</span><span class="sxs-lookup"><span data-stu-id="507ef-117">**Attribute**</span></span>|<span data-ttu-id="507ef-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="507ef-118">**Type**</span></span>|<span data-ttu-id="507ef-119">**必需**</span><span class="sxs-lookup"><span data-stu-id="507ef-119">**Required**</span></span>|<span data-ttu-id="507ef-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="507ef-120">**Description**</span></span>|<span data-ttu-id="507ef-121">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="507ef-121">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="507ef-122">date</span><span class="sxs-lookup"><span data-stu-id="507ef-122">date</span></span>  <br/> |<span data-ttu-id="507ef-123">xs：date</span><span class="sxs-lookup"><span data-stu-id="507ef-123">xs:date</span></span>  <br/> |<span data-ttu-id="507ef-124">必需</span><span class="sxs-lookup"><span data-stu-id="507ef-124">required</span></span>  <br/> |<span data-ttu-id="507ef-125">指定预测的日期。</span><span class="sxs-lookup"><span data-stu-id="507ef-125">Specifies the date for the forecast.</span></span>  <br/> |<span data-ttu-id="507ef-126">xs：date 类型的值</span><span class="sxs-lookup"><span data-stu-id="507ef-126">A value of the type xs:date</span></span>  <br/> |
|<span data-ttu-id="507ef-127">day</span><span class="sxs-lookup"><span data-stu-id="507ef-127">day</span></span>  <br/> |<span data-ttu-id="507ef-128">xs：string</span><span class="sxs-lookup"><span data-stu-id="507ef-128">xs:string</span></span>  <br/> |<span data-ttu-id="507ef-129">必需</span><span class="sxs-lookup"><span data-stu-id="507ef-129">required</span></span>  <br/> |<span data-ttu-id="507ef-130">指定预测的一天。</span><span class="sxs-lookup"><span data-stu-id="507ef-130">Specifies a day for the forecast.</span></span>  <br/> |<span data-ttu-id="507ef-131">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="507ef-131">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="507ef-132">high</span><span class="sxs-lookup"><span data-stu-id="507ef-132">high</span></span>  <br/> |<span data-ttu-id="507ef-133">xs：integer</span><span class="sxs-lookup"><span data-stu-id="507ef-133">xs:integer</span></span>  <br/> |<span data-ttu-id="507ef-134">必需</span><span class="sxs-lookup"><span data-stu-id="507ef-134">required</span></span>  <br/> |<span data-ttu-id="507ef-135">指定预测的最高温度。</span><span class="sxs-lookup"><span data-stu-id="507ef-135">Specifies the forecasted highest temperature.</span></span>  <br/> |<span data-ttu-id="507ef-136">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="507ef-136">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="507ef-137">low</span><span class="sxs-lookup"><span data-stu-id="507ef-137">low</span></span>  <br/> |<span data-ttu-id="507ef-138">xs：integer</span><span class="sxs-lookup"><span data-stu-id="507ef-138">xs:integer</span></span>  <br/> |<span data-ttu-id="507ef-139">必需</span><span class="sxs-lookup"><span data-stu-id="507ef-139">required</span></span>  <br/> |<span data-ttu-id="507ef-140">指定预测的最低温度。</span><span class="sxs-lookup"><span data-stu-id="507ef-140">Specifies the forecasted lowest temperature.</span></span>  <br/> |<span data-ttu-id="507ef-141">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="507ef-141">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="507ef-142">precip</span><span class="sxs-lookup"><span data-stu-id="507ef-142">precip</span></span>  <br/> |<span data-ttu-id="507ef-143">xs：integer</span><span class="sxs-lookup"><span data-stu-id="507ef-143">xs:integer</span></span>  <br/> |<span data-ttu-id="507ef-144">必需</span><span class="sxs-lookup"><span data-stu-id="507ef-144">required</span></span>  <br/> |<span data-ttu-id="507ef-145">指定可能性的百分比。</span><span class="sxs-lookup"><span data-stu-id="507ef-145">Specifies the percentage possibility of precipitation.</span></span>  <br/> |<span data-ttu-id="507ef-146">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="507ef-146">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="507ef-147">shortday</span><span class="sxs-lookup"><span data-stu-id="507ef-147">shortday</span></span>  <br/> |<span data-ttu-id="507ef-148">xs：string</span><span class="sxs-lookup"><span data-stu-id="507ef-148">xs:string</span></span>  <br/> |<span data-ttu-id="507ef-149">必需</span><span class="sxs-lookup"><span data-stu-id="507ef-149">required</span></span>  <br/> |<span data-ttu-id="507ef-150">以缩写形式指定一天。</span><span class="sxs-lookup"><span data-stu-id="507ef-150">Specifies a day in abbreviated form.</span></span>  <br/> |<span data-ttu-id="507ef-151">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="507ef-151">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="507ef-152">skycodeday</span><span class="sxs-lookup"><span data-stu-id="507ef-152">skycodeday</span></span>  <br/> |<span data-ttu-id="507ef-153">xs：integer</span><span class="sxs-lookup"><span data-stu-id="507ef-153">xs:integer</span></span>  <br/> |<span data-ttu-id="507ef-154">必需</span><span class="sxs-lookup"><span data-stu-id="507ef-154">required</span></span>  <br/> |<span data-ttu-id="507ef-155">指定预测条件的代码。</span><span class="sxs-lookup"><span data-stu-id="507ef-155">Specifies a code for the forecasted conditions.</span></span>  <br/> |<span data-ttu-id="507ef-156">xs：integer 类型的值</span><span class="sxs-lookup"><span data-stu-id="507ef-156">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="507ef-157">skytextday</span><span class="sxs-lookup"><span data-stu-id="507ef-157">skytextday</span></span>  <br/> |<span data-ttu-id="507ef-158">xs：string</span><span class="sxs-lookup"><span data-stu-id="507ef-158">xs:string</span></span>  <br/> |<span data-ttu-id="507ef-159">必需</span><span class="sxs-lookup"><span data-stu-id="507ef-159">required</span></span>  <br/> |<span data-ttu-id="507ef-160">指定描述预测条件的一到两个单词。</span><span class="sxs-lookup"><span data-stu-id="507ef-160">Specifies one to two words that describe the forecasted conditions.</span></span>  <br/> |<span data-ttu-id="507ef-161">xs：string 类型的值</span><span class="sxs-lookup"><span data-stu-id="507ef-161">A value of the type xs:string</span></span>  <br/> |
   

