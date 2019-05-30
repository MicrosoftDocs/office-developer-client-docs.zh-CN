---
title: DataConnections_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 83a3c944-9582-bf80-ec2a-7a752da03cd3
ms.openlocfilehash: 712632a74b0ffad6d0c9ca8745d67018518d87de
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542455"
---
# <a name="dataconnectionstype-complextype-visio-xml"></a><span data-ttu-id="8dc38-102">DataConnections_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="8dc38-102">DataConnections_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="8dc38-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="8dc38-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8dc38-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="8dc38-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="8dc38-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="8dc38-105">**Schema file**</span></span> <br/> |<span data-ttu-id="8dc38-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="8dc38-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="8dc38-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="8dc38-107">**Extension base**</span></span> <br/> |<span data-ttu-id="8dc38-108">无</span><span class="sxs-lookup"><span data-stu-id="8dc38-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="8dc38-109">定义</span><span class="sxs-lookup"><span data-stu-id="8dc38-109">Definition</span></span>

```XML
          <xs:complexType name="DataConnections_Type">
          
          <xs:sequence>
    <xs:element name="DataConnection"  type="DataConnection_Type"
     minOccurs="1"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="NextID"
  type="xsd:unsignedInt"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="8dc38-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="8dc38-110">Elements and attributes</span></span>

<span data-ttu-id="8dc38-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="8dc38-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="8dc38-112">子元素</span><span class="sxs-lookup"><span data-stu-id="8dc38-112">Child elements</span></span>

|<span data-ttu-id="8dc38-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="8dc38-113">**Element**</span></span>|<span data-ttu-id="8dc38-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="8dc38-114">**Type**</span></span>|<span data-ttu-id="8dc38-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="8dc38-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8dc38-116">DataConnection</span><span class="sxs-lookup"><span data-stu-id="8dc38-116">DataConnection</span></span>](dataconnection-element-dataconnections_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="8dc38-117">DataConnection_Type</span><span class="sxs-lookup"><span data-stu-id="8dc38-117">DataConnection_Type</span></span>](dataconnection_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="8dc38-118">属性</span><span class="sxs-lookup"><span data-stu-id="8dc38-118">Attributes</span></span>

|<span data-ttu-id="8dc38-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="8dc38-119">**Attribute**</span></span>|<span data-ttu-id="8dc38-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="8dc38-120">**Type**</span></span>|<span data-ttu-id="8dc38-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="8dc38-121">**Required**</span></span>|<span data-ttu-id="8dc38-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="8dc38-122">**Description**</span></span>|<span data-ttu-id="8dc38-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="8dc38-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8dc38-124">NextID</span><span class="sxs-lookup"><span data-stu-id="8dc38-124">NextID</span></span>  <br/> |<span data-ttu-id="8dc38-125">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="8dc38-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="8dc38-126">必需</span><span class="sxs-lookup"><span data-stu-id="8dc38-126">required</span></span>  <br/> ||<span data-ttu-id="8dc38-127">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="8dc38-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

