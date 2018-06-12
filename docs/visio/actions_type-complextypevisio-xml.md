---
title: Actions_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 31070969-2091-d00e-5dd1-b9c6034f76d9
ms.openlocfilehash: e28b80e64865196fd6ba13035385b9523f6b1bc5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779628"
---
# <a name="actionstype-complextype-visio-xml"></a><span data-ttu-id="15e6f-102">Actions_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="15e6f-102">Actions_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="15e6f-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="15e6f-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="15e6f-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="15e6f-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="15e6f-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="15e6f-105">**Schema file**</span></span> <br/> |<span data-ttu-id="15e6f-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="15e6f-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="15e6f-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="15e6f-107">**Extension base**</span></span> <br/> |<span data-ttu-id="15e6f-108">Section_Type</span><span class="sxs-lookup"><span data-stu-id="15e6f-108">Section_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="15e6f-109">定义</span><span class="sxs-lookup"><span data-stu-id="15e6f-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="15e6f-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="15e6f-110">Elements and attributes</span></span>

<span data-ttu-id="15e6f-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="15e6f-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="15e6f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="15e6f-112">Child elements</span></span>

|<span data-ttu-id="15e6f-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="15e6f-113">**Element**</span></span>|<span data-ttu-id="15e6f-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="15e6f-114">**Type**</span></span>|<span data-ttu-id="15e6f-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="15e6f-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="15e6f-116">Row</span><span class="sxs-lookup"><span data-stu-id="15e6f-116">Row</span></span>](row-element-actions-sectionvisio-xml.md) <br/> |[<span data-ttu-id="15e6f-117">ActionsRow_Type</span><span class="sxs-lookup"><span data-stu-id="15e6f-117">ActionsRow_Type</span></span>](actionsrow_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="15e6f-118">属性</span><span class="sxs-lookup"><span data-stu-id="15e6f-118">Attributes</span></span>

<span data-ttu-id="15e6f-119">无。</span><span class="sxs-lookup"><span data-stu-id="15e6f-119">None.</span></span>
  

