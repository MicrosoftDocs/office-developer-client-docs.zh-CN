---
title: ProtectMasters 元素 (DocumentSettings_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: edc46630-c320-6b4e-4747-961075dd5fd7
description: 指定是否阻止用户创建、编辑或删除主控形状。 用户仍可以从主控形状创建新形状, 而不考虑此设置。
ms.openlocfilehash: 2730fa3aa3f9f4f7529d6b939e48d3533e31e1f3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314817"
---
# <a name="protectmasters-element-documentsettingstype-complextype-visio-xml"></a><span data-ttu-id="9b1e8-104">ProtectMasters 元素 (DocumentSettings_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="9b1e8-104">ProtectMasters element (DocumentSettings_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="9b1e8-105">指定是否阻止用户创建、编辑或删除主控形状。</span><span class="sxs-lookup"><span data-stu-id="9b1e8-105">Specifies whether the user is prevented from creating, editing, or deleting master shapes.</span></span> <span data-ttu-id="9b1e8-106">用户仍可以从主控形状创建新形状, 而不考虑此设置。</span><span class="sxs-lookup"><span data-stu-id="9b1e8-106">The user can still create new shapes from a master shape, regardless of this setting.</span></span> 
  
<span data-ttu-id="9b1e8-107">此元素的可能值的范围是 "0" 或 "1"。</span><span class="sxs-lookup"><span data-stu-id="9b1e8-107">The range of possible values for this element is either '0' or '1'.</span></span> <span data-ttu-id="9b1e8-108">值为 "0" 表示用户可以创建、编辑或删除主控形状。</span><span class="sxs-lookup"><span data-stu-id="9b1e8-108">A value of '0' indicates that users can create, edit, or delete master shapes.</span></span> <span data-ttu-id="9b1e8-109">值为 "1" 表示用户无法创建、编辑或删除主控形状。</span><span class="sxs-lookup"><span data-stu-id="9b1e8-109">A value of '1' indicates that users cannot create, edit, or delete master shapes.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="9b1e8-110">元素信息</span><span class="sxs-lookup"><span data-stu-id="9b1e8-110">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9b1e8-111">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="9b1e8-111">**Element type**</span></span> <br/> |[<span data-ttu-id="9b1e8-112">ProtectMasters_Type</span><span class="sxs-lookup"><span data-stu-id="9b1e8-112">ProtectMasters_Type</span></span>](protectmasters_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="9b1e8-113">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9b1e8-113">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="9b1e8-114">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9b1e8-114">**Schema file**</span></span> <br/> |<span data-ttu-id="9b1e8-115">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="9b1e8-115">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="9b1e8-116">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="9b1e8-116">**Document parts**</span></span> <br/> |<span data-ttu-id="9b1e8-117">document .xml</span><span class="sxs-lookup"><span data-stu-id="9b1e8-117">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9b1e8-118">定义</span><span class="sxs-lookup"><span data-stu-id="9b1e8-118">Definition</span></span>

```XML
< xs:element name="ProtectMasters" type="ProtectMasters_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="9b1e8-119">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9b1e8-119">Elements and attributes</span></span>

<span data-ttu-id="9b1e8-120">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="9b1e8-120">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="9b1e8-121">父元素</span><span class="sxs-lookup"><span data-stu-id="9b1e8-121">Parent elements</span></span>

|<span data-ttu-id="9b1e8-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="9b1e8-122">**Element**</span></span>|<span data-ttu-id="9b1e8-123">**类型**</span><span class="sxs-lookup"><span data-stu-id="9b1e8-123">**Type**</span></span>|<span data-ttu-id="9b1e8-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="9b1e8-124">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9b1e8-125">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="9b1e8-125">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9b1e8-126">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="9b1e8-126">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9b1e8-127">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="9b1e8-127">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="9b1e8-128">子元素</span><span class="sxs-lookup"><span data-stu-id="9b1e8-128">Child elements</span></span>

<span data-ttu-id="9b1e8-129">无。</span><span class="sxs-lookup"><span data-stu-id="9b1e8-129">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="9b1e8-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="9b1e8-130">Attributes</span></span>

<span data-ttu-id="9b1e8-131">无。</span><span class="sxs-lookup"><span data-stu-id="9b1e8-131">None.</span></span>
  

