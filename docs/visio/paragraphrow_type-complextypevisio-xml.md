---
title: ParagraphRow_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 32bb67e1-8db8-fe28-f173-028a20bb136c
ms.openlocfilehash: 64001e12b3e65e3259c3ebe381b2825fb80ad7b0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25390686"
---
# <a name="paragraphrowtype-complextype-visio-xml"></a><span data-ttu-id="65b07-102">ParagraphRow_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="65b07-102">ParagraphRow_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="65b07-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="65b07-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="65b07-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="65b07-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="65b07-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="65b07-105">**Schema file**</span></span> <br/> |<span data-ttu-id="65b07-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="65b07-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="65b07-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="65b07-107">**Extension base**</span></span> <br/> |<span data-ttu-id="65b07-108">IndexedRow_Type</span><span class="sxs-lookup"><span data-stu-id="65b07-108">IndexedRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="65b07-109">定义</span><span class="sxs-lookup"><span data-stu-id="65b07-109">Definition</span></span>

```XML
          <xs:complexType name="ParagraphRow_Type">
          
          <xs:complexContent>
          <xs:extension base="IndexedRow_Type">
          <xs:sequence>
    <xs:element name="Cell"  type="Cell_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="65b07-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="65b07-110">Elements and attributes</span></span>

<span data-ttu-id="65b07-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="65b07-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="65b07-112">子元素</span><span class="sxs-lookup"><span data-stu-id="65b07-112">Child elements</span></span>

|<span data-ttu-id="65b07-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="65b07-113">**Element**</span></span>|<span data-ttu-id="65b07-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="65b07-114">**Type**</span></span>|<span data-ttu-id="65b07-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="65b07-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="65b07-116">Cell</span><span class="sxs-lookup"><span data-stu-id="65b07-116">Cell</span></span>](cell-element-paragraph-sectionvisio-xml.md) <br/> |[<span data-ttu-id="65b07-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="65b07-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="65b07-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="65b07-118">Attributes</span></span>

<span data-ttu-id="65b07-119">无。</span><span class="sxs-lookup"><span data-stu-id="65b07-119">None.</span></span>
  

