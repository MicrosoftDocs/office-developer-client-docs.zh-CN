---
title: GlueSettings 元素 (Window_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b5292f82-f299-ea96-6101-ebb799bbec9a
description: 指定在文档中启用粘附时形状粘附到的对象。
ms.openlocfilehash: 46d1ec09729cd26cfa3fc2f78a39edb6e7b7b02f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351210"
---
# <a name="gluesettings-element-windowtype-complextype-visio-xml"></a><span data-ttu-id="a9d00-103">GlueSettings 元素 (Window_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="a9d00-103">GlueSettings element (Window_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="a9d00-104">指定在文档中启用粘附时形状粘附到的对象。</span><span class="sxs-lookup"><span data-stu-id="a9d00-104">Specifies the objects that shapes glue to when glue is enabled in the document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="a9d00-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="a9d00-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="a9d00-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="a9d00-106">**Element type**</span></span> <br/> |[<span data-ttu-id="a9d00-107">GlueSettings_Type</span><span class="sxs-lookup"><span data-stu-id="a9d00-107">GlueSettings_Type</span></span>](gluesettings_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="a9d00-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="a9d00-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="a9d00-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="a9d00-109">**Schema file**</span></span> <br/> |<span data-ttu-id="a9d00-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="a9d00-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="a9d00-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="a9d00-111">**Document parts**</span></span> <br/> |<span data-ttu-id="a9d00-112">windows .xml、document、.xml</span><span class="sxs-lookup"><span data-stu-id="a9d00-112">windows.xml, document.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="a9d00-113">定义</span><span class="sxs-lookup"><span data-stu-id="a9d00-113">Definition</span></span>

```XML
< xs:element name="GlueSettings" type="GlueSettings_Type" minOccurs="0" maxOccurs="1" >
</xs:element>
```

## <a name="elements-and-attributes"></a><span data-ttu-id="a9d00-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="a9d00-114">Elements and attributes</span></span>

<span data-ttu-id="a9d00-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="a9d00-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="a9d00-116">父元素</span><span class="sxs-lookup"><span data-stu-id="a9d00-116">Parent elements</span></span>

|<span data-ttu-id="a9d00-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="a9d00-117">**Element**</span></span>|<span data-ttu-id="a9d00-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="a9d00-118">**Type**</span></span>|<span data-ttu-id="a9d00-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="a9d00-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="a9d00-120">Window</span><span class="sxs-lookup"><span data-stu-id="a9d00-120">Window</span></span>](window-element-windows_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="a9d00-121">Window_Type</span><span class="sxs-lookup"><span data-stu-id="a9d00-121">Window_Type</span></span>](window_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="a9d00-122">代表 Microsoft Visio 实例中打开的窗口。</span><span class="sxs-lookup"><span data-stu-id="a9d00-122">Represents an open window in a Microsoft Visio instance.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="a9d00-123">子元素</span><span class="sxs-lookup"><span data-stu-id="a9d00-123">Child elements</span></span>

<span data-ttu-id="a9d00-124">无。</span><span class="sxs-lookup"><span data-stu-id="a9d00-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="a9d00-125">Attributes</span><span class="sxs-lookup"><span data-stu-id="a9d00-125">Attributes</span></span>

<span data-ttu-id="a9d00-126">无。</span><span class="sxs-lookup"><span data-stu-id="a9d00-126">None.</span></span>
  

