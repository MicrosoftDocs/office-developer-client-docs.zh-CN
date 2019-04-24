---
title: pp_Type 复杂类型 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 9259b546-4a4d-81d9-4e0d-cff693d28a56
ms.openlocfilehash: 390b478a2c0cc8dc22a13c072bf35f88aaf44251
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356124"
---
# <a name="pptype-complextype-visio-xml"></a><span data-ttu-id="61134-102">pp_Type 复杂类型 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="61134-102">pp_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="61134-103">类型信息</span><span class="sxs-lookup"><span data-stu-id="61134-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="61134-104">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="61134-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="61134-105">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="61134-105">**Schema file**</span></span> <br/> |<span data-ttu-id="61134-106">VisioSchema15-2012-06-05</span><span class="sxs-lookup"><span data-stu-id="61134-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="61134-107">**扩展基**</span><span class="sxs-lookup"><span data-stu-id="61134-107">**Extension base**</span></span> <br/> |<span data-ttu-id="61134-108">无</span><span class="sxs-lookup"><span data-stu-id="61134-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="61134-109">定义</span><span class="sxs-lookup"><span data-stu-id="61134-109">Definition</span></span>

```XML
      <xs:complexType name="pp_Type">
    <xs:attribute name="IX"
  type="xsd:unsignedInt"
     use="required"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="61134-110">元素和属性</span><span class="sxs-lookup"><span data-stu-id="61134-110">Elements and attributes</span></span>

<span data-ttu-id="61134-111">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="61134-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="61134-112">子元素</span><span class="sxs-lookup"><span data-stu-id="61134-112">Child elements</span></span>

<span data-ttu-id="61134-113">无。</span><span class="sxs-lookup"><span data-stu-id="61134-113">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="61134-114">属性</span><span class="sxs-lookup"><span data-stu-id="61134-114">Attributes</span></span>

|<span data-ttu-id="61134-115">**属性**</span><span class="sxs-lookup"><span data-stu-id="61134-115">**Attribute**</span></span>|<span data-ttu-id="61134-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="61134-116">**Type**</span></span>|<span data-ttu-id="61134-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="61134-117">**Required**</span></span>|<span data-ttu-id="61134-118">**描述**</span><span class="sxs-lookup"><span data-stu-id="61134-118">**Description**</span></span>|<span data-ttu-id="61134-119">**可能的值**</span><span class="sxs-lookup"><span data-stu-id="61134-119">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61134-120">IX</span><span class="sxs-lookup"><span data-stu-id="61134-120">IX</span></span>  <br/> |<span data-ttu-id="61134-121">xsd: unsignedInt</span><span class="sxs-lookup"><span data-stu-id="61134-121">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="61134-122">必需</span><span class="sxs-lookup"><span data-stu-id="61134-122">required</span></span>  <br/> ||<span data-ttu-id="61134-123">xsd: unsignedInt 类型的值。</span><span class="sxs-lookup"><span data-stu-id="61134-123">Values of the xsd:unsignedInt type.</span></span>  <br/> |
   

