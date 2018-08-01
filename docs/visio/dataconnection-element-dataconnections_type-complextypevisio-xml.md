---
title: DataConnection 元素 （DataConnections_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 6aab8be3-b236-029b-1df3-b6860d4f4586
description: 使一个或多个 DataRecordset 元素和与非 XML 数据源之间的通信抽象化。
ms.openlocfilehash: 74e15795e023517263d9b79e9f19557653e4e939
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780043"
---
# <a name="dataconnection-element-dataconnectionstype-complextype-visio-xml"></a><span data-ttu-id="40ca5-103">DataConnection 元素 （DataConnections_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="40ca5-103">DataConnection element (DataConnections_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="40ca5-104">使一个或多个**DataRecordset**元素和与非 XML 数据源之间的通信抽象化。</span><span class="sxs-lookup"><span data-stu-id="40ca5-104">Abstracts communication between one or more **DataRecordset** elements and a non-XML data source.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="40ca5-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="40ca5-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="40ca5-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="40ca5-106">**Element type**</span></span> <br/> |[<span data-ttu-id="40ca5-107">DataConnection_Type</span><span class="sxs-lookup"><span data-stu-id="40ca5-107">DataConnection_Type</span></span>](dataconnection_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="40ca5-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="40ca5-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="40ca5-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="40ca5-109">**Schema file**</span></span> <br/> |<span data-ttu-id="40ca5-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="40ca5-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="40ca5-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="40ca5-111">**Document parts**</span></span> <br/> |<span data-ttu-id="40ca5-112">connections.xml</span><span class="sxs-lookup"><span data-stu-id="40ca5-112">connections.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="40ca5-113">定义</span><span class="sxs-lookup"><span data-stu-id="40ca5-113">Definition</span></span>

