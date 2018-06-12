---
title: 主控形状元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: eb90df82-58b6-5d0b-6b7d-826c5c27c755
description: 包含主控形状的文档的元素。
ms.openlocfilehash: d40071c64dc454eeb92f8518f89ef4de8b3b0cb5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780692"
---
# <a name="masters-element-visio-xml"></a><span data-ttu-id="fe4e4-103">主控形状元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="fe4e4-103">Masters element ('Visio XML')</span></span>

<span data-ttu-id="fe4e4-104">包含主控形状的文档的元素。</span><span class="sxs-lookup"><span data-stu-id="fe4e4-104">Contains the Master elements for the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="fe4e4-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="fe4e4-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fe4e4-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="fe4e4-106">**Element type**</span></span> <br/> |[<span data-ttu-id="fe4e4-107">Masters_Type</span><span class="sxs-lookup"><span data-stu-id="fe4e4-107">Masters_Type</span></span>](masters_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="fe4e4-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="fe4e4-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="fe4e4-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="fe4e4-109">**Schema file**</span></span> <br/> |<span data-ttu-id="fe4e4-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="fe4e4-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="fe4e4-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="fe4e4-111">**Document parts**</span></span> <br/> |<span data-ttu-id="fe4e4-112">masters.xml</span><span class="sxs-lookup"><span data-stu-id="fe4e4-112">masters.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="fe4e4-113">定义</span><span class="sxs-lookup"><span data-stu-id="fe4e4-113">Definition</span></span>

```XML
< xs:element name="Masters" type="Masters_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="fe4e4-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="fe4e4-114">Elements and attributes</span></span>

<span data-ttu-id="fe4e4-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="fe4e4-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="fe4e4-116">父元素</span><span class="sxs-lookup"><span data-stu-id="fe4e4-116">Parent elements</span></span>

<span data-ttu-id="fe4e4-117">无。</span><span class="sxs-lookup"><span data-stu-id="fe4e4-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="fe4e4-118">子元素</span><span class="sxs-lookup"><span data-stu-id="fe4e4-118">Child elements</span></span>

|<span data-ttu-id="fe4e4-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="fe4e4-119">**Element**</span></span>|<span data-ttu-id="fe4e4-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="fe4e4-120">**Type**</span></span>|<span data-ttu-id="fe4e4-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe4e4-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="fe4e4-122">Master</span><span class="sxs-lookup"><span data-stu-id="fe4e4-122">Master</span></span>](master-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fe4e4-123">Master_Type</span><span class="sxs-lookup"><span data-stu-id="fe4e4-123">Master_Type</span></span>](master_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="fe4e4-124">包含用于定义文档主控形状的元素。</span><span class="sxs-lookup"><span data-stu-id="fe4e4-124">Contains elements that define a master for the document.</span></span>  <br/> |
|[<span data-ttu-id="fe4e4-125">MasterShortcut</span><span class="sxs-lookup"><span data-stu-id="fe4e4-125">MasterShortcut</span></span>](mastershortcut-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="fe4e4-126">MasterShortcut_Type</span><span class="sxs-lookup"><span data-stu-id="fe4e4-126">MasterShortcut_Type</span></span>](mastershortcut_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="fe4e4-127">指定文档中定义的主控形状快捷方式。</span><span class="sxs-lookup"><span data-stu-id="fe4e4-127">Specifies a master shortcut defined in the document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="fe4e4-128">属性</span><span class="sxs-lookup"><span data-stu-id="fe4e4-128">Attributes</span></span>

<span data-ttu-id="fe4e4-129">无。</span><span class="sxs-lookup"><span data-stu-id="fe4e4-129">None.</span></span>
  

