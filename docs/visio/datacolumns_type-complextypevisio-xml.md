---
title: 'DataColumns_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ad003c9e-5e72-2df0-f9c5-dea20a220ab5
ms.openlocfilehash: ffe0fbfeaf0b0b67386a6cadd1beb78058819d39
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541146"
---
# <a name="datacolumns_type-complextype-visio-xml"></a><span data-ttu-id="a83cd-102">DataColumns_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="a83cd-102">DataColumns_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="a83cd-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="a83cd-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a83cd-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="a83cd-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="a83cd-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="a83cd-105">**Schema file**</span></span> <br/> |<span data-ttu-id="a83cd-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="a83cd-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="a83cd-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="a83cd-107">**Extension base**</span></span> <br/> |<span data-ttu-id="a83cd-108">无</span><span class="sxs-lookup"><span data-stu-id="a83cd-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="a83cd-109">定义</span><span class="sxs-lookup"><span data-stu-id="a83cd-109">Definition</span></span>

```XML
          <xs:complexType name="DataColumns_Type">
          
          <xs:sequence>
    <xs:element name="DataColumn"  type="DataColumn_Type"
     minOccurs="1"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="SortColumn"
  type="xsd:string"
    />
    <xs:attribute name="SortAsc"
  type="xsd:boolean"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="a83cd-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="a83cd-110">Elements and attributes</span></span>

<span data-ttu-id="a83cd-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="a83cd-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="a83cd-112">子元素</span><span class="sxs-lookup"><span data-stu-id="a83cd-112">Child elements</span></span>

|<span data-ttu-id="a83cd-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="a83cd-113">**Element**</span></span>|<span data-ttu-id="a83cd-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="a83cd-114">**Type**</span></span>|<span data-ttu-id="a83cd-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="a83cd-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="a83cd-116">DataColumn</span><span class="sxs-lookup"><span data-stu-id="a83cd-116">DataColumn</span></span>](datacolumn-element-datacolumns_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="a83cd-117">DataColumn_Type</span><span class="sxs-lookup"><span data-stu-id="a83cd-117">DataColumn_Type</span></span>](datacolumn_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="a83cd-118">属性</span><span class="sxs-lookup"><span data-stu-id="a83cd-118">Attributes</span></span>

|<span data-ttu-id="a83cd-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="a83cd-119">**Attribute**</span></span>|<span data-ttu-id="a83cd-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="a83cd-120">**Type**</span></span>|<span data-ttu-id="a83cd-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="a83cd-121">**Required**</span></span>|<span data-ttu-id="a83cd-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="a83cd-122">**Description**</span></span>|<span data-ttu-id="a83cd-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="a83cd-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a83cd-124">SortAsc</span><span class="sxs-lookup"><span data-stu-id="a83cd-124">SortAsc</span></span>  <br/> |<span data-ttu-id="a83cd-125">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="a83cd-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="a83cd-126">可选</span><span class="sxs-lookup"><span data-stu-id="a83cd-126">optional</span></span>  <br/> ||<span data-ttu-id="a83cd-127">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a83cd-127">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="a83cd-128">SortColumn</span><span class="sxs-lookup"><span data-stu-id="a83cd-128">SortColumn</span></span>  <br/> |<span data-ttu-id="a83cd-129">xsd：string</span><span class="sxs-lookup"><span data-stu-id="a83cd-129">xsd:string</span></span>  <br/> |<span data-ttu-id="a83cd-130">可选</span><span class="sxs-lookup"><span data-stu-id="a83cd-130">optional</span></span>  <br/> ||<span data-ttu-id="a83cd-131">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="a83cd-131">Values of the xsd:string type.</span></span>  <br/> |
   

