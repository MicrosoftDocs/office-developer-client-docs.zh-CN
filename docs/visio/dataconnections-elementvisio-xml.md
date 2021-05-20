---
title: 'DataConnections 元素 (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 3cac0cd0-87ff-8c82-2d33-20070a505f4e
description: 包含文档的 DataConnection 元素。
ms.openlocfilehash: 5d45d1dcd76524c2144336235e8277cd51f8a138
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539180"
---
# <a name="dataconnections-element-visio-xml"></a><span data-ttu-id="78f9e-103">DataConnections 元素 (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="78f9e-103">DataConnections element (Visio XML)</span></span>

<span data-ttu-id="78f9e-104">包含 **文档的 DataConnection** 元素。</span><span class="sxs-lookup"><span data-stu-id="78f9e-104">Contains the **DataConnection** elements for the document.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="78f9e-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="78f9e-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="78f9e-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="78f9e-106">**Element type**</span></span> <br/> |[<span data-ttu-id="78f9e-107">DataConnections_Type</span><span class="sxs-lookup"><span data-stu-id="78f9e-107">DataConnections_Type</span></span>](dataconnections_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="78f9e-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="78f9e-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="78f9e-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="78f9e-109">**Schema file**</span></span> <br/> |<span data-ttu-id="78f9e-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="78f9e-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="78f9e-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="78f9e-111">**Document parts**</span></span> <br/> |<span data-ttu-id="78f9e-112">connections.xml</span><span class="sxs-lookup"><span data-stu-id="78f9e-112">connections.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="78f9e-113">定义</span><span class="sxs-lookup"><span data-stu-id="78f9e-113">Definition</span></span>

```XML
< xs:element name="DataConnections" type="DataConnections_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="78f9e-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="78f9e-114">Elements and attributes</span></span>

<span data-ttu-id="78f9e-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="78f9e-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="78f9e-116">父元素</span><span class="sxs-lookup"><span data-stu-id="78f9e-116">Parent elements</span></span>

<span data-ttu-id="78f9e-117">无。</span><span class="sxs-lookup"><span data-stu-id="78f9e-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="78f9e-118">子元素</span><span class="sxs-lookup"><span data-stu-id="78f9e-118">Child elements</span></span>

|<span data-ttu-id="78f9e-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="78f9e-119">**Element**</span></span>|<span data-ttu-id="78f9e-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="78f9e-120">**Type**</span></span>|<span data-ttu-id="78f9e-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="78f9e-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="78f9e-122">DataConnection</span><span class="sxs-lookup"><span data-stu-id="78f9e-122">DataConnection</span></span>](dataconnection-element-dataconnections_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="78f9e-123">DataConnection_Type</span><span class="sxs-lookup"><span data-stu-id="78f9e-123">DataConnection_Type</span></span>](dataconnection_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="78f9e-124">抽象化一个或多个 **DataRecordset** 元素与非 XML 数据源之间的通信。</span><span class="sxs-lookup"><span data-stu-id="78f9e-124">Abstracts communication between one or more **DataRecordset** elements and a non-XML data source.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="78f9e-125">属性</span><span class="sxs-lookup"><span data-stu-id="78f9e-125">Attributes</span></span>

|<span data-ttu-id="78f9e-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="78f9e-126">**Attribute**</span></span>|<span data-ttu-id="78f9e-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="78f9e-127">**Type**</span></span>|<span data-ttu-id="78f9e-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="78f9e-128">**Required**</span></span>|<span data-ttu-id="78f9e-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="78f9e-129">**Description**</span></span>|<span data-ttu-id="78f9e-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="78f9e-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="78f9e-131">NextID</span><span class="sxs-lookup"><span data-stu-id="78f9e-131">NextID</span></span>  <br/> |<span data-ttu-id="78f9e-132">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="78f9e-132">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="78f9e-133">必需</span><span class="sxs-lookup"><span data-stu-id="78f9e-133">required</span></span>  <br/> |<span data-ttu-id="78f9e-134">新连接的下一个可用 ID。</span><span class="sxs-lookup"><span data-stu-id="78f9e-134">The next available ID for new connections.</span></span>  <br/> |<span data-ttu-id="78f9e-135">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="78f9e-135">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

