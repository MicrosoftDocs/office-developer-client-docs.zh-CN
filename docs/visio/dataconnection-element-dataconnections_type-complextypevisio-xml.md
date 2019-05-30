---
title: DataConnection 元素 (DataConnections_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6aab8be3-b236-029b-1df3-b6860d4f4586
description: 抽象化一个或多个 DataRecordset 元素与非 XML 数据源之间的通信。
ms.openlocfilehash: 619f3b4e3d9c93831cc23bc38fba3670107b2b51
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538401"
---
# <a name="dataconnection-element-dataconnectionstype-complextype-visio-xml"></a><span data-ttu-id="9cefd-103">DataConnection 元素 (DataConnections_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="9cefd-103">DataConnection element (DataConnections_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="9cefd-104">抽象化一个或多个**DataRecordset**元素与非 XML 数据源之间的通信。</span><span class="sxs-lookup"><span data-stu-id="9cefd-104">Abstracts communication between one or more **DataRecordset** elements and a non-XML data source.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="9cefd-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="9cefd-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9cefd-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="9cefd-106">**Element type**</span></span> <br/> |[<span data-ttu-id="9cefd-107">DataConnection_Type</span><span class="sxs-lookup"><span data-stu-id="9cefd-107">DataConnection_Type</span></span>](dataconnection_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="9cefd-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9cefd-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="9cefd-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9cefd-109">**Schema file**</span></span> <br/> |<span data-ttu-id="9cefd-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="9cefd-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="9cefd-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="9cefd-111">**Document parts**</span></span> <br/> |<span data-ttu-id="9cefd-112">连接 .xml</span><span class="sxs-lookup"><span data-stu-id="9cefd-112">connections.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9cefd-113">定义</span><span class="sxs-lookup"><span data-stu-id="9cefd-113">Definition</span></span>

```XML
< xs:element name="DataConnection" type="DataConnection_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="9cefd-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9cefd-114">Elements and attributes</span></span>

<span data-ttu-id="9cefd-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="9cefd-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="9cefd-116">父元素</span><span class="sxs-lookup"><span data-stu-id="9cefd-116">Parent elements</span></span>

|<span data-ttu-id="9cefd-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="9cefd-117">**Element**</span></span>|<span data-ttu-id="9cefd-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="9cefd-118">**Type**</span></span>|<span data-ttu-id="9cefd-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="9cefd-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9cefd-120">DataConnections</span><span class="sxs-lookup"><span data-stu-id="9cefd-120">DataConnections</span></span>](dataconnections-elementvisio-xml.md) <br/> |[<span data-ttu-id="9cefd-121">DataConnections_Type</span><span class="sxs-lookup"><span data-stu-id="9cefd-121">DataConnections_Type</span></span>](dataconnections_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9cefd-122">包含文档的**DataConnection**元素。</span><span class="sxs-lookup"><span data-stu-id="9cefd-122">Contains the **DataConnection** elements for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="9cefd-123">子元素</span><span class="sxs-lookup"><span data-stu-id="9cefd-123">Child elements</span></span>

<span data-ttu-id="9cefd-124">无。</span><span class="sxs-lookup"><span data-stu-id="9cefd-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="9cefd-125">属性</span><span class="sxs-lookup"><span data-stu-id="9cefd-125">Attributes</span></span>

|<span data-ttu-id="9cefd-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="9cefd-126">**Attribute**</span></span>|<span data-ttu-id="9cefd-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="9cefd-127">**Type**</span></span>|<span data-ttu-id="9cefd-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="9cefd-128">**Required**</span></span>|<span data-ttu-id="9cefd-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="9cefd-129">**Description**</span></span>|<span data-ttu-id="9cefd-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="9cefd-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9cefd-131">AlwaysUseConnectionFile</span><span class="sxs-lookup"><span data-stu-id="9cefd-131">AlwaysUseConnectionFile</span></span>  <br/> |<span data-ttu-id="9cefd-132">xsd: boolean</span><span class="sxs-lookup"><span data-stu-id="9cefd-132">xsd:boolean</span></span>  <br/> |<span data-ttu-id="9cefd-133">可选</span><span class="sxs-lookup"><span data-stu-id="9cefd-133">optional</span></span>  <br/> |<span data-ttu-id="9cefd-134">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="9cefd-134">The default value is false.</span></span> <span data-ttu-id="9cefd-135">有关详细信息，请参阅"说明"。</span><span class="sxs-lookup"><span data-stu-id="9cefd-135">See Remarks for more information.</span></span>  <br/> |<span data-ttu-id="9cefd-136">Xsd: boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9cefd-136">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="9cefd-137">Command</span><span class="sxs-lookup"><span data-stu-id="9cefd-137">Command</span></span>  <br/> |<span data-ttu-id="9cefd-138">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9cefd-138">xsd:string</span></span>  <br/> |<span data-ttu-id="9cefd-139">可选</span><span class="sxs-lookup"><span data-stu-id="9cefd-139">optional</span></span>  <br/> |<span data-ttu-id="9cefd-140">用于查询数据源的命令字符串。</span><span class="sxs-lookup"><span data-stu-id="9cefd-140">The command string used to query the data source.</span></span>  <br/> |<span data-ttu-id="9cefd-141">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9cefd-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="9cefd-142">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="9cefd-142">ConnectionString</span></span>  <br/> |<span data-ttu-id="9cefd-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9cefd-143">xsd:string</span></span>  <br/> |<span data-ttu-id="9cefd-144">可选</span><span class="sxs-lookup"><span data-stu-id="9cefd-144">optional</span></span>  <br/> |<span data-ttu-id="9cefd-145">定义连接到数据源所需参数的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="9cefd-145">The connection string that defines the parameters necessary to connect to a data source.</span></span>  <br/> |<span data-ttu-id="9cefd-146">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9cefd-146">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="9cefd-147">FileName</span><span class="sxs-lookup"><span data-stu-id="9cefd-147">FileName</span></span>  <br/> |<span data-ttu-id="9cefd-148">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9cefd-148">xsd:string</span></span>  <br/> |<span data-ttu-id="9cefd-149">必需</span><span class="sxs-lookup"><span data-stu-id="9cefd-149">required</span></span>  <br/> |<span data-ttu-id="9cefd-150">连接文件的名称。</span><span class="sxs-lookup"><span data-stu-id="9cefd-150">The name of the connection file.</span></span> <span data-ttu-id="9cefd-151">有关详细信息，请参阅"说明"。</span><span class="sxs-lookup"><span data-stu-id="9cefd-151">See Remarks for more information.</span></span>  <br/> |<span data-ttu-id="9cefd-152">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9cefd-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="9cefd-153">FriendlyName</span><span class="sxs-lookup"><span data-stu-id="9cefd-153">FriendlyName</span></span>  <br/> |<span data-ttu-id="9cefd-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="9cefd-154">xsd:string</span></span>  <br/> |<span data-ttu-id="9cefd-155">可选</span><span class="sxs-lookup"><span data-stu-id="9cefd-155">optional</span></span>  <br/> |<span data-ttu-id="9cefd-156">用户为数据连接提供的名称。</span><span class="sxs-lookup"><span data-stu-id="9cefd-156">A user provided name for the data connection.</span></span>  <br/> |<span data-ttu-id="9cefd-157">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9cefd-157">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="9cefd-158">ID</span><span class="sxs-lookup"><span data-stu-id="9cefd-158">ID</span></span>  <br/> |<span data-ttu-id="9cefd-159">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9cefd-159">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9cefd-160">必需</span><span class="sxs-lookup"><span data-stu-id="9cefd-160">required</span></span>  <br/> |<span data-ttu-id="9cefd-161">由 Visio 为指定的连接分配的 ID, 在文档中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="9cefd-161">The ID assigned by Visio for a given connection, unique within the document.</span></span>  <br/> |<span data-ttu-id="9cefd-162">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9cefd-162">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="9cefd-163">Timeout</span><span class="sxs-lookup"><span data-stu-id="9cefd-163">Timeout</span></span>  <br/> |<span data-ttu-id="9cefd-164">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="9cefd-164">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="9cefd-165">可选</span><span class="sxs-lookup"><span data-stu-id="9cefd-165">optional</span></span>  <br/> |<span data-ttu-id="9cefd-166">尝试在终止尝试之前建立连接时的等待时间 (以分钟为单位)。</span><span class="sxs-lookup"><span data-stu-id="9cefd-166">The wait time in minutes while trying to establish a connection before terminating the attempt.</span></span>  <br/> |<span data-ttu-id="9cefd-167">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="9cefd-167">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

