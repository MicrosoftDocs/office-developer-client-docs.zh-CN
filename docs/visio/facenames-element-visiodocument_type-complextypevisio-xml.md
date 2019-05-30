---
title: FaceNames 元素 (VisioDocument_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 61e30f57-abd6-9378-45ed-51236ab3d3ee
description: 包含 FaceName 元素的集合。
ms.openlocfilehash: ce18847fdd46a0c703a0df5e8d8c7a877f864d35
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539711"
---
# <a name="facenames-element-visiodocumenttype-complextype-visio-xml"></a><span data-ttu-id="497b8-103">FaceNames 元素 (VisioDocument_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="497b8-103">FaceNames element (VisioDocument_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="497b8-104">包含**FaceName**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="497b8-104">Contains a collection of **FaceName** elements.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="497b8-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="497b8-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="497b8-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="497b8-106">**Element type**</span></span> <br/> |[<span data-ttu-id="497b8-107">FaceNames_Type</span><span class="sxs-lookup"><span data-stu-id="497b8-107">FaceNames_Type</span></span>](facenames_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="497b8-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="497b8-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="497b8-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="497b8-109">**Schema file**</span></span> <br/> |<span data-ttu-id="497b8-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="497b8-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="497b8-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="497b8-111">**Document parts**</span></span> <br/> |<span data-ttu-id="497b8-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="497b8-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="497b8-113">定义</span><span class="sxs-lookup"><span data-stu-id="497b8-113">Definition</span></span>

```XML
< xs:element name="FaceNames" type="FaceNames_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="497b8-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="497b8-114">Elements and attributes</span></span>

<span data-ttu-id="497b8-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="497b8-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="497b8-116">父元素</span><span class="sxs-lookup"><span data-stu-id="497b8-116">Parent elements</span></span>

|<span data-ttu-id="497b8-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="497b8-117">**Element**</span></span>|<span data-ttu-id="497b8-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="497b8-118">**Type**</span></span>|<span data-ttu-id="497b8-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="497b8-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="497b8-120">VisioDocument</span><span class="sxs-lookup"><span data-stu-id="497b8-120">VisioDocument</span></span>](visiodocument-elementvisio-xml.md) <br/> |[<span data-ttu-id="497b8-121">VisioDocument_Type</span><span class="sxs-lookup"><span data-stu-id="497b8-121">VisioDocument_Type</span></span>](visiodocument_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="497b8-122">Microsoft Visio 文档的根元素。</span><span class="sxs-lookup"><span data-stu-id="497b8-122">The root element of a Microsoft Visio document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="497b8-123">子元素</span><span class="sxs-lookup"><span data-stu-id="497b8-123">Child elements</span></span>

|<span data-ttu-id="497b8-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="497b8-124">**Element**</span></span>|<span data-ttu-id="497b8-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="497b8-125">**Type**</span></span>|<span data-ttu-id="497b8-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="497b8-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="497b8-127">FaceName</span><span class="sxs-lookup"><span data-stu-id="497b8-127">FaceName</span></span>](facename-element-facenames_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="497b8-128">FaceName_Type</span><span class="sxs-lookup"><span data-stu-id="497b8-128">FaceName_Type</span></span>](facename_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="497b8-129">包含有关字体的信息。</span><span class="sxs-lookup"><span data-stu-id="497b8-129">Contains information about a font.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="497b8-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="497b8-130">Attributes</span></span>

<span data-ttu-id="497b8-131">无。</span><span class="sxs-lookup"><span data-stu-id="497b8-131">None.</span></span>
  

