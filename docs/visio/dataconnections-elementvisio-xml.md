---
title: DataConnections 元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3cac0cd0-87ff-8c82-2d33-20070a505f4e
description: 包含文档的 DataConnection 元素。
ms.openlocfilehash: 5b1619253a2818f2a181d281c78a0445318ed6ca
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395026"
---
# <a name="dataconnections-element-visio-xml"></a><span data-ttu-id="734d7-103">DataConnections 元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="734d7-103">DataConnections element ('Visio XML')</span></span>

<span data-ttu-id="734d7-104">包含文档的**DataConnection**元素。</span><span class="sxs-lookup"><span data-stu-id="734d7-104">Contains the **DataConnection** elements for the document.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="734d7-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="734d7-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="734d7-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="734d7-106">**Element type**</span></span> <br/> |[<span data-ttu-id="734d7-107">DataConnections_Type</span><span class="sxs-lookup"><span data-stu-id="734d7-107">DataConnections_Type</span></span>](dataconnections_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="734d7-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="734d7-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="734d7-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="734d7-109">**Schema file**</span></span> <br/> |<span data-ttu-id="734d7-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="734d7-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="734d7-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="734d7-111">**Document parts**</span></span> <br/> |<span data-ttu-id="734d7-112">connections.xml</span><span class="sxs-lookup"><span data-stu-id="734d7-112">connections.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="734d7-113">定义</span><span class="sxs-lookup"><span data-stu-id="734d7-113">Definition</span></span>

```XML
< xs:element name="DataConnections" type="DataConnections_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="734d7-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="734d7-114">Elements and attributes</span></span>

<span data-ttu-id="734d7-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="734d7-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="734d7-116">父元素</span><span class="sxs-lookup"><span data-stu-id="734d7-116">Parent elements</span></span>

<span data-ttu-id="734d7-117">无。</span><span class="sxs-lookup"><span data-stu-id="734d7-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="734d7-118">子元素</span><span class="sxs-lookup"><span data-stu-id="734d7-118">Child elements</span></span>

|<span data-ttu-id="734d7-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="734d7-119">**Element**</span></span>|<span data-ttu-id="734d7-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="734d7-120">**Type**</span></span>|<span data-ttu-id="734d7-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="734d7-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="734d7-122">DataConnection</span><span class="sxs-lookup"><span data-stu-id="734d7-122">DataConnection</span></span>](dataconnection-element-dataconnections_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="734d7-123">DataConnection_Type</span><span class="sxs-lookup"><span data-stu-id="734d7-123">DataConnection_Type</span></span>](dataconnection_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="734d7-124">使一个或多个**DataRecordset**元素和与非 XML 数据源之间的通信抽象化。</span><span class="sxs-lookup"><span data-stu-id="734d7-124">Abstracts communication between one or more **DataRecordset** elements and a non-XML data source.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="734d7-125">Attributes</span><span class="sxs-lookup"><span data-stu-id="734d7-125">Attributes</span></span>

|<span data-ttu-id="734d7-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="734d7-126">**Attribute**</span></span>|<span data-ttu-id="734d7-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="734d7-127">**Type**</span></span>|<span data-ttu-id="734d7-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="734d7-128">**Required**</span></span>|<span data-ttu-id="734d7-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="734d7-129">**Description**</span></span>|<span data-ttu-id="734d7-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="734d7-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="734d7-131">NextID</span><span class="sxs-lookup"><span data-stu-id="734d7-131">NextID</span></span>  <br/> |<span data-ttu-id="734d7-132">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="734d7-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="734d7-133">必需</span><span class="sxs-lookup"><span data-stu-id="734d7-133">required</span></span>  <br/> |<span data-ttu-id="734d7-134">下一个可用 ID 的新连接。</span><span class="sxs-lookup"><span data-stu-id="734d7-134">The next available ID for new connections.</span></span>  <br/> |<span data-ttu-id="734d7-135">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="734d7-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

