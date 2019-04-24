---
title: Icon 元素 (MasterShortcut_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 07d8ba86-8e35-d151-e6c1-150c37cc2acd
description: 为文档中的 MasterShortcut 元素指定 MIME (多用途 Internet 邮件扩展) 编码的二进制图标 (在 .ico 格式中)。
ms.openlocfilehash: b2c9a662266620a10ed6d07592388f83bf2aedf6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344861"
---
# <a name="icon-element-mastershortcuttype-complextype-visio-xml"></a><span data-ttu-id="4762e-103">Icon 元素 (MasterShortcut_Type 复杂类型) ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="4762e-103">Icon element (MasterShortcut_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="4762e-104">为文档中的 MasterShortcut 元素指定 MIME (多用途 Internet 邮件扩展) 编码的二进制图标 (在 .ico 格式中)。</span><span class="sxs-lookup"><span data-stu-id="4762e-104">Specifies a MIME (Multipurpose Internet Mail Extensions) encoded binary icon (in .ico format) for a MasterShortcut element in a document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="4762e-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="4762e-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4762e-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="4762e-106">**Element type**</span></span> <br/> |[<span data-ttu-id="4762e-107">Icon_Type</span><span class="sxs-lookup"><span data-stu-id="4762e-107">Icon_Type</span></span>](icon_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="4762e-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="4762e-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="4762e-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="4762e-109">**Schema file**</span></span> <br/> |<span data-ttu-id="4762e-110">VisioSchema15</span><span class="sxs-lookup"><span data-stu-id="4762e-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="4762e-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="4762e-111">**Document parts**</span></span> <br/> |<span data-ttu-id="4762e-112">主控 xml</span><span class="sxs-lookup"><span data-stu-id="4762e-112">masters.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="4762e-113">定义</span><span class="sxs-lookup"><span data-stu-id="4762e-113">Definition</span></span>

```XML
< xs:element name="Icon" type="Icon_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="4762e-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="4762e-114">Elements and attributes</span></span>

<span data-ttu-id="4762e-115">如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。</span><span class="sxs-lookup"><span data-stu-id="4762e-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="4762e-116">父元素</span><span class="sxs-lookup"><span data-stu-id="4762e-116">Parent elements</span></span>

|<span data-ttu-id="4762e-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="4762e-117">**Element**</span></span>|<span data-ttu-id="4762e-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="4762e-118">**Type**</span></span>|<span data-ttu-id="4762e-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="4762e-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="4762e-120">MasterShortcut</span><span class="sxs-lookup"><span data-stu-id="4762e-120">MasterShortcut</span></span>](mastershortcut-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="4762e-121">MasterShortcut_Type</span><span class="sxs-lookup"><span data-stu-id="4762e-121">MasterShortcut_Type</span></span>](mastershortcut_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="4762e-122">指定未使用的主控形状格式。</span><span class="sxs-lookup"><span data-stu-id="4762e-122">Specifies an unused master format.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="4762e-123">子元素</span><span class="sxs-lookup"><span data-stu-id="4762e-123">Child elements</span></span>

<span data-ttu-id="4762e-124">无。</span><span class="sxs-lookup"><span data-stu-id="4762e-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="4762e-125">Attributes</span><span class="sxs-lookup"><span data-stu-id="4762e-125">Attributes</span></span>

<span data-ttu-id="4762e-126">无。</span><span class="sxs-lookup"><span data-stu-id="4762e-126">None.</span></span>
  

