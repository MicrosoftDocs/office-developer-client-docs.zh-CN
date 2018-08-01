---
title: EventList_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0e7a6e5e-5ce4-1e21-c1e8-dafd22bd367f
ms.openlocfilehash: 7bbb8d1074d869a9171a188118c920260b3a903d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780204"
---
# <a name="eventlisttype-complextype-visio-xml"></a><span data-ttu-id="2a544-102">EventList_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="2a544-102">EventList_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="2a544-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="2a544-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2a544-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2a544-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="2a544-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2a544-105">**Schema file**</span></span> <br/> |<span data-ttu-id="2a544-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="2a544-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="2a544-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="2a544-107">**Extension base**</span></span> <br/> |<span data-ttu-id="2a544-108">无</span><span class="sxs-lookup"><span data-stu-id="2a544-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2a544-109">定义</span><span class="sxs-lookup"><span data-stu-id="2a544-109">Definition</span></span>

```XML
          <xs:complexType name="EventList_Type">
          
          <xs:sequence>
    <xs:element name="EventItem"  type="EventItem_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="2a544-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2a544-110">Elements and attributes</span></span>

<span data-ttu-id="2a544-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="2a544-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="2a544-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2a544-112">Child elements</span></span>

|<span data-ttu-id="2a544-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="2a544-113">**Element**</span></span>|<span data-ttu-id="2a544-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="2a544-114">**Type**</span></span>|<span data-ttu-id="2a544-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a544-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2a544-116">EventItem</span><span class="sxs-lookup"><span data-stu-id="2a544-116">EventItem</span></span>](eventitem-element-eventlist_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2a544-117">EventItem_Type</span><span class="sxs-lookup"><span data-stu-id="2a544-117">EventItem_Type</span></span>](eventitem_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="2a544-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="2a544-118">Attributes</span></span>

<span data-ttu-id="2a544-119">无。</span><span class="sxs-lookup"><span data-stu-id="2a544-119">None.</span></span>
  

