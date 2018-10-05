---
title: DataRecordSets_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 04448cfa-7eb4-62ca-97d2-409b59a8db90
ms.openlocfilehash: 1705d0ea92e278008c33321f135409373b7317fd
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388558"
---
# <a name="datarecordsetstype-complextype-visio-xml"></a><span data-ttu-id="3699c-102">DataRecordSets_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="3699c-102">DataRecordSets_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="3699c-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="3699c-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3699c-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="3699c-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="3699c-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="3699c-105">**Schema file**</span></span> <br/> |<span data-ttu-id="3699c-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="3699c-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="3699c-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="3699c-107">**Extension base**</span></span> <br/> |<span data-ttu-id="3699c-108">无</span><span class="sxs-lookup"><span data-stu-id="3699c-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="3699c-109">定义</span><span class="sxs-lookup"><span data-stu-id="3699c-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="3699c-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="3699c-110">Elements and attributes</span></span>

<span data-ttu-id="3699c-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="3699c-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="3699c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="3699c-112">Child elements</span></span>

|<span data-ttu-id="3699c-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="3699c-113">**Element**</span></span>|<span data-ttu-id="3699c-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="3699c-114">**Type**</span></span>|<span data-ttu-id="3699c-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="3699c-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="3699c-116">数据记录集</span><span class="sxs-lookup"><span data-stu-id="3699c-116">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="3699c-117">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="3699c-117">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="3699c-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="3699c-118">Attributes</span></span>

|<span data-ttu-id="3699c-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="3699c-119">**Attribute**</span></span>|<span data-ttu-id="3699c-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="3699c-120">**Type**</span></span>|<span data-ttu-id="3699c-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="3699c-121">**Required**</span></span>|<span data-ttu-id="3699c-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="3699c-122">**Description**</span></span>|<span data-ttu-id="3699c-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="3699c-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3699c-124">ActiveRecordsetID</span><span class="sxs-lookup"><span data-stu-id="3699c-124">ActiveRecordsetID</span></span>  <br/> |<span data-ttu-id="3699c-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="3699c-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="3699c-126">可选</span><span class="sxs-lookup"><span data-stu-id="3699c-126">optional</span></span>  <br/> ||<span data-ttu-id="3699c-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3699c-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="3699c-128">DataWindowOrder</span><span class="sxs-lookup"><span data-stu-id="3699c-128">DataWindowOrder</span></span>  <br/> |<span data-ttu-id="3699c-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="3699c-129">xsd:string</span></span>  <br/> |<span data-ttu-id="3699c-130">可选</span><span class="sxs-lookup"><span data-stu-id="3699c-130">optional</span></span>  <br/> ||<span data-ttu-id="3699c-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3699c-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="3699c-132">NextID</span><span class="sxs-lookup"><span data-stu-id="3699c-132">NextID</span></span>  <br/> |<span data-ttu-id="3699c-133">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="3699c-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="3699c-134">必需</span><span class="sxs-lookup"><span data-stu-id="3699c-134">required</span></span>  <br/> ||<span data-ttu-id="3699c-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3699c-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

