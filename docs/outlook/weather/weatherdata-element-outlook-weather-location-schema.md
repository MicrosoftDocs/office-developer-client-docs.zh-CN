---
title: weatherdata 元素 (Outlook 天气位置架构)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 14e0c469-31dc-fbe2-0d45-da602df04f13
description: 定义气象元素。
ms.openlocfilehash: 65dd0ee5686fb773479c8b63a43f51bff67fd2f7
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540929"
---
# <a name="weatherdata-element-outlook-weather-location-schema"></a><span data-ttu-id="2b361-103">weatherdata 元素 (Outlook 天气位置架构)</span><span class="sxs-lookup"><span data-stu-id="2b361-103">weatherdata element (Outlook Weather Location Schema)</span></span>

<span data-ttu-id="2b361-104">定义气象元素。</span><span class="sxs-lookup"><span data-stu-id="2b361-104">Defines the weather element.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="2b361-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="2b361-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2b361-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="2b361-106">**Element type**</span></span> <br/> ||
|<span data-ttu-id="2b361-107">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2b361-107">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherlocation.xsd  <br/> |
|<span data-ttu-id="2b361-108">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2b361-108">**Schema file**</span></span> <br/> |<span data-ttu-id="2b361-109">getweatherlocation</span><span class="sxs-lookup"><span data-stu-id="2b361-109">getweatherlocation.xsd</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2b361-110">定义</span><span class="sxs-lookup"><span data-stu-id="2b361-110">Definition</span></span>

```XML
    <xs:element name="weatherdata"
    >
          <xs:complexType>
          <xs:sequence>
    <xs:element name="weather"
     type="weatherType" maxOccurs="unbounded"
      >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
    </xs:element>
    
```

## <a name="elements-and-attributes"></a><span data-ttu-id="2b361-111">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2b361-111">Elements and attributes</span></span>

<span data-ttu-id="2b361-112">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="2b361-112">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="2b361-113">父元素</span><span class="sxs-lookup"><span data-stu-id="2b361-113">Parent elements</span></span>

<span data-ttu-id="2b361-114">无。</span><span class="sxs-lookup"><span data-stu-id="2b361-114">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="2b361-115">子元素</span><span class="sxs-lookup"><span data-stu-id="2b361-115">Child elements</span></span>

|<span data-ttu-id="2b361-116">**元素**</span><span class="sxs-lookup"><span data-stu-id="2b361-116">**Element**</span></span>|<span data-ttu-id="2b361-117">**类型**</span><span class="sxs-lookup"><span data-stu-id="2b361-117">**Type**</span></span>|<span data-ttu-id="2b361-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="2b361-118">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2b361-119">气候</span><span class="sxs-lookup"><span data-stu-id="2b361-119">weather</span></span>](weather-element-weatherdata-elementoutlook-weather-location-schema.md) <br/> |[<span data-ttu-id="2b361-120">weatherType</span><span class="sxs-lookup"><span data-stu-id="2b361-120">weatherType</span></span>](weathertype-complextype-outlook-weather-location-schema.md) <br/> |<span data-ttu-id="2b361-121">指定要在其上报告天气的位置。</span><span class="sxs-lookup"><span data-stu-id="2b361-121">Specifies the location to report weather on.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="2b361-122">Attributes</span><span class="sxs-lookup"><span data-stu-id="2b361-122">Attributes</span></span>

<span data-ttu-id="2b361-123">无。</span><span class="sxs-lookup"><span data-stu-id="2b361-123">None.</span></span>
  

