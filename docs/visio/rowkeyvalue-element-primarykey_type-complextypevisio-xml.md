---
title: RowKeyValue 元素 （PrimaryKey_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9077ad4b-c539-c0c8-d268-9a009990abdd
description: 指定记录集的各个行的主关键字的值。
ms.openlocfilehash: 3b91997b5fe8184eb89f8c53197a512d809171b9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781186"
---
# <a name="rowkeyvalue-element-primarykeytype-complextype-visio-xml"></a><span data-ttu-id="55693-103">RowKeyValue 元素 （PrimaryKey_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="55693-103">RowKeyValue element (PrimaryKey_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="55693-104">指定记录集的各个行的主关键字的值。</span><span class="sxs-lookup"><span data-stu-id="55693-104">Specifies the value of a primary key for an individual row of a recordset.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="55693-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="55693-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="55693-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="55693-106">**Element type**</span></span> <br/> |[<span data-ttu-id="55693-107">RowKeyValue_Type</span><span class="sxs-lookup"><span data-stu-id="55693-107">RowKeyValue_Type</span></span>](rowkeyvalue_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="55693-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="55693-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="55693-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="55693-109">**Schema file**</span></span> <br/> |<span data-ttu-id="55693-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="55693-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="55693-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="55693-111">**Document parts**</span></span> <br/> |<span data-ttu-id="55693-112">recordsets.xml</span><span class="sxs-lookup"><span data-stu-id="55693-112">recordsets.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="55693-113">定义</span><span class="sxs-lookup"><span data-stu-id="55693-113">Definition</span></span>

```XML
< xs:element name="RowKeyValue" type="RowKeyValue_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="55693-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="55693-114">Elements and attributes</span></span>

<span data-ttu-id="55693-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="55693-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="55693-116">父元素</span><span class="sxs-lookup"><span data-stu-id="55693-116">Parent elements</span></span>

|<span data-ttu-id="55693-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="55693-117">**Element**</span></span>|<span data-ttu-id="55693-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="55693-118">**Type**</span></span>|<span data-ttu-id="55693-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="55693-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="55693-120">PrimaryKey</span><span class="sxs-lookup"><span data-stu-id="55693-120">PrimaryKey</span></span>](primarykey-element-datarecordset_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="55693-121">PrimaryKey_Type</span><span class="sxs-lookup"><span data-stu-id="55693-121">PrimaryKey_Type</span></span>](primarykey_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="55693-122">指定记录集的主键。</span><span class="sxs-lookup"><span data-stu-id="55693-122">Specifies a primary key of a recordset.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="55693-123">子元素</span><span class="sxs-lookup"><span data-stu-id="55693-123">Child elements</span></span>

<span data-ttu-id="55693-124">无。</span><span class="sxs-lookup"><span data-stu-id="55693-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="55693-125">属性</span><span class="sxs-lookup"><span data-stu-id="55693-125">Attributes</span></span>

|<span data-ttu-id="55693-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="55693-126">**Attribute**</span></span>|<span data-ttu-id="55693-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="55693-127">**Type**</span></span>|<span data-ttu-id="55693-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="55693-128">**Required**</span></span>|<span data-ttu-id="55693-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="55693-129">**Description**</span></span>|<span data-ttu-id="55693-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="55693-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="55693-131">RowID</span><span class="sxs-lookup"><span data-stu-id="55693-131">RowID</span></span>  <br/> |<span data-ttu-id="55693-132">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="55693-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="55693-133">必需</span><span class="sxs-lookup"><span data-stu-id="55693-133">required</span></span>  <br/> |<span data-ttu-id="55693-134">一个唯一的值，标识的记录集行。</span><span class="sxs-lookup"><span data-stu-id="55693-134">A unique value that identifies a row of a recordset.</span></span>  <br/> |<span data-ttu-id="55693-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="55693-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="55693-136">值</span><span class="sxs-lookup"><span data-stu-id="55693-136">Value</span></span>  <br/> |<span data-ttu-id="55693-137">xsd: string</span><span class="sxs-lookup"><span data-stu-id="55693-137">xsd:string</span></span>  <br/> |<span data-ttu-id="55693-138">必需</span><span class="sxs-lookup"><span data-stu-id="55693-138">required</span></span>  <br/> |<span data-ttu-id="55693-139">此行 recordset 的主关键字的值。</span><span class="sxs-lookup"><span data-stu-id="55693-139">The value of the primary key for this row of the recordset.</span></span>  <br/> |<span data-ttu-id="55693-140">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="55693-140">Values of the xsd:string type.</span></span>  <br/> |
   

