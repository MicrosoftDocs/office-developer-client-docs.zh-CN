---
title: RowDef_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 64897258-dd7e-a730-d4f5-d9c217308491
ms.openlocfilehash: 4d751df50d4239263947a917cb16f2305cb06170
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781166"
---
# <a name="rowdeftype-complextype-visio-xml"></a><span data-ttu-id="40c1f-102">RowDef_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="40c1f-102">RowDef_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="40c1f-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="40c1f-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="40c1f-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="40c1f-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="40c1f-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="40c1f-105">**Schema file**</span></span> <br/> |<span data-ttu-id="40c1f-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="40c1f-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="40c1f-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="40c1f-107">**Extension base**</span></span> <br/> |<span data-ttu-id="40c1f-108">无</span><span class="sxs-lookup"><span data-stu-id="40c1f-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="40c1f-109">定义</span><span class="sxs-lookup"><span data-stu-id="40c1f-109">Definition</span></span>

```XML
          <xs:complexType name="RowDef_Type">
          
          <xs:sequence>
    <xs:element name="CellDef"  type="CellDef_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="40c1f-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="40c1f-110">Elements and attributes</span></span>

<span data-ttu-id="40c1f-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="40c1f-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="40c1f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="40c1f-112">Child elements</span></span>

|<span data-ttu-id="40c1f-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="40c1f-113">**Element**</span></span>|<span data-ttu-id="40c1f-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="40c1f-114">**Type**</span></span>|<span data-ttu-id="40c1f-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="40c1f-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="40c1f-116">CellDef</span><span class="sxs-lookup"><span data-stu-id="40c1f-116">CellDef</span></span>](http://msdn.microsoft.com/library/f94c8227-020a-f613-3715-96a5eaaf14fb%28Office.15%29.aspx) <br/> |[<span data-ttu-id="40c1f-117">CellDef_Type</span><span class="sxs-lookup"><span data-stu-id="40c1f-117">CellDef_Type</span></span>](celldef_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="40c1f-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="40c1f-118">Attributes</span></span>

<span data-ttu-id="40c1f-119">无。</span><span class="sxs-lookup"><span data-stu-id="40c1f-119">None.</span></span>
  

