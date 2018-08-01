---
title: 图标元素 （MasterShortcut_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 07d8ba86-8e35-d151-e6c1-150c37cc2acd
description: 文档中的 MasterShortcut 元素指定的 MIME （多用途 Internet 邮件扩展） 编码二进制图标 （.ico 格式）。
ms.openlocfilehash: 46ca7c3f6ba733d31823f6b47f083c46dd941c14
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780426"
---
# <a name="icon-element-mastershortcuttype-complextype-visio-xml"></a><span data-ttu-id="6df36-103">图标元素 （MasterShortcut_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="6df36-103">Icon element (MasterShortcut_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="6df36-104">文档中的 MasterShortcut 元素指定的 MIME （多用途 Internet 邮件扩展） 编码二进制图标 （.ico 格式）。</span><span class="sxs-lookup"><span data-stu-id="6df36-104">Specifies a MIME (Multipurpose Internet Mail Extensions) encoded binary icon (in .ico format) for a MasterShortcut element in a document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="6df36-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="6df36-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6df36-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="6df36-106">**Element type**</span></span> <br/> |[<span data-ttu-id="6df36-107">Icon_Type</span><span class="sxs-lookup"><span data-stu-id="6df36-107">Icon_Type</span></span>](icon_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="6df36-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="6df36-108">**Namespace**</span></span> <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="6df36-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="6df36-109">**Schema file**</span></span> <br/> |<span data-ttu-id="6df36-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="6df36-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="6df36-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="6df36-111">**Document parts**</span></span> <br/> |<span data-ttu-id="6df36-112">masters.xml</span><span class="sxs-lookup"><span data-stu-id="6df36-112">masters.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="6df36-113">定义</span><span class="sxs-lookup"><span data-stu-id="6df36-113">Definition</span></span>

```XML
< xs:element name="Icon" type="Icon_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="6df36-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="6df36-114">Elements and attributes</span></span>

<span data-ttu-id="6df36-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="6df36-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="6df36-116">父元素</span><span class="sxs-lookup"><span data-stu-id="6df36-116">Parent elements</span></span>

|<span data-ttu-id="6df36-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="6df36-117">**Element**</span></span>|<span data-ttu-id="6df36-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="6df36-118">**Type**</span></span>|<span data-ttu-id="6df36-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="6df36-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="6df36-120">MasterShortcut</span><span class="sxs-lookup"><span data-stu-id="6df36-120">MasterShortcut</span></span>](mastershortcut-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="6df36-121">MasterShortcut_Type</span><span class="sxs-lookup"><span data-stu-id="6df36-121">MasterShortcut_Type</span></span>](mastershortcut_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="6df36-122">指定未使用的主控形状格式。</span><span class="sxs-lookup"><span data-stu-id="6df36-122">Specifies an unused master format.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="6df36-123">子元素</span><span class="sxs-lookup"><span data-stu-id="6df36-123">Child elements</span></span>

<span data-ttu-id="6df36-124">无。</span><span class="sxs-lookup"><span data-stu-id="6df36-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="6df36-125">属性</span><span class="sxs-lookup"><span data-stu-id="6df36-125">Attributes</span></span>

<span data-ttu-id="6df36-126">无。</span><span class="sxs-lookup"><span data-stu-id="6df36-126">None.</span></span>
  

