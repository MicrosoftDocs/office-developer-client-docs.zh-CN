---
title: 'DataConnection 元素 (DataConnections_Type complexType)  (Visio XML) '
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
# <a name="dataconnection-element-dataconnections_type-complextype-visio-xml"></a><span data-ttu-id="ef0e2-103">DataConnection 元素 (DataConnections_Type complexType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="ef0e2-103">DataConnection element (DataConnections_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="ef0e2-104">抽象化一个或多个 **DataRecordset** 元素与非 XML 数据源之间的通信。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-104">Abstracts communication between one or more **DataRecordset** elements and a non-XML data source.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="ef0e2-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="ef0e2-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ef0e2-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="ef0e2-106">**Element type**</span></span> <br/> |[<span data-ttu-id="ef0e2-107">DataConnection_Type</span><span class="sxs-lookup"><span data-stu-id="ef0e2-107">DataConnection_Type</span></span>](dataconnection_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="ef0e2-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ef0e2-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="ef0e2-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ef0e2-109">**Schema file**</span></span> <br/> |<span data-ttu-id="ef0e2-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="ef0e2-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="ef0e2-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="ef0e2-111">**Document parts**</span></span> <br/> |<span data-ttu-id="ef0e2-112">connections.xml</span><span class="sxs-lookup"><span data-stu-id="ef0e2-112">connections.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ef0e2-113">定义</span><span class="sxs-lookup"><span data-stu-id="ef0e2-113">Definition</span></span>

