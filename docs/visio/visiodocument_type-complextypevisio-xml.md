---
title: 'VisioDocument_Type XML (Visio complexType) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5003f98e-4fed-73f8-be55-5b068d9cbffe
ms.openlocfilehash: 8c0a5976139aee2f3aee41b3709ce5fd1ac5c00d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538471"
---
# <a name="visiodocument_type-complextype-visio-xml"></a><span data-ttu-id="1ab9a-102">VisioDocument_Type XML (Visio complexType) </span><span class="sxs-lookup"><span data-stu-id="1ab9a-102">VisioDocument_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="1ab9a-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="1ab9a-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1ab9a-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1ab9a-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="1ab9a-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1ab9a-105">**Schema file**</span></span> <br/> |<span data-ttu-id="1ab9a-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="1ab9a-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="1ab9a-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="1ab9a-107">**Extension base**</span></span> <br/> |<span data-ttu-id="1ab9a-108">无</span><span class="sxs-lookup"><span data-stu-id="1ab9a-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1ab9a-109">定义</span><span class="sxs-lookup"><span data-stu-id="1ab9a-109">Definition</span></span>

```XML
          <xs:complexType name="VisioDocument_Type">
          
          <xs:sequence>
    <xs:element name="DocumentSettings"  type="DocumentSettings_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="Colors"  type="Colors_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="FaceNames"  type="FaceNames_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="StyleSheets"  type="StyleSheets_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="DocumentSheet"  type="DocumentSheet_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="EventList"  type="EventList_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="HeaderFooter"  type="HeaderFooter_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="PublishSettings"  type="PublishSettings_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs: name="" >
    </xs:>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="1ab9a-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1ab9a-110">Elements and attributes</span></span>

<span data-ttu-id="1ab9a-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="1ab9a-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="1ab9a-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1ab9a-112">Child elements</span></span>

|<span data-ttu-id="1ab9a-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="1ab9a-113">**Element**</span></span>|<span data-ttu-id="1ab9a-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="1ab9a-114">**Type**</span></span>|<span data-ttu-id="1ab9a-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="1ab9a-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="1ab9a-116">Colors</span><span class="sxs-lookup"><span data-stu-id="1ab9a-116">Colors</span></span>](colors-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1ab9a-117">Colors_Type</span><span class="sxs-lookup"><span data-stu-id="1ab9a-117">Colors_Type</span></span>](colors_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="1ab9a-118">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="1ab9a-118">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1ab9a-119">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="1ab9a-119">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="1ab9a-120">DocumentSheet</span><span class="sxs-lookup"><span data-stu-id="1ab9a-120">DocumentSheet</span></span>](documentsheet-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1ab9a-121">DocumentSheet_Type</span><span class="sxs-lookup"><span data-stu-id="1ab9a-121">DocumentSheet_Type</span></span>](documentsheet_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="1ab9a-122">EventList</span><span class="sxs-lookup"><span data-stu-id="1ab9a-122">EventList</span></span>](eventlist-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1ab9a-123">EventList_Type</span><span class="sxs-lookup"><span data-stu-id="1ab9a-123">EventList_Type</span></span>](eventlist_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="1ab9a-124">FaceNames</span><span class="sxs-lookup"><span data-stu-id="1ab9a-124">FaceNames</span></span>](facenames-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1ab9a-125">FaceNames_Type</span><span class="sxs-lookup"><span data-stu-id="1ab9a-125">FaceNames_Type</span></span>](facenames_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="1ab9a-126">HeaderFooter</span><span class="sxs-lookup"><span data-stu-id="1ab9a-126">HeaderFooter</span></span>](headerfooter-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1ab9a-127">HeaderFooter_Type</span><span class="sxs-lookup"><span data-stu-id="1ab9a-127">HeaderFooter_Type</span></span>](headerfooter_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="1ab9a-128">PublishSettings</span><span class="sxs-lookup"><span data-stu-id="1ab9a-128">PublishSettings</span></span>](publishsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1ab9a-129">PublishSettings_Type</span><span class="sxs-lookup"><span data-stu-id="1ab9a-129">PublishSettings_Type</span></span>](publishsettings_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="1ab9a-130">StyleSheets</span><span class="sxs-lookup"><span data-stu-id="1ab9a-130">StyleSheets</span></span>](stylesheets-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1ab9a-131">StyleSheets_Type</span><span class="sxs-lookup"><span data-stu-id="1ab9a-131">StyleSheets_Type</span></span>](stylesheets_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="1ab9a-132">Attributes</span><span class="sxs-lookup"><span data-stu-id="1ab9a-132">Attributes</span></span>

<span data-ttu-id="1ab9a-133">无。</span><span class="sxs-lookup"><span data-stu-id="1ab9a-133">None.</span></span>
  

