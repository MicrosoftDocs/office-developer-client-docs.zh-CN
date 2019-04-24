---
title: ActionsRow_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 32777219-850b-9526-425f-bcb017c45093
ms.openlocfilehash: d62513877dc2c441d521b20505f5849ea31a1a4a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283000"
---
# <a name="actionsrowtype-complextype-visio-xml"></a><span data-ttu-id="e245b-102">ActionsRow_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="e245b-102">ActionsRow_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="e245b-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="e245b-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e245b-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e245b-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="e245b-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e245b-105">**Schema file**</span></span> <br/> |<span data-ttu-id="e245b-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="e245b-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="e245b-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="e245b-107">**Extension base**</span></span> <br/> |<span data-ttu-id="e245b-108">NamedIndexedRow_Type</span><span class="sxs-lookup"><span data-stu-id="e245b-108">NamedIndexedRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e245b-109">定义</span><span class="sxs-lookup"><span data-stu-id="e245b-109">Definition</span></span>

```XML
          <xs:complexType name="ActionsRow_Type">
          
          <xs:complexContent>
          <xs:extension base="NamedIndexedRow_Type">
          <xs:all>
    <xs:element name="Cell"  type="Cell_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:all>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="e245b-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e245b-110">Elements and attributes</span></span>

<span data-ttu-id="e245b-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="e245b-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="e245b-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e245b-112">Child elements</span></span>

|<span data-ttu-id="e245b-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="e245b-113">**Element**</span></span>|<span data-ttu-id="e245b-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="e245b-114">**Type**</span></span>|<span data-ttu-id="e245b-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="e245b-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e245b-116">Cell</span><span class="sxs-lookup"><span data-stu-id="e245b-116">Cell</span></span>](cell-element-actions-rowvisio-xml.md) <br/> |[<span data-ttu-id="e245b-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="e245b-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="e245b-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="e245b-118">Attributes</span></span>

<span data-ttu-id="e245b-119">无。</span><span class="sxs-lookup"><span data-stu-id="e245b-119">None.</span></span>
  

