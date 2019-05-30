---
title: Control_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9eba241a-e64d-6bac-6d8e-a049e4febe96
ms.openlocfilehash: 8e5cb58e6964f2bb6db530e9ff01781520d06539
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538702"
---
# <a name="controltype-complextype-visio-xml"></a><span data-ttu-id="f0a5f-102">Control_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="f0a5f-102">Control_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="f0a5f-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="f0a5f-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f0a5f-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f0a5f-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="f0a5f-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f0a5f-105">**Schema file**</span></span> <br/> |<span data-ttu-id="f0a5f-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="f0a5f-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="f0a5f-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="f0a5f-107">**Extension base**</span></span> <br/> |<span data-ttu-id="f0a5f-108">Section_Type</span><span class="sxs-lookup"><span data-stu-id="f0a5f-108">Section_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f0a5f-109">定义</span><span class="sxs-lookup"><span data-stu-id="f0a5f-109">Definition</span></span>

```XML
          <xs:complexType name="Control_Type">
          
          <xs:complexContent>
          <xs:extension base="Section_Type">
          <xs:sequence minOccurs="0" maxOccurs="unbounded">
    <xs:element name="Row"  type="ControlRow_Type"
    >
    </xs:element>
    
      </xs:sequence>
      </xs:extension>
      </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f0a5f-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f0a5f-110">Elements and attributes</span></span>

<span data-ttu-id="f0a5f-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="f0a5f-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="f0a5f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="f0a5f-112">Child elements</span></span>

|<span data-ttu-id="f0a5f-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="f0a5f-113">**Element**</span></span>|<span data-ttu-id="f0a5f-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="f0a5f-114">**Type**</span></span>|<span data-ttu-id="f0a5f-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="f0a5f-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f0a5f-116">Row</span><span class="sxs-lookup"><span data-stu-id="f0a5f-116">Row</span></span>](row-element-controls-sectionvisio-xml.md) <br/> |[<span data-ttu-id="f0a5f-117">ControlRow_Type</span><span class="sxs-lookup"><span data-stu-id="f0a5f-117">ControlRow_Type</span></span>](controlrow_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="f0a5f-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="f0a5f-118">Attributes</span></span>

<span data-ttu-id="f0a5f-119">无。</span><span class="sxs-lookup"><span data-stu-id="f0a5f-119">None.</span></span>
  

