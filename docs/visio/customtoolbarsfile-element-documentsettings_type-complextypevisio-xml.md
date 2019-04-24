---
title: CustomToolbarsFile 元素 (DocumentSettings_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c9789239-a919-97f6-8109-126bb1038be6
description: 包含 Microsoft Visio 用户界面 (vsu) 文件的名称, 该文件定义文档的自定义工具栏和状态栏。
ms.openlocfilehash: 3744caeb09e1fe865c9e669b9cacfada4cbef1c7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282857"
---
# <a name="customtoolbarsfile-element-documentsettingstype-complextype-visio-xml"></a><span data-ttu-id="84ea3-103">CustomToolbarsFile 元素 (DocumentSettings_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="84ea3-103">CustomToolbarsFile element (DocumentSettings_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="84ea3-104">包含 Microsoft Visio 用户界面 (vsu) 文件的名称, 该文件定义文档的自定义工具栏和状态栏。</span><span class="sxs-lookup"><span data-stu-id="84ea3-104">Contains the name of the Microsoft Visio user interface (.vsu) file that defines custom toolbars and status bars for a document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="84ea3-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="84ea3-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="84ea3-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="84ea3-106">**Element type**</span></span> <br/> |[<span data-ttu-id="84ea3-107">CustomToolbarsFile_Type</span><span class="sxs-lookup"><span data-stu-id="84ea3-107">CustomToolbarsFile_Type</span></span>](customtoolbarsfile_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="84ea3-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="84ea3-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="84ea3-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="84ea3-109">**Schema file**</span></span> <br/> |<span data-ttu-id="84ea3-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="84ea3-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="84ea3-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="84ea3-111">**Document parts**</span></span> <br/> |<span data-ttu-id="84ea3-112">document .xml</span><span class="sxs-lookup"><span data-stu-id="84ea3-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="84ea3-113">定义</span><span class="sxs-lookup"><span data-stu-id="84ea3-113">Definition</span></span>

```XML
< xs:element name="CustomToolbarsFile" type="CustomToolbarsFile_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="84ea3-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="84ea3-114">Elements and attributes</span></span>

<span data-ttu-id="84ea3-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="84ea3-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="84ea3-116">父元素</span><span class="sxs-lookup"><span data-stu-id="84ea3-116">Parent elements</span></span>

|<span data-ttu-id="84ea3-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="84ea3-117">**Element**</span></span>|<span data-ttu-id="84ea3-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="84ea3-118">**Type**</span></span>|<span data-ttu-id="84ea3-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="84ea3-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="84ea3-120">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="84ea3-120">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="84ea3-121">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="84ea3-121">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="84ea3-122">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="84ea3-122">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="84ea3-123">子元素</span><span class="sxs-lookup"><span data-stu-id="84ea3-123">Child elements</span></span>

<span data-ttu-id="84ea3-124">无。</span><span class="sxs-lookup"><span data-stu-id="84ea3-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="84ea3-125">Attributes</span><span class="sxs-lookup"><span data-stu-id="84ea3-125">Attributes</span></span>

<span data-ttu-id="84ea3-126">无。</span><span class="sxs-lookup"><span data-stu-id="84ea3-126">None.</span></span>
  

