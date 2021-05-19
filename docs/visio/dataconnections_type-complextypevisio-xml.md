---
title: 'DataConnections_Type XML (Visio complexType) '
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
# <a name="dataconnections_type-complextype-visio-xml"></a><span data-ttu-id="5290f-102">DataConnections_Type XML (Visio complexType) </span><span class="sxs-lookup"><span data-stu-id="5290f-102">DataConnections_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="5290f-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="5290f-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5290f-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="5290f-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="5290f-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="5290f-105">**Schema file**</span></span> <br/> |<span data-ttu-id="5290f-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="5290f-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="5290f-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="5290f-107">**Extension base**</span></span> <br/> |<span data-ttu-id="5290f-108">无</span><span class="sxs-lookup"><span data-stu-id="5290f-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="5290f-109">定义</span><span class="sxs-lookup"><span data-stu-id="5290f-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="5290f-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="5290f-110">Elements and attributes</span></span>

<span data-ttu-id="5290f-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="5290f-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="5290f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5290f-112">Child elements</span></span>

|<span data-ttu-id="5290f-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="5290f-113">**Element**</span></span>|<span data-ttu-id="5290f-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="5290f-114">**Type**</span></span>|<span data-ttu-id="5290f-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="5290f-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="5290f-116">DataConnection</span><span class="sxs-lookup"><span data-stu-id="5290f-116">DataConnection</span></span>](dataconnection-element-dataconnections_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="5290f-117">DataConnection_Type</span><span class="sxs-lookup"><span data-stu-id="5290f-117">DataConnection_Type</span></span>](dataconnection_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="5290f-118">属性</span><span class="sxs-lookup"><span data-stu-id="5290f-118">Attributes</span></span>

|<span data-ttu-id="5290f-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="5290f-119">**Attribute**</span></span>|<span data-ttu-id="5290f-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="5290f-120">**Type**</span></span>|<span data-ttu-id="5290f-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="5290f-121">**Required**</span></span>|<span data-ttu-id="5290f-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="5290f-122">**Description**</span></span>|<span data-ttu-id="5290f-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="5290f-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5290f-124">NextID</span><span class="sxs-lookup"><span data-stu-id="5290f-124">NextID</span></span>  <br/> |<span data-ttu-id="5290f-125">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="5290f-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="5290f-126">必需</span><span class="sxs-lookup"><span data-stu-id="5290f-126">required</span></span>  <br/> ||<span data-ttu-id="5290f-127">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="5290f-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