```XML
< xs:element name="DataConnection" type="DataConnection_Type" minOccurs="1" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="40ca5-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="40ca5-114">Elements and attributes</span></span>

<span data-ttu-id="40ca5-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="40ca5-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="40ca5-116">父元素</span><span class="sxs-lookup"><span data-stu-id="40ca5-116">Parent elements</span></span>

|<span data-ttu-id="40ca5-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="40ca5-117">**Element**</span></span>|<span data-ttu-id="40ca5-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="40ca5-118">**Type**</span></span>|<span data-ttu-id="40ca5-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="40ca5-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="40ca5-120">DataConnections</span><span class="sxs-lookup"><span data-stu-id="40ca5-120">DataConnections</span></span>](dataconnections-elementvisio-xml.md) <br/> |[<span data-ttu-id="40ca5-121">DataConnections_Type</span><span class="sxs-lookup"><span data-stu-id="40ca5-121">DataConnections_Type</span></span>](dataconnections_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="40ca5-122">包含文档的**DataConnection**元素。</span><span class="sxs-lookup"><span data-stu-id="40ca5-122">Contains the **DataConnection** elements for the document.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="40ca5-123">子元素</span><span class="sxs-lookup"><span data-stu-id="40ca5-123">Child elements</span></span>

<span data-ttu-id="40ca5-124">无。</span><span class="sxs-lookup"><span data-stu-id="40ca5-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="40ca5-125">属性</span><span class="sxs-lookup"><span data-stu-id="40ca5-125">Attributes</span></span>

|<span data-ttu-id="40ca5-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="40ca5-126">**Attribute**</span></span>|<span data-ttu-id="40ca5-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="40ca5-127">**Type**</span></span>|<span data-ttu-id="40ca5-128">**必需**</span><span class="sxs-lookup"><span data-stu-id="40ca5-128">**Required**</span></span>|<span data-ttu-id="40ca5-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="40ca5-129">**Description**</span></span>|<span data-ttu-id="40ca5-130">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="40ca5-130">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="40ca5-131">AlwaysUseConnectionFile</span><span class="sxs-lookup"><span data-stu-id="40ca5-131">AlwaysUseConnectionFile</span></span>  <br/> |<span data-ttu-id="40ca5-132">化</span><span class="sxs-lookup"><span data-stu-id="40ca5-132">xsd:boolean</span></span>  <br/> |<span data-ttu-id="40ca5-133">可选</span><span class="sxs-lookup"><span data-stu-id="40ca5-133">optional</span></span>  <br/> |<span data-ttu-id="40ca5-134">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="40ca5-134">The default value is false.</span></span> <span data-ttu-id="40ca5-135">有关详细信息，请参阅"说明"。</span><span class="sxs-lookup"><span data-stu-id="40ca5-135">See Remarks for more information.</span></span>  <br/> |<span data-ttu-id="40ca5-136">化类型的值。</span><span class="sxs-lookup"><span data-stu-id="40ca5-136">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="40ca5-137">命令</span><span class="sxs-lookup"><span data-stu-id="40ca5-137">Command</span></span>  <br/> |<span data-ttu-id="40ca5-138">xsd: string</span><span class="sxs-lookup"><span data-stu-id="40ca5-138">xsd:string</span></span>  <br/> |<span data-ttu-id="40ca5-139">可选</span><span class="sxs-lookup"><span data-stu-id="40ca5-139">optional</span></span>  <br/> |<span data-ttu-id="40ca5-140">用于查询数据源的命令字符串。</span><span class="sxs-lookup"><span data-stu-id="40ca5-140">The command string used to query the data source.</span></span>  <br/> |<span data-ttu-id="40ca5-141">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="40ca5-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="40ca5-142">ConnectionString</span><span class="sxs-lookup"><span data-stu-id="40ca5-142">ConnectionString</span></span>  <br/> |<span data-ttu-id="40ca5-143">xsd: string</span><span class="sxs-lookup"><span data-stu-id="40ca5-143">xsd:string</span></span>  <br/> |<span data-ttu-id="40ca5-144">可选</span><span class="sxs-lookup"><span data-stu-id="40ca5-144">optional</span></span>  <br/> |<span data-ttu-id="40ca5-145">用于定义连接到数据源所需的参数的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="40ca5-145">The connection string that defines the parameters necessary to connect to a data source.</span></span>  <br/> |<span data-ttu-id="40ca5-146">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="40ca5-146">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="40ca5-147">FileName</span><span class="sxs-lookup"><span data-stu-id="40ca5-147">FileName</span></span>  <br/> |<span data-ttu-id="40ca5-148">xsd: string</span><span class="sxs-lookup"><span data-stu-id="40ca5-148">xsd:string</span></span>  <br/> |<span data-ttu-id="40ca5-149">必需</span><span class="sxs-lookup"><span data-stu-id="40ca5-149">required</span></span>  <br/> |<span data-ttu-id="40ca5-150">连接文件的名称。</span><span class="sxs-lookup"><span data-stu-id="40ca5-150">The name of the connection file.</span></span> <span data-ttu-id="40ca5-151">有关详细信息，请参阅"说明"。</span><span class="sxs-lookup"><span data-stu-id="40ca5-151">See Remarks for more information.</span></span>  <br/> |<span data-ttu-id="40ca5-152">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="40ca5-152">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="40ca5-153">FriendlyName</span><span class="sxs-lookup"><span data-stu-id="40ca5-153">FriendlyName</span></span>  <br/> |<span data-ttu-id="40ca5-154">xsd: string</span><span class="sxs-lookup"><span data-stu-id="40ca5-154">xsd:string</span></span>  <br/> |<span data-ttu-id="40ca5-155">可选</span><span class="sxs-lookup"><span data-stu-id="40ca5-155">optional</span></span>  <br/> |<span data-ttu-id="40ca5-156">数据连接的用户提供的名称。</span><span class="sxs-lookup"><span data-stu-id="40ca5-156">A user provided name for the data connection.</span></span>  <br/> |<span data-ttu-id="40ca5-157">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="40ca5-157">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="40ca5-158">ID</span><span class="sxs-lookup"><span data-stu-id="40ca5-158">ID</span></span>  <br/> |<span data-ttu-id="40ca5-159">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="40ca5-159">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="40ca5-160">必需</span><span class="sxs-lookup"><span data-stu-id="40ca5-160">required</span></span>  <br/> |<span data-ttu-id="40ca5-161">由 Visio 分配对于给定的连接，唯一的文档中的 ID。</span><span class="sxs-lookup"><span data-stu-id="40ca5-161">The ID assigned by Visio for a given connection, unique within the document.</span></span>  <br/> |<span data-ttu-id="40ca5-162">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="40ca5-162">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="40ca5-163">Timeout</span><span class="sxs-lookup"><span data-stu-id="40ca5-163">Timeout</span></span>  <br/> |<span data-ttu-id="40ca5-164">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="40ca5-164">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="40ca5-165">可选</span><span class="sxs-lookup"><span data-stu-id="40ca5-165">optional</span></span>  <br/> |<span data-ttu-id="40ca5-166">以分钟为单位试图建立在终止尝试之前等待时间。</span><span class="sxs-lookup"><span data-stu-id="40ca5-166">The wait time in minutes while trying to establish a connection before terminating the attempt.</span></span>  <br/> |<span data-ttu-id="40ca5-167">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="40ca5-167">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

