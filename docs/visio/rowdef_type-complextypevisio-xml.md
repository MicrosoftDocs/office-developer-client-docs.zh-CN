---
title: RowDef_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 64897258-dd7e-a730-d4f5-d9c217308491
ms.openlocfilehash: 11acab820fe51b6dde9cf9d57977699ca3c977cb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355767"
---
# <a name="rowdeftype-complextype-visio-xml"></a><span data-ttu-id="b10c4-102">RowDef_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="b10c4-102">RowDef_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="b10c4-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="b10c4-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="b10c4-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="b10c4-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="b10c4-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="b10c4-105">**Schema file**</span></span> <br/> |<span data-ttu-id="b10c4-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="b10c4-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="b10c4-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="b10c4-107">**Extension base**</span></span> <br/> |<span data-ttu-id="b10c4-108">无</span><span class="sxs-lookup"><span data-stu-id="b10c4-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="b10c4-109">定义</span><span class="sxs-lookup"><span data-stu-id="b10c4-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="b10c4-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="b10c4-110">Elements and attributes</span></span>

<span data-ttu-id="b10c4-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="b10c4-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="b10c4-112">子元素</span><span class="sxs-lookup"><span data-stu-id="b10c4-112">Child elements</span></span>

|<span data-ttu-id="b10c4-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="b10c4-113">**Element**</span></span>|<span data-ttu-id="b10c4-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="b10c4-114">**Type**</span></span>|<span data-ttu-id="b10c4-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="b10c4-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b10c4-116">CellDef</span><span class="sxs-lookup"><span data-stu-id="b10c4-116">CellDef</span></span> <br/> |[<span data-ttu-id="b10c4-117">CellDef_Type</span><span class="sxs-lookup"><span data-stu-id="b10c4-117">CellDef_Type</span></span>](celldef_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="b10c4-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="b10c4-118">Attributes</span></span>

<span data-ttu-id="b10c4-119">无。</span><span class="sxs-lookup"><span data-stu-id="b10c4-119">None.</span></span>
  

