---
title: Section_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2f8e855f-064c-d286-560f-9f89e7fce7b7
ms.openlocfilehash: 48dd7a0ffc487b4a7a4200505f08d0aca42fd3c6
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542126"
---
# <a name="sectiontype-complextype-visio-xml"></a><span data-ttu-id="4b783-102">Section_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="4b783-102">Section_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="4b783-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="4b783-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4b783-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4b783-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="4b783-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4b783-105">**Schema file**</span></span> <br/> |<span data-ttu-id="4b783-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="4b783-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="4b783-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="4b783-107">**Extension base**</span></span> <br/> |<span data-ttu-id="4b783-108">无</span><span class="sxs-lookup"><span data-stu-id="4b783-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4b783-109">定义</span><span class="sxs-lookup"><span data-stu-id="4b783-109">Definition</span></span>

```XML
          <xs:complexType name="Section_Type">
          
          <xs:sequence>
    <xs:element name="Cell"  type="Cell_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="Trigger"  type="Trigger_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="Row"  type="Row_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="N"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="Del"
  type="xsd:boolean"
    />
    <xs:attribute name="IX"
  type="xsd:unsignedInt"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4b783-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4b783-110">Elements and attributes</span></span>

<span data-ttu-id="4b783-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="4b783-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="4b783-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4b783-112">Child elements</span></span>

|<span data-ttu-id="4b783-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="4b783-113">**Element**</span></span>|<span data-ttu-id="4b783-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="4b783-114">**Type**</span></span>|<span data-ttu-id="4b783-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="4b783-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4b783-116">Cell</span><span class="sxs-lookup"><span data-stu-id="4b783-116">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="4b783-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="4b783-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="4b783-118">行</span><span class="sxs-lookup"><span data-stu-id="4b783-118">Row</span></span>](https://msdn.microsoft.com/library/c978e3eb-b895-8fb7-e2ba-88c50e57b3db%28Office.15%29.aspx) <br/> |[<span data-ttu-id="4b783-119">Row_Type</span><span class="sxs-lookup"><span data-stu-id="4b783-119">Row_Type</span></span>](row_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="4b783-120">Trigger</span><span class="sxs-lookup"><span data-stu-id="4b783-120">Trigger</span></span>](trigger-elementvisio-xml.md) <br/> |[<span data-ttu-id="4b783-121">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="4b783-121">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="4b783-122">属性</span><span class="sxs-lookup"><span data-stu-id="4b783-122">Attributes</span></span>

|<span data-ttu-id="4b783-123">**属性**</span><span class="sxs-lookup"><span data-stu-id="4b783-123">**Attribute**</span></span>|<span data-ttu-id="4b783-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="4b783-124">**Type**</span></span>|<span data-ttu-id="4b783-125">**必需**</span><span class="sxs-lookup"><span data-stu-id="4b783-125">**Required**</span></span>|<span data-ttu-id="4b783-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="4b783-126">**Description**</span></span>|<span data-ttu-id="4b783-127">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="4b783-127">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4b783-128">键</span><span class="sxs-lookup"><span data-stu-id="4b783-128">Del</span></span>  <br/> |<span data-ttu-id="4b783-129">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="4b783-129">xsd:boolean</span></span>  <br/> |<span data-ttu-id="4b783-130">可选</span><span class="sxs-lookup"><span data-stu-id="4b783-130">optional</span></span>  <br/> ||<span data-ttu-id="4b783-131">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4b783-131">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="4b783-132">IX</span><span class="sxs-lookup"><span data-stu-id="4b783-132">IX</span></span>  <br/> |<span data-ttu-id="4b783-133">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="4b783-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="4b783-134">可选</span><span class="sxs-lookup"><span data-stu-id="4b783-134">optional</span></span>  <br/> ||<span data-ttu-id="4b783-135">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4b783-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="4b783-136">N</span><span class="sxs-lookup"><span data-stu-id="4b783-136">N</span></span>  <br/> |<span data-ttu-id="4b783-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="4b783-137">xsd:string</span></span>  <br/> |<span data-ttu-id="4b783-138">必需</span><span class="sxs-lookup"><span data-stu-id="4b783-138">required</span></span>  <br/> ||<span data-ttu-id="4b783-139">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="4b783-139">Values of the xsd:string type.</span></span>  <br/> |
   

