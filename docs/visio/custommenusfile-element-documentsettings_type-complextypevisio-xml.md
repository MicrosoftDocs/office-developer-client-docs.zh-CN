---
title: 'CustomMenusFile 元素 (DocumentSettings_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 4c88bde5-45e1-8030-e72c-a735c374a5c4
description: 包含定义文档的自定义菜单Visio快捷方式的 Microsoft Visio (.vsu) 文件的名称。
ms.openlocfilehash: 69eca703acf30a10296c13452c2f3e2a11521cd4
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540523"
---
# <a name="custommenusfile-element-documentsettings_type-complextype-visio-xml"></a><span data-ttu-id="60ce2-103">CustomMenusFile 元素 (DocumentSettings_Type COMPLEXType)  (Visio XML) </span><span class="sxs-lookup"><span data-stu-id="60ce2-103">CustomMenusFile element (DocumentSettings_Type complexType) (Visio XML)</span></span>

<span data-ttu-id="60ce2-104">包含定义文档的自定义菜单Visio快捷方式的 Microsoft Visio (.vsu) 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="60ce2-104">Contains the name of the Microsoft Visio user interface (.vsu) file that defines custom menus and accelerators for a document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="60ce2-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="60ce2-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="60ce2-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="60ce2-106">**Element type**</span></span> <br/> |[<span data-ttu-id="60ce2-107">CustomMenusFile_Type</span><span class="sxs-lookup"><span data-stu-id="60ce2-107">CustomMenusFile_Type</span></span>](custommenusfile_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="60ce2-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="60ce2-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="60ce2-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="60ce2-109">**Schema file**</span></span> <br/> |<span data-ttu-id="60ce2-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="60ce2-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="60ce2-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="60ce2-111">**Document parts**</span></span> <br/> |<span data-ttu-id="60ce2-112">document.xml</span><span class="sxs-lookup"><span data-stu-id="60ce2-112">document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="60ce2-113">定义</span><span class="sxs-lookup"><span data-stu-id="60ce2-113">Definition</span></span>

```XML
< xs:element name="CustomMenusFile" type="CustomMenusFile_Type" minOccurs="0" maxOccurs="1" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="60ce2-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="60ce2-114">Elements and attributes</span></span>

<span data-ttu-id="60ce2-115">如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="60ce2-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="60ce2-116">父元素</span><span class="sxs-lookup"><span data-stu-id="60ce2-116">Parent elements</span></span>

|<span data-ttu-id="60ce2-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="60ce2-117">**Element**</span></span>|<span data-ttu-id="60ce2-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="60ce2-118">**Type**</span></span>|<span data-ttu-id="60ce2-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="60ce2-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="60ce2-120">DocumentSettings</span><span class="sxs-lookup"><span data-stu-id="60ce2-120">DocumentSettings</span></span>](documentsettings-element-visiodocument_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="60ce2-121">DocumentSettings_Type</span><span class="sxs-lookup"><span data-stu-id="60ce2-121">DocumentSettings_Type</span></span>](documentsettings_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="60ce2-122">包含指定文档设置的元素。</span><span class="sxs-lookup"><span data-stu-id="60ce2-122">Contains elements that specify document settings.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="60ce2-123">子元素</span><span class="sxs-lookup"><span data-stu-id="60ce2-123">Child elements</span></span>

<span data-ttu-id="60ce2-124">无。</span><span class="sxs-lookup"><span data-stu-id="60ce2-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="60ce2-125">Attributes</span><span class="sxs-lookup"><span data-stu-id="60ce2-125">Attributes</span></span>

<span data-ttu-id="60ce2-126">无。</span><span class="sxs-lookup"><span data-stu-id="60ce2-126">None.</span></span>
  

