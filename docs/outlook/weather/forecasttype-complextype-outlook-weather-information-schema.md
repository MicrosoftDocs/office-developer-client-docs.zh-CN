---
title: forecastType 复杂类型 （Outlook 天气信息架构）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6301d6b6-34fa-af8d-e682-605d35cfdf47
description: 定义有关的位置的预报的天气条件的参数。
ms.openlocfilehash: 75f20d7857fac85e1e95d23cf5ac826336648132
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390623"
---
# <a name="forecasttype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="0265b-103">forecastType 复杂类型 （Outlook 天气信息架构）</span><span class="sxs-lookup"><span data-stu-id="0265b-103">forecastType complexType (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="0265b-104">定义有关的位置的预报的天气条件的参数。</span><span class="sxs-lookup"><span data-stu-id="0265b-104">Defines the parameters about the forecast weather conditions of a location.</span></span>
  
## <a name="type-information"></a><span data-ttu-id="0265b-105">类型信息</span><span class="sxs-lookup"><span data-stu-id="0265b-105">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0265b-106">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="0265b-106">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="0265b-107">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="0265b-107">**Schema file**</span></span> <br/> |<span data-ttu-id="0265b-108">getweatherinfo.xsd</span><span class="sxs-lookup"><span data-stu-id="0265b-108">getweatherinfo.xsd</span></span>  <br/> |
|<span data-ttu-id="0265b-109">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="0265b-109">**Extension base**</span></span> <br/> |<span data-ttu-id="0265b-110">无</span><span class="sxs-lookup"><span data-stu-id="0265b-110">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="0265b-111">定义</span><span class="sxs-lookup"><span data-stu-id="0265b-111">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="0265b-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="0265b-112">Elements and attributes</span></span>

<span data-ttu-id="0265b-113">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="0265b-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="0265b-114">子元素</span><span class="sxs-lookup"><span data-stu-id="0265b-114">Child elements</span></span>

<span data-ttu-id="0265b-115">无。</span><span class="sxs-lookup"><span data-stu-id="0265b-115">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="0265b-116">属性</span><span class="sxs-lookup"><span data-stu-id="0265b-116">Attributes</span></span>

