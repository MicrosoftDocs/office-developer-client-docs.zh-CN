---
title: PidLidBusinessCardDisplayDefinition 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidBusinessCardDisplayDefinition
api_type:
- COM
ms.assetid: c0b956dd-7139-49e3-a32a-d70bfb11e0b1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f25f8a538ff61bc7e04c234efd7404b1c866d64d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342033"
---
# <a name="pidlidbusinesscarddisplaydefinition-canonical-property"></a><span data-ttu-id="f6a8e-103">PidLidBusinessCardDisplayDefinition 规范属性</span><span class="sxs-lookup"><span data-stu-id="f6a8e-103">PidLidBusinessCardDisplayDefinition Canonical Property</span></span>

  
  
<span data-ttu-id="f6a8e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f6a8e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f6a8e-105">包含用于将联系人显示为名片的用户自定义详细信息。</span><span class="sxs-lookup"><span data-stu-id="f6a8e-105">Contains user-customization details for displaying a contact as a business card.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f6a8e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f6a8e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f6a8e-107">dispidBCDisplayDefinition</span><span class="sxs-lookup"><span data-stu-id="f6a8e-107">dispidBCDisplayDefinition</span></span>  <br/> |
|<span data-ttu-id="f6a8e-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="f6a8e-108">Property set:</span></span>  <br/> |<span data-ttu-id="f6a8e-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="f6a8e-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="f6a8e-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="f6a8e-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="f6a8e-111">0x00008040</span><span class="sxs-lookup"><span data-stu-id="f6a8e-111">0x00008040</span></span>  <br/> |
|<span data-ttu-id="f6a8e-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f6a8e-112">Data type:</span></span>  <br/> |<span data-ttu-id="f6a8e-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="f6a8e-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="f6a8e-114">区域：</span><span class="sxs-lookup"><span data-stu-id="f6a8e-114">Area:</span></span>  <br/> |<span data-ttu-id="f6a8e-115">Contact</span><span class="sxs-lookup"><span data-stu-id="f6a8e-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f6a8e-116">注解</span><span class="sxs-lookup"><span data-stu-id="f6a8e-116">Remarks</span></span>

<span data-ttu-id="f6a8e-117">名片的布局可以表示为图像和多个文本字段。</span><span class="sxs-lookup"><span data-stu-id="f6a8e-117">The layout of a business card can be represented as an image and a number of text fields.</span></span> <span data-ttu-id="f6a8e-118">图像可以是联系人照片, 也可以是卡片图片。</span><span class="sxs-lookup"><span data-stu-id="f6a8e-118">The image can be either a contact photo, or a card picture.</span></span> <span data-ttu-id="f6a8e-119">文本字段由来自联系人的其他属性集和用户提供的可选自定义标签字符串中的值组成。</span><span class="sxs-lookup"><span data-stu-id="f6a8e-119">Text fields consist of a value from another property set on the contact and an optional customized label string provided by the user.</span></span> <span data-ttu-id="f6a8e-120">请注意, 多字节值以小端格式存储在缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="f6a8e-120">Note that multi-byte values are stored in little-endian format in the buffer.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f6a8e-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="f6a8e-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f6a8e-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="f6a8e-122">Protocol specifications</span></span>

<span data-ttu-id="f6a8e-123">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f6a8e-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f6a8e-124">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="f6a8e-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f6a8e-125">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f6a8e-125">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f6a8e-126">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="f6a8e-126">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f6a8e-127">头文件</span><span class="sxs-lookup"><span data-stu-id="f6a8e-127">Header files</span></span>

<span data-ttu-id="f6a8e-128">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="f6a8e-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="f6a8e-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f6a8e-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f6a8e-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6a8e-130">See also</span></span>



[<span data-ttu-id="f6a8e-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f6a8e-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f6a8e-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f6a8e-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f6a8e-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f6a8e-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f6a8e-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f6a8e-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

