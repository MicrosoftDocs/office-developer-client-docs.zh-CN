---
title: DataColumns_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ad003c9e-5e72-2df0-f9c5-dea20a220ab5
ms.openlocfilehash: f125bce02fab43b808608ef6b14d59dfc08a1179
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780027"
---
# <a name="datacolumnstype-complextype-visio-xml"></a><span data-ttu-id="3dcd0-102">DataColumns_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="3dcd0-102">DataColumns_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="3dcd0-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="3dcd0-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3dcd0-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="3dcd0-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="3dcd0-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="3dcd0-105">**Schema file**</span></span> <br/> |<span data-ttu-id="3dcd0-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="3dcd0-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="3dcd0-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="3dcd0-107">**Extension base**</span></span> <br/> |<span data-ttu-id="3dcd0-108">无</span><span class="sxs-lookup"><span data-stu-id="3dcd0-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="3dcd0-109">定义</span><span class="sxs-lookup"><span data-stu-id="3dcd0-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="3dcd0-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="3dcd0-110">Elements and attributes</span></span>

<span data-ttu-id="3dcd0-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="3dcd0-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="3dcd0-112">子元素</span><span class="sxs-lookup"><span data-stu-id="3dcd0-112">Child elements</span></span>

|<span data-ttu-id="3dcd0-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="3dcd0-113">**Element**</span></span>|<span data-ttu-id="3dcd0-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="3dcd0-114">**Type**</span></span>|<span data-ttu-id="3dcd0-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="3dcd0-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="3dcd0-116">DataColumn</span><span class="sxs-lookup"><span data-stu-id="3dcd0-116">DataColumn</span></span>](datacolumn-element-datacolumns_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="3dcd0-117">DataColumn_Type</span><span class="sxs-lookup"><span data-stu-id="3dcd0-117">DataColumn_Type</span></span>](datacolumn_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="3dcd0-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="3dcd0-118">Attributes</span></span>

|<span data-ttu-id="3dcd0-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="3dcd0-119">**Attribute**</span></span>|<span data-ttu-id="3dcd0-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="3dcd0-120">**Type**</span></span>|<span data-ttu-id="3dcd0-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="3dcd0-121">**Required**</span></span>|<span data-ttu-id="3dcd0-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="3dcd0-122">**Description**</span></span>|<span data-ttu-id="3dcd0-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="3dcd0-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3dcd0-124">SortAsc</span><span class="sxs-lookup"><span data-stu-id="3dcd0-124">SortAsc</span></span>  <br/> |<span data-ttu-id="3dcd0-125">化</span><span class="sxs-lookup"><span data-stu-id="3dcd0-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="3dcd0-126">可选</span><span class="sxs-lookup"><span data-stu-id="3dcd0-126">optional</span></span>  <br/> ||<span data-ttu-id="3dcd0-127">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="3dcd0-127">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="3dcd0-128">SortColumn</span><span class="sxs-lookup"><span data-stu-id="3dcd0-128">SortColumn</span></span>  <br/> |<span data-ttu-id="3dcd0-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="3dcd0-129">xsd:string</span></span>  <br/> |<span data-ttu-id="3dcd0-130">可选</span><span class="sxs-lookup"><span data-stu-id="3dcd0-130">optional</span></span>  <br/> ||<span data-ttu-id="3dcd0-131">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3dcd0-131">Values of the xsd:string type.</span></span>  <br/> |
   

