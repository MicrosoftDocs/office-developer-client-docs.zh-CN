---
title: currentType 复杂类型 （Outlook 天气信息架构）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9f4663ac-13d3-6c46-f839-ba6bca4047a3
description: 定义有关的当前的天气条件的位置的参数。
ms.openlocfilehash: 16d3e23375f68315c9b9f3a7e914d93f4fec9d0a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387032"
---
# <a name="currenttype-complextype-outlook-weather-information-schema"></a><span data-ttu-id="8355d-103">currentType 复杂类型 （Outlook 天气信息架构）</span><span class="sxs-lookup"><span data-stu-id="8355d-103">currentType complexType (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="8355d-104">定义有关的当前的天气条件的位置的参数。</span><span class="sxs-lookup"><span data-stu-id="8355d-104">Defines the parameters about the current weather conditions of a location.</span></span>
  
## <a name="type-information"></a><span data-ttu-id="8355d-105">类型信息</span><span class="sxs-lookup"><span data-stu-id="8355d-105">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8355d-106">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="8355d-106">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="8355d-107">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="8355d-107">**Schema file**</span></span> <br/> |<span data-ttu-id="8355d-108">getweatherinfo.xsd</span><span class="sxs-lookup"><span data-stu-id="8355d-108">getweatherinfo.xsd</span></span>  <br/> |
|<span data-ttu-id="8355d-109">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="8355d-109">**Extension base**</span></span> <br/> |<span data-ttu-id="8355d-110">无</span><span class="sxs-lookup"><span data-stu-id="8355d-110">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="8355d-111">定义</span><span class="sxs-lookup"><span data-stu-id="8355d-111">Definition</span></span>

```XML
       <xs:complexType name="currentType">
     <xs:attribute name="winddisplay"   type="xs:string"      use="required"     />
     <xs:attribute name="windspeed"   type="xs:integer"      use="required"     />
     <xs:attribute name="humidity"   type="xs:integer"      use="required"     />
     <xs:attribute name="feelslike"   type="xs:integer"      use="required"     />
     <xs:attribute name="observationpoint"   type="xs:string"      use="required"     />
     <xs:attribute name="observationtime"   type="xs:time"      use="required"     />
     <xs:attribute name="date"   type="xs:date"      use="required"     />
     <xs:attribute name="skytext"   type="xs:string"      use="required"     />
     <xs:attribute name="skycode"   type="xs:integer"      use="required"     />
     <xs:attribute name="temperature"   type="xs:integer"      use="required"     />
     <xs:attribute name="shortday"   type="xs:string"      use="optional"     />
     <xs:attribute name="day"   type="xs:string"      use="optional"     />
       </xs:complexType>

```

## <a name="elements-and-attributes"></a><span data-ttu-id="8355d-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="8355d-112">Elements and attributes</span></span>

<span data-ttu-id="8355d-113">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="8355d-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="8355d-114">子元素</span><span class="sxs-lookup"><span data-stu-id="8355d-114">Child elements</span></span>

<span data-ttu-id="8355d-115">无。</span><span class="sxs-lookup"><span data-stu-id="8355d-115">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="8355d-116">属性</span><span class="sxs-lookup"><span data-stu-id="8355d-116">Attributes</span></span>

