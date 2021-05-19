---
title: 'DataRecordSets_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 04448cfa-7eb4-62ca-97d2-409b59a8db90
ms.openlocfilehash: 77a6588a1b5fba05d14e91a39ba570d21142f953
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539156"
---
# <a name="datarecordsets_type-complextype-visio-xml"></a><span data-ttu-id="05397-102">DataRecordSets_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="05397-102">DataRecordSets_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="05397-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="05397-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="05397-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="05397-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="05397-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="05397-105">**Schema file**</span></span> <br/> |<span data-ttu-id="05397-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="05397-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="05397-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="05397-107">**Extension base**</span></span> <br/> |<span data-ttu-id="05397-108">无</span><span class="sxs-lookup"><span data-stu-id="05397-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="05397-109">定义</span><span class="sxs-lookup"><span data-stu-id="05397-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="05397-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="05397-110">Elements and attributes</span></span>

<span data-ttu-id="05397-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="05397-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="05397-112">子元素</span><span class="sxs-lookup"><span data-stu-id="05397-112">Child elements</span></span>

|<span data-ttu-id="05397-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="05397-113">**Element**</span></span>|<span data-ttu-id="05397-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="05397-114">**Type**</span></span>|<span data-ttu-id="05397-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="05397-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="05397-116">DataRecordSet</span><span class="sxs-lookup"><span data-stu-id="05397-116">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="05397-117">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="05397-117">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="05397-118">属性</span><span class="sxs-lookup"><span data-stu-id="05397-118">Attributes</span></span>

|<span data-ttu-id="05397-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="05397-119">**Attribute**</span></span>|<span data-ttu-id="05397-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="05397-120">**Type**</span></span>|<span data-ttu-id="05397-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="05397-121">**Required**</span></span>|<span data-ttu-id="05397-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="05397-122">**Description**</span></span>|<span data-ttu-id="05397-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="05397-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="05397-124">ActiveRecordsetID</span><span class="sxs-lookup"><span data-stu-id="05397-124">ActiveRecordsetID</span></span>  <br/> |<span data-ttu-id="05397-125">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="05397-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="05397-126">可选</span><span class="sxs-lookup"><span data-stu-id="05397-126">optional</span></span>  <br/> ||<span data-ttu-id="05397-127">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="05397-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="05397-128">DataWindowOrder</span><span class="sxs-lookup"><span data-stu-id="05397-128">DataWindowOrder</span></span>  <br/> |<span data-ttu-id="05397-129">xsd：string</span><span class="sxs-lookup"><span data-stu-id="05397-129">xsd:string</span></span>  <br/> |<span data-ttu-id="05397-130">可选</span><span class="sxs-lookup"><span data-stu-id="05397-130">optional</span></span>  <br/> ||<span data-ttu-id="05397-131">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="05397-131">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="05397-132">NextID</span><span class="sxs-lookup"><span data-stu-id="05397-132">NextID</span></span>  <br/> |<span data-ttu-id="05397-133">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="05397-133">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="05397-134">必需</span><span class="sxs-lookup"><span data-stu-id="05397-134">required</span></span>  <br/> ||<span data-ttu-id="05397-135">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="05397-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

