---
title: RowKeyValue 元素 (PrimaryKey_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9077ad4b-c539-c0c8-d268-9a009990abdd
description: 指定 recordset 的单个行的主键的值。
ms.openlocfilehash: 12d60bb0ccccdcd8c1790678cae4ad1e887e73b6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283501"
---
# <a name="rowkeyvalue-element-primarykeytype-complextype-visio-xml"></a><span data-ttu-id="e7f1b-103">RowKeyValue 元素 (PrimaryKey_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="e7f1b-103">RowKeyValue element (PrimaryKey_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="e7f1b-104">指定 recordset 的单个行的主键的值。</span><span class="sxs-lookup"><span data-stu-id="e7f1b-104">Specifies the value of a primary key for an individual row of a recordset.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="e7f1b-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="e7f1b-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e7f1b-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="e7f1b-106">**Element type**</span></span> <br/> |[<span data-ttu-id="e7f1b-107">RowKeyValue_Type</span><span class="sxs-lookup"><span data-stu-id="e7f1b-107">RowKeyValue_Type</span></span>](rowkeyvalue_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="e7f1b-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e7f1b-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="e7f1b-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e7f1b-109">**Schema file**</span></span> <br/> |<span data-ttu-id="e7f1b-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="e7f1b-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="e7f1b-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="e7f1b-111">**Document parts**</span></span> <br/> |<span data-ttu-id="e7f1b-112">记录集 .xml</span><span class="sxs-lookup"><span data-stu-id="e7f1b-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e7f1b-113">定义</span><span class="sxs-lookup"><span data-stu-id="e7f1b-113">Definition</span></span>

```XML
< xs:element name="RowKeyValue" type="RowKeyValue_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e7f1b-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e7f1b-114">Elements and attributes</span></span>

<span data-ttu-id="e7f1b-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="e7f1b-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="e7f1b-116">父元素</span><span class="sxs-lookup"><span data-stu-id="e7f1b-116">Parent elements</span></span>

|<span data-ttu-id="e7f1b-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="e7f1b-117">**Element**</span></span>|<span data-ttu-id="e7f1b-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="e7f1b-118">**Type**</span></span>|<span data-ttu-id="e7f1b-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="e7f1b-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e7f1b-120">关键字</span><span class="sxs-lookup"><span data-stu-id="e7f1b-120">PrimaryKey</span></span>](primarykey-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="e7f1b-121">PrimaryKey_Type</span><span class="sxs-lookup"><span data-stu-id="e7f1b-121">PrimaryKey_Type</span></span>](primarykey_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="e7f1b-122">指定 recordset 的主键。</span><span class="sxs-lookup"><span data-stu-id="e7f1b-122">Specifies a primary key of a recordset.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="e7f1b-123">子元素</span><span class="sxs-lookup"><span data-stu-id="e7f1b-123">Child elements</span></span>

<span data-ttu-id="e7f1b-124">无。</span><span class="sxs-lookup"><span data-stu-id="e7f1b-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="e7f1b-125">属性</span><span class="sxs-lookup"><span data-stu-id="e7f1b-125">Attributes</span></span>

|<span data-ttu-id="e7f1b-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="e7f1b-126">**Attribute**</span></span>|<span data-ttu-id="e7f1b-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="e7f1b-127">**Type**</span></span>|<span data-ttu-id="e7f1b-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="e7f1b-128">**Required**</span></span>|<span data-ttu-id="e7f1b-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="e7f1b-129">**Description**</span></span>|<span data-ttu-id="e7f1b-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e7f1b-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e7f1b-131">RowID</span><span class="sxs-lookup"><span data-stu-id="e7f1b-131">RowID</span></span>  <br/> |<span data-ttu-id="e7f1b-132">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="e7f1b-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="e7f1b-133">必需</span><span class="sxs-lookup"><span data-stu-id="e7f1b-133">required</span></span>  <br/> |<span data-ttu-id="e7f1b-134">标识记录集的行的唯一值。</span><span class="sxs-lookup"><span data-stu-id="e7f1b-134">A unique value that identifies a row of a recordset.</span></span>  <br/> |<span data-ttu-id="e7f1b-135">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e7f1b-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="e7f1b-136">值</span><span class="sxs-lookup"><span data-stu-id="e7f1b-136">Value</span></span>  <br/> |<span data-ttu-id="e7f1b-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e7f1b-137">xsd:string</span></span>  <br/> |<span data-ttu-id="e7f1b-138">必需</span><span class="sxs-lookup"><span data-stu-id="e7f1b-138">required</span></span>  <br/> |<span data-ttu-id="e7f1b-139">此 recordset 行的主键的值。</span><span class="sxs-lookup"><span data-stu-id="e7f1b-139">The value of the primary key for this row of the recordset.</span></span>  <br/> |<span data-ttu-id="e7f1b-140">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e7f1b-140">Values of the xsd:string type.</span></span>  <br/> |
   

