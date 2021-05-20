---
title: 'fld_Type XML (Visio complexType) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f680eb55-2dbb-a7b9-0879-6e91576983f3
ms.openlocfilehash: 5651a0b0a2d09e3fbbdb0d1dbf66f1be3d374c12
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539598"
---
# <a name="fld_type-complextype-visio-xml"></a><span data-ttu-id="1610e-102">fld_Type XML (Visio complexType) </span><span class="sxs-lookup"><span data-stu-id="1610e-102">fld_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="1610e-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="1610e-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="1610e-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="1610e-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="1610e-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="1610e-105">**Schema file**</span></span> <br/> |<span data-ttu-id="1610e-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="1610e-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="1610e-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="1610e-107">**Extension base**</span></span> <br/> |<span data-ttu-id="1610e-108">xsd：string</span><span class="sxs-lookup"><span data-stu-id="1610e-108">xsd:string</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="1610e-109">定义</span><span class="sxs-lookup"><span data-stu-id="1610e-109">Definition</span></span>

```XML
      <xs:complexType name="fld_Type">
        <xs:complexContent>
        <xs:extension base="xsd:string">
      
    <xs:attribute name="IX"
  type="xsd:unsignedInt"
     use="required"
    />
        </xs:extension>
        </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="1610e-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="1610e-110">Elements and attributes</span></span>

<span data-ttu-id="1610e-111">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="1610e-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="1610e-112">子元素</span><span class="sxs-lookup"><span data-stu-id="1610e-112">Child elements</span></span>

<span data-ttu-id="1610e-113">无。</span><span class="sxs-lookup"><span data-stu-id="1610e-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="1610e-114">属性</span><span class="sxs-lookup"><span data-stu-id="1610e-114">Attributes</span></span>

|<span data-ttu-id="1610e-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="1610e-115">**Attribute**</span></span>|<span data-ttu-id="1610e-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="1610e-116">**Type**</span></span>|<span data-ttu-id="1610e-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="1610e-117">**Required**</span></span>|<span data-ttu-id="1610e-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="1610e-118">**Description**</span></span>|<span data-ttu-id="1610e-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="1610e-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1610e-120">IX</span><span class="sxs-lookup"><span data-stu-id="1610e-120">IX</span></span>  <br/> |<span data-ttu-id="1610e-121">xsd：unsignedInt</span><span class="sxs-lookup"><span data-stu-id="1610e-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="1610e-122">必需</span><span class="sxs-lookup"><span data-stu-id="1610e-122">required</span></span>  <br/> ||<span data-ttu-id="1610e-123">xsd：unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="1610e-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

