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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 34d29b9a15cc6f5a3f88a6477738eb63904e1fdb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776708"
---
# <a name="pidlidbusinesscarddisplaydefinition-canonical-property"></a><span data-ttu-id="6ce68-103">PidLidBusinessCardDisplayDefinition 规范属性</span><span class="sxs-lookup"><span data-stu-id="6ce68-103">PidLidBusinessCardDisplayDefinition Canonical Property</span></span>

  
  
<span data-ttu-id="6ce68-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6ce68-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6ce68-105">包含用户自定义作为名片显示联系人的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6ce68-105">Contains user-customization details for displaying a contact as a business card.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6ce68-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="6ce68-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6ce68-107">dispidBCDisplayDefinition</span><span class="sxs-lookup"><span data-stu-id="6ce68-107">dispidBCDisplayDefinition</span></span>  <br/> |
|<span data-ttu-id="6ce68-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="6ce68-108">Property set:</span></span>  <br/> |<span data-ttu-id="6ce68-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="6ce68-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="6ce68-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="6ce68-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="6ce68-111">0x00008040</span><span class="sxs-lookup"><span data-stu-id="6ce68-111">0x00008040</span></span>  <br/> |
|<span data-ttu-id="6ce68-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6ce68-112">Data type:</span></span>  <br/> |<span data-ttu-id="6ce68-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="6ce68-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="6ce68-114">区域：</span><span class="sxs-lookup"><span data-stu-id="6ce68-114">Area:</span></span>  <br/> |<span data-ttu-id="6ce68-115">联系人</span><span class="sxs-lookup"><span data-stu-id="6ce68-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6ce68-116">备注</span><span class="sxs-lookup"><span data-stu-id="6ce68-116">Remarks</span></span>

<span data-ttu-id="6ce68-117">名片的布局可以表示为一个图像和文本字段的数量。</span><span class="sxs-lookup"><span data-stu-id="6ce68-117">The layout of a business card can be represented as an image and a number of text fields.</span></span> <span data-ttu-id="6ce68-118">图像可以是联系人的照片或卡片图片。</span><span class="sxs-lookup"><span data-stu-id="6ce68-118">The image can be either a contact photo, or a card picture.</span></span> <span data-ttu-id="6ce68-119">文本字段包含中设置该联系人上的另一个属性和用户提供可选的自定义的标签字符串的值。</span><span class="sxs-lookup"><span data-stu-id="6ce68-119">Text fields consist of a value from another property set on the contact and an optional customized label string provided by the user.</span></span> <span data-ttu-id="6ce68-120">请注意，多字节值存储在-little-endian 缓冲区中的格式。</span><span class="sxs-lookup"><span data-stu-id="6ce68-120">Note that multi-byte values are stored in little-endian format in the buffer.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6ce68-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="6ce68-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6ce68-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="6ce68-122">Protocol specifications</span></span>

<span data-ttu-id="6ce68-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6ce68-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6ce68-124">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="6ce68-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6ce68-125">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6ce68-125">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6ce68-126">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="6ce68-126">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6ce68-127">头文件</span><span class="sxs-lookup"><span data-stu-id="6ce68-127">Header files</span></span>

<span data-ttu-id="6ce68-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6ce68-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="6ce68-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6ce68-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6ce68-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ce68-130">See also</span></span>



[<span data-ttu-id="6ce68-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6ce68-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6ce68-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6ce68-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6ce68-133">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6ce68-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6ce68-134">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6ce68-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

