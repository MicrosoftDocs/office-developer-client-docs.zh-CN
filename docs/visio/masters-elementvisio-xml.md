---
title: 主控形状元素 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: eb90df82-58b6-5d0b-6b7d-826c5c27c755
description: 包含文档的主控形状元素。
ms.openlocfilehash: ea2cee2f9845f8a72220081617a11cf4f72dafd1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341424"
---
# <a name="masters-element-visio-xml"></a><span data-ttu-id="be580-103">主控形状元素 ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="be580-103">Masters element ('Visio XML')</span></span>

<span data-ttu-id="be580-104">包含文档的主控形状元素。</span><span class="sxs-lookup"><span data-stu-id="be580-104">Contains the Master elements for the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="be580-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="be580-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="be580-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="be580-106">**Element type**</span></span> <br/> |[<span data-ttu-id="be580-107">Masters_Type</span><span class="sxs-lookup"><span data-stu-id="be580-107">Masters_Type</span></span>](masters_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="be580-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="be580-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="be580-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="be580-109">**Schema file**</span></span> <br/> |<span data-ttu-id="be580-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="be580-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="be580-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="be580-111">**Document parts**</span></span> <br/> |<span data-ttu-id="be580-112">主控 xml</span><span class="sxs-lookup"><span data-stu-id="be580-112">masters.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="be580-113">定义</span><span class="sxs-lookup"><span data-stu-id="be580-113">Definition</span></span>

```XML
< xs:element name="Masters" type="Masters_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="be580-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="be580-114">Elements and attributes</span></span>

<span data-ttu-id="be580-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="be580-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="be580-116">父元素</span><span class="sxs-lookup"><span data-stu-id="be580-116">Parent elements</span></span>

<span data-ttu-id="be580-117">无。</span><span class="sxs-lookup"><span data-stu-id="be580-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="be580-118">子元素</span><span class="sxs-lookup"><span data-stu-id="be580-118">Child elements</span></span>

|<span data-ttu-id="be580-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="be580-119">**Element**</span></span>|<span data-ttu-id="be580-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="be580-120">**Type**</span></span>|<span data-ttu-id="be580-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="be580-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="be580-122">Master</span><span class="sxs-lookup"><span data-stu-id="be580-122">Master</span></span>](master-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="be580-123">Master_Type</span><span class="sxs-lookup"><span data-stu-id="be580-123">Master_Type</span></span>](master_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="be580-124">包含用于定义文档主控形状的元素。</span><span class="sxs-lookup"><span data-stu-id="be580-124">Contains elements that define a master for the document.</span></span>  <br/> |
|[<span data-ttu-id="be580-125">MasterShortcut</span><span class="sxs-lookup"><span data-stu-id="be580-125">MasterShortcut</span></span>](mastershortcut-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="be580-126">MasterShortcut_Type</span><span class="sxs-lookup"><span data-stu-id="be580-126">MasterShortcut_Type</span></span>](mastershortcut_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="be580-127">指定在文档中定义的主控形状快捷方式。</span><span class="sxs-lookup"><span data-stu-id="be580-127">Specifies a master shortcut defined in the document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="be580-128">Attributes</span><span class="sxs-lookup"><span data-stu-id="be580-128">Attributes</span></span>

<span data-ttu-id="be580-129">无。</span><span class="sxs-lookup"><span data-stu-id="be580-129">None.</span></span>
  

