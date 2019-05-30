---
title: UserRow_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ae2e014b-2e53-c317-0bfa-9a0cb1e09588
ms.openlocfilehash: aed034bb2f8ced384e8c7c9c82b9be7570988332
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538555"
---
# <a name="userrowtype-complextype-visio-xml"></a><span data-ttu-id="fefa5-102">UserRow_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="fefa5-102">UserRow_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="fefa5-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="fefa5-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fefa5-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="fefa5-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="fefa5-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="fefa5-105">**Schema file**</span></span> <br/> |<span data-ttu-id="fefa5-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="fefa5-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="fefa5-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="fefa5-107">**Extension base**</span></span> <br/> |<span data-ttu-id="fefa5-108">NamedRow_Type</span><span class="sxs-lookup"><span data-stu-id="fefa5-108">NamedRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="fefa5-109">定义</span><span class="sxs-lookup"><span data-stu-id="fefa5-109">Definition</span></span>

```XML
          <xs:complexType name="UserRow_Type">
          
          <xs:complexContent>
          <xs:extension base="NamedRow_Type">
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

## <a name="elements-and-attributes"></a><span data-ttu-id="fefa5-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="fefa5-110">Elements and attributes</span></span>

<span data-ttu-id="fefa5-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="fefa5-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="fefa5-112">子元素</span><span class="sxs-lookup"><span data-stu-id="fefa5-112">Child elements</span></span>

|<span data-ttu-id="fefa5-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="fefa5-113">**Element**</span></span>|<span data-ttu-id="fefa5-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="fefa5-114">**Type**</span></span>|<span data-ttu-id="fefa5-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="fefa5-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="fefa5-116">Cell</span><span class="sxs-lookup"><span data-stu-id="fefa5-116">Cell</span></span>](cell-element-user-defined-cells-sectionvisio-xml.md) <br/> |[<span data-ttu-id="fefa5-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="fefa5-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="fefa5-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="fefa5-118">Attributes</span></span>

<span data-ttu-id="fefa5-119">无。</span><span class="sxs-lookup"><span data-stu-id="fefa5-119">None.</span></span>
  

