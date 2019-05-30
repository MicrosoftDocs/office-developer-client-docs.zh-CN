---
title: ProtectMasters 元素 (DocumentSettings_Type 复杂类型) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: edc46630-c320-6b4e-4747-961075dd5fd7
description: 指定是否阻止用户创建、编辑或删除主控形状。 用户仍可以从主控形状创建新形状, 而不考虑此设置。
ms.openlocfilehash: 34ace8c873b133f44ea7bd7c9c2e4127a103a760
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540691"
---
# <a name="protectmasters-element-documentsettingstype-complextype-visio-xml"></a><span data-ttu-id="2d174-104">ProtectMasters 元素 (DocumentSettings_Type 复杂类型) (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="2d174-104">ProtectMasters element (DocumentSettings_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="2d174-105">指定是否阻止用户创建、编辑或删除主控形状。</span><span class="sxs-lookup"><span data-stu-id="2d174-105">Specifies whether the user is prevented from creating, editing, or deleting master shapes.</span></span> <span data-ttu-id="2d174-106">用户仍可以从主控形状创建新形状, 而不考虑此设置。</span><span class="sxs-lookup"><span data-stu-id="2d174-106">The user can still create new shapes from a master shape, regardless of this setting.</span></span> 
  
<span data-ttu-id="2d174-107">此元素的可能值的范围是 "0" 或 "1"。</span><span class="sxs-lookup"><span data-stu-id="2d174-107">The range of possible values for this element is either '0' or '1'.</span></span> <span data-ttu-id="2d174-108">值为 "0" 表示用户可以创建、编辑或删除主控形状。</span><span class="sxs-lookup"><span data-stu-id="2d174-108">A value of '0' indicates that users can create, edit, or delete master shapes.</span></span> <span data-ttu-id="2d174-109">值为 "1" 表示用户无法创建、编辑或删除主控形状。</span><span class="sxs-lookup"><span data-stu-id="2d174-109">A value of '1' indicates that users cannot create, edit, or delete master shapes.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="2d174-110">元素信息</span><span class="sxs-lookup"><span data-stu-id="2d174-110">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2d174-111">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="2d174-111">**Element type**</span></span> <br/> |[<span data-ttu-id="2d174-112">ProtectMasters_Type</span><span class="sxs-lookup"><span data-stu-id="2d174-112">ProtectMasters_Type</span></span>](protectmasters_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="2d174-113">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="2d174-113">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="2d174-114">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="2d174-114">**Schema file**</span></span> <br/> |<span data-ttu-id="2d174-115">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="2d174-115">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="2d174-116">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="2d174-116">**Document parts**</span></span> <br/> |<span data-ttu-id="2d174-117">document .xml</span><span class="sxs-lookup"><span data-stu-id="2d174-117">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="2d174-118">定义</span><span class="sxs-lookup"><span data-stu-id="2d174-118">Definition</span></span>

```XML
< xs:element name="ProtectMasters" type="ProtectMasters_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="2d174-119">元素和属性</span><span class="sxs-lookup"><span data-stu-id="2d174-119">Elements and attributes</span></span>

<span data-ttu-id="2d174-120">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="2d174-120">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="2d174-121">父元素</span><span class="sxs-lookup"><span data-stu-id="2d174-121">Parent elements</span></span>

|<span data-ttu-id="2d174-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="2d174-122">**Element**</span></span>|<span data-ttu-id="2d174-123">**类型**</span><span class="sxs-lookup"><span data-stu-id="2d174-123">**Type**</span></span>|<span data-ttu-id="2d174-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="2d174-124">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="2d174-125">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="2d174-125">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="2d174-126">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="2d174-126">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="2d174-127">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="2d174-127">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="2d174-128">子元素</span><span class="sxs-lookup"><span data-stu-id="2d174-128">Child elements</span></span>

<span data-ttu-id="2d174-129">无。</span><span class="sxs-lookup"><span data-stu-id="2d174-129">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="2d174-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="2d174-130">Attributes</span></span>

<span data-ttu-id="2d174-131">无。</span><span class="sxs-lookup"><span data-stu-id="2d174-131">None.</span></span>
  

