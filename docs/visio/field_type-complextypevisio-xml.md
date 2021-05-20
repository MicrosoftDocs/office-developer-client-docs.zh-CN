---
title: 'Field_Type COMPLEXType (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c346fb8d-f247-4a14-19cd-9368ec86ce3f
ms.openlocfilehash: e67ea9dd5eed1892888ccd59c2ade1d95bd5d79e
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542364"
---
# <a name="field_type-complextype-visio-xml"></a><span data-ttu-id="1445e-102">Field_Type COMPLEXType (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="1445e-102">Field_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="1445e-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="1445e-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1445e-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1445e-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="1445e-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1445e-105">**Schema file**</span></span> <br/> |<span data-ttu-id="1445e-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="1445e-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="1445e-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="1445e-107">**Extension base**</span></span> <br/> |<span data-ttu-id="1445e-108">Section_Type</span><span class="sxs-lookup"><span data-stu-id="1445e-108">Section_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1445e-109">定义</span><span class="sxs-lookup"><span data-stu-id="1445e-109">Definition</span></span>

```XML
          <xs:complexType name="Field_Type">
          
          <xs:complexContent>
          <xs:extension base="Section_Type">
          <xs:sequence minOccurs="0" maxOccurs="unbounded">
    <xs:element name="Row"  type="FieldRow_Type"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="1445e-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1445e-110">Elements and attributes</span></span>

<span data-ttu-id="1445e-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="1445e-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="1445e-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1445e-112">Child elements</span></span>

|<span data-ttu-id="1445e-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="1445e-113">**Element**</span></span>|<span data-ttu-id="1445e-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="1445e-114">**Type**</span></span>|<span data-ttu-id="1445e-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="1445e-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="1445e-116">Row</span><span class="sxs-lookup"><span data-stu-id="1445e-116">Row</span></span>](row-element-field-sectionvisio-xml.md) <br/> |[<span data-ttu-id="1445e-117">FieldRow_Type</span><span class="sxs-lookup"><span data-stu-id="1445e-117">FieldRow_Type</span></span>](fieldrow_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="1445e-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="1445e-118">Attributes</span></span>

<span data-ttu-id="1445e-119">无。</span><span class="sxs-lookup"><span data-stu-id="1445e-119">None.</span></span>
  

