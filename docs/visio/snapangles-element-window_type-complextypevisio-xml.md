---
title: SnapAngles 元素 (Window_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5997f374-303a-92b6-6dd3-87ef81104af4
description: 包含 SnapAngle 元素的集合。
ms.openlocfilehash: 09a975b280a99fdc2535503b587efdd2143cf18b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334634"
---
# <a name="snapangles-element-windowtype-complextype-visio-xml"></a><span data-ttu-id="f878a-103">SnapAngles 元素 (Window_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="f878a-103">SnapAngles element (Window_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="f878a-104">包含**SnapAngle**元素的集合。</span><span class="sxs-lookup"><span data-stu-id="f878a-104">Contains a collection of **SnapAngle** elements.</span></span> 
  
## <a name="element-information"></a><span data-ttu-id="f878a-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="f878a-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="f878a-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="f878a-106">**Element type**</span></span> <br/> |[<span data-ttu-id="f878a-107">SnapAngles_Type</span><span class="sxs-lookup"><span data-stu-id="f878a-107">SnapAngles_Type</span></span>](snapangles_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="f878a-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="f878a-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="f878a-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="f878a-109">**Schema file**</span></span> <br/> |<span data-ttu-id="f878a-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="f878a-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="f878a-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="f878a-111">**Document parts**</span></span> <br/> |<span data-ttu-id="f878a-112">windows .xml</span><span class="sxs-lookup"><span data-stu-id="f878a-112">windows.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="f878a-113">定义</span><span class="sxs-lookup"><span data-stu-id="f878a-113">Definition</span></span>

```XML
< xs:element name="SnapAngles" type="SnapAngles_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="f878a-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="f878a-114">Elements and attributes</span></span>

<span data-ttu-id="f878a-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="f878a-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="f878a-116">父元素</span><span class="sxs-lookup"><span data-stu-id="f878a-116">Parent elements</span></span>

|<span data-ttu-id="f878a-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="f878a-117">**Element**</span></span>|<span data-ttu-id="f878a-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="f878a-118">**Type**</span></span>|<span data-ttu-id="f878a-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="f878a-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f878a-120">Window</span><span class="sxs-lookup"><span data-stu-id="f878a-120">Window</span></span>](window-element-windows_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f878a-121">Window_Type</span><span class="sxs-lookup"><span data-stu-id="f878a-121">Window_Type</span></span>](window_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f878a-122">代表 Microsoft Visio 实例中打开的窗口。</span><span class="sxs-lookup"><span data-stu-id="f878a-122">Represents an open window in a Microsoft Visio instance.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="f878a-123">子元素</span><span class="sxs-lookup"><span data-stu-id="f878a-123">Child elements</span></span>

|<span data-ttu-id="f878a-124">**元素**</span><span class="sxs-lookup"><span data-stu-id="f878a-124">**Element**</span></span>|<span data-ttu-id="f878a-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="f878a-125">**Type**</span></span>|<span data-ttu-id="f878a-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="f878a-126">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="f878a-127">SnapAngle</span><span class="sxs-lookup"><span data-stu-id="f878a-127">SnapAngle</span></span>](snapangle-element-snapangles_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="f878a-128">SnapAngle_Type</span><span class="sxs-lookup"><span data-stu-id="f878a-128">SnapAngle_Type</span></span>](snapangle_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="f878a-129">包含以度为单位指定对齐角度的浮点数字。</span><span class="sxs-lookup"><span data-stu-id="f878a-129">Contains a floating point number that specifies a snap angle in degrees.</span></span>  <br/> |
   
### <a name="attributes"></a><span data-ttu-id="f878a-130">Attributes</span><span class="sxs-lookup"><span data-stu-id="f878a-130">Attributes</span></span>

<span data-ttu-id="f878a-131">无。</span><span class="sxs-lookup"><span data-stu-id="f878a-131">None.</span></span>
  

