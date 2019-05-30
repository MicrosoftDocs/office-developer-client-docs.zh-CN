---
title: pp_Type 复杂类型 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9259b546-4a4d-81d9-4e0d-cff693d28a56
ms.openlocfilehash: 4e86d95459e7df7c8a145459c268b647e79c6a4c
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34539003"
---
# <a name="pptype-complextype-visio-xml"></a><span data-ttu-id="560fc-102">pp_Type 复杂类型 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="560fc-102">pp_Type complexType (Visio XML)</span></span>

## <a name="type-information"></a><span data-ttu-id="560fc-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="560fc-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="560fc-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="560fc-104">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="560fc-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="560fc-105">**Schema file**</span></span> <br/> |<span data-ttu-id="560fc-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="560fc-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="560fc-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="560fc-107">**Extension base**</span></span> <br/> |<span data-ttu-id="560fc-108">无</span><span class="sxs-lookup"><span data-stu-id="560fc-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="560fc-109">定义</span><span class="sxs-lookup"><span data-stu-id="560fc-109">Definition</span></span>

```XML
      <xs:complexType name="pp_Type">
    <xs:attribute name="IX"
  type="xsd:unsignedInt"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="560fc-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="560fc-110">Elements and attributes</span></span>

<span data-ttu-id="560fc-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="560fc-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="560fc-112">子元素</span><span class="sxs-lookup"><span data-stu-id="560fc-112">Child elements</span></span>

<span data-ttu-id="560fc-113">无。</span><span class="sxs-lookup"><span data-stu-id="560fc-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="560fc-114">属性</span><span class="sxs-lookup"><span data-stu-id="560fc-114">Attributes</span></span>

|<span data-ttu-id="560fc-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="560fc-115">**Attribute**</span></span>|<span data-ttu-id="560fc-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="560fc-116">**Type**</span></span>|<span data-ttu-id="560fc-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="560fc-117">**Required**</span></span>|<span data-ttu-id="560fc-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="560fc-118">**Description**</span></span>|<span data-ttu-id="560fc-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="560fc-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="560fc-120">IX</span><span class="sxs-lookup"><span data-stu-id="560fc-120">IX</span></span>  <br/> |<span data-ttu-id="560fc-121">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="560fc-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="560fc-122">必需</span><span class="sxs-lookup"><span data-stu-id="560fc-122">required</span></span>  <br/> ||<span data-ttu-id="560fc-123">Xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="560fc-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

