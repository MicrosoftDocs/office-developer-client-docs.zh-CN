---
title: weatherType 复杂类型 (Outlook 天气位置架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f8054fd9-85ba-fcf6-c96d-a54095d5238c
description: 定义有关位置的天气条件的参数。
ms.openlocfilehash: c3d640789cb68891878c3dca5210ab9dea280180
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355179"
---
# <a name="weathertype-complextype-outlook-weather-location-schema"></a><span data-ttu-id="3b5a4-103">weatherType 复杂类型 (Outlook 天气位置架构)</span><span class="sxs-lookup"><span data-stu-id="3b5a4-103">weatherType complexType (Outlook Weather Location Schema)</span></span>

<span data-ttu-id="3b5a4-104">定义有关位置的天气条件的参数。</span><span class="sxs-lookup"><span data-stu-id="3b5a4-104">Defines the parameters about the weather conditions of a location.</span></span>
  
## <a name="type-information"></a><span data-ttu-id="3b5a4-105">类型信息</span><span class="sxs-lookup"><span data-stu-id="3b5a4-105">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3b5a4-106">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="3b5a4-106">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherlocation.xsd  <br/> |
|<span data-ttu-id="3b5a4-107">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="3b5a4-107">**Schema file**</span></span> <br/> |<span data-ttu-id="3b5a4-108">getweatherlocation</span><span class="sxs-lookup"><span data-stu-id="3b5a4-108">getweatherlocation.xsd</span></span>  <br/> |
|<span data-ttu-id="3b5a4-109">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="3b5a4-109">**Extension base**</span></span> <br/> |<span data-ttu-id="3b5a4-110">无</span><span class="sxs-lookup"><span data-stu-id="3b5a4-110">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="3b5a4-111">定义</span><span class="sxs-lookup"><span data-stu-id="3b5a4-111">Definition</span></span>

```XML
       <xs:complexType name="weatherType">
     <xs:attribute name="weatherlocationname"   type="xs:string"      use="required"     />
     <xs:attribute name="weatherlocationcode"   type="xs:string"      use="required"     />
       </xs:complexType>

```

## <a name="elements-and-attributes"></a><span data-ttu-id="3b5a4-112">元素和属性</span><span class="sxs-lookup"><span data-stu-id="3b5a4-112">Elements and attributes</span></span>

<span data-ttu-id="3b5a4-113">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="3b5a4-113">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="3b5a4-114">子元素</span><span class="sxs-lookup"><span data-stu-id="3b5a4-114">Child elements</span></span>

<span data-ttu-id="3b5a4-115">无。</span><span class="sxs-lookup"><span data-stu-id="3b5a4-115">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="3b5a4-116">属性</span><span class="sxs-lookup"><span data-stu-id="3b5a4-116">Attributes</span></span>

|<span data-ttu-id="3b5a4-117">**属性**</span><span class="sxs-lookup"><span data-stu-id="3b5a4-117">**Attribute**</span></span>|<span data-ttu-id="3b5a4-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="3b5a4-118">**Type**</span></span>|<span data-ttu-id="3b5a4-119">**必需**</span><span class="sxs-lookup"><span data-stu-id="3b5a4-119">**Required**</span></span>|<span data-ttu-id="3b5a4-120">**描述**</span><span class="sxs-lookup"><span data-stu-id="3b5a4-120">**Description**</span></span>|<span data-ttu-id="3b5a4-121">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="3b5a4-121">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b5a4-122">weatherlocationcode</span><span class="sxs-lookup"><span data-stu-id="3b5a4-122">weatherlocationcode</span></span>  <br/> |<span data-ttu-id="3b5a4-123">xs: string</span><span class="sxs-lookup"><span data-stu-id="3b5a4-123">xs:string</span></span>  <br/> |<span data-ttu-id="3b5a4-124">必需</span><span class="sxs-lookup"><span data-stu-id="3b5a4-124">required</span></span>  <br/> |<span data-ttu-id="3b5a4-125">指定与位置相关联的代码, 以区分具有相同名称的多个位置。</span><span class="sxs-lookup"><span data-stu-id="3b5a4-125">Specifies a code that is associated with the location to distinguish multiple locations with the same name.</span></span>  <br/> |<span data-ttu-id="3b5a4-126">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="3b5a4-126">A value of the type xs:string</span></span>  <br/> |
|<span data-ttu-id="3b5a4-127">表示 weatherlocationname</span><span class="sxs-lookup"><span data-stu-id="3b5a4-127">weatherlocationname</span></span>  <br/> |<span data-ttu-id="3b5a4-128">xs: string</span><span class="sxs-lookup"><span data-stu-id="3b5a4-128">xs:string</span></span>  <br/> |<span data-ttu-id="3b5a4-129">必需</span><span class="sxs-lookup"><span data-stu-id="3b5a4-129">required</span></span>  <br/> |<span data-ttu-id="3b5a4-130">指定位置的名称。</span><span class="sxs-lookup"><span data-stu-id="3b5a4-130">Specifies the name of the location.</span></span>  <br/> |<span data-ttu-id="3b5a4-131">类型 xs: string 的值</span><span class="sxs-lookup"><span data-stu-id="3b5a4-131">A value of the type xs:string</span></span>  <br/> |
   

