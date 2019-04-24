---
title: DataConnection 元素 (DataConnections_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6aab8be3-b236-029b-1df3-b6860d4f4586
description: 抽象化一个或多个 DataRecordset 元素与非 XML 数据源之间的通信。
ms.openlocfilehash: 0073c329ec9149263530421531522c4d0b95633d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344623"
---
# <a name="dataconnection-element-dataconnectionstype-complextype-visio-xml"></a><span data-ttu-id="e3305-103">DataConnection 元素 (DataConnections_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="e3305-103">DataConnection element (DataConnections_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="e3305-104">抽象化一个或多个**DataRecordset**元素与非 XML 数据源之间的通信。</span><span class="sxs-lookup"><span data-stu-id="e3305-104">Abstracts communication between one or more **DataRecordset** elements and a non-XML data source.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="e3305-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="e3305-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e3305-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="e3305-106">**Element type**</span></span> <br/> |[<span data-ttu-id="e3305-107">DataConnection_Type</span><span class="sxs-lookup"><span data-stu-id="e3305-107">DataConnection_Type</span></span>](dataconnection_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="e3305-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e3305-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="e3305-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e3305-109">**Schema file**</span></span> <br/> |<span data-ttu-id="e3305-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="e3305-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="e3305-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="e3305-111">**Document parts**</span></span> <br/> |<span data-ttu-id="e3305-112">连接 .xml</span><span class="sxs-lookup"><span data-stu-id="e3305-112">connections.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e3305-113">定义</span><span class="sxs-lookup"><span data-stu-id="e3305-113">Definition</span></span>

```XML
< xs:element name="DataConnection" type="DataConnection_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e3305-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e3305-114">Elements and attributes</span></span>

<span data-ttu-id="e3305-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="e3305-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="e3305-116">父元素</span><span class="sxs-lookup"><span data-stu-id="e3305-116">Parent elements</span></span>

|<span data-ttu-id="e3305-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="e3305-117">**Element**</span></span>|<span data-ttu-id="e3305-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="e3305-118">**Type**</span></span>|<span data-ttu-id="e3305-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="e3305-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e3305-120">DataConnections</span><span class="sxs-lookup"><span data-stu-id="e3305-120">DataConnections</span></span>](dataconnections-elementvisio-xml.md) <br/> |[<span data-ttu-id="e3305-121">DataConnections_Type</span><span class="sxs-lookup"><span data-stu-id="e3305-121">DataConnections_Type</span></span>](dataconnections_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="e3305-122">包含文档的**DataConnection**元素。</span><span class="sxs-lookup"><span data-stu-id="e3305-122">Contains the **DataConnection** elements for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="e3305-123">子元素</span><span class="sxs-lookup"><span data-stu-id="e3305-123">Child elements</span></span>

<span data-ttu-id="e3305-124">无。</span><span class="sxs-lookup"><span data-stu-id="e3305-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="e3305-125">属性</span><span class="sxs-lookup"><span data-stu-id="e3305-125">Attributes</span></span>

|<span data-ttu-id="e3305-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="e3305-126">**Attribute**</span></span>|<span data-ttu-id="e3305-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="e3305-127">**Type**</span></span>|<span data-ttu-id="e3305-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="e3305-128">**Required**</span></span>|<span data-ttu-id="e3305-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="e3305-129">**Description**</span></span>|<span data-ttu-id="e3305-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="e3305-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e3305-131">AlwaysUseConnectionFile</span><span class="sxs-lookup"><span data-stu-id="e3305-131">AlwaysUseConnectionFile</span></span>  <br/> |<span data-ttu-id="e3305-132">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="e3305-132">xsd:boolean</span></span>  <br/> |<span data-ttu-id="e3305-133">可选</span><span class="sxs-lookup"><span data-stu-id="e3305-133">optional</span></span>  <br/> |<span data-ttu-id="e3305-134">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="e3305-134">The default value is false.</span></span> <span data-ttu-id="e3305-135">有关详细信息，请参阅"说明"。</span><span class="sxs-lookup"><span data-stu-id="e3305-135">See Remarks for more information.</span></span>  <br/> |<span data-ttu-id="e3305-136">xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e3305-136">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="e3305-137">Command</span><span class="sxs-lookup"><span data-stu-id="e3305-137">Command</span></span>  <br/> |<span data-ttu-id="e3305-138">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e3305-138">xsd:string</span></span>  <br/> |<span data-ttu-id="e3305-139">可选</span><span class="sxs-lookup"><span data-stu-id="e3305-139">optional</span></span>  <br/> |<span data-ttu-id="e3305-140">用于查询数据源的命令字符串。</span><span class="sxs-lookup"><span data-stu-id="e3305-140">The command string used to query the data source.</span></span>  <br/> |<span data-ttu-id="e3305-141">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e3305-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e3305-142">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="e3305-142">ConnectionString</span></span>  <br/> |<span data-ttu-id="e3305-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e3305-143">xsd:string</span></span>  <br/> |<span data-ttu-id="e3305-144">可选</span><span class="sxs-lookup"><span data-stu-id="e3305-144">optional</span></span>  <br/> |<span data-ttu-id="e3305-145">定义连接到数据源所需参数的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="e3305-145">The connection string that defines the parameters necessary to connect to a data source.</span></span>  <br/> |<span data-ttu-id="e3305-146">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e3305-146">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e3305-147">FileName</span><span class="sxs-lookup"><span data-stu-id="e3305-147">FileName</span></span>  <br/> |<span data-ttu-id="e3305-148">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e3305-148">xsd:string</span></span>  <br/> |<span data-ttu-id="e3305-149">必需</span><span class="sxs-lookup"><span data-stu-id="e3305-149">required</span></span>  <br/> |<span data-ttu-id="e3305-150">连接文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e3305-150">The name of the connection file.</span></span> <span data-ttu-id="e3305-151">有关详细信息，请参阅"说明"。</span><span class="sxs-lookup"><span data-stu-id="e3305-151">See Remarks for more information.</span></span>  <br/> |<span data-ttu-id="e3305-152">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e3305-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e3305-153">FriendlyName</span><span class="sxs-lookup"><span data-stu-id="e3305-153">FriendlyName</span></span>  <br/> |<span data-ttu-id="e3305-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="e3305-154">xsd:string</span></span>  <br/> |<span data-ttu-id="e3305-155">可选</span><span class="sxs-lookup"><span data-stu-id="e3305-155">optional</span></span>  <br/> |<span data-ttu-id="e3305-156">用户为数据连接提供的名称。</span><span class="sxs-lookup"><span data-stu-id="e3305-156">A user provided name for the data connection.</span></span>  <br/> |<span data-ttu-id="e3305-157">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e3305-157">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="e3305-158">ID</span><span class="sxs-lookup"><span data-stu-id="e3305-158">ID</span></span>  <br/> |<span data-ttu-id="e3305-159">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="e3305-159">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="e3305-160">必需</span><span class="sxs-lookup"><span data-stu-id="e3305-160">required</span></span>  <br/> |<span data-ttu-id="e3305-161">由 Visio 为指定的连接分配的 ID, 在文档中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e3305-161">The ID assigned by Visio for a given connection, unique within the document.</span></span>  <br/> |<span data-ttu-id="e3305-162">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e3305-162">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="e3305-163">Timeout</span><span class="sxs-lookup"><span data-stu-id="e3305-163">Timeout</span></span>  <br/> |<span data-ttu-id="e3305-164">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="e3305-164">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="e3305-165">可选</span><span class="sxs-lookup"><span data-stu-id="e3305-165">optional</span></span>  <br/> |<span data-ttu-id="e3305-166">尝试在终止尝试之前建立连接时的等待时间 (以分钟为单位)。</span><span class="sxs-lookup"><span data-stu-id="e3305-166">The wait time in minutes while trying to establish a connection before terminating the attempt.</span></span>  <br/> |<span data-ttu-id="e3305-167">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="e3305-167">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

