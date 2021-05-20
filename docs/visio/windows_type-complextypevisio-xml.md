---
title: 'Windows_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 2e8257df-4af0-aab1-a979-df9fa8a56f20
ms.openlocfilehash: b8d8ed39637bdd692b2ba113525f40a3f91ffc9c
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538436"
---
# <a name="windows_type-complextype-visio-xml"></a><span data-ttu-id="652b5-102">Windows_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="652b5-102">Windows_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="652b5-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="652b5-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="652b5-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="652b5-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="652b5-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="652b5-105">**Schema file**</span></span> <br/> |<span data-ttu-id="652b5-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="652b5-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="652b5-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="652b5-107">**Extension base**</span></span> <br/> |<span data-ttu-id="652b5-108">无</span><span class="sxs-lookup"><span data-stu-id="652b5-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="652b5-109">定义</span><span class="sxs-lookup"><span data-stu-id="652b5-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="652b5-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="652b5-110">Elements and attributes</span></span>

<span data-ttu-id="652b5-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="652b5-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="652b5-112">子元素</span><span class="sxs-lookup"><span data-stu-id="652b5-112">Child elements</span></span>

|<span data-ttu-id="652b5-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="652b5-113">**Element**</span></span>|<span data-ttu-id="652b5-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="652b5-114">**Type**</span></span>|<span data-ttu-id="652b5-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="652b5-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="652b5-116">Window</span><span class="sxs-lookup"><span data-stu-id="652b5-116">Window</span></span>](window-element-windows_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="652b5-117">Window_Type</span><span class="sxs-lookup"><span data-stu-id="652b5-117">Window_Type</span></span>](window_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="652b5-118">属性</span><span class="sxs-lookup"><span data-stu-id="652b5-118">Attributes</span></span>

|<span data-ttu-id="652b5-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="652b5-119">**Attribute**</span></span>|<span data-ttu-id="652b5-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="652b5-120">**Type**</span></span>|<span data-ttu-id="652b5-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="652b5-121">**Required**</span></span>|<span data-ttu-id="652b5-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="652b5-122">**Description**</span></span>|<span data-ttu-id="652b5-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="652b5-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="652b5-124">ClientHeight</span><span class="sxs-lookup"><span data-stu-id="652b5-124">ClientHeight</span></span>  <br/> |<span data-ttu-id="652b5-125">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="652b5-125">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="652b5-126">可选</span><span class="sxs-lookup"><span data-stu-id="652b5-126">optional</span></span>  <br/> ||<span data-ttu-id="652b5-127">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="652b5-127">Values of the xsd:unsignedShort type.</span></span>  <br/> |
|<span data-ttu-id="652b5-128">ClientWidth</span><span class="sxs-lookup"><span data-stu-id="652b5-128">ClientWidth</span></span>  <br/> |<span data-ttu-id="652b5-129">xsd：unsignedShort</span><span class="sxs-lookup"><span data-stu-id="652b5-129">xsd:unsignedShort</span></span>  <br/> |<span data-ttu-id="652b5-130">可选</span><span class="sxs-lookup"><span data-stu-id="652b5-130">optional</span></span>  <br/> ||<span data-ttu-id="652b5-131">xsd：unsignedShort 类型的值。</span><span class="sxs-lookup"><span data-stu-id="652b5-131">Values of the xsd:unsignedShort type.</span></span>  <br/> |
   

