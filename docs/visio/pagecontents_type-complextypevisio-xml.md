---
title: PageContents_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: d611c03f-6a4f-9de2-6714-87131cddce85
ms.openlocfilehash: 70f28182d8c82b9283e793856f7944c9a4823bc0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25383427"
---
# <a name="pagecontentstype-complextype-visio-xml"></a><span data-ttu-id="3b4d8-102">PageContents_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="3b4d8-102">PageContents_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="3b4d8-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="3b4d8-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3b4d8-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="3b4d8-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="3b4d8-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="3b4d8-105">**Schema file**</span></span> <br/> |<span data-ttu-id="3b4d8-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="3b4d8-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="3b4d8-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="3b4d8-107">**Extension base**</span></span> <br/> |<span data-ttu-id="3b4d8-108">无</span><span class="sxs-lookup"><span data-stu-id="3b4d8-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="3b4d8-109">定义</span><span class="sxs-lookup"><span data-stu-id="3b4d8-109">Definition</span></span>

```XML
          <xs:complexType name="PageContents_Type">
          
          <xs:sequence>
    <xs:element name="Shapes"  type="Shapes_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
    <xs:element name="Connects"  type="Connects_Type"
     minOccurs="0"
     maxOccurs="1"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="3b4d8-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="3b4d8-110">Elements and attributes</span></span>

<span data-ttu-id="3b4d8-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="3b4d8-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="3b4d8-112">子元素</span><span class="sxs-lookup"><span data-stu-id="3b4d8-112">Child elements</span></span>

|<span data-ttu-id="3b4d8-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="3b4d8-113">**Element**</span></span>|<span data-ttu-id="3b4d8-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="3b4d8-114">**Type**</span></span>|<span data-ttu-id="3b4d8-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="3b4d8-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="3b4d8-116">Connects</span><span class="sxs-lookup"><span data-stu-id="3b4d8-116">Connects</span></span>](connects-element-pagecontents_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="3b4d8-117">Connects_Type</span><span class="sxs-lookup"><span data-stu-id="3b4d8-117">Connects_Type</span></span>](connects_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="3b4d8-118">Shapes</span><span class="sxs-lookup"><span data-stu-id="3b4d8-118">Shapes</span></span>](shapes-element-pagecontents_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="3b4d8-119">Shapes_Type</span><span class="sxs-lookup"><span data-stu-id="3b4d8-119">Shapes_Type</span></span>](shapes_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="3b4d8-120">Attributes</span><span class="sxs-lookup"><span data-stu-id="3b4d8-120">Attributes</span></span>

<span data-ttu-id="3b4d8-121">无。</span><span class="sxs-lookup"><span data-stu-id="3b4d8-121">None.</span></span>
  