|<span data-ttu-id="0265b-117">**属性**</span><span class="sxs-lookup"><span data-stu-id="0265b-117">**Attribute**</span></span>|<span data-ttu-id="0265b-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="0265b-118">**Type**</span></span>|<span data-ttu-id="0265b-119">**必需**</span><span class="sxs-lookup"><span data-stu-id="0265b-119">**Required**</span></span>|<span data-ttu-id="0265b-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="0265b-120">**Description**</span></span>|<span data-ttu-id="0265b-121">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="0265b-121">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0265b-122">date</span><span class="sxs-lookup"><span data-stu-id="0265b-122">date</span></span>  <br/> |<span data-ttu-id="0265b-123">xs: date</span><span class="sxs-lookup"><span data-stu-id="0265b-123">xs:date</span></span>  <br/> |<span data-ttu-id="0265b-124">必需</span><span class="sxs-lookup"><span data-stu-id="0265b-124">required</span></span>  <br/> |<span data-ttu-id="0265b-125">指定为预测的日期。</span><span class="sxs-lookup"><span data-stu-id="0265b-125">Specifies the date for the forecast.</span></span>  <br/> |<span data-ttu-id="0265b-126">值为类型 xs: date</span><span class="sxs-lookup"><span data-stu-id="0265b-126">A value of the type xs:date</span></span>  <br/> |
|<span data-ttu-id="0265b-127">一天</span><span class="sxs-lookup"><span data-stu-id="0265b-127">day</span></span>  <br/> |<span data-ttu-id="0265b-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="0265b-128">xs:string</span></span>  <br/> |<span data-ttu-id="0265b-129">必需</span><span class="sxs-lookup"><span data-stu-id="0265b-129">required</span></span>  <br/> |<span data-ttu-id="0265b-130">指定为预测一天。</span><span class="sxs-lookup"><span data-stu-id="0265b-130">Specifies a day for the forecast.</span></span>  <br/> |<span data-ttu-id="0265b-131">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="0265b-131">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="0265b-132">高</span><span class="sxs-lookup"><span data-stu-id="0265b-132">high</span></span>  <br/> |<span data-ttu-id="0265b-133">xs:integer</span><span class="sxs-lookup"><span data-stu-id="0265b-133">xs:integer</span></span>  <br/> |<span data-ttu-id="0265b-134">必需</span><span class="sxs-lookup"><span data-stu-id="0265b-134">required</span></span>  <br/> |<span data-ttu-id="0265b-135">指定的预测的最高温度。</span><span class="sxs-lookup"><span data-stu-id="0265b-135">Specifies the forecasted highest temperature.</span></span>  <br/> |<span data-ttu-id="0265b-136">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="0265b-136">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="0265b-137">低</span><span class="sxs-lookup"><span data-stu-id="0265b-137">low</span></span>  <br/> |<span data-ttu-id="0265b-138">xs:integer</span><span class="sxs-lookup"><span data-stu-id="0265b-138">xs:integer</span></span>  <br/> |<span data-ttu-id="0265b-139">必需</span><span class="sxs-lookup"><span data-stu-id="0265b-139">required</span></span>  <br/> |<span data-ttu-id="0265b-140">指定的预测的最低温度。</span><span class="sxs-lookup"><span data-stu-id="0265b-140">Specifies the forecasted lowest temperature.</span></span>  <br/> |<span data-ttu-id="0265b-141">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="0265b-141">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="0265b-142">precip</span><span class="sxs-lookup"><span data-stu-id="0265b-142">precip</span></span>  <br/> |<span data-ttu-id="0265b-143">xs:integer</span><span class="sxs-lookup"><span data-stu-id="0265b-143">xs:integer</span></span>  <br/> |<span data-ttu-id="0265b-144">必需</span><span class="sxs-lookup"><span data-stu-id="0265b-144">required</span></span>  <br/> |<span data-ttu-id="0265b-145">指定雨百分比的可能性。</span><span class="sxs-lookup"><span data-stu-id="0265b-145">Specifies the percentage possibility of precipitation.</span></span>  <br/> |<span data-ttu-id="0265b-146">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="0265b-146">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="0265b-147">shortday</span><span class="sxs-lookup"><span data-stu-id="0265b-147">shortday</span></span>  <br/> |<span data-ttu-id="0265b-148">xs:string</span><span class="sxs-lookup"><span data-stu-id="0265b-148">xs:string</span></span>  <br/> |<span data-ttu-id="0265b-149">必需</span><span class="sxs-lookup"><span data-stu-id="0265b-149">required</span></span>  <br/> |<span data-ttu-id="0265b-150">缩写形式指定一天。</span><span class="sxs-lookup"><span data-stu-id="0265b-150">Specifies a day in abbreviated form.</span></span>  <br/> |<span data-ttu-id="0265b-151">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="0265b-151">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="0265b-152">skycodeday</span><span class="sxs-lookup"><span data-stu-id="0265b-152">skycodeday</span></span>  <br/> |<span data-ttu-id="0265b-153">xs:integer</span><span class="sxs-lookup"><span data-stu-id="0265b-153">xs:integer</span></span>  <br/> |<span data-ttu-id="0265b-154">必需</span><span class="sxs-lookup"><span data-stu-id="0265b-154">required</span></span>  <br/> |<span data-ttu-id="0265b-155">指定的预测的条件的代码。</span><span class="sxs-lookup"><span data-stu-id="0265b-155">Specifies a code for the forecasted conditions.</span></span>  <br/> |<span data-ttu-id="0265b-156">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="0265b-156">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="0265b-157">skytextday</span><span class="sxs-lookup"><span data-stu-id="0265b-157">skytextday</span></span>  <br/> |<span data-ttu-id="0265b-158">xs:string</span><span class="sxs-lookup"><span data-stu-id="0265b-158">xs:string</span></span>  <br/> |<span data-ttu-id="0265b-159">必需</span><span class="sxs-lookup"><span data-stu-id="0265b-159">required</span></span>  <br/> |<span data-ttu-id="0265b-160">指定一到两个单词的描述的预测的条件。</span><span class="sxs-lookup"><span data-stu-id="0265b-160">Specifies one to two words that describe the forecasted conditions.</span></span>  <br/> |<span data-ttu-id="0265b-161">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="0265b-161">A value of the type xs:string</span></span>  <br/> |
   

