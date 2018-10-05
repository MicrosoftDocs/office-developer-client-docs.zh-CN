---
title: Windows_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2e8257df-4af0-aab1-a979-df9fa8a56f20
ms.openlocfilehash: 5aeffa7b78c4c402d03b6a2774a2df8b339e03e7
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386556"
---
# <a name="windowstype-complextype-visio-xml"></a><span data-ttu-id="f480d-102">Windows_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="f480d-102">Windows_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="f480d-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="f480d-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f480d-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f480d-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="f480d-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f480d-105">**Schema file**</span></span> <br/> |<span data-ttu-id="f480d-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="f480d-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="f480d-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="f480d-107">**Extension base**</span></span> <br/> |<span data-ttu-id="f480d-108">无</span><span class="sxs-lookup"><span data-stu-id="f480d-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f480d-109">定义</span><span class="sxs-lookup"><span data-stu-id="f480d-109">Definition</span></span>

```XML
          <xs:complexType name="Windows_Type">
          
          <xs:sequence>
    <xs:element name="Window"  type="Window_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="ClientWidth"
  type="xsd:unsignedShort"
    />
    <xs:attribute name="ClientHeight"
  type="xsd:unsignedShort"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f480d-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f480d-110">Elements and attributes</span></span>

<span data-ttu-id="f480d-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="f480d-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="f480d-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f480d-112">Child elements</span></span>

|<span data-ttu-id="f480d-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="f480d-113">**Element**</span></span>|<span data-ttu-id="f480d-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="f480d-114">**Type**</span></span>|<span data-ttu-id="f480d-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="f480d-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f480d-116">Window</span><span class="sxs-lookup"><span data-stu-id="f480d-116">Window</span></span>](window-element-windows_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f480d-117">Window_Type</span><span class="sxs-lookup"><span data-stu-id="f480d-117">Window_Type</span></span>](window_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="f480d-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="f480d-118">Attributes</span></span>

|<span data-ttu-id="f480d-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="f480d-119">**Attribute**</span></span>|<span data-ttu-id="f480d-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="f480d-120">**Type**</span></span>|<span data-ttu-id="f480d-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="f480d-121">**Required**</span></span>|<span data-ttu-id="f480d-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="f480d-122">**Description**</span></span>|<span data-ttu-id="f480d-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="f480d-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f480d-124">ClientHeight</span><span class="sxs-lookup"><span data-stu-id="f480d-124">ClientHeight</span></span>  <br/> |<span data-ttu-id="f480d-125">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="f480d-125">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="f480d-126">可选</span><span class="sxs-lookup"><span data-stu-id="f480d-126">optional</span></span>  <br/> ||<span data-ttu-id="f480d-127">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f480d-127">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="f480d-128">ClientWidth</span><span class="sxs-lookup"><span data-stu-id="f480d-128">ClientWidth</span></span>  <br/> |<span data-ttu-id="f480d-129">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="f480d-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="f480d-130">可选</span><span class="sxs-lookup"><span data-stu-id="f480d-130">optional</span></span>  <br/> ||<span data-ttu-id="f480d-131">Xsd:unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="f480d-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
   