```XML
< xs:element name="DataConnection" type="DataConnection_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="ef0e2-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ef0e2-114">Elements and attributes</span></span>

<span data-ttu-id="ef0e2-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="ef0e2-116">父元素</span><span class="sxs-lookup"><span data-stu-id="ef0e2-116">Parent elements</span></span>

|<span data-ttu-id="ef0e2-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="ef0e2-117">**Element**</span></span>|<span data-ttu-id="ef0e2-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="ef0e2-118">**Type**</span></span>|<span data-ttu-id="ef0e2-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="ef0e2-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="ef0e2-120">DataConnections</span><span class="sxs-lookup"><span data-stu-id="ef0e2-120">DataConnections</span></span>](dataconnections-elementvisio-xml.md) <br/> |[<span data-ttu-id="ef0e2-121">DataConnections_Type</span><span class="sxs-lookup"><span data-stu-id="ef0e2-121">DataConnections_Type</span></span>](dataconnections_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="ef0e2-122">包含 **文档的 DataConnection** 元素。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-122">Contains the **DataConnection** elements for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="ef0e2-123">子元素</span><span class="sxs-lookup"><span data-stu-id="ef0e2-123">Child elements</span></span>

<span data-ttu-id="ef0e2-124">无。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="ef0e2-125">属性</span><span class="sxs-lookup"><span data-stu-id="ef0e2-125">Attributes</span></span>

|<span data-ttu-id="ef0e2-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="ef0e2-126">**Attribute**</span></span>|<span data-ttu-id="ef0e2-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="ef0e2-127">**Type**</span></span>|<span data-ttu-id="ef0e2-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="ef0e2-128">**Required**</span></span>|<span data-ttu-id="ef0e2-129">**描述**</span><span class="sxs-lookup"><span data-stu-id="ef0e2-129">**Description**</span></span>|<span data-ttu-id="ef0e2-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="ef0e2-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ef0e2-131">AlwaysUseConnectionFile</span><span class="sxs-lookup"><span data-stu-id="ef0e2-131">AlwaysUseConnectionFile</span></span>  <br/> |<span data-ttu-id="ef0e2-132">xsd：boolean</span><span class="sxs-lookup"><span data-stu-id="ef0e2-132">xsd:boolean</span></span>  <br/> |<span data-ttu-id="ef0e2-133">可选</span><span class="sxs-lookup"><span data-stu-id="ef0e2-133">optional</span></span>  <br/> |<span data-ttu-id="ef0e2-134">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-134">The default value is false.</span></span> <span data-ttu-id="ef0e2-135">有关详细信息，请参阅"说明"。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-135">See Remarks for more information.</span></span>  <br/> |<span data-ttu-id="ef0e2-136">xsd：boolean 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-136">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="ef0e2-137">Command</span><span class="sxs-lookup"><span data-stu-id="ef0e2-137">Command</span></span>  <br/> |<span data-ttu-id="ef0e2-138">xsd：string</span><span class="sxs-lookup"><span data-stu-id="ef0e2-138">xsd:string</span></span>  <br/> |<span data-ttu-id="ef0e2-139">可选</span><span class="sxs-lookup"><span data-stu-id="ef0e2-139">optional</span></span>  <br/> |<span data-ttu-id="ef0e2-140">用于查询数据源的命令字符串。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-140">The command string used to query the data source.</span></span>  <br/> |<span data-ttu-id="ef0e2-141">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="ef0e2-142">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="ef0e2-142">ConnectionString</span></span>  <br/> |<span data-ttu-id="ef0e2-143">xsd：string</span><span class="sxs-lookup"><span data-stu-id="ef0e2-143">xsd:string</span></span>  <br/> |<span data-ttu-id="ef0e2-144">可选</span><span class="sxs-lookup"><span data-stu-id="ef0e2-144">optional</span></span>  <br/> |<span data-ttu-id="ef0e2-145">定义连接到数据源所需的参数的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-145">The connection string that defines the parameters necessary to connect to a data source.</span></span>  <br/> |<span data-ttu-id="ef0e2-146">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-146">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="ef0e2-147">FileName</span><span class="sxs-lookup"><span data-stu-id="ef0e2-147">FileName</span></span>  <br/> |<span data-ttu-id="ef0e2-148">xsd：string</span><span class="sxs-lookup"><span data-stu-id="ef0e2-148">xsd:string</span></span>  <br/> |<span data-ttu-id="ef0e2-149">必需</span><span class="sxs-lookup"><span data-stu-id="ef0e2-149">required</span></span>  <br/> |<span data-ttu-id="ef0e2-150">连接文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-150">The name of the connection file.</span></span> <span data-ttu-id="ef0e2-151">有关详细信息，请参阅"说明"。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-151">See Remarks for more information.</span></span>  <br/> |<span data-ttu-id="ef0e2-152">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="ef0e2-153">FriendlyName</span><span class="sxs-lookup"><span data-stu-id="ef0e2-153">FriendlyName</span></span>  <br/> |<span data-ttu-id="ef0e2-154">xsd：string</span><span class="sxs-lookup"><span data-stu-id="ef0e2-154">xsd:string</span></span>  <br/> |<span data-ttu-id="ef0e2-155">可选</span><span class="sxs-lookup"><span data-stu-id="ef0e2-155">optional</span></span>  <br/> |<span data-ttu-id="ef0e2-156">用户为数据连接提供的名称。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-156">A user provided name for the data connection.</span></span>  <br/> |<span data-ttu-id="ef0e2-157">xsd：string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-157">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="ef0e2-158">ID</span><span class="sxs-lookup"><span data-stu-id="ef0e2-158">ID</span></span>  <br/> |<span data-ttu-id="ef0e2-159">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ef0e2-159">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="ef0e2-160">必需</span><span class="sxs-lookup"><span data-stu-id="ef0e2-160">required</span></span>  <br/> |<span data-ttu-id="ef0e2-161">由指定连接Visio的 ID，在文档中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-161">The ID assigned by Visio for a given connection, unique within the document.</span></span>  <br/> |<span data-ttu-id="ef0e2-162">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-162">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="ef0e2-163">Timeout</span><span class="sxs-lookup"><span data-stu-id="ef0e2-163">Timeout</span></span>  <br/> |<span data-ttu-id="ef0e2-164">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ef0e2-164">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="ef0e2-165">可选</span><span class="sxs-lookup"><span data-stu-id="ef0e2-165">optional</span></span>  <br/> |<span data-ttu-id="ef0e2-166">尝试在终止尝试之前建立连接的等待时间（分钟）。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-166">The wait time in minutes while trying to establish a connection before terminating the attempt.</span></span>  <br/> |<span data-ttu-id="ef0e2-167">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ef0e2-167">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

