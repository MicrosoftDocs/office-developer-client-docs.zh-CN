---
title: RowDef_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 64897258-dd7e-a730-d4f5-d9c217308491
ms.openlocfilehash: 79a01d9fe5edf1de933f05683eca3bfd6e95e4b3
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538135"
---
# <a name="rowdeftype-complextype-visio-xml"></a><span data-ttu-id="e31f6-102">RowDef_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="e31f6-102">RowDef_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="e31f6-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="e31f6-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e31f6-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="e31f6-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="e31f6-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="e31f6-105">**Schema file**</span></span> <br/> |<span data-ttu-id="e31f6-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="e31f6-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="e31f6-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="e31f6-107">**Extension base**</span></span> <br/> |<span data-ttu-id="e31f6-108">无</span><span class="sxs-lookup"><span data-stu-id="e31f6-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="e31f6-109">定义</span><span class="sxs-lookup"><span data-stu-id="e31f6-109">Definition</span></span>

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

## <a name="elements-and-attributes"></a><span data-ttu-id="e31f6-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="e31f6-110">Elements and attributes</span></span>

<span data-ttu-id="e31f6-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="e31f6-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="e31f6-112">子元素</span><span class="sxs-lookup"><span data-stu-id="e31f6-112">Child elements</span></span>

|<span data-ttu-id="e31f6-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="e31f6-113">**Element**</span></span>|<span data-ttu-id="e31f6-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="e31f6-114">**Type**</span></span>|<span data-ttu-id="e31f6-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="e31f6-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e31f6-116">CellDef</span><span class="sxs-lookup"><span data-stu-id="e31f6-116">CellDef</span></span> <br/> |[<span data-ttu-id="e31f6-117">CellDef_Type</span><span class="sxs-lookup"><span data-stu-id="e31f6-117">CellDef_Type</span></span>](celldef_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="e31f6-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="e31f6-118">Attributes</span></span>

<span data-ttu-id="e31f6-119">无。</span><span class="sxs-lookup"><span data-stu-id="e31f6-119">None.</span></span>
  

