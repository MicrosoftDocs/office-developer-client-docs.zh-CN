---
title: PrimaryKey 元素 (DataRecordSet_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 47533e6e-0a48-af61-a0c2-b2cec140ae4b
description: 标识数据记录集中的一个或多个主关键字列。
ms.openlocfilehash: c001c343c33e65c3990744b885f1c345575b1ab3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355993"
---
# <a name="primarykey-element-datarecordsettype-complextype-visio-xml"></a><span data-ttu-id="44da2-103">PrimaryKey 元素 (DataRecordSet_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="44da2-103">PrimaryKey element (DataRecordSet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="44da2-104">标识数据记录集中的一个或多个主关键字列。</span><span class="sxs-lookup"><span data-stu-id="44da2-104">Identifies one or more primary-key columns in the data recordset.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="44da2-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="44da2-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="44da2-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="44da2-106">**Element type**</span></span> <br/> |[<span data-ttu-id="44da2-107">PrimaryKey_Type</span><span class="sxs-lookup"><span data-stu-id="44da2-107">PrimaryKey_Type</span></span>](primarykey_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="44da2-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="44da2-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="44da2-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="44da2-109">**Schema file**</span></span> <br/> |<span data-ttu-id="44da2-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="44da2-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="44da2-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="44da2-111">**Document parts**</span></span> <br/> |<span data-ttu-id="44da2-112">记录集 .xml</span><span class="sxs-lookup"><span data-stu-id="44da2-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="44da2-113">定义</span><span class="sxs-lookup"><span data-stu-id="44da2-113">Definition</span></span>

```XML
< xs:element name="PrimaryKey" type="PrimaryKey_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="44da2-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="44da2-114">Elements and attributes</span></span>

<span data-ttu-id="44da2-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="44da2-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="44da2-116">父元素</span><span class="sxs-lookup"><span data-stu-id="44da2-116">Parent elements</span></span>

|<span data-ttu-id="44da2-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="44da2-117">**Element**</span></span>|<span data-ttu-id="44da2-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="44da2-118">**Type**</span></span>|<span data-ttu-id="44da2-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="44da2-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="44da2-120">DataRecordSet</span><span class="sxs-lookup"><span data-stu-id="44da2-120">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="44da2-121">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="44da2-121">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="44da2-122">在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。</span><span class="sxs-lookup"><span data-stu-id="44da2-122">Stores, formats, refreshes, and exposes data queried from a database in Microsoft Visio.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="44da2-123">子元素</span><span class="sxs-lookup"><span data-stu-id="44da2-123">Child elements</span></span>

|<span data-ttu-id="44da2-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="44da2-124">**Element**</span></span>|<span data-ttu-id="44da2-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="44da2-125">**Type**</span></span>|<span data-ttu-id="44da2-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="44da2-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="44da2-127">RowKeyValue</span><span class="sxs-lookup"><span data-stu-id="44da2-127">RowKeyValue</span></span>](rowkeyvalue-element-primarykey_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="44da2-128">RowKeyValue_Type</span><span class="sxs-lookup"><span data-stu-id="44da2-128">RowKeyValue_Type</span></span>](rowkeyvalue_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="44da2-129">为 recordset 的单个行指定主键的此部分的值。</span><span class="sxs-lookup"><span data-stu-id="44da2-129">Specifies the value of this component of the primary key for an individual row of a recordset.</span></span> <span data-ttu-id="44da2-130">此子元素必须至少有一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="44da2-130">There MUST be at least one occurrence of this child element.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="44da2-131">属性</span><span class="sxs-lookup"><span data-stu-id="44da2-131">Attributes</span></span>

|<span data-ttu-id="44da2-132">**属性**</span><span class="sxs-lookup"><span data-stu-id="44da2-132">**Attribute**</span></span>|<span data-ttu-id="44da2-133">**类型**</span><span class="sxs-lookup"><span data-stu-id="44da2-133">**Type**</span></span>|<span data-ttu-id="44da2-134">**必需**</span><span class="sxs-lookup"><span data-stu-id="44da2-134">**Required**</span></span>|<span data-ttu-id="44da2-135">**描述**</span><span class="sxs-lookup"><span data-stu-id="44da2-135">**Description**</span></span>|<span data-ttu-id="44da2-136">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="44da2-136">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="44da2-137">ColumnNameID</span><span class="sxs-lookup"><span data-stu-id="44da2-137">ColumnNameID</span></span>  <br/> |<span data-ttu-id="44da2-138">xsd: string</span><span class="sxs-lookup"><span data-stu-id="44da2-138">xsd:string</span></span>  <br/> |<span data-ttu-id="44da2-139">可选</span><span class="sxs-lookup"><span data-stu-id="44da2-139">optional</span></span>  <br/> |<span data-ttu-id="44da2-140">指定作为主键的组成部分的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="44da2-140">Specifies the name of a field that is a component of the primary key.</span></span> <span data-ttu-id="44da2-141">它必须是要指定其主键的 DataRecordSet_Type 的 DataColumn_Type 后代元素的**ColumnNameID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="44da2-141">It MUST be the value of the **ColumnNameID** attribute of a DataColumn_Type descendant element of the DataRecordSet_Type whose primary key is being specified.</span></span>  <br/> |<span data-ttu-id="44da2-142">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="44da2-142">Values of the xsd:string type.</span></span>  <br/> |
   

