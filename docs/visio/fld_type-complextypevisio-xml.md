---
title: fld_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f680eb55-2dbb-a7b9-0879-6e91576983f3
ms.openlocfilehash: 2b1ecb21090658e1d2b042ac0f7e394d929d43c1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346205"
---
# <a name="fldtype-complextype-visio-xml"></a><span data-ttu-id="2b26d-102">fld_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="2b26d-102">fld_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="2b26d-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="2b26d-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2b26d-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2b26d-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="2b26d-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2b26d-105">**Schema file**</span></span> <br/> |<span data-ttu-id="2b26d-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="2b26d-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="2b26d-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="2b26d-107">**Extension base**</span></span> <br/> |<span data-ttu-id="2b26d-108">xsd: string</span><span class="sxs-lookup"><span data-stu-id="2b26d-108">xsd:string</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2b26d-109">定义</span><span class="sxs-lookup"><span data-stu-id="2b26d-109">Definition</span></span>

```XML
      <xs:complexType name="fld_Type">
        <xs:complexContent>
        <xs:extension base="xsd:string">
      
    <xs:attribute name="IX"
  type="xsd:unsignedInt"
     use="required"
    />
        </xs:extension>
        </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="2b26d-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2b26d-110">Elements and attributes</span></span>

<span data-ttu-id="2b26d-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="2b26d-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="2b26d-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2b26d-112">Child elements</span></span>

<span data-ttu-id="2b26d-113">无。</span><span class="sxs-lookup"><span data-stu-id="2b26d-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="2b26d-114">属性</span><span class="sxs-lookup"><span data-stu-id="2b26d-114">Attributes</span></span>

|<span data-ttu-id="2b26d-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="2b26d-115">**Attribute**</span></span>|<span data-ttu-id="2b26d-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="2b26d-116">**Type**</span></span>|<span data-ttu-id="2b26d-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="2b26d-117">**Required**</span></span>|<span data-ttu-id="2b26d-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="2b26d-118">**Description**</span></span>|<span data-ttu-id="2b26d-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="2b26d-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2b26d-120">IX</span><span class="sxs-lookup"><span data-stu-id="2b26d-120">IX</span></span>  <br/> |<span data-ttu-id="2b26d-121">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="2b26d-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="2b26d-122">必需</span><span class="sxs-lookup"><span data-stu-id="2b26d-122">required</span></span>  <br/> ||<span data-ttu-id="2b26d-123">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="2b26d-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

