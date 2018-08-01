---
title: AuthorList_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fc1e059b-7705-8b30-aeab-f56707086416
ms.openlocfilehash: e4cee87a5060580e8b7f1efc7970091d56fd310f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779640"
---
# <a name="authorlisttype-complextype-visio-xml"></a><span data-ttu-id="89011-102">AuthorList_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="89011-102">AuthorList_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="89011-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="89011-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="89011-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="89011-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="89011-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="89011-105">**Schema file**</span></span> <br/> |<span data-ttu-id="89011-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="89011-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="89011-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="89011-107">**Extension base**</span></span> <br/> |<span data-ttu-id="89011-108">无</span><span class="sxs-lookup"><span data-stu-id="89011-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="89011-109">定义</span><span class="sxs-lookup"><span data-stu-id="89011-109">Definition</span></span>

```XML
          <xs:complexType name="AuthorList_Type">
          
          <xs:sequence>
    <xs:element name="AuthorEntry"  type="AuthorEntry_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="89011-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="89011-110">Elements and attributes</span></span>

<span data-ttu-id="89011-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="89011-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="89011-112">子元素</span><span class="sxs-lookup"><span data-stu-id="89011-112">Child elements</span></span>

|<span data-ttu-id="89011-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="89011-113">**Element**</span></span>|<span data-ttu-id="89011-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="89011-114">**Type**</span></span>|<span data-ttu-id="89011-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="89011-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="89011-116">AuthorEntry</span><span class="sxs-lookup"><span data-stu-id="89011-116">AuthorEntry</span></span>](authorentry-element-authorlist_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="89011-117">AuthorEntry_Type</span><span class="sxs-lookup"><span data-stu-id="89011-117">AuthorEntry_Type</span></span>](authorentry_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="89011-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="89011-118">Attributes</span></span>

<span data-ttu-id="89011-119">无。</span><span class="sxs-lookup"><span data-stu-id="89011-119">None.</span></span>
  

