---
title: DataConnections_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 83a3c944-9582-bf80-ec2a-7a752da03cd3
ms.openlocfilehash: 2bbea48e1d5340c5a68bbafbef9a900a98357385
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397385"
---
# <a name="dataconnectionstype-complextype-visio-xml"></a><span data-ttu-id="92306-102">DataConnections_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="92306-102">DataConnections_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="92306-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="92306-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="92306-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="92306-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="92306-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="92306-105">**Schema file**</span></span> <br/> |<span data-ttu-id="92306-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="92306-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="92306-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="92306-107">**Extension base**</span></span> <br/> |<span data-ttu-id="92306-108">无</span><span class="sxs-lookup"><span data-stu-id="92306-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="92306-109">定义</span><span class="sxs-lookup"><span data-stu-id="92306-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="92306-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="92306-110">Elements and attributes</span></span>

<span data-ttu-id="92306-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="92306-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="92306-112">子元素</span><span class="sxs-lookup"><span data-stu-id="92306-112">Child elements</span></span>

|<span data-ttu-id="92306-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="92306-113">**Element**</span></span>|<span data-ttu-id="92306-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="92306-114">**Type**</span></span>|<span data-ttu-id="92306-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="92306-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="92306-116">DataConnection</span><span class="sxs-lookup"><span data-stu-id="92306-116">DataConnection</span></span>](dataconnection-element-dataconnections_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="92306-117">DataConnection_Type</span><span class="sxs-lookup"><span data-stu-id="92306-117">DataConnection_Type</span></span>](dataconnection_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="92306-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="92306-118">Attributes</span></span>

|<span data-ttu-id="92306-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="92306-119">**Attribute**</span></span>|<span data-ttu-id="92306-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="92306-120">**Type**</span></span>|<span data-ttu-id="92306-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="92306-121">**Required**</span></span>|<span data-ttu-id="92306-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="92306-122">**Description**</span></span>|<span data-ttu-id="92306-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="92306-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="92306-124">NextID</span><span class="sxs-lookup"><span data-stu-id="92306-124">NextID</span></span>  <br/> |<span data-ttu-id="92306-125">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="92306-125">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="92306-126">必需</span><span class="sxs-lookup"><span data-stu-id="92306-126">required</span></span>  <br/> ||<span data-ttu-id="92306-127">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="92306-127">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

