---
title: HeaderMargin_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 756b87f6-aa0e-c643-c733-7db788f63ac8
ms.openlocfilehash: 9bb32471f1384c89e02e9ffdbcceebfc48d2b22e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393717"
---
# <a name="headermargintype-complextype-visio-xml"></a><span data-ttu-id="07a14-102">HeaderMargin_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="07a14-102">HeaderMargin_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="07a14-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="07a14-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="07a14-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="07a14-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="07a14-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="07a14-105">**Schema file**</span></span> <br/> |<span data-ttu-id="07a14-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="07a14-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="07a14-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="07a14-107">**Extension base**</span></span> <br/> |<span data-ttu-id="07a14-108">化</span><span class="sxs-lookup"><span data-stu-id="07a14-108">xsd:double</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="07a14-109">定义</span><span class="sxs-lookup"><span data-stu-id="07a14-109">Definition</span></span>

```XML
      <xs:complexType name="HeaderMargin_Type">
        <xs:complexContent>
        <xs:extension base="xsd:double">
      
    <xs:attribute name="Unit"
  type="xsd:string"
    />
        </xs:extension>
        </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="07a14-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="07a14-110">Elements and attributes</span></span>

<span data-ttu-id="07a14-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="07a14-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="07a14-112">子元素</span><span class="sxs-lookup"><span data-stu-id="07a14-112">Child elements</span></span>

<span data-ttu-id="07a14-113">无。</span><span class="sxs-lookup"><span data-stu-id="07a14-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="07a14-114">属性</span><span class="sxs-lookup"><span data-stu-id="07a14-114">Attributes</span></span>

|<span data-ttu-id="07a14-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="07a14-115">**Attribute**</span></span>|<span data-ttu-id="07a14-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="07a14-116">**Type**</span></span>|<span data-ttu-id="07a14-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="07a14-117">**Required**</span></span>|<span data-ttu-id="07a14-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="07a14-118">**Description**</span></span>|<span data-ttu-id="07a14-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="07a14-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07a14-120">单位</span><span class="sxs-lookup"><span data-stu-id="07a14-120">Unit</span></span>  <br/> |<span data-ttu-id="07a14-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="07a14-121">xsd:string</span></span>  <br/> |<span data-ttu-id="07a14-122">可选</span><span class="sxs-lookup"><span data-stu-id="07a14-122">optional</span></span>  <br/> ||<span data-ttu-id="07a14-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="07a14-123">Values of the xsd:string type.</span></span>  <br/> |
   

