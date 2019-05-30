---
title: FillGradientRow_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 40c88316-4710-b5b4-7be4-e3047474d519
ms.openlocfilehash: c16eacef6afee8e90b5fb6a0e6844fcbd9735c0d
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539626"
---
# <a name="fillgradientrowtype-complextype-visio-xml"></a><span data-ttu-id="d98bb-102">FillGradientRow_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="d98bb-102">FillGradientRow_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="d98bb-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="d98bb-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d98bb-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="d98bb-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="d98bb-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="d98bb-105">**Schema file**</span></span> <br/> |<span data-ttu-id="d98bb-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="d98bb-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="d98bb-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="d98bb-107">**Extension base**</span></span> <br/> |<span data-ttu-id="d98bb-108">IndexedRow_Type</span><span class="sxs-lookup"><span data-stu-id="d98bb-108">IndexedRow_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="d98bb-109">定义</span><span class="sxs-lookup"><span data-stu-id="d98bb-109">Definition</span></span>

```XML
          <xs:complexType name="FillGradientRow_Type">
          
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

## <a name="elements-and-attributes"></a><span data-ttu-id="d98bb-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="d98bb-110">Elements and attributes</span></span>

<span data-ttu-id="d98bb-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="d98bb-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="d98bb-112">子元素</span><span class="sxs-lookup"><span data-stu-id="d98bb-112">Child elements</span></span>

|<span data-ttu-id="d98bb-113">**元素**</span><span class="sxs-lookup"><span data-stu-id="d98bb-113">**Element**</span></span>|<span data-ttu-id="d98bb-114">**类型**</span><span class="sxs-lookup"><span data-stu-id="d98bb-114">**Type**</span></span>|<span data-ttu-id="d98bb-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="d98bb-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="d98bb-116">Cell</span><span class="sxs-lookup"><span data-stu-id="d98bb-116">Cell</span></span>](cell-element-fill-gradient-sectionvisio-xml.md) <br/> |[<span data-ttu-id="d98bb-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="d98bb-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="d98bb-118">Attributes</span><span class="sxs-lookup"><span data-stu-id="d98bb-118">Attributes</span></span>

<span data-ttu-id="d98bb-119">无。</span><span class="sxs-lookup"><span data-stu-id="d98bb-119">None.</span></span>
  

