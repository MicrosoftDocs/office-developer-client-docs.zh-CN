---
title: PageSheet_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f7bce473-9a3d-65f2-8323-1e00db110c71
ms.openlocfilehash: 45e3dec8dc97fd3467195102a42227b844f07a98
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400150"
---
# <a name="pagesheettype-complextype-visio-xml"></a><span data-ttu-id="877d4-102">PageSheet_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="877d4-102">PageSheet_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="877d4-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="877d4-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="877d4-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="877d4-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="877d4-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="877d4-105">**Schema file**</span></span> <br/> |<span data-ttu-id="877d4-106">VisioSchema15 2012 06 05.xsd</span><span class="sxs-lookup"><span data-stu-id="877d4-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="877d4-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="877d4-107">**Extension base**</span></span> <br/> |<span data-ttu-id="877d4-108">Sheet_Type</span><span class="sxs-lookup"><span data-stu-id="877d4-108">Sheet_Type</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="877d4-109">定义</span><span class="sxs-lookup"><span data-stu-id="877d4-109">Definition</span></span>

```XML
      <xs:complexType name="PageSheet_Type">
        <xs:complexContent>
        <xs:extension base="Sheet_Type">
      
    <xs:attribute name="UniqueID"
  type="xsd:string"
    />
        </xs:extension>
        </xs:complexContent>
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="877d4-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="877d4-110">Elements and attributes</span></span>

<span data-ttu-id="877d4-111">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="877d4-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="877d4-112">子元素</span><span class="sxs-lookup"><span data-stu-id="877d4-112">Child elements</span></span>

<span data-ttu-id="877d4-113">无。</span><span class="sxs-lookup"><span data-stu-id="877d4-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="877d4-114">属性</span><span class="sxs-lookup"><span data-stu-id="877d4-114">Attributes</span></span>

|<span data-ttu-id="877d4-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="877d4-115">**Attribute**</span></span>|<span data-ttu-id="877d4-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="877d4-116">**Type**</span></span>|<span data-ttu-id="877d4-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="877d4-117">**Required**</span></span>|<span data-ttu-id="877d4-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="877d4-118">**Description**</span></span>|<span data-ttu-id="877d4-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="877d4-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="877d4-120">UniqueID</span><span class="sxs-lookup"><span data-stu-id="877d4-120">UniqueID</span></span>  <br/> |<span data-ttu-id="877d4-121">xsd: string</span><span class="sxs-lookup"><span data-stu-id="877d4-121">xsd:string</span></span>  <br/> |<span data-ttu-id="877d4-122">可选</span><span class="sxs-lookup"><span data-stu-id="877d4-122">optional</span></span>  <br/> ||<span data-ttu-id="877d4-123">Xsd: string 类型的值。</span><span class="sxs-lookup"><span data-stu-id="877d4-123">Values of the xsd:string type.</span></span>  <br/> |
   

