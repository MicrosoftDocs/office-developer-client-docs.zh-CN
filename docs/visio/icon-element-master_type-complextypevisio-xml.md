---
title: 图标元素 （Master_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 80061e7d-dbcb-f7a1-b63a-052eee4ec7d7
description: 指定的 MIME （多用途 Internet 邮件扩展） 编码为主控形状的二进制图标 （.ico 格式） 文档中的元素。
ms.openlocfilehash: 80d9089442318c834a9a211941187588359f7041
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395754"
---
# <a name="icon-element-mastertype-complextype-visio-xml"></a><span data-ttu-id="6aa7d-103">图标元素 （Master_Type 复杂类型） (Visio XML)</span><span class="sxs-lookup"><span data-stu-id="6aa7d-103">Icon element (Master_Type complexType) ('Visio XML')</span></span>

<span data-ttu-id="6aa7d-104">指定的 MIME （多用途 Internet 邮件扩展） 编码为主控形状的二进制图标 （.ico 格式） 文档中的元素。</span><span class="sxs-lookup"><span data-stu-id="6aa7d-104">Specifies a MIME (Multipurpose Internet Mail Extensions) encoded binary icon (in .ico format) for a Master element in a document.</span></span>
  
## <a name="element-information"></a><span data-ttu-id="6aa7d-105">元素信息</span><span class="sxs-lookup"><span data-stu-id="6aa7d-105">Element information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6aa7d-106">**元素类型**</span><span class="sxs-lookup"><span data-stu-id="6aa7d-106">**Element type**</span></span> <br/> |[<span data-ttu-id="6aa7d-107">Icon_Type</span><span class="sxs-lookup"><span data-stu-id="6aa7d-107">Icon_Type</span></span>](icon_type-complextypevisio-xml.md) <br/> |
|<span data-ttu-id="6aa7d-108">**命名空间**</span><span class="sxs-lookup"><span data-stu-id="6aa7d-108">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|<span data-ttu-id="6aa7d-109">**架构文件**</span><span class="sxs-lookup"><span data-stu-id="6aa7d-109">**Schema file**</span></span> <br/> |<span data-ttu-id="6aa7d-110">VisioSchema15.xsd</span><span class="sxs-lookup"><span data-stu-id="6aa7d-110">VisioSchema15.xsd</span></span>  <br/> |
|<span data-ttu-id="6aa7d-111">**文档部件**</span><span class="sxs-lookup"><span data-stu-id="6aa7d-111">**Document parts**</span></span> <br/> |<span data-ttu-id="6aa7d-112">masters.xml</span><span class="sxs-lookup"><span data-stu-id="6aa7d-112">masters.xml</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="6aa7d-113">定义</span><span class="sxs-lookup"><span data-stu-id="6aa7d-113">Definition</span></span>

```XML
< xs:element name="Icon" type="Icon_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a><span data-ttu-id="6aa7d-114">元素和属性</span><span class="sxs-lookup"><span data-stu-id="6aa7d-114">Elements and attributes</span></span>

<span data-ttu-id="6aa7d-115">如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。</span><span class="sxs-lookup"><span data-stu-id="6aa7d-115">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="parent-elements"></a><span data-ttu-id="6aa7d-116">父元素</span><span class="sxs-lookup"><span data-stu-id="6aa7d-116">Parent elements</span></span>

|<span data-ttu-id="6aa7d-117">**元素**</span><span class="sxs-lookup"><span data-stu-id="6aa7d-117">**Element**</span></span>|<span data-ttu-id="6aa7d-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="6aa7d-118">**Type**</span></span>|<span data-ttu-id="6aa7d-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="6aa7d-119">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="6aa7d-120">Master</span><span class="sxs-lookup"><span data-stu-id="6aa7d-120">Master</span></span>](master-element-masters_type-complextypevisio-xml.md) <br/> |[<span data-ttu-id="6aa7d-121">Master_Type</span><span class="sxs-lookup"><span data-stu-id="6aa7d-121">Master_Type</span></span>](master_type-complextypevisio-xml.md) <br/> |<span data-ttu-id="6aa7d-122">指定与绘图中的主控形状。</span><span class="sxs-lookup"><span data-stu-id="6aa7d-122">Specifies a master in a drawing.</span></span>  <br/> |
   
### <a name="child-elements"></a><span data-ttu-id="6aa7d-123">子元素</span><span class="sxs-lookup"><span data-stu-id="6aa7d-123">Child elements</span></span>

<span data-ttu-id="6aa7d-124">无。</span><span class="sxs-lookup"><span data-stu-id="6aa7d-124">None.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="6aa7d-125">属性</span><span class="sxs-lookup"><span data-stu-id="6aa7d-125">Attributes</span></span>

<span data-ttu-id="6aa7d-126">无。</span><span class="sxs-lookup"><span data-stu-id="6aa7d-126">None.</span></span>
  

