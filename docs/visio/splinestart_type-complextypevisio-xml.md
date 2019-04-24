---
title: SplineStart_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4395e39c-51bb-b232-bd8a-c5e53ae95169
ms.openlocfilehash: 963ef696e66861f6f67466446e0c1ea19933029e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329874"
---
# <a name="splinestarttype-complextype-visio-xml"></a><span data-ttu-id="382b7-102">SplineStart_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="382b7-102">SplineStart_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="382b7-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="382b7-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="382b7-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="382b7-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="382b7-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="382b7-105">**Schema file**</span></span> <br/> |<span data-ttu-id="382b7-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="382b7-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="382b7-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="382b7-107">**Extension base**</span></span> <br/> |<span data-ttu-id="382b7-108">GeometryRow_Type</span><span class="sxs-lookup"><span data-stu-id="382b7-108">GeometryRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="382b7-109">定义</span><span class="sxs-lookup"><span data-stu-id="382b7-109">Definition</span></span>

```XML
          <xs:complexType name="SplineStart_Type">
          
          <xs:complexContent>
          <xs:extension base="GeometryRow_Type">
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

## <a name="elements-and-attributes"></a><span data-ttu-id="382b7-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="382b7-110">Elements and attributes</span></span>

<span data-ttu-id="382b7-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="382b7-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="382b7-112">子元素</span><span class="sxs-lookup"><span data-stu-id="382b7-112">Child elements</span></span>

|<span data-ttu-id="382b7-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="382b7-113">**Element**</span></span>|<span data-ttu-id="382b7-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="382b7-114">**Type**</span></span>|<span data-ttu-id="382b7-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="382b7-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="382b7-116">Cell</span><span class="sxs-lookup"><span data-stu-id="382b7-116">Cell</span></span>](cell-element-splinestart-rowvisio-xml.md) <br/> |[<span data-ttu-id="382b7-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="382b7-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="382b7-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="382b7-118">Attributes</span></span>

<span data-ttu-id="382b7-119">无。</span><span class="sxs-lookup"><span data-stu-id="382b7-119">None.</span></span>
  

