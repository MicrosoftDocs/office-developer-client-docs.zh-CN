---
title: CustomToolbarsFile 元素 （DocumentSettings_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c9789239-a919-97f6-8109-126bb1038be6
description: 包含定义自定义工具栏和状态栏文档的 Microsoft Visio 用户界面 (.vsu) 文件的名称。
ms.openlocfilehash: 3744caeb09e1fe865c9e669b9cacfada4cbef1c7
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392905"
---
# <a name="customtoolbarsfile-element-documentsettingstype-complextype-visio-xml"></a><span data-ttu-id="67ba8-103">CustomToolbarsFile 元素 （DocumentSettings_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="67ba8-103">CustomToolbarsFile element (DocumentSettings_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="67ba8-104">包含定义自定义工具栏和状态栏文档的 Microsoft Visio 用户界面 (.vsu) 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="67ba8-104">Contains the name of the Microsoft Visio user interface (.vsu) file that defines custom toolbars and status bars for a document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="67ba8-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="67ba8-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="67ba8-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="67ba8-106">**Element type**</span></span> <br/> |[<span data-ttu-id="67ba8-107">CustomToolbarsFile_Type</span><span class="sxs-lookup"><span data-stu-id="67ba8-107">CustomToolbarsFile_Type</span></span>](customtoolbarsfile_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="67ba8-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="67ba8-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="67ba8-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="67ba8-109">**Schema file**</span></span> <br/> |<span data-ttu-id="67ba8-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="67ba8-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="67ba8-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="67ba8-111">**Document parts**</span></span> <br/> |<span data-ttu-id="67ba8-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="67ba8-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="67ba8-113">定义</span><span class="sxs-lookup"><span data-stu-id="67ba8-113">Definition</span></span>

```XML
< xs:element name="CustomToolbarsFile" type="CustomToolbarsFile_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="67ba8-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="67ba8-114">Elements and attributes</span></span>

<span data-ttu-id="67ba8-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="67ba8-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="67ba8-116">父元素</span><span class="sxs-lookup"><span data-stu-id="67ba8-116">Parent elements</span></span>

|<span data-ttu-id="67ba8-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="67ba8-117">**Element**</span></span>|<span data-ttu-id="67ba8-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="67ba8-118">**Type**</span></span>|<span data-ttu-id="67ba8-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="67ba8-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="67ba8-120">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="67ba8-120">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="67ba8-121">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="67ba8-121">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="67ba8-122">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="67ba8-122">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="67ba8-123">子元素</span><span class="sxs-lookup"><span data-stu-id="67ba8-123">Child elements</span></span>

<span data-ttu-id="67ba8-124">无。</span><span class="sxs-lookup"><span data-stu-id="67ba8-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="67ba8-125">属性</span><span class="sxs-lookup"><span data-stu-id="67ba8-125">Attributes</span></span>

<span data-ttu-id="67ba8-126">无。</span><span class="sxs-lookup"><span data-stu-id="67ba8-126">None.</span></span>
  

