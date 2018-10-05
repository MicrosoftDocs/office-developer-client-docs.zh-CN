---
title: Pages_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 13508e59-e29a-ca70-676b-c5b23ca8e3d0
ms.openlocfilehash: a03c5df25a28da40724178cf1c7f917ee4e723c5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400157"
---
# <a name="pagestype-complextype-visio-xml"></a><span data-ttu-id="8e773-102">Pages_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="8e773-102">Pages_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="8e773-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="8e773-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8e773-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="8e773-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="8e773-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="8e773-105">**Schema file**</span></span> <br/> |<span data-ttu-id="8e773-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="8e773-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="8e773-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="8e773-107">**Extension base**</span></span> <br/> |<span data-ttu-id="8e773-108">无</span><span class="sxs-lookup"><span data-stu-id="8e773-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="8e773-109">定义</span><span class="sxs-lookup"><span data-stu-id="8e773-109">Definition</span></span>

```XML
          <xs:complexType name="Pages_Type">
          
          <xs:sequence>
    <xs:element name="Page"  type="Page_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="8e773-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="8e773-110">Elements and attributes</span></span>

<span data-ttu-id="8e773-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="8e773-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="8e773-112">子元素</span><span class="sxs-lookup"><span data-stu-id="8e773-112">Child elements</span></span>

|<span data-ttu-id="8e773-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="8e773-113">**Element**</span></span>|<span data-ttu-id="8e773-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="8e773-114">**Type**</span></span>|<span data-ttu-id="8e773-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="8e773-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8e773-116">网页</span><span class="sxs-lookup"><span data-stu-id="8e773-116">Page</span></span>](page-element-pages_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="8e773-117">Page_Type</span><span class="sxs-lookup"><span data-stu-id="8e773-117">Page_Type</span></span>](page_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="8e773-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="8e773-118">Attributes</span></span>

<span data-ttu-id="8e773-119">无。</span><span class="sxs-lookup"><span data-stu-id="8e773-119">None.</span></span>
  

