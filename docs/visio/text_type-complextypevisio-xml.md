---
title: Text_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bc6b37c3-7f55-fe18-a9b7-884ea87b3f46
ms.openlocfilehash: cfacc84cb8b38acfbda3c37c669dd9714d899098
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541377"
---
# <a name="texttype-complextype-visio-xml"></a><span data-ttu-id="1f927-102">Text_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="1f927-102">Text_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="1f927-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="1f927-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1f927-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1f927-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="1f927-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1f927-105">**Schema file**</span></span> <br/> |<span data-ttu-id="1f927-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="1f927-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="1f927-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="1f927-107">**Extension base**</span></span> <br/> |<span data-ttu-id="1f927-108">无</span><span class="sxs-lookup"><span data-stu-id="1f927-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1f927-109">定义</span><span class="sxs-lookup"><span data-stu-id="1f927-109">Definition</span></span>

```XML
          <xs:complexType name="Text_Type">
          
          <xs:choice minOccurs="0" maxOccurs="unbounded">
    <xs:element name="cp"  type="cp_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="pp"  type="pp_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="tp"  type="tp_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="fld"  type="fld_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:choice>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="1f927-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1f927-110">Elements and attributes</span></span>

<span data-ttu-id="1f927-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="1f927-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="1f927-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1f927-112">Child elements</span></span>

|<span data-ttu-id="1f927-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="1f927-113">**Element**</span></span>|<span data-ttu-id="1f927-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="1f927-114">**Type**</span></span>|<span data-ttu-id="1f927-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="1f927-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="1f927-116">cp</span><span class="sxs-lookup"><span data-stu-id="1f927-116">cp</span></span>](cp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1f927-117">cp_Type</span><span class="sxs-lookup"><span data-stu-id="1f927-117">cp_Type</span></span>](cp_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="1f927-118">.fld</span><span class="sxs-lookup"><span data-stu-id="1f927-118">fld</span></span>](fld-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1f927-119">fld_Type</span><span class="sxs-lookup"><span data-stu-id="1f927-119">fld_Type</span></span>](fld_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="1f927-120">pp</span><span class="sxs-lookup"><span data-stu-id="1f927-120">pp</span></span>](pp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1f927-121">pp_Type</span><span class="sxs-lookup"><span data-stu-id="1f927-121">pp_Type</span></span>](pp_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="1f927-122">tp</span><span class="sxs-lookup"><span data-stu-id="1f927-122">tp</span></span>](tp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="1f927-123">tp_Type</span><span class="sxs-lookup"><span data-stu-id="1f927-123">tp_Type</span></span>](tp_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="1f927-124">Attributes</span><span class="sxs-lookup"><span data-stu-id="1f927-124">Attributes</span></span>

<span data-ttu-id="1f927-125">无。</span><span class="sxs-lookup"><span data-stu-id="1f927-125">None.</span></span>
  

