---
title: DataRecordSets_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 04448cfa-7eb4-62ca-97d2-409b59a8db90
ms.openlocfilehash: 1705d0ea92e278008c33321f135409373b7317fd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360345"
---
# <a name="datarecordsetstype-complextype-visio-xml"></a><span data-ttu-id="2e665-102">DataRecordSets_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="2e665-102">DataRecordSets_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="2e665-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="2e665-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2e665-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2e665-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="2e665-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2e665-105">**Schema file**</span></span> <br/> |<span data-ttu-id="2e665-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="2e665-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="2e665-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="2e665-107">**Extension base**</span></span> <br/> |<span data-ttu-id="2e665-108">无</span><span class="sxs-lookup"><span data-stu-id="2e665-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2e665-109">定义</span><span class="sxs-lookup"><span data-stu-id="2e665-109">Definition</span></span>

```XML
          <xs:complexType name="DataRecordSets_Type">
          
          <xs:sequence>
    <xs:element name="DataRecordSet"  type="DataRecordSet_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="NextID"
  type="xsd:unsignedInt"
     use="required"
    />
    <xs:attribute name="ActiveRecordsetID"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="DataWindowOrder"
  type="xsd:string"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="2e665-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2e665-110">Elements and attributes</span></span>

<span data-ttu-id="2e665-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="2e665-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="2e665-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2e665-112">Child elements</span></span>

|<span data-ttu-id="2e665-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="2e665-113">**Element**</span></span>|<span data-ttu-id="2e665-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="2e665-114">**Type**</span></span>|<span data-ttu-id="2e665-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="2e665-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2e665-116">DataRecordSet</span><span class="sxs-lookup"><span data-stu-id="2e665-116">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2e665-117">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="2e665-117">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="2e665-118">属性</span><span class="sxs-lookup"><span data-stu-id="2e665-118">Attributes</span></span>

|<span data-ttu-id="2e665-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="2e665-119">**Attribute**</span></span>|<span data-ttu-id="2e665-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="2e665-120">**Type**</span></span>|<span data-ttu-id="2e665-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="2e665-121">**Required**</span></span>|<span data-ttu-id="2e665-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="2e665-122">**Description**</span></span>|<span data-ttu-id="2e665-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="2e665-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2e665-124">ActiveRecordsetID</span><span class="sxs-lookup"><span data-stu-id="2e665-124">ActiveRecordsetID</span></span>  <br/> |<span data-ttu-id="2e665-125">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="2e665-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="2e665-126">可选</span><span class="sxs-lookup"><span data-stu-id="2e665-126">optional</span></span>  <br/> ||<span data-ttu-id="2e665-127">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2e665-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="2e665-128">DataWindowOrder</span><span class="sxs-lookup"><span data-stu-id="2e665-128">DataWindowOrder</span></span>  <br/> |<span data-ttu-id="2e665-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2e665-129">xsd:string</span></span>  <br/> |<span data-ttu-id="2e665-130">可选</span><span class="sxs-lookup"><span data-stu-id="2e665-130">optional</span></span>  <br/> ||<span data-ttu-id="2e665-131">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2e665-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="2e665-132">NextID</span><span class="sxs-lookup"><span data-stu-id="2e665-132">NextID</span></span>  <br/> |<span data-ttu-id="2e665-133">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="2e665-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="2e665-134">必需</span><span class="sxs-lookup"><span data-stu-id="2e665-134">required</span></span>  <br/> ||<span data-ttu-id="2e665-135">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2e665-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

