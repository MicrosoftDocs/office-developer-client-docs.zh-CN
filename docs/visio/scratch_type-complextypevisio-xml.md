---
title: 'Scratch_Type复杂类型 (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1e3dd8c8-e84c-61ff-bfff-57d97545e441
ms.openlocfilehash: 434565cafe7d4345f3da7727760b21bfc186ee96
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539052"
---
# <a name="scratch_type-complextype-visio-xml"></a><span data-ttu-id="128e8-102">Scratch_Type复杂类型 (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="128e8-102">Scratch_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="128e8-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="128e8-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="128e8-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="128e8-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="128e8-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="128e8-105">**Schema file**</span></span> <br/> |<span data-ttu-id="128e8-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="128e8-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="128e8-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="128e8-107">**Extension base**</span></span> <br/> |<span data-ttu-id="128e8-108">Section_Type</span><span class="sxs-lookup"><span data-stu-id="128e8-108">Section_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="128e8-109">定义</span><span class="sxs-lookup"><span data-stu-id="128e8-109">Definition</span></span>

```XML
          <xs:complexType name="Scratch_Type">
          
          <xs:complexContent>
          <xs:extension base="Section_Type">
          <xs:sequence minOccurs="0" maxOccurs="unbounded">
    <xs:element name="Row"  type="ScratchRow_Type"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="128e8-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="128e8-110">Elements and attributes</span></span>

<span data-ttu-id="128e8-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="128e8-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="128e8-112">子元素</span><span class="sxs-lookup"><span data-stu-id="128e8-112">Child elements</span></span>

|<span data-ttu-id="128e8-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="128e8-113">**Element**</span></span>|<span data-ttu-id="128e8-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="128e8-114">**Type**</span></span>|<span data-ttu-id="128e8-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="128e8-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="128e8-116">Row</span><span class="sxs-lookup"><span data-stu-id="128e8-116">Row</span></span>](row-element-scratch-sectionvisio-xml.md) <br/> |[<span data-ttu-id="128e8-117">ScratchRow_Type</span><span class="sxs-lookup"><span data-stu-id="128e8-117">ScratchRow_Type</span></span>](scratchrow_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="128e8-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="128e8-118">Attributes</span></span>

<span data-ttu-id="128e8-119">无。</span><span class="sxs-lookup"><span data-stu-id="128e8-119">None.</span></span>
  

