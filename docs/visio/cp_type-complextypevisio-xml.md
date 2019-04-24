---
title: cp_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 1e69b0db-f705-61f0-e6ab-811b2acc358e
ms.openlocfilehash: 9419882f8f61293f0160b8e645f0f76bb443d46f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282913"
---
# <a name="cptype-complextype-visio-xml"></a><span data-ttu-id="3d211-102">cp_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="3d211-102">cp_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="3d211-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="3d211-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="3d211-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="3d211-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="3d211-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="3d211-105">**Schema file**</span></span> <br/> |<span data-ttu-id="3d211-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="3d211-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="3d211-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="3d211-107">**Extension base**</span></span> <br/> |<span data-ttu-id="3d211-108">无</span><span class="sxs-lookup"><span data-stu-id="3d211-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="3d211-109">定义</span><span class="sxs-lookup"><span data-stu-id="3d211-109">Definition</span></span>

```XML
      <xs:complexType name="cp_Type">
    <xs:attribute name="IX"
  type="xsd:unsignedInt"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="3d211-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="3d211-110">Elements and attributes</span></span>

<span data-ttu-id="3d211-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="3d211-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="3d211-112">子元素</span><span class="sxs-lookup"><span data-stu-id="3d211-112">Child elements</span></span>

<span data-ttu-id="3d211-113">无。</span><span class="sxs-lookup"><span data-stu-id="3d211-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="3d211-114">属性</span><span class="sxs-lookup"><span data-stu-id="3d211-114">Attributes</span></span>

|<span data-ttu-id="3d211-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="3d211-115">**Attribute**</span></span>|<span data-ttu-id="3d211-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="3d211-116">**Type**</span></span>|<span data-ttu-id="3d211-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="3d211-117">**Required**</span></span>|<span data-ttu-id="3d211-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="3d211-118">**Description**</span></span>|<span data-ttu-id="3d211-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="3d211-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3d211-120">IX</span><span class="sxs-lookup"><span data-stu-id="3d211-120">IX</span></span>  <br/> |<span data-ttu-id="3d211-121">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="3d211-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="3d211-122">必需</span><span class="sxs-lookup"><span data-stu-id="3d211-122">required</span></span>  <br/> ||<span data-ttu-id="3d211-123">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="3d211-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