|<span data-ttu-id="8355d-117">**属性**</span><span class="sxs-lookup"><span data-stu-id="8355d-117">**Attribute**</span></span>|<span data-ttu-id="8355d-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="8355d-118">**Type**</span></span>|<span data-ttu-id="8355d-119">**必需**</span><span class="sxs-lookup"><span data-stu-id="8355d-119">**Required**</span></span>|<span data-ttu-id="8355d-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="8355d-120">**Description**</span></span>|<span data-ttu-id="8355d-121">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="8355d-121">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8355d-122">date</span><span class="sxs-lookup"><span data-stu-id="8355d-122">date</span></span>  <br/> |<span data-ttu-id="8355d-123">xs: date</span><span class="sxs-lookup"><span data-stu-id="8355d-123">xs:date</span></span>  <br/> |<span data-ttu-id="8355d-124">必需</span><span class="sxs-lookup"><span data-stu-id="8355d-124">required</span></span>  <br/> |<span data-ttu-id="8355d-125">指定今天的日期。</span><span class="sxs-lookup"><span data-stu-id="8355d-125">Specifies today's date.</span></span>  <br/> |<span data-ttu-id="8355d-126">值为类型 xs: date</span><span class="sxs-lookup"><span data-stu-id="8355d-126">A value of the type xs:date</span></span>  <br/> |
|<span data-ttu-id="8355d-127">一天</span><span class="sxs-lookup"><span data-stu-id="8355d-127">day</span></span>  <br/> |<span data-ttu-id="8355d-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="8355d-128">xs:string</span></span>  <br/> |<span data-ttu-id="8355d-129">可选</span><span class="sxs-lookup"><span data-stu-id="8355d-129">optional</span></span>  <br/> |<span data-ttu-id="8355d-130">指定为预测一天。</span><span class="sxs-lookup"><span data-stu-id="8355d-130">Specifies a day for the forecast.</span></span>  <br/> |<span data-ttu-id="8355d-131">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="8355d-131">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="8355d-132">feelslike</span><span class="sxs-lookup"><span data-stu-id="8355d-132">feelslike</span></span>  <br/> |<span data-ttu-id="8355d-133">xs:integer</span><span class="sxs-lookup"><span data-stu-id="8355d-133">xs:integer</span></span>  <br/> |<span data-ttu-id="8355d-134">必需</span><span class="sxs-lookup"><span data-stu-id="8355d-134">required</span></span>  <br/> |<span data-ttu-id="8355d-135">指定如何当前天气外观的温度。</span><span class="sxs-lookup"><span data-stu-id="8355d-135">Specifies the temperature of how the current weather feels like.</span></span>  <br/> |<span data-ttu-id="8355d-136">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="8355d-136">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="8355d-137">湿度</span><span class="sxs-lookup"><span data-stu-id="8355d-137">humidity</span></span>  <br/> |<span data-ttu-id="8355d-138">xs:integer</span><span class="sxs-lookup"><span data-stu-id="8355d-138">xs:integer</span></span>  <br/> |<span data-ttu-id="8355d-139">必需</span><span class="sxs-lookup"><span data-stu-id="8355d-139">required</span></span>  <br/> |<span data-ttu-id="8355d-140">指定当前的数字湿度值。</span><span class="sxs-lookup"><span data-stu-id="8355d-140">Specifies the current numerical humidity value.</span></span>  <br/> |<span data-ttu-id="8355d-141">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="8355d-141">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="8355d-142">observationpoint</span><span class="sxs-lookup"><span data-stu-id="8355d-142">observationpoint</span></span>  <br/> |<span data-ttu-id="8355d-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="8355d-143">xs:string</span></span>  <br/> |<span data-ttu-id="8355d-144">必需</span><span class="sxs-lookup"><span data-stu-id="8355d-144">required</span></span>  <br/> |<span data-ttu-id="8355d-145">指定从其中观察到当前的天气信息。</span><span class="sxs-lookup"><span data-stu-id="8355d-145">Specifies where the current weather information is observed from.</span></span>  <br/> |<span data-ttu-id="8355d-146">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="8355d-146">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="8355d-147">observationtime</span><span class="sxs-lookup"><span data-stu-id="8355d-147">observationtime</span></span>  <br/> |<span data-ttu-id="8355d-148">xs:time</span><span class="sxs-lookup"><span data-stu-id="8355d-148">xs:time</span></span>  <br/> |<span data-ttu-id="8355d-149">必需</span><span class="sxs-lookup"><span data-stu-id="8355d-149">required</span></span>  <br/> |<span data-ttu-id="8355d-150">指定当在观察到当前的天气信息。</span><span class="sxs-lookup"><span data-stu-id="8355d-150">Specifies when the current weather information is observed at.</span></span>  <br/> |<span data-ttu-id="8355d-151">值为类型 xs:time</span><span class="sxs-lookup"><span data-stu-id="8355d-151">A value of the type xs:time</span></span>  <br/> |
|<span data-ttu-id="8355d-152">shortday</span><span class="sxs-lookup"><span data-stu-id="8355d-152">shortday</span></span>  <br/> |<span data-ttu-id="8355d-153">xs:string</span><span class="sxs-lookup"><span data-stu-id="8355d-153">xs:string</span></span>  <br/> |<span data-ttu-id="8355d-154">可选</span><span class="sxs-lookup"><span data-stu-id="8355d-154">optional</span></span>  <br/> |<span data-ttu-id="8355d-155">缩写形式指定一天。</span><span class="sxs-lookup"><span data-stu-id="8355d-155">Specifies a day in abbreviated form.</span></span>  <br/> |<span data-ttu-id="8355d-156">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="8355d-156">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="8355d-157">skycode</span><span class="sxs-lookup"><span data-stu-id="8355d-157">skycode</span></span>  <br/> |<span data-ttu-id="8355d-158">xs:integer</span><span class="sxs-lookup"><span data-stu-id="8355d-158">xs:integer</span></span>  <br/> |<span data-ttu-id="8355d-159">必需</span><span class="sxs-lookup"><span data-stu-id="8355d-159">required</span></span>  <br/> |<span data-ttu-id="8355d-160">指定为当前的天气条件整数代码。</span><span class="sxs-lookup"><span data-stu-id="8355d-160">Specifies an integer code for the current weather conditions.</span></span>  <br/> |<span data-ttu-id="8355d-161">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="8355d-161">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="8355d-162">skytext</span><span class="sxs-lookup"><span data-stu-id="8355d-162">skytext</span></span>  <br/> |<span data-ttu-id="8355d-163">xs:string</span><span class="sxs-lookup"><span data-stu-id="8355d-163">xs:string</span></span>  <br/> |<span data-ttu-id="8355d-164">必需</span><span class="sxs-lookup"><span data-stu-id="8355d-164">required</span></span>  <br/> |<span data-ttu-id="8355d-165">指定一到两个单词描述当前天气条件。</span><span class="sxs-lookup"><span data-stu-id="8355d-165">Specifies one to two words describing current weather conditions.</span></span>  <br/> |<span data-ttu-id="8355d-166">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="8355d-166">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="8355d-167">温度</span><span class="sxs-lookup"><span data-stu-id="8355d-167">temperature</span></span>  <br/> |<span data-ttu-id="8355d-168">xs:integer</span><span class="sxs-lookup"><span data-stu-id="8355d-168">xs:integer</span></span>  <br/> |<span data-ttu-id="8355d-169">必需</span><span class="sxs-lookup"><span data-stu-id="8355d-169">required</span></span>  <br/> |<span data-ttu-id="8355d-170">指定当前温度的位置。</span><span class="sxs-lookup"><span data-stu-id="8355d-170">Specifies the current temperature of the location.</span></span>  <br/> |<span data-ttu-id="8355d-171">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="8355d-171">A value of the type xs:integer</span></span>  <br/> |
|<span data-ttu-id="8355d-172">winddisplay</span><span class="sxs-lookup"><span data-stu-id="8355d-172">winddisplay</span></span>  <br/> |<span data-ttu-id="8355d-173">xs:string</span><span class="sxs-lookup"><span data-stu-id="8355d-173">xs:string</span></span>  <br/> |<span data-ttu-id="8355d-174">必需</span><span class="sxs-lookup"><span data-stu-id="8355d-174">required</span></span>  <br/> |<span data-ttu-id="8355d-175">描述的当前风条件的字符串。</span><span class="sxs-lookup"><span data-stu-id="8355d-175">A string that describes the current wind conditions.</span></span>  <br/> |<span data-ttu-id="8355d-176">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="8355d-176">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="8355d-177">windspeed</span><span class="sxs-lookup"><span data-stu-id="8355d-177">windspeed</span></span>  <br/> |<span data-ttu-id="8355d-178">xs:integer</span><span class="sxs-lookup"><span data-stu-id="8355d-178">xs:integer</span></span>  <br/> |<span data-ttu-id="8355d-179">必需</span><span class="sxs-lookup"><span data-stu-id="8355d-179">required</span></span>  <br/> |<span data-ttu-id="8355d-180">指定当前数字风速度值。</span><span class="sxs-lookup"><span data-stu-id="8355d-180">Specifies the current numerical wind speed value.</span></span>  <br/> |<span data-ttu-id="8355d-181">值为类型 xs:integer</span><span class="sxs-lookup"><span data-stu-id="8355d-181">A value of the type xs:integer</span></span>  <br/> |
   

