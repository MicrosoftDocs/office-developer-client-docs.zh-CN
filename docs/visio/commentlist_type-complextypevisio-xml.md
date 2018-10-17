---
title: CommentList_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 76a41e59-d2cf-dd6a-0ac4-370c1aca4c01
ms.openlocfilehash: af23616556cecdbfa1157a8d4c49de1ca4b2fd88
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393094"
---
# <a name="commentlisttype-complextype-visio-xml"></a><span data-ttu-id="c487c-102">CommentList_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="c487c-102">CommentList_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="c487c-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="c487c-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c487c-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="c487c-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="c487c-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="c487c-105">**Schema file**</span></span> <br/> |<span data-ttu-id="c487c-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="c487c-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="c487c-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="c487c-107">**Extension base**</span></span> <br/> |<span data-ttu-id="c487c-108">无</span><span class="sxs-lookup"><span data-stu-id="c487c-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="c487c-109">定义</span><span class="sxs-lookup"><span data-stu-id="c487c-109">Definition</span></span>

```XML
          <xs:complexType name="CommentList_Type">
          
          <xs:sequence>
    <xs:element name="CommentEntry"  type="CommentEntry_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="c487c-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="c487c-110">Elements and attributes</span></span>

<span data-ttu-id="c487c-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="c487c-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="c487c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="c487c-112">Child elements</span></span>

|<span data-ttu-id="c487c-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="c487c-113">**Element**</span></span>|<span data-ttu-id="c487c-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="c487c-114">**Type**</span></span>|<span data-ttu-id="c487c-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="c487c-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="c487c-116">CommentEntry</span><span class="sxs-lookup"><span data-stu-id="c487c-116">CommentEntry</span></span>](commententry-element-commentlist_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="c487c-117">CommentEntry_Type</span><span class="sxs-lookup"><span data-stu-id="c487c-117">CommentEntry_Type</span></span>](commententry_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="c487c-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="c487c-118">Attributes</span></span>

<span data-ttu-id="c487c-119">无。</span><span class="sxs-lookup"><span data-stu-id="c487c-119">None.</span></span>
  
