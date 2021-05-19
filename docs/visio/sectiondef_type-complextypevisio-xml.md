---
title: 'SectionDef_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ab57bf2-0d9f-4a3a-4882-c77d7c781cbd
ms.openlocfilehash: 96812d1911d249ebce02aeab20b0a77ef518fbff
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542077"
---
# <a name="sectiondef_type-complextype-visio-xml"></a><span data-ttu-id="a9bdb-102">SectionDef_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="a9bdb-102">SectionDef_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="a9bdb-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="a9bdb-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a9bdb-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="a9bdb-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="a9bdb-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="a9bdb-105">**Schema file**</span></span> <br/> |<span data-ttu-id="a9bdb-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="a9bdb-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="a9bdb-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="a9bdb-107">**Extension base**</span></span> <br/> |<span data-ttu-id="a9bdb-108">无</span><span class="sxs-lookup"><span data-stu-id="a9bdb-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="a9bdb-109">定义</span><span class="sxs-lookup"><span data-stu-id="a9bdb-109">Definition</span></span>

```XML
          <xs:complexType name="SectionDef_Type">
          
          <xs:sequence>
    <xs:element name="CellDef"  type="CellDef_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="RowDef"  type="RowDef_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="N"
  type="xsd:string"
     use="required"
    />
    <xs:attribute name="T"
  type="xsd:string"
    />
    <xs:attribute name="S"
  type="xsd:unsignedByte"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="a9bdb-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="a9bdb-110">Elements and attributes</span></span>

<span data-ttu-id="a9bdb-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="a9bdb-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="a9bdb-112">子元素</span><span class="sxs-lookup"><span data-stu-id="a9bdb-112">Child elements</span></span>

|<span data-ttu-id="a9bdb-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="a9bdb-113">**Element**</span></span>|<span data-ttu-id="a9bdb-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="a9bdb-114">**Type**</span></span>|<span data-ttu-id="a9bdb-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="a9bdb-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a9bdb-116">CellDef</span><span class="sxs-lookup"><span data-stu-id="a9bdb-116">CellDef</span></span> <br/> |[<span data-ttu-id="a9bdb-117">CellDef_Type</span><span class="sxs-lookup"><span data-stu-id="a9bdb-117">CellDef_Type</span></span>](celldef_type-complextypevisio-xml.md) <br/> ||
|<span data-ttu-id="a9bdb-118">RowDef</span><span class="sxs-lookup"><span data-stu-id="a9bdb-118">RowDef</span></span> <br/> |[<span data-ttu-id="a9bdb-119">RowDef_Type</span><span class="sxs-lookup"><span data-stu-id="a9bdb-119">RowDef_Type</span></span>](rowdef_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="a9bdb-120">属性</span><span class="sxs-lookup"><span data-stu-id="a9bdb-120">Attributes</span></span>

|<span data-ttu-id="a9bdb-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="a9bdb-121">**Attribute**</span></span>|<span data-ttu-id="a9bdb-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="a9bdb-122">**Type**</span></span>|<span data-ttu-id="a9bdb-123">**必需**</span><span class="sxs-lookup"><span data-stu-id="a9bdb-123">**Required**</span></span>|<span data-ttu-id="a9bdb-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="a9bdb-124">**Description**</span></span>|<span data-ttu-id="a9bdb-125">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a9bdb-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a9bdb-126">N</span><span class="sxs-lookup"><span data-stu-id="a9bdb-126">N</span></span>  <br/> |<span data-ttu-id="a9bdb-127">xsd：string</span><span class="sxs-lookup"><span data-stu-id="a9bdb-127">xsd:string</span></span>  <br/> |<span data-ttu-id="a9bdb-128">必需</span><span class="sxs-lookup"><span data-stu-id="a9bdb-128">required</span></span>  <br/> ||<span data-ttu-id="a9bdb-129">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a9bdb-129">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="a9bdb-130">S</span><span class="sxs-lookup"><span data-stu-id="a9bdb-130">S</span></span>  <br/> |<span data-ttu-id="a9bdb-131">xsd：unsignedByte</span><span class="sxs-lookup"><span data-stu-id="a9bdb-131">xsd:unsignedByte</span></span>  <br/> |<span data-ttu-id="a9bdb-132">可选</span><span class="sxs-lookup"><span data-stu-id="a9bdb-132">optional</span></span>  <br/> ||<span data-ttu-id="a9bdb-133">xsd：unsignedByte 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a9bdb-133">Values of the xsd:unsignedByte type.</span></span>  <br/> |
|<span data-ttu-id="a9bdb-134">T</span><span class="sxs-lookup"><span data-stu-id="a9bdb-134">T</span></span>  <br/> |<span data-ttu-id="a9bdb-135">xsd：string</span><span class="sxs-lookup"><span data-stu-id="a9bdb-135">xsd:string</span></span>  <br/> |<span data-ttu-id="a9bdb-136">可选</span><span class="sxs-lookup"><span data-stu-id="a9bdb-136">optional</span></span>  <br/> ||<span data-ttu-id="a9bdb-137">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a9bdb-137">Values of the xsd:string type.</span></span>  <br/> |
   

