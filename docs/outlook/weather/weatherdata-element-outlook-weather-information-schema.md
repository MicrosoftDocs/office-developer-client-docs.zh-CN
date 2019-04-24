---
title: weatherdata 元素 (Outlook 天气信息架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 84b16927-964e-24be-feaa-e0c11cf062f3
description: 定义气象元素。
ms.openlocfilehash: 2273f7ce6c6a04464ea3da430661c3d6f410cc9f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355074"
---
# <a name="weatherdata-element-outlook-weather-information-schema"></a><span data-ttu-id="589cb-103">weatherdata 元素 (Outlook 天气信息架构)</span><span class="sxs-lookup"><span data-stu-id="589cb-103">weatherdata element (Outlook Weather Information Schema)</span></span>

<span data-ttu-id="589cb-104">定义气象元素。</span><span class="sxs-lookup"><span data-stu-id="589cb-104">Defines the weather element.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="589cb-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="589cb-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="589cb-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="589cb-106">**Element type**</span></span> <br/> ||
|<span data-ttu-id="589cb-107">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="589cb-107">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|<span data-ttu-id="589cb-108">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="589cb-108">**Schema file**</span></span> <br/> |<span data-ttu-id="589cb-109">getweatherinfo</span><span class="sxs-lookup"><span data-stu-id="589cb-109">getweatherinfo.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="589cb-110">定义</span><span class="sxs-lookup"><span data-stu-id="589cb-110">Definition</span></span>

```XML
    <xs:element name="weatherdata"
    >
          <xs:complexType>
          <xs:sequence>
    <xs:element name="weather"
     type="weatherType">
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
    </xs:element>
    
```

## <a name="elements-and-attributes"></a><span data-ttu-id="589cb-111">元素和属性</span><span class="sxs-lookup"><span data-stu-id="589cb-111">Elements and attributes</span></span>

<span data-ttu-id="589cb-112">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="589cb-112">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="589cb-113">父元素</span><span class="sxs-lookup"><span data-stu-id="589cb-113">Parent elements</span></span>

<span data-ttu-id="589cb-114">无。</span><span class="sxs-lookup"><span data-stu-id="589cb-114">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="589cb-115">子元素</span><span class="sxs-lookup"><span data-stu-id="589cb-115">Child elements</span></span>

|<span data-ttu-id="589cb-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="589cb-116">**Element**</span></span>|<span data-ttu-id="589cb-117">**类型**</span><span class="sxs-lookup"><span data-stu-id="589cb-117">**Type**</span></span>|<span data-ttu-id="589cb-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="589cb-118">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="589cb-119">气候</span><span class="sxs-lookup"><span data-stu-id="589cb-119">weather</span></span>](weather-element-weatherdata-elementoutlook-weather-information-schema.md) <br/> |[<span data-ttu-id="589cb-120">weatherType</span><span class="sxs-lookup"><span data-stu-id="589cb-120">weatherType</span></span>](weathertype-complextype-outlook-weather-information-schema.md) <br/> |<span data-ttu-id="589cb-121">指定位置的天气情况。</span><span class="sxs-lookup"><span data-stu-id="589cb-121">Specifies the weather conditions of a location.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="589cb-122">Attributes</span><span class="sxs-lookup"><span data-stu-id="589cb-122">Attributes</span></span>

<span data-ttu-id="589cb-123">无。</span><span class="sxs-lookup"><span data-stu-id="589cb-123">None.</span></span>
  

