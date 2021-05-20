---
title: 'EventList_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0e7a6e5e-5ce4-1e21-c1e8-dafd22bd367f
ms.openlocfilehash: bcee61ba9347dc77dd704d0221a9362843bf9858
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540761"
---
# <a name="eventlist_type-complextype-visio-xml"></a><span data-ttu-id="03f3f-102">EventList_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="03f3f-102">EventList_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="03f3f-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="03f3f-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="03f3f-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="03f3f-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="03f3f-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="03f3f-105">**Schema file**</span></span> <br/> |<span data-ttu-id="03f3f-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="03f3f-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="03f3f-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="03f3f-107">**Extension base**</span></span> <br/> |<span data-ttu-id="03f3f-108">无</span><span class="sxs-lookup"><span data-stu-id="03f3f-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="03f3f-109">定义</span><span class="sxs-lookup"><span data-stu-id="03f3f-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="03f3f-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="03f3f-110">Elements and attributes</span></span>

<span data-ttu-id="03f3f-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="03f3f-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="03f3f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="03f3f-112">Child elements</span></span>

|<span data-ttu-id="03f3f-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="03f3f-113">**Element**</span></span>|<span data-ttu-id="03f3f-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="03f3f-114">**Type**</span></span>|<span data-ttu-id="03f3f-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="03f3f-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="03f3f-116">EventItem</span><span class="sxs-lookup"><span data-stu-id="03f3f-116">EventItem</span></span>](eventitem-element-eventlist_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="03f3f-117">EventItem_Type</span><span class="sxs-lookup"><span data-stu-id="03f3f-117">EventItem_Type</span></span>](eventitem_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="03f3f-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="03f3f-118">Attributes</span></span>

<span data-ttu-id="03f3f-119">无。</span><span class="sxs-lookup"><span data-stu-id="03f3f-119">None.</span></span>
  

