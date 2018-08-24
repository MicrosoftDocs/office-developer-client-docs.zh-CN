---
title: PidLidBusinessCardCardPicture 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidBusinessCardCardPicture
api_type:
- COM
ms.assetid: 2c7af147-f7eb-41ef-8403-93584a2041ba
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1b83316b599ea9ee62bde78cbd734dfb6b2d8b80
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588494"
---
# <a name="pidlidbusinesscardcardpicture-canonical-property"></a><span data-ttu-id="e6a14-103">PidLidBusinessCardCardPicture 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6a14-103">PidLidBusinessCardCardPicture Canonical Property</span></span>

  
  
<span data-ttu-id="e6a14-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e6a14-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e6a14-105">包含要在名片上使用的图像。</span><span class="sxs-lookup"><span data-stu-id="e6a14-105">Contains the image to use on a business card.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e6a14-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e6a14-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e6a14-107">dispidBCCardPicture</span><span class="sxs-lookup"><span data-stu-id="e6a14-107">dispidBCCardPicture</span></span>  <br/> |
|<span data-ttu-id="e6a14-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="e6a14-108">Property set:</span></span>  <br/> |<span data-ttu-id="e6a14-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="e6a14-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="e6a14-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="e6a14-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="e6a14-111">0x00008041</span><span class="sxs-lookup"><span data-stu-id="e6a14-111">0x00008041</span></span>  <br/> |
|<span data-ttu-id="e6a14-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e6a14-112">Data type:</span></span>  <br/> |<span data-ttu-id="e6a14-113">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="e6a14-113">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="e6a14-114">区域：</span><span class="sxs-lookup"><span data-stu-id="e6a14-114">Area:</span></span>  <br/> |<span data-ttu-id="e6a14-115">联系人</span><span class="sxs-lookup"><span data-stu-id="e6a14-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e6a14-116">注解</span><span class="sxs-lookup"><span data-stu-id="e6a14-116">Remarks</span></span>

<span data-ttu-id="e6a14-117">此属性的值必须是可移植网络图形 (PNG) 或 JPEG 流。</span><span class="sxs-lookup"><span data-stu-id="e6a14-117">The value of this property must be either a portable network graphics (PNG) or JPEG stream.</span></span> <span data-ttu-id="e6a14-118">此属性应使用与**dispidBCDisplayDefinition** ([PidLidBusinessCardDisplayDefinition](pidlidbusinesscarddisplaydefinition-canonical-property.md)) 属性结合使用，如下所示： **dispidBCCardPicture**不应存在于联系人如果**dispidBCDisplayDefinition**不存在。</span><span class="sxs-lookup"><span data-stu-id="e6a14-118">This property should be used in conjunction with the **dispidBCDisplayDefinition** ([PidLidBusinessCardDisplayDefinition](pidlidbusinesscarddisplaydefinition-canonical-property.md)) property as follows: **dispidBCCardPicture** should not be present on a contact if **dispidBCDisplayDefinition** is not present.</span></span> <span data-ttu-id="e6a14-119">此属性也不应存在如果**dispidBCCardPicture**中的数据不需要一个名片图像。</span><span class="sxs-lookup"><span data-stu-id="e6a14-119">This property also should not be present if the data in **dispidBCCardPicture** does not require a card image.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e6a14-120">相关资源</span><span class="sxs-lookup"><span data-stu-id="e6a14-120">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e6a14-121">协议规范</span><span class="sxs-lookup"><span data-stu-id="e6a14-121">Protocol specifications</span></span>

<span data-ttu-id="e6a14-122">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6a14-122">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6a14-123">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="e6a14-123">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e6a14-124">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6a14-124">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6a14-125">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="e6a14-125">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e6a14-126">头文件</span><span class="sxs-lookup"><span data-stu-id="e6a14-126">Header files</span></span>

<span data-ttu-id="e6a14-127">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e6a14-127">Mapidefs.h</span></span>
  
> <span data-ttu-id="e6a14-128">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e6a14-128">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e6a14-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6a14-129">See also</span></span>



[<span data-ttu-id="e6a14-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e6a14-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e6a14-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6a14-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e6a14-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e6a14-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e6a14-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e6a14-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

