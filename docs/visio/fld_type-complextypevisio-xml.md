---
title: fld_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f680eb55-2dbb-a7b9-0879-6e91576983f3
ms.openlocfilehash: c4ea016adea237258ba699c54bf05b902119eca1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780273"
---
# <a name="fldtype-complextype-visio-xml"></a><span data-ttu-id="ec7f3-102">fld_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="ec7f3-102">fld_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="ec7f3-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="ec7f3-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="ec7f3-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="ec7f3-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="ec7f3-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="ec7f3-105">**Schema file**</span></span> <br/> |<span data-ttu-id="ec7f3-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="ec7f3-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="ec7f3-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="ec7f3-107">**Extension base**</span></span> <br/> |<span data-ttu-id="ec7f3-108">xsd: string</span><span class="sxs-lookup"><span data-stu-id="ec7f3-108">xsd:string</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="ec7f3-109">定义</span><span class="sxs-lookup"><span data-stu-id="ec7f3-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="ec7f3-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="ec7f3-110">Elements and attributes</span></span>

<span data-ttu-id="ec7f3-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="ec7f3-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="ec7f3-112">子元素</span><span class="sxs-lookup"><span data-stu-id="ec7f3-112">Child elements</span></span>

<span data-ttu-id="ec7f3-113">无。</span><span class="sxs-lookup"><span data-stu-id="ec7f3-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="ec7f3-114">属性</span><span class="sxs-lookup"><span data-stu-id="ec7f3-114">Attributes</span></span>

|<span data-ttu-id="ec7f3-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="ec7f3-115">**Attribute**</span></span>|<span data-ttu-id="ec7f3-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="ec7f3-116">**Type**</span></span>|<span data-ttu-id="ec7f3-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="ec7f3-117">**Required**</span></span>|<span data-ttu-id="ec7f3-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="ec7f3-118">**Description**</span></span>|<span data-ttu-id="ec7f3-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="ec7f3-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ec7f3-120">IX</span><span class="sxs-lookup"><span data-stu-id="ec7f3-120">IX</span></span>  <br/> |<span data-ttu-id="ec7f3-121">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="ec7f3-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="ec7f3-122">必需</span><span class="sxs-lookup"><span data-stu-id="ec7f3-122">required</span></span>  <br/> ||<span data-ttu-id="ec7f3-123">Xsd:unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="ec7f3-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

