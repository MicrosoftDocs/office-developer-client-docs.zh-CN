---
title: Trigger_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 50de80d5-c846-1bdc-55e0-c688fe3d364c
ms.openlocfilehash: e34ef122a6f0a08168f838fdaeb130d68349ecb8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280855"
---
# <a name="triggertype-complextype-visio-xml"></a><span data-ttu-id="24113-102">Trigger_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="24113-102">Trigger_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="24113-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="24113-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="24113-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="24113-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="24113-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="24113-105">**Schema file**</span></span> <br/> |<span data-ttu-id="24113-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="24113-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="24113-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="24113-107">**Extension base**</span></span> <br/> |<span data-ttu-id="24113-108">无</span><span class="sxs-lookup"><span data-stu-id="24113-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="24113-109">定义</span><span class="sxs-lookup"><span data-stu-id="24113-109">Definition</span></span>

```XML
          <xs:complexType name="Trigger_Type">
          
          <xs:sequence>
    <xs:element name="RefBy"  type="RefBy_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="N"
  type="xsd:string"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="24113-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="24113-110">Elements and attributes</span></span>

<span data-ttu-id="24113-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="24113-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="24113-112">子元素</span><span class="sxs-lookup"><span data-stu-id="24113-112">Child elements</span></span>

|<span data-ttu-id="24113-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="24113-113">**Element**</span></span>|<span data-ttu-id="24113-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="24113-114">**Type**</span></span>|<span data-ttu-id="24113-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="24113-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="24113-116">RefBy</span><span class="sxs-lookup"><span data-stu-id="24113-116">RefBy</span></span>](refby-element-trigger_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="24113-117">RefBy_Type</span><span class="sxs-lookup"><span data-stu-id="24113-117">RefBy_Type</span></span>](refby_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="24113-118">属性</span><span class="sxs-lookup"><span data-stu-id="24113-118">Attributes</span></span>

|<span data-ttu-id="24113-119">**属性**</span><span class="sxs-lookup"><span data-stu-id="24113-119">**Attribute**</span></span>|<span data-ttu-id="24113-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="24113-120">**Type**</span></span>|<span data-ttu-id="24113-121">**必需**</span><span class="sxs-lookup"><span data-stu-id="24113-121">**Required**</span></span>|<span data-ttu-id="24113-122">**描述**</span><span class="sxs-lookup"><span data-stu-id="24113-122">**Description**</span></span>|<span data-ttu-id="24113-123">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="24113-123">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="24113-124">N</span><span class="sxs-lookup"><span data-stu-id="24113-124">N</span></span>  <br/> |<span data-ttu-id="24113-125">xsd: string</span><span class="sxs-lookup"><span data-stu-id="24113-125">xsd:string</span></span>  <br/> |<span data-ttu-id="24113-126">必需</span><span class="sxs-lookup"><span data-stu-id="24113-126">required</span></span>  <br/> ||<span data-ttu-id="24113-127">xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="24113-127">Values of the xsd:string type.</span></span>  <br/> |
   

