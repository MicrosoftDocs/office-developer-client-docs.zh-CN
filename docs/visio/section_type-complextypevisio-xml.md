---
title: Section_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2f8e855f-064c-d286-560f-9f89e7fce7b7
ms.openlocfilehash: 35cd638d36f4ddd1d90e0c312e65626f7d8b0bff
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326094"
---
# <a name="sectiontype-complextype-visio-xml"></a><span data-ttu-id="121a4-102">Section_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="121a4-102">Section_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="121a4-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="121a4-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="121a4-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="121a4-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="121a4-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="121a4-105">**Schema file**</span></span> <br/> |<span data-ttu-id="121a4-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="121a4-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="121a4-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="121a4-107">**Extension base**</span></span> <br/> |<span data-ttu-id="121a4-108">无</span><span class="sxs-lookup"><span data-stu-id="121a4-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="121a4-109">定义</span><span class="sxs-lookup"><span data-stu-id="121a4-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="121a4-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="121a4-110">Elements and attributes</span></span>

<span data-ttu-id="121a4-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="121a4-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="121a4-112">子元素</span><span class="sxs-lookup"><span data-stu-id="121a4-112">Child elements</span></span>

|<span data-ttu-id="121a4-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="121a4-113">**Element**</span></span>|<span data-ttu-id="121a4-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="121a4-114">**Type**</span></span>|<span data-ttu-id="121a4-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="121a4-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="121a4-116">Cell</span><span class="sxs-lookup"><span data-stu-id="121a4-116">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="121a4-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="121a4-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="121a4-118">行</span><span class="sxs-lookup"><span data-stu-id="121a4-118">Row</span></span>](https://msdn.microsoft.com/library/c978e3eb-b895-8fb7-e2ba-88c50e57b3db%28Office.15%29.aspx) <br/> |[<span data-ttu-id="121a4-119">Row_Type</span><span class="sxs-lookup"><span data-stu-id="121a4-119">Row_Type</span></span>](row_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="121a4-120">Trigger</span><span class="sxs-lookup"><span data-stu-id="121a4-120">Trigger</span></span>](trigger-elementvisio-xml.md) <br/> |[<span data-ttu-id="121a4-121">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="121a4-121">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="121a4-122">属性</span><span class="sxs-lookup"><span data-stu-id="121a4-122">Attributes</span></span>

|<span data-ttu-id="121a4-123">**属性**</span><span class="sxs-lookup"><span data-stu-id="121a4-123">**Attribute**</span></span>|<span data-ttu-id="121a4-124">**类型**</span><span class="sxs-lookup"><span data-stu-id="121a4-124">**Type**</span></span>|<span data-ttu-id="121a4-125">**必需**</span><span class="sxs-lookup"><span data-stu-id="121a4-125">**Required**</span></span>|<span data-ttu-id="121a4-126">**描述**</span><span class="sxs-lookup"><span data-stu-id="121a4-126">**Description**</span></span>|<span data-ttu-id="121a4-127">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="121a4-127">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="121a4-128">键</span><span class="sxs-lookup"><span data-stu-id="121a4-128">Del</span></span>  <br/> |<span data-ttu-id="121a4-129">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="121a4-129">xsd:boolean</span></span>  <br/> |<span data-ttu-id="121a4-130">可选</span><span class="sxs-lookup"><span data-stu-id="121a4-130">optional</span></span>  <br/> ||<span data-ttu-id="121a4-131">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="121a4-131">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="121a4-132">IX</span><span class="sxs-lookup"><span data-stu-id="121a4-132">IX</span></span>  <br/> |<span data-ttu-id="121a4-133">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="121a4-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="121a4-134">可选</span><span class="sxs-lookup"><span data-stu-id="121a4-134">optional</span></span>  <br/> ||<span data-ttu-id="121a4-135">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="121a4-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="121a4-136">N</span><span class="sxs-lookup"><span data-stu-id="121a4-136">N</span></span>  <br/> |<span data-ttu-id="121a4-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="121a4-137">xsd:string</span></span>  <br/> |<span data-ttu-id="121a4-138">必需</span><span class="sxs-lookup"><span data-stu-id="121a4-138">required</span></span>  <br/> ||<span data-ttu-id="121a4-139">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="121a4-139">Values of the xsd:string type.</span></span>  <br/> |
   

