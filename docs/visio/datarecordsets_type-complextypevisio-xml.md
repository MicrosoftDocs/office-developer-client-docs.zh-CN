---
title: DataRecordSets_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 04448cfa-7eb4-62ca-97d2-409b59a8db90
ms.openlocfilehash: b646e7a0d4e1f49aa71b162aecdd901813b01f49
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780045"
---
# <a name="datarecordsetstype-complextype-visio-xml"></a><span data-ttu-id="11abd-102">DataRecordSets_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="11abd-102">DataRecordSets_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="11abd-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="11abd-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="11abd-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="11abd-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="11abd-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="11abd-105">**Schema file**</span></span> <br/> |<span data-ttu-id="11abd-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="11abd-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="11abd-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="11abd-107">**Extension base**</span></span> <br/> |<span data-ttu-id="11abd-108">无</span><span class="sxs-lookup"><span data-stu-id="11abd-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="11abd-109">定义</span><span class="sxs-lookup"><span data-stu-id="11abd-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="11abd-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="11abd-110">Elements and attributes</span></span>

<span data-ttu-id="11abd-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="11abd-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="11abd-112">子元素</span><span class="sxs-lookup"><span data-stu-id="11abd-112">Child elements</span></span>

|<span data-ttu-id="11abd-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="11abd-113">**Element**</span></span>|<span data-ttu-id="11abd-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="11abd-114">**Type**</span></span>|<span data-ttu-id="11abd-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="11abd-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="11abd-116">数据记录集</span><span class="sxs-lookup"><span data-stu-id="11abd-116">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="11abd-117">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="11abd-117">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="11abd-118">属性</span><span class="sxs-lookup"><span data-stu-id="11abd-118">Attributes</span></span>

|<span data-ttu-id="11abd-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="11abd-119">**Attribute**</span></span>|<span data-ttu-id="11abd-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="11abd-120">**Type**</span></span>|<span data-ttu-id="11abd-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="11abd-121">**Required**</span></span>|<span data-ttu-id="11abd-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="11abd-122">**Description**</span></span>|<span data-ttu-id="11abd-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="11abd-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="11abd-124">ActiveRecordsetID</span><span class="sxs-lookup"><span data-stu-id="11abd-124">ActiveRecordsetID</span></span>  <br/> |<span data-ttu-id="11abd-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="11abd-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="11abd-126">可选</span><span class="sxs-lookup"><span data-stu-id="11abd-126">optional</span></span>  <br/> ||<span data-ttu-id="11abd-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="11abd-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="11abd-128">DataWindowOrder</span><span class="sxs-lookup"><span data-stu-id="11abd-128">DataWindowOrder</span></span>  <br/> |<span data-ttu-id="11abd-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="11abd-129">xsd:string</span></span>  <br/> |<span data-ttu-id="11abd-130">可选</span><span class="sxs-lookup"><span data-stu-id="11abd-130">optional</span></span>  <br/> ||<span data-ttu-id="11abd-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="11abd-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="11abd-132">NextID</span><span class="sxs-lookup"><span data-stu-id="11abd-132">NextID</span></span>  <br/> |<span data-ttu-id="11abd-133">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="11abd-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="11abd-134">必需</span><span class="sxs-lookup"><span data-stu-id="11abd-134">required</span></span>  <br/> ||<span data-ttu-id="11abd-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="11abd-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

