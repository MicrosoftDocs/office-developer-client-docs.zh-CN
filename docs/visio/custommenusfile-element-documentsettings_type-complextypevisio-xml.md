---
title: CustomMenusFile 元素 (DocumentSettings_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4c88bde5-45e1-8030-e72c-a735c374a5c4
description: 包含为文档定义自定义菜单和加速器的 Microsoft Visio 用户界面 (vsu) 文件的名称。
ms.openlocfilehash: 347660abab266493254b4dc2b47150f3b80fd371
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282899"
---
# <a name="custommenusfile-element-documentsettingstype-complextype-visio-xml"></a><span data-ttu-id="f3b89-103">CustomMenusFile 元素 (DocumentSettings_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="f3b89-103">CustomMenusFile element (DocumentSettings_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="f3b89-104">包含为文档定义自定义菜单和加速器的 Microsoft Visio 用户界面 (vsu) 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f3b89-104">Contains the name of the Microsoft Visio user interface (.vsu) file that defines custom menus and accelerators for a document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="f3b89-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="f3b89-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f3b89-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="f3b89-106">**Element type**</span></span> <br/> |[<span data-ttu-id="f3b89-107">CustomMenusFile_Type</span><span class="sxs-lookup"><span data-stu-id="f3b89-107">CustomMenusFile_Type</span></span>](custommenusfile_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="f3b89-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f3b89-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="f3b89-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f3b89-109">**Schema file**</span></span> <br/> |<span data-ttu-id="f3b89-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="f3b89-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="f3b89-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="f3b89-111">**Document parts**</span></span> <br/> |<span data-ttu-id="f3b89-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="f3b89-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f3b89-113">定义</span><span class="sxs-lookup"><span data-stu-id="f3b89-113">Definition</span></span>

```XML
< xs:element name="CustomMenusFile" type="CustomMenusFile_Type" minOccurs="0" maxOccurs="1" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f3b89-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f3b89-114">Elements and attributes</span></span>

<span data-ttu-id="f3b89-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="f3b89-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="f3b89-116">父元素</span><span class="sxs-lookup"><span data-stu-id="f3b89-116">Parent elements</span></span>

|<span data-ttu-id="f3b89-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="f3b89-117">**Element**</span></span>|<span data-ttu-id="f3b89-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="f3b89-118">**Type**</span></span>|<span data-ttu-id="f3b89-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="f3b89-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f3b89-120">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="f3b89-120">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f3b89-121">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="f3b89-121">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f3b89-122">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="f3b89-122">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="f3b89-123">子元素</span><span class="sxs-lookup"><span data-stu-id="f3b89-123">Child elements</span></span>

<span data-ttu-id="f3b89-124">无。</span><span class="sxs-lookup"><span data-stu-id="f3b89-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="f3b89-125">Attributes</span><span class="sxs-lookup"><span data-stu-id="f3b89-125">Attributes</span></span>

<span data-ttu-id="f3b89-126">无。</span><span class="sxs-lookup"><span data-stu-id="f3b89-126">None.</span></span>
  

