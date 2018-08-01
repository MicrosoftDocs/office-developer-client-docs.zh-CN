---
title: ProtectShapes 元素 （DocumentSettings_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e3835fc6-0ae6-b8c3-b1d0-bf893d4a9470
description: 指定是否禁止用户选择已设置为 1 其 LockSelect 元素的形状。
ms.openlocfilehash: 98bb9c565f0dccc2add4a03e3dd6cd82a52015c7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780993"
---
# <a name="protectshapes-element-documentsettingstype-complextype-visio-xml"></a><span data-ttu-id="6b8a3-103">ProtectShapes 元素 （DocumentSettings_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="6b8a3-103">ProtectShapes element (DocumentSettings_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="6b8a3-104">指定是否禁止用户选择已设置为 1 其**LockSelect**元素的形状。</span><span class="sxs-lookup"><span data-stu-id="6b8a3-104">Specifies whether the user is prevented from selecting shapes that have their **LockSelect** element set to 1.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="6b8a3-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="6b8a3-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6b8a3-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="6b8a3-106">**Element type**</span></span> <br/> |[<span data-ttu-id="6b8a3-107">ProtectShapes_Type</span><span class="sxs-lookup"><span data-stu-id="6b8a3-107">ProtectShapes_Type</span></span>](protectshapes_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="6b8a3-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="6b8a3-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="6b8a3-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="6b8a3-109">**Schema file**</span></span> <br/> |<span data-ttu-id="6b8a3-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="6b8a3-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="6b8a3-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="6b8a3-111">**Document parts**</span></span> <br/> |<span data-ttu-id="6b8a3-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="6b8a3-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="6b8a3-113">定义</span><span class="sxs-lookup"><span data-stu-id="6b8a3-113">Definition</span></span>

```XML
< xs:element name="ProtectShapes" type="ProtectShapes_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="6b8a3-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="6b8a3-114">Elements and attributes</span></span>

<span data-ttu-id="6b8a3-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="6b8a3-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="6b8a3-116">父元素</span><span class="sxs-lookup"><span data-stu-id="6b8a3-116">Parent elements</span></span>

|<span data-ttu-id="6b8a3-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="6b8a3-117">**Element**</span></span>|<span data-ttu-id="6b8a3-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="6b8a3-118">**Type**</span></span>|<span data-ttu-id="6b8a3-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="6b8a3-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="6b8a3-120">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="6b8a3-120">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="6b8a3-121">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="6b8a3-121">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="6b8a3-122">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="6b8a3-122">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="6b8a3-123">子元素</span><span class="sxs-lookup"><span data-stu-id="6b8a3-123">Child elements</span></span>

<span data-ttu-id="6b8a3-124">无。</span><span class="sxs-lookup"><span data-stu-id="6b8a3-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="6b8a3-125">属性</span><span class="sxs-lookup"><span data-stu-id="6b8a3-125">Attributes</span></span>

<span data-ttu-id="6b8a3-126">无。</span><span class="sxs-lookup"><span data-stu-id="6b8a3-126">None.</span></span>
  

