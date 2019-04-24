---
title: DataColumns_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ad003c9e-5e72-2df0-f9c5-dea20a220ab5
ms.openlocfilehash: 6d802bf646ee87f4c96b9ce041352af3cab48a16
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344595"
---
# <a name="datacolumnstype-complextype-visio-xml"></a><span data-ttu-id="c40e9-102">DataColumns_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="c40e9-102">DataColumns_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="c40e9-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="c40e9-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c40e9-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c40e9-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="c40e9-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c40e9-105">**Schema file**</span></span> <br/> |<span data-ttu-id="c40e9-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="c40e9-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="c40e9-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="c40e9-107">**Extension base**</span></span> <br/> |<span data-ttu-id="c40e9-108">无</span><span class="sxs-lookup"><span data-stu-id="c40e9-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c40e9-109">定义</span><span class="sxs-lookup"><span data-stu-id="c40e9-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="c40e9-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c40e9-110">Elements and attributes</span></span>

<span data-ttu-id="c40e9-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="c40e9-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="c40e9-112">子元素</span><span class="sxs-lookup"><span data-stu-id="c40e9-112">Child elements</span></span>

|<span data-ttu-id="c40e9-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="c40e9-113">**Element**</span></span>|<span data-ttu-id="c40e9-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="c40e9-114">**Type**</span></span>|<span data-ttu-id="c40e9-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="c40e9-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c40e9-116">DataColumn</span><span class="sxs-lookup"><span data-stu-id="c40e9-116">DataColumn</span></span>](datacolumn-element-datacolumns_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c40e9-117">DataColumn_Type</span><span class="sxs-lookup"><span data-stu-id="c40e9-117">DataColumn_Type</span></span>](datacolumn_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="c40e9-118">属性</span><span class="sxs-lookup"><span data-stu-id="c40e9-118">Attributes</span></span>

|<span data-ttu-id="c40e9-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="c40e9-119">**Attribute**</span></span>|<span data-ttu-id="c40e9-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="c40e9-120">**Type**</span></span>|<span data-ttu-id="c40e9-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="c40e9-121">**Required**</span></span>|<span data-ttu-id="c40e9-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="c40e9-122">**Description**</span></span>|<span data-ttu-id="c40e9-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="c40e9-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c40e9-124">SortAsc</span><span class="sxs-lookup"><span data-stu-id="c40e9-124">SortAsc</span></span>  <br/> |<span data-ttu-id="c40e9-125">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="c40e9-125">xsd:boolean</span></span>  <br/> |<span data-ttu-id="c40e9-126">可选</span><span class="sxs-lookup"><span data-stu-id="c40e9-126">optional</span></span>  <br/> ||<span data-ttu-id="c40e9-127">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c40e9-127">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="c40e9-128">SortColumn</span><span class="sxs-lookup"><span data-stu-id="c40e9-128">SortColumn</span></span>  <br/> |<span data-ttu-id="c40e9-129">xsd: string</span><span class="sxs-lookup"><span data-stu-id="c40e9-129">xsd:string</span></span>  <br/> |<span data-ttu-id="c40e9-130">可选</span><span class="sxs-lookup"><span data-stu-id="c40e9-130">optional</span></span>  <br/> ||<span data-ttu-id="c40e9-131">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="c40e9-131">Values of the xsd:string type.</span></span>  <br/> |
   

