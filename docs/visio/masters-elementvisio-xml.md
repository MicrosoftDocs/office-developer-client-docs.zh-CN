---
title: 主控形状元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: eb90df82-58b6-5d0b-6b7d-826c5c27c755
description: 包含文档的主控形状元素。
ms.openlocfilehash: b2506466a5208223e3e7b9668ad6442030ec95c9
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538051"
---
# <a name="masters-element-visio-xml"></a><span data-ttu-id="eb30c-103">主控形状元素 (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="eb30c-103">Masters element (Visio XML)</span></span>

<span data-ttu-id="eb30c-104">包含文档的主控形状元素。</span><span class="sxs-lookup"><span data-stu-id="eb30c-104">Contains the Master elements for the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="eb30c-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="eb30c-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="eb30c-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="eb30c-106">**Element type**</span></span> <br/> |[<span data-ttu-id="eb30c-107">Masters_Type</span><span class="sxs-lookup"><span data-stu-id="eb30c-107">Masters_Type</span></span>](masters_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="eb30c-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="eb30c-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="eb30c-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="eb30c-109">**Schema file**</span></span> <br/> |<span data-ttu-id="eb30c-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="eb30c-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="eb30c-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="eb30c-111">**Document parts**</span></span> <br/> |<span data-ttu-id="eb30c-112">主控 xml</span><span class="sxs-lookup"><span data-stu-id="eb30c-112">masters.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="eb30c-113">定义</span><span class="sxs-lookup"><span data-stu-id="eb30c-113">Definition</span></span>

```XML
< xs:element name="Masters" type="Masters_Type" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="eb30c-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="eb30c-114">Elements and attributes</span></span>

<span data-ttu-id="eb30c-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="eb30c-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="eb30c-116">父元素</span><span class="sxs-lookup"><span data-stu-id="eb30c-116">Parent elements</span></span>

<span data-ttu-id="eb30c-117">无。</span><span class="sxs-lookup"><span data-stu-id="eb30c-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="eb30c-118">子元素</span><span class="sxs-lookup"><span data-stu-id="eb30c-118">Child elements</span></span>

|<span data-ttu-id="eb30c-119">**元素**</span><span class="sxs-lookup"><span data-stu-id="eb30c-119">**Element**</span></span>|<span data-ttu-id="eb30c-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="eb30c-120">**Type**</span></span>|<span data-ttu-id="eb30c-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="eb30c-121">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="eb30c-122">Master</span><span class="sxs-lookup"><span data-stu-id="eb30c-122">Master</span></span>](master-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="eb30c-123">Master_Type</span><span class="sxs-lookup"><span data-stu-id="eb30c-123">Master_Type</span></span>](master_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="eb30c-124">包含用于定义文档主控形状的元素。</span><span class="sxs-lookup"><span data-stu-id="eb30c-124">Contains elements that define a master for the document.</span></span>  <br/> |
|[<span data-ttu-id="eb30c-125">MasterShortcut</span><span class="sxs-lookup"><span data-stu-id="eb30c-125">MasterShortcut</span></span>](mastershortcut-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="eb30c-126">MasterShortcut_Type</span><span class="sxs-lookup"><span data-stu-id="eb30c-126">MasterShortcut_Type</span></span>](mastershortcut_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="eb30c-127">指定在文档中定义的主控形状快捷方式。</span><span class="sxs-lookup"><span data-stu-id="eb30c-127">Specifies a master shortcut defined in the document.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="eb30c-128">Attributes</span><span class="sxs-lookup"><span data-stu-id="eb30c-128">Attributes</span></span>

<span data-ttu-id="eb30c-129">无。</span><span class="sxs-lookup"><span data-stu-id="eb30c-129">None.</span></span>
  

