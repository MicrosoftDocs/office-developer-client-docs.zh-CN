---
title: ActionTag_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1bcc17e7-d59d-d392-f299-78d7665202fc
ms.openlocfilehash: e5061e4a4e6e51437ba53ec01f1bfcc33a17d6ed
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779621"
---
# <a name="actiontagtype-complextype-visio-xml"></a><span data-ttu-id="e25d4-102">ActionTag_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="e25d4-102">ActionTag_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="e25d4-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="e25d4-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e25d4-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e25d4-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="e25d4-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e25d4-105">**Schema file**</span></span> <br/> |<span data-ttu-id="e25d4-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="e25d4-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="e25d4-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="e25d4-107">**Extension base**</span></span> <br/> |<span data-ttu-id="e25d4-108">Section_Type</span><span class="sxs-lookup"><span data-stu-id="e25d4-108">Section_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e25d4-109">定义</span><span class="sxs-lookup"><span data-stu-id="e25d4-109">Definition</span></span>

```XML
          <xs:complexType name="ActionTag_Type">
          
          <xs:complexContent>
          <xs:extension base="Section_Type">
          <xs:sequence minOccurs="0" maxOccurs="unbounded">
    <xs:element name="Row"  type="ActionTagRow_Type"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e25d4-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e25d4-110">Elements and attributes</span></span>

<span data-ttu-id="e25d4-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="e25d4-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="e25d4-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e25d4-112">Child elements</span></span>

|<span data-ttu-id="e25d4-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="e25d4-113">**Element**</span></span>|<span data-ttu-id="e25d4-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="e25d4-114">**Type**</span></span>|<span data-ttu-id="e25d4-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="e25d4-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e25d4-116">Row</span><span class="sxs-lookup"><span data-stu-id="e25d4-116">Row</span></span>](row-element-action-tag-sectionvisio-xml.md) <br/> |[<span data-ttu-id="e25d4-117">ActionTagRow_Type</span><span class="sxs-lookup"><span data-stu-id="e25d4-117">ActionTagRow_Type</span></span>](actiontagrow_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="e25d4-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="e25d4-118">Attributes</span></span>

<span data-ttu-id="e25d4-119">无。</span><span class="sxs-lookup"><span data-stu-id="e25d4-119">None.</span></span>
  

