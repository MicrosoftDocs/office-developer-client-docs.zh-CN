---
title: ProtectMasters 元素 （DocumentSettings_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: edc46630-c320-6b4e-4747-961075dd5fd7
description: 指定是否禁止用户创建、 编辑或删除主控形状。 用户仍可以从主控形状，则无论此设置创建新的形状。
ms.openlocfilehash: cb576f267e076b06f2088ce53a18e9af36a46b0c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780980"
---
# <a name="protectmasters-element-documentsettingstype-complextype-visio-xml"></a><span data-ttu-id="13129-104">ProtectMasters 元素 （DocumentSettings_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="13129-104">ProtectMasters element (DocumentSettings_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="13129-105">指定是否禁止用户创建、 编辑或删除主控形状。</span><span class="sxs-lookup"><span data-stu-id="13129-105">Specifies whether the user is prevented from creating, editing, or deleting master shapes.</span></span> <span data-ttu-id="13129-106">用户仍可以从主控形状，则无论此设置创建新的形状。</span><span class="sxs-lookup"><span data-stu-id="13129-106">The user can still create new shapes from a master shape, regardless of this setting.</span></span> 
  
<span data-ttu-id="13129-107">此元素的可能值的范围是"0"或"1"。</span><span class="sxs-lookup"><span data-stu-id="13129-107">The range of possible values for this element is either '0' or '1'.</span></span> <span data-ttu-id="13129-108">"0"的值指示用户可以创建、 编辑或删除主控形状。</span><span class="sxs-lookup"><span data-stu-id="13129-108">A value of '0' indicates that users can create, edit, or delete master shapes.</span></span> <span data-ttu-id="13129-109">"1"的值表示用户无法创建、 编辑或删除主控形状。</span><span class="sxs-lookup"><span data-stu-id="13129-109">A value of '1' indicates that users cannot create, edit, or delete master shapes.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="13129-110">元素信息</span><span class="sxs-lookup"><span data-stu-id="13129-110">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="13129-111">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="13129-111">**Element type**</span></span> <br/> |[<span data-ttu-id="13129-112">ProtectMasters_Type</span><span class="sxs-lookup"><span data-stu-id="13129-112">ProtectMasters_Type</span></span>](protectmasters_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="13129-113">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="13129-113">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="13129-114">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="13129-114">**Schema file**</span></span> <br/> |<span data-ttu-id="13129-115">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="13129-115">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="13129-116">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="13129-116">**Document parts**</span></span> <br/> |<span data-ttu-id="13129-117">document.xml</span><span class="sxs-lookup"><span data-stu-id="13129-117">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="13129-118">定义</span><span class="sxs-lookup"><span data-stu-id="13129-118">Definition</span></span>

```XML
< xs:element name="ProtectMasters" type="ProtectMasters_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="13129-119">元素和属性</span><span class="sxs-lookup"><span data-stu-id="13129-119">Elements and attributes</span></span>

<span data-ttu-id="13129-120">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="13129-120">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="13129-121">父元素</span><span class="sxs-lookup"><span data-stu-id="13129-121">Parent elements</span></span>

|<span data-ttu-id="13129-122">**元素**</span><span class="sxs-lookup"><span data-stu-id="13129-122">**Element**</span></span>|<span data-ttu-id="13129-123">**类型**</span><span class="sxs-lookup"><span data-stu-id="13129-123">**Type**</span></span>|<span data-ttu-id="13129-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="13129-124">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="13129-125">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="13129-125">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="13129-126">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="13129-126">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="13129-127">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="13129-127">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="13129-128">子元素</span><span class="sxs-lookup"><span data-stu-id="13129-128">Child elements</span></span>

<span data-ttu-id="13129-129">无。</span><span class="sxs-lookup"><span data-stu-id="13129-129">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="13129-130">属性</span><span class="sxs-lookup"><span data-stu-id="13129-130">Attributes</span></span>

<span data-ttu-id="13129-131">无。</span><span class="sxs-lookup"><span data-stu-id="13129-131">None.</span></span>
  

