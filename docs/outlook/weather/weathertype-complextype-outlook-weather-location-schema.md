---
title: weatherType 复杂类型 （Outlook 天气位置架构）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f8054fd9-85ba-fcf6-c96d-a54095d5238c
description: 定义有关的位置的天气条件的参数。
ms.openlocfilehash: c3d640789cb68891878c3dca5210ab9dea280180
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25387711"
---
# <a name="weathertype-complextype-outlook-weather-location-schema"></a><span data-ttu-id="6beec-103">weatherType 复杂类型 （Outlook 天气位置架构）</span><span class="sxs-lookup"><span data-stu-id="6beec-103">weatherType complexType (Outlook Weather Location Schema)</span></span>

<span data-ttu-id="6beec-104">定义有关的位置的天气条件的参数。</span><span class="sxs-lookup"><span data-stu-id="6beec-104">Defines the parameters about the weather conditions of a location.</span></span>
  
## <a name="type-information"></a><span data-ttu-id="6beec-105">类型信息</span><span class="sxs-lookup"><span data-stu-id="6beec-105">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6beec-106">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="6beec-106">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherlocation.xsd  <br/> |
|<span data-ttu-id="6beec-107">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="6beec-107">**Schema file**</span></span> <br/> |<span data-ttu-id="6beec-108">getweatherlocation.xsd</span><span class="sxs-lookup"><span data-stu-id="6beec-108">getweatherlocation.xsd</span></span>  <br/> |
|<span data-ttu-id="6beec-109">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="6beec-109">**Extension base**</span></span> <br/> |<span data-ttu-id="6beec-110">无</span><span class="sxs-lookup"><span data-stu-id="6beec-110">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="6beec-111">定义</span><span class="sxs-lookup"><span data-stu-id="6beec-111">Definition</span></span>

```XML
       <xs:complexType name="weatherType">
     <xs:attribute name="weatherlocationname"   type="xs:string"      use="required"     />
     <xs:attribute name="weatherlocationcode"   type="xs:string"      use="required"     />
       </xs:complexType>

```

## <a name="elements-and-attributes"></a><span data-ttu-id="6beec-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="6beec-112">Elements and attributes</span></span>

<span data-ttu-id="6beec-113">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="6beec-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="6beec-114">子元素</span><span class="sxs-lookup"><span data-stu-id="6beec-114">Child elements</span></span>

<span data-ttu-id="6beec-115">无。</span><span class="sxs-lookup"><span data-stu-id="6beec-115">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="6beec-116">属性</span><span class="sxs-lookup"><span data-stu-id="6beec-116">Attributes</span></span>

|<span data-ttu-id="6beec-117">**属性**</span><span class="sxs-lookup"><span data-stu-id="6beec-117">**Attribute**</span></span>|<span data-ttu-id="6beec-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="6beec-118">**Type**</span></span>|<span data-ttu-id="6beec-119">**必需**</span><span class="sxs-lookup"><span data-stu-id="6beec-119">**Required**</span></span>|<span data-ttu-id="6beec-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="6beec-120">**Description**</span></span>|<span data-ttu-id="6beec-121">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="6beec-121">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6beec-122">weatherlocationcode</span><span class="sxs-lookup"><span data-stu-id="6beec-122">weatherlocationcode</span></span>  <br/> |<span data-ttu-id="6beec-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="6beec-123">xs:string</span></span>  <br/> |<span data-ttu-id="6beec-124">必需</span><span class="sxs-lookup"><span data-stu-id="6beec-124">required</span></span>  <br/> |<span data-ttu-id="6beec-125">指定与要区分具有相同名称的多个位置的位置相关联的代码。</span><span class="sxs-lookup"><span data-stu-id="6beec-125">Specifies a code that is associated with the location to distinguish multiple locations with the same name.</span></span>  <br/> |<span data-ttu-id="6beec-126">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="6beec-126">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="6beec-127">weatherlocationname</span><span class="sxs-lookup"><span data-stu-id="6beec-127">weatherlocationname</span></span>  <br/> |<span data-ttu-id="6beec-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="6beec-128">xs:string</span></span>  <br/> |<span data-ttu-id="6beec-129">必需</span><span class="sxs-lookup"><span data-stu-id="6beec-129">required</span></span>  <br/> |<span data-ttu-id="6beec-130">指定的位置的名称。</span><span class="sxs-lookup"><span data-stu-id="6beec-130">Specifies the name of the location.</span></span>  <br/> |<span data-ttu-id="6beec-131">类型将一个值</span><span class="sxs-lookup"><span data-stu-id="6beec-131">A value of the type xs:string</span></span>  <br/> |
   

