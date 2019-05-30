---
title: Hyperlink_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 48c31987-bb85-e49a-c337-740fa507a02d
ms.openlocfilehash: ce9a1f5b9a6e402ec157d641f81a82c6df4b92e1
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541552"
---
# <a name="hyperlinktype-complextype-visio-xml"></a><span data-ttu-id="08cff-102">Hyperlink_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="08cff-102">Hyperlink_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="08cff-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="08cff-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="08cff-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="08cff-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="08cff-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="08cff-105">**Schema file**</span></span> <br/> |<span data-ttu-id="08cff-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="08cff-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="08cff-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="08cff-107">**Extension base**</span></span> <br/> |<span data-ttu-id="08cff-108">Section_Type</span><span class="sxs-lookup"><span data-stu-id="08cff-108">Section_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="08cff-109">定义</span><span class="sxs-lookup"><span data-stu-id="08cff-109">Definition</span></span>

```XML
          <xs:complexType name="Hyperlink_Type">
          
          <xs:complexContent>
          <xs:extension base="Section_Type">
          <xs:sequence minOccurs="0" maxOccurs="unbounded">
    <xs:element name="Row"  type="HyperlinkRow_Type"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="08cff-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="08cff-110">Elements and attributes</span></span>

<span data-ttu-id="08cff-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="08cff-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="08cff-112">子元素</span><span class="sxs-lookup"><span data-stu-id="08cff-112">Child elements</span></span>

|<span data-ttu-id="08cff-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="08cff-113">**Element**</span></span>|<span data-ttu-id="08cff-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="08cff-114">**Type**</span></span>|<span data-ttu-id="08cff-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="08cff-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="08cff-116">Row</span><span class="sxs-lookup"><span data-stu-id="08cff-116">Row</span></span>](row-element-hyperlink-sectionvisio-xml.md) <br/> |[<span data-ttu-id="08cff-117">HyperlinkRow_Type</span><span class="sxs-lookup"><span data-stu-id="08cff-117">HyperlinkRow_Type</span></span>](hyperlinkrow_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="08cff-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="08cff-118">Attributes</span></span>

<span data-ttu-id="08cff-119">无。</span><span class="sxs-lookup"><span data-stu-id="08cff-119">None.</span></span>
  

