---
title: PrimaryKey 元素 （DataRecordSet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 47533e6e-0a48-af61-a0c2-b2cec140ae4b
description: 标识数据记录集中的一个或多个主键列。
ms.openlocfilehash: c001c343c33e65c3990744b885f1c345575b1ab3
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396356"
---
# <a name="primarykey-element-datarecordsettype-complextype-visio-xml"></a><span data-ttu-id="0dc97-103">PrimaryKey 元素 （DataRecordSet_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="0dc97-103">PrimaryKey element (DataRecordSet_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="0dc97-104">标识数据记录集中的一个或多个主键列。</span><span class="sxs-lookup"><span data-stu-id="0dc97-104">Identifies one or more primary-key columns in the data recordset.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="0dc97-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="0dc97-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="0dc97-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="0dc97-106">**Element type**</span></span> <br/> |[<span data-ttu-id="0dc97-107">PrimaryKey_Type</span><span class="sxs-lookup"><span data-stu-id="0dc97-107">PrimaryKey_Type</span></span>](primarykey_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="0dc97-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="0dc97-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="0dc97-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="0dc97-109">**Schema file**</span></span> <br/> |<span data-ttu-id="0dc97-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="0dc97-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="0dc97-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="0dc97-111">**Document parts**</span></span> <br/> |<span data-ttu-id="0dc97-112">recordsets.xml</span><span class="sxs-lookup"><span data-stu-id="0dc97-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="0dc97-113">定义</span><span class="sxs-lookup"><span data-stu-id="0dc97-113">Definition</span></span>

```XML
< xs:element name="PrimaryKey" type="PrimaryKey_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="0dc97-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="0dc97-114">Elements and attributes</span></span>

<span data-ttu-id="0dc97-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="0dc97-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="0dc97-116">父元素</span><span class="sxs-lookup"><span data-stu-id="0dc97-116">Parent elements</span></span>

|<span data-ttu-id="0dc97-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="0dc97-117">**Element**</span></span>|<span data-ttu-id="0dc97-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="0dc97-118">**Type**</span></span>|<span data-ttu-id="0dc97-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="0dc97-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="0dc97-120">数据记录集</span><span class="sxs-lookup"><span data-stu-id="0dc97-120">DataRecordSet</span></span>](datarecordset-element-datarecordsets_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0dc97-121">DataRecordSet_Type</span><span class="sxs-lookup"><span data-stu-id="0dc97-121">DataRecordSet_Type</span></span>](datarecordset_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="0dc97-122">在 Microsoft Visio 中对从数据库中查询的数据进行存储、格式设置、刷新和公开操作。</span><span class="sxs-lookup"><span data-stu-id="0dc97-122">Stores, formats, refreshes, and exposes data queried from a database in Microsoft Visio.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="0dc97-123">子元素</span><span class="sxs-lookup"><span data-stu-id="0dc97-123">Child elements</span></span>

|<span data-ttu-id="0dc97-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="0dc97-124">**Element**</span></span>|<span data-ttu-id="0dc97-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="0dc97-125">**Type**</span></span>|<span data-ttu-id="0dc97-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="0dc97-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="0dc97-127">RowKeyValue</span><span class="sxs-lookup"><span data-stu-id="0dc97-127">RowKeyValue</span></span>](rowkeyvalue-element-primarykey_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="0dc97-128">RowKeyValue_Type</span><span class="sxs-lookup"><span data-stu-id="0dc97-128">RowKeyValue_Type</span></span>](rowkeyvalue_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="0dc97-129">指定此组件的记录集的各个行的主关键字的值。</span><span class="sxs-lookup"><span data-stu-id="0dc97-129">Specifies the value of this component of the primary key for an individual row of a recordset.</span></span> <span data-ttu-id="0dc97-130">必须有至少一个匹配项的此子元素。</span><span class="sxs-lookup"><span data-stu-id="0dc97-130">There MUST be at least one occurrence of this child element.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="0dc97-131">Attributes</span><span class="sxs-lookup"><span data-stu-id="0dc97-131">Attributes</span></span>

|<span data-ttu-id="0dc97-132">**属性**</span><span class="sxs-lookup"><span data-stu-id="0dc97-132">**Attribute**</span></span>|<span data-ttu-id="0dc97-133">**类型**</span><span class="sxs-lookup"><span data-stu-id="0dc97-133">**Type**</span></span>|<span data-ttu-id="0dc97-134">**必需**</span><span class="sxs-lookup"><span data-stu-id="0dc97-134">**Required**</span></span>|<span data-ttu-id="0dc97-135">**说明**</span><span class="sxs-lookup"><span data-stu-id="0dc97-135">**Description**</span></span>|<span data-ttu-id="0dc97-136">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="0dc97-136">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0dc97-137">ColumnNameID</span><span class="sxs-lookup"><span data-stu-id="0dc97-137">ColumnNameID</span></span>  <br/> |<span data-ttu-id="0dc97-138">xsd: string</span><span class="sxs-lookup"><span data-stu-id="0dc97-138">xsd:string</span></span>  <br/> |<span data-ttu-id="0dc97-139">可选</span><span class="sxs-lookup"><span data-stu-id="0dc97-139">optional</span></span>  <br/> |<span data-ttu-id="0dc97-140">指定是主键的一个组件的域的名称。</span><span class="sxs-lookup"><span data-stu-id="0dc97-140">Specifies the name of a field that is a component of the primary key.</span></span> <span data-ttu-id="0dc97-141">它必须是正在指定其主键 DataRecordSet_Type DataColumn_Type 后代元素的**ColumnNameID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="0dc97-141">It MUST be the value of the **ColumnNameID** attribute of a DataColumn_Type descendant element of the DataRecordSet_Type whose primary key is being specified.</span></span>  <br/> |<span data-ttu-id="0dc97-142">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="0dc97-142">Values of the xsd:string type.</span></span>  <br/> |
   

