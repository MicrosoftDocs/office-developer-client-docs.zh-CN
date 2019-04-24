---
title: LayerRow_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c8015f59-06a7-54c5-2df6-bc9e4d19f17b
ms.openlocfilehash: 332bd6bc93f66bad46b726cb42bad471980a6a3c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358987"
---
# <a name="layerrowtype-complextype-visio-xml"></a><span data-ttu-id="9bd94-102">LayerRow_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="9bd94-102">LayerRow_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="9bd94-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="9bd94-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9bd94-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9bd94-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="9bd94-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9bd94-105">**Schema file**</span></span> <br/> |<span data-ttu-id="9bd94-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="9bd94-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="9bd94-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="9bd94-107">**Extension base**</span></span> <br/> |<span data-ttu-id="9bd94-108">IndexedRow_Type</span><span class="sxs-lookup"><span data-stu-id="9bd94-108">IndexedRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9bd94-109">定义</span><span class="sxs-lookup"><span data-stu-id="9bd94-109">Definition</span></span>

```XML
          <xs:complexType name="LayerRow_Type">
          
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

## <a name="elements-and-attributes"></a><span data-ttu-id="9bd94-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9bd94-110">Elements and attributes</span></span>

<span data-ttu-id="9bd94-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="9bd94-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="9bd94-112">子元素</span><span class="sxs-lookup"><span data-stu-id="9bd94-112">Child elements</span></span>

|<span data-ttu-id="9bd94-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="9bd94-113">**Element**</span></span>|<span data-ttu-id="9bd94-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="9bd94-114">**Type**</span></span>|<span data-ttu-id="9bd94-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="9bd94-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9bd94-116">Cell</span><span class="sxs-lookup"><span data-stu-id="9bd94-116">Cell</span></span>](cell-element-layer-sectionvisio-xml.md) <br/> |[<span data-ttu-id="9bd94-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="9bd94-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="9bd94-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="9bd94-118">Attributes</span></span>

<span data-ttu-id="9bd94-119">无。</span><span class="sxs-lookup"><span data-stu-id="9bd94-119">None.</span></span>
  

