---
title: Text_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bc6b37c3-7f55-fe18-a9b7-884ea87b3f46
ms.openlocfilehash: 3309184c47eaf6c6a8cb20d7c6485c21c5ec8c50
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781477"
---
# <a name="texttype-complextype-visio-xml"></a><span data-ttu-id="b8e41-102">Text_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="b8e41-102">Text_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="b8e41-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="b8e41-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b8e41-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b8e41-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="b8e41-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b8e41-105">**Schema file**</span></span> <br/> |<span data-ttu-id="b8e41-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="b8e41-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="b8e41-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="b8e41-107">**Extension base**</span></span> <br/> |<span data-ttu-id="b8e41-108">无</span><span class="sxs-lookup"><span data-stu-id="b8e41-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b8e41-109">定义</span><span class="sxs-lookup"><span data-stu-id="b8e41-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="b8e41-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b8e41-110">Elements and attributes</span></span>

<span data-ttu-id="b8e41-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="b8e41-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="b8e41-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b8e41-112">Child elements</span></span>

|<span data-ttu-id="b8e41-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="b8e41-113">**Element**</span></span>|<span data-ttu-id="b8e41-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="b8e41-114">**Type**</span></span>|<span data-ttu-id="b8e41-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="b8e41-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="b8e41-116">cp</span><span class="sxs-lookup"><span data-stu-id="b8e41-116">cp</span></span>](cp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b8e41-117">cp_Type</span><span class="sxs-lookup"><span data-stu-id="b8e41-117">cp_Type</span></span>](cp_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b8e41-118">文件夹</span><span class="sxs-lookup"><span data-stu-id="b8e41-118">fld</span></span>](fld-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b8e41-119">fld_Type</span><span class="sxs-lookup"><span data-stu-id="b8e41-119">fld_Type</span></span>](fld_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b8e41-120">pp</span><span class="sxs-lookup"><span data-stu-id="b8e41-120">pp</span></span>](pp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b8e41-121">pp_Type</span><span class="sxs-lookup"><span data-stu-id="b8e41-121">pp_Type</span></span>](pp_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="b8e41-122">tp</span><span class="sxs-lookup"><span data-stu-id="b8e41-122">tp</span></span>](tp-element-text_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="b8e41-123">tp_Type</span><span class="sxs-lookup"><span data-stu-id="b8e41-123">tp_Type</span></span>](tp_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="b8e41-124">属性</span><span class="sxs-lookup"><span data-stu-id="b8e41-124">Attributes</span></span>

<span data-ttu-id="b8e41-125">无。</span><span class="sxs-lookup"><span data-stu-id="b8e41-125">None.</span></span>
  

