---
title: GlueSettings 元素 （DocumentSettings_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a5675dea-3b78-9fc2-c1c0-51fefe45c6e3
description: 指定当在文档中启用粘附形状粘附到的对象。
ms.openlocfilehash: c85f1b201a15f5edb7e3ddb0f21553d80b9dd17a
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398141"
---
# <a name="gluesettings-element-documentsettingstype-complextype-visio-xml"></a><span data-ttu-id="9f5c0-103">GlueSettings 元素 （DocumentSettings_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="9f5c0-103">GlueSettings element (DocumentSettings_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="9f5c0-104">指定当在文档中启用粘附形状粘附到的对象。</span><span class="sxs-lookup"><span data-stu-id="9f5c0-104">Specifies the objects that shapes glue to when glue is enabled in the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="9f5c0-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="9f5c0-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9f5c0-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="9f5c0-106">**Element type**</span></span> <br/> |[<span data-ttu-id="9f5c0-107">GlueSettings_Type</span><span class="sxs-lookup"><span data-stu-id="9f5c0-107">GlueSettings_Type</span></span>](gluesettings_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="9f5c0-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="9f5c0-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="9f5c0-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="9f5c0-109">**Schema file**</span></span> <br/> |<span data-ttu-id="9f5c0-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="9f5c0-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="9f5c0-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="9f5c0-111">**Document parts**</span></span> <br/> |<span data-ttu-id="9f5c0-112">windows.xml、 document.xml</span><span class="sxs-lookup"><span data-stu-id="9f5c0-112">windows.xml, document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="9f5c0-113">定义</span><span class="sxs-lookup"><span data-stu-id="9f5c0-113">Definition</span></span>

```XML
< xs:element name="GlueSettings" type="GlueSettings_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="9f5c0-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="9f5c0-114">Elements and attributes</span></span>

<span data-ttu-id="9f5c0-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="9f5c0-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="9f5c0-116">父元素</span><span class="sxs-lookup"><span data-stu-id="9f5c0-116">Parent elements</span></span>

|<span data-ttu-id="9f5c0-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="9f5c0-117">**Element**</span></span>|<span data-ttu-id="9f5c0-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="9f5c0-118">**Type**</span></span>|<span data-ttu-id="9f5c0-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="9f5c0-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="9f5c0-120">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="9f5c0-120">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="9f5c0-121">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="9f5c0-121">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="9f5c0-122">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="9f5c0-122">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="9f5c0-123">子元素</span><span class="sxs-lookup"><span data-stu-id="9f5c0-123">Child elements</span></span>

<span data-ttu-id="9f5c0-124">无。</span><span class="sxs-lookup"><span data-stu-id="9f5c0-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="9f5c0-125">属性</span><span class="sxs-lookup"><span data-stu-id="9f5c0-125">Attributes</span></span>

<span data-ttu-id="9f5c0-126">无。</span><span class="sxs-lookup"><span data-stu-id="9f5c0-126">None.</span></span>
  

