---
title: forecastType 复杂类型 (Outlook 天气信息架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6301d6b6-34fa-af8d-e682-605d35cfdf47
description: 定义有关某个位置的预测天气条件的参数。
ms.openlocfilehash: e799ebbea72daa1788aedbdcadbc523b5e4dff0d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540950"
---
# <a name="forecasttype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="55640-103">forecastType 复杂类型 (Outlook 天气信息架构)</span><span class="sxs-lookup"><span data-stu-id="55640-103">forecastType complexType (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="55640-104">定义有关某个位置的预测天气条件的参数。</span><span class="sxs-lookup"><span data-stu-id="55640-104">Defines the parameters about the forecast weather conditions of a location.</span></span>
  
## <a name="type-information"></a><span data-ttu-id="55640-105">类型信息</span><span class="sxs-lookup"><span data-stu-id="55640-105">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="55640-106">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="55640-106">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="55640-107">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="55640-107">**Schema file**</span></span> <br/> |<span data-ttu-id="55640-108">getweatherinfo</span><span class="sxs-lookup"><span data-stu-id="55640-108">getweatherinfo.xsd</span></span>  <br/> |
|<span data-ttu-id="55640-109">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="55640-109">**Extension base**</span></span> <br/> |<span data-ttu-id="55640-110">无</span><span class="sxs-lookup"><span data-stu-id="55640-110">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="55640-111">定义</span><span class="sxs-lookup"><span data-stu-id="55640-111">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="55640-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="55640-112">Elements and attributes</span></span>

<span data-ttu-id="55640-113">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="55640-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="55640-114">子元素</span><span class="sxs-lookup"><span data-stu-id="55640-114">Child elements</span></span>

<span data-ttu-id="55640-115">无。</span><span class="sxs-lookup"><span data-stu-id="55640-115">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="55640-116">属性</span><span class="sxs-lookup"><span data-stu-id="55640-116">Attributes</span></span>

|<span data-ttu-id="55640-117">**属性**</span><span class="sxs-lookup"><span data-stu-id="55640-117">**Attribute**</span></span>|<span data-ttu-id="55640-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="55640-118">**Type**</span></span>|<span data-ttu-id="55640-119">**必需**</span><span class="sxs-lookup"><span data-stu-id="55640-119">**Required**</span></span>|<span data-ttu-id="55640-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="55640-120">**Description**</span></span>|<span data-ttu-id="55640-121">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="55640-121">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="55640-122">date</span><span class="sxs-lookup"><span data-stu-id="55640-122">date</span></span>  <br/> |<span data-ttu-id="55640-123">xs: date</span><span class="sxs-lookup"><span data-stu-id="55640-123">xs:date</span></span>  <br/> |<span data-ttu-id="55640-124">必需</span><span class="sxs-lookup"><span data-stu-id="55640-124">required</span></span>  <br/> |<span data-ttu-id="55640-125">指定预测的日期。</span><span class="sxs-lookup"><span data-stu-id="55640-125">Specifies the date for the forecast.</span></span>  <br/> |<span data-ttu-id="55640-126">类型 xs: date 的值</span><span class="sxs-lookup"><span data-stu-id="55640-126">A value of the type xs:date</span></span>  <br/> |
|<span data-ttu-id="55640-127">为期</span><span class="sxs-lookup"><span data-stu-id="55640-127">day</span></span>  <br/> |<span data-ttu-id="55640-128">xs: string</span><span class="sxs-lookup"><span data-stu-id="55640-128">xs:string</span></span>  <br/> |<span data-ttu-id="55640-129">必需</span><span class="sxs-lookup"><span data-stu-id="55640-129">required</span></span>  <br/> |<span data-ttu-id="55640-130">指定预测的日期。</span><span class="sxs-lookup"><span data-stu-id="55640-130">Specifies a day for the forecast.</span></span>  <br/> |<span data-ttu-id="55640-131">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="55640-131">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="55640-132">高效</span><span class="sxs-lookup"><span data-stu-id="55640-132">high</span></span>  <br/> |<span data-ttu-id="55640-133">xs: integer</span><span class="sxs-lookup"><span data-stu-id="55640-133">xs:integer</span></span>  <br/> |<span data-ttu-id="55640-134">必需</span><span class="sxs-lookup"><span data-stu-id="55640-134">required</span></span>  <br/> |<span data-ttu-id="55640-135">指定预测的最高温度。</span><span class="sxs-lookup"><span data-stu-id="55640-135">Specifies the forecasted highest temperature.</span></span>  <br/> |<span data-ttu-id="55640-136">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="55640-136">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="55640-137">降低</span><span class="sxs-lookup"><span data-stu-id="55640-137">low</span></span>  <br/> |<span data-ttu-id="55640-138">xs: integer</span><span class="sxs-lookup"><span data-stu-id="55640-138">xs:integer</span></span>  <br/> |<span data-ttu-id="55640-139">必需</span><span class="sxs-lookup"><span data-stu-id="55640-139">required</span></span>  <br/> |<span data-ttu-id="55640-140">指定预测的最低温度。</span><span class="sxs-lookup"><span data-stu-id="55640-140">Specifies the forecasted lowest temperature.</span></span>  <br/> |<span data-ttu-id="55640-141">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="55640-141">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="55640-142">precip</span><span class="sxs-lookup"><span data-stu-id="55640-142">precip</span></span>  <br/> |<span data-ttu-id="55640-143">xs: integer</span><span class="sxs-lookup"><span data-stu-id="55640-143">xs:integer</span></span>  <br/> |<span data-ttu-id="55640-144">必需</span><span class="sxs-lookup"><span data-stu-id="55640-144">required</span></span>  <br/> |<span data-ttu-id="55640-145">指定 precipitation 的百分比可能性。</span><span class="sxs-lookup"><span data-stu-id="55640-145">Specifies the percentage possibility of precipitation.</span></span>  <br/> |<span data-ttu-id="55640-146">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="55640-146">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="55640-147">shortday</span><span class="sxs-lookup"><span data-stu-id="55640-147">shortday</span></span>  <br/> |<span data-ttu-id="55640-148">xs: string</span><span class="sxs-lookup"><span data-stu-id="55640-148">xs:string</span></span>  <br/> |<span data-ttu-id="55640-149">必需</span><span class="sxs-lookup"><span data-stu-id="55640-149">required</span></span>  <br/> |<span data-ttu-id="55640-150">指定缩写形式的日期。</span><span class="sxs-lookup"><span data-stu-id="55640-150">Specifies a day in abbreviated form.</span></span>  <br/> |<span data-ttu-id="55640-151">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="55640-151">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="55640-152">skycodeday</span><span class="sxs-lookup"><span data-stu-id="55640-152">skycodeday</span></span>  <br/> |<span data-ttu-id="55640-153">xs: integer</span><span class="sxs-lookup"><span data-stu-id="55640-153">xs:integer</span></span>  <br/> |<span data-ttu-id="55640-154">必需</span><span class="sxs-lookup"><span data-stu-id="55640-154">required</span></span>  <br/> |<span data-ttu-id="55640-155">指定预测条件的代码。</span><span class="sxs-lookup"><span data-stu-id="55640-155">Specifies a code for the forecasted conditions.</span></span>  <br/> |<span data-ttu-id="55640-156">类型 xs: integer 的值</span><span class="sxs-lookup"><span data-stu-id="55640-156">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="55640-157">skytextday</span><span class="sxs-lookup"><span data-stu-id="55640-157">skytextday</span></span>  <br/> |<span data-ttu-id="55640-158">xs: string</span><span class="sxs-lookup"><span data-stu-id="55640-158">xs:string</span></span>  <br/> |<span data-ttu-id="55640-159">必需</span><span class="sxs-lookup"><span data-stu-id="55640-159">required</span></span>  <br/> |<span data-ttu-id="55640-160">指定一到两个描述预测条件的词。</span><span class="sxs-lookup"><span data-stu-id="55640-160">Specifies one to two words that describe the forecasted conditions.</span></span>  <br/> |<span data-ttu-id="55640-161">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="55640-161">A value of the type xs:string</span></span>  <br/> |
   

