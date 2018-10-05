---
title: Actions_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 31070969-2091-d00e-5dd1-b9c6034f76d9
ms.openlocfilehash: 158a0dfa31c2da3ac9e530c07edd075b4fabbd75
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389559"
---
# <a name="actionstype-complextype-visio-xml"></a><span data-ttu-id="46979-102">Actions_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="46979-102">Actions_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="46979-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="46979-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="46979-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="46979-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="46979-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="46979-105">**Schema file**</span></span> <br/> |<span data-ttu-id="46979-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="46979-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="46979-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="46979-107">**Extension base**</span></span> <br/> |<span data-ttu-id="46979-108">Section_Type</span><span class="sxs-lookup"><span data-stu-id="46979-108">Section_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="46979-109">定义</span><span class="sxs-lookup"><span data-stu-id="46979-109">Definition</span></span>

```XML
          <xs:complexType name="Actions_Type">
          
          <xs:complexContent>
          <xs:extension base="Section_Type">
          <xs:sequence minOccurs="0" maxOccurs="unbounded">
    <xs:element name="Row"  type="ActionsRow_Type"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="46979-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="46979-110">Elements and attributes</span></span>

<span data-ttu-id="46979-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="46979-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="46979-112">子元素</span><span class="sxs-lookup"><span data-stu-id="46979-112">Child elements</span></span>

|<span data-ttu-id="46979-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="46979-113">**Element**</span></span>|<span data-ttu-id="46979-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="46979-114">**Type**</span></span>|<span data-ttu-id="46979-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="46979-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="46979-116">Row</span><span class="sxs-lookup"><span data-stu-id="46979-116">Row</span></span>](row-element-actions-sectionvisio-xml.md) <br/> |[<span data-ttu-id="46979-117">ActionsRow_Type</span><span class="sxs-lookup"><span data-stu-id="46979-117">ActionsRow_Type</span></span>](actionsrow_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="46979-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="46979-118">Attributes</span></span>

<span data-ttu-id="46979-119">无。</span><span class="sxs-lookup"><span data-stu-id="46979-119">None.</span></span>
  

