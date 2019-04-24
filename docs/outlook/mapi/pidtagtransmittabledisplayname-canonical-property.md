---
title: PidTagTransmittableDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTransmittableDisplayName
api_type:
- COM
ms.assetid: aadd9086-b936-4067-bf7d-f54fc50e3c83
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e66fe8d3621c122ccc19bdde169f20f7d47a148d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331855"
---
# <a name="pidtagtransmittabledisplayname-canonical-property"></a><span data-ttu-id="7e0d9-103">PidTagTransmittableDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="7e0d9-103">PidTagTransmittableDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="7e0d9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7e0d9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7e0d9-105">在安全窗体中包含收件人的显示名称, 该名称不能更改。</span><span class="sxs-lookup"><span data-stu-id="7e0d9-105">Contains a recipient's display name in a secure form that cannot be changed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7e0d9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7e0d9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7e0d9-107">PR_TRANSMITABLE_DISPLAY_NAME、PR_TRANSMITABLE_DISPLAY_NAME_A、PR_TRANSMITABLE_DISPLAY_NAME_W</span><span class="sxs-lookup"><span data-stu-id="7e0d9-107">PR_TRANSMITABLE_DISPLAY_NAME, PR_TRANSMITABLE_DISPLAY_NAME_A, PR_TRANSMITABLE_DISPLAY_NAME_W</span></span>  <br/> |
|<span data-ttu-id="7e0d9-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="7e0d9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7e0d9-109">0x3A20</span><span class="sxs-lookup"><span data-stu-id="7e0d9-109">0x3A20</span></span>  <br/> |
|<span data-ttu-id="7e0d9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7e0d9-110">Data type:</span></span>  <br/> |<span data-ttu-id="7e0d9-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="7e0d9-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="7e0d9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7e0d9-112">Area:</span></span>  <br/> |<span data-ttu-id="7e0d9-113">Address</span><span class="sxs-lookup"><span data-stu-id="7e0d9-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7e0d9-114">注解</span><span class="sxs-lookup"><span data-stu-id="7e0d9-114">Remarks</span></span>

<span data-ttu-id="7e0d9-115">这些属性应由所有通讯簿提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="7e0d9-115">These properties should be implemented by all address book providers.</span></span> <span data-ttu-id="7e0d9-116">它们包含与邮件一起传输的收件人的显示名称的版本。</span><span class="sxs-lookup"><span data-stu-id="7e0d9-116">They contain the version of the recipient's display name that is transmitted with the message.</span></span> <span data-ttu-id="7e0d9-117">对于大多数通讯簿提供程序, 这些属性的值与**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值相同。</span><span class="sxs-lookup"><span data-stu-id="7e0d9-117">For most address book providers these properties have the same value as the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property.</span></span> <span data-ttu-id="7e0d9-118">没有安全显示名称的提供程序返回 PT_ERROR, MAPI 通过在名称的两边添加引号来更改显示名称。</span><span class="sxs-lookup"><span data-stu-id="7e0d9-118">Providers that do not have a secure display name return PT_ERROR and MAPI changes the display name by adding quotation marks around the name.</span></span>
  
<span data-ttu-id="7e0d9-119">客户端应用程序可以使用此属性来防止对条目进行更改或 "欺骗"。</span><span class="sxs-lookup"><span data-stu-id="7e0d9-119">A client application can use this property to prevent alteration or "spoofing" of entries.</span></span> <span data-ttu-id="7e0d9-120">哄骗的一个示例是, 将 john Doe 视为 john (专家) doe。</span><span class="sxs-lookup"><span data-stu-id="7e0d9-120">An example of spoofing is transmitting John Doe as John (What a Guy) Doe.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7e0d9-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="7e0d9-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7e0d9-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="7e0d9-122">Protocol specifications</span></span>

<span data-ttu-id="7e0d9-123">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7e0d9-123">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7e0d9-124">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7e0d9-124">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7e0d9-125">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7e0d9-125">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7e0d9-126">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="7e0d9-126">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="7e0d9-127">[[毫秒-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7e0d9-127">[[MS-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7e0d9-128">处理客户端与名称服务提供程序接口 (NSPI) 服务器的通信。</span><span class="sxs-lookup"><span data-stu-id="7e0d9-128">Handles a client's communications with a Name Service Provider Interface (NSPI) server.</span></span>
    
<span data-ttu-id="7e0d9-129">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7e0d9-129">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7e0d9-130">处理客户端与服务器之间的数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="7e0d9-130">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="7e0d9-131">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7e0d9-131">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7e0d9-132">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="7e0d9-132">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7e0d9-133">头文件</span><span class="sxs-lookup"><span data-stu-id="7e0d9-133">Header files</span></span>

<span data-ttu-id="7e0d9-134">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="7e0d9-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="7e0d9-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7e0d9-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="7e0d9-136">Mapitags</span><span class="sxs-lookup"><span data-stu-id="7e0d9-136">Mapitags.h</span></span>
  
> <span data-ttu-id="7e0d9-137">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7e0d9-137">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7e0d9-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e0d9-138">See also</span></span>



[<span data-ttu-id="7e0d9-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7e0d9-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7e0d9-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7e0d9-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7e0d9-141">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7e0d9-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7e0d9-142">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7e0d9-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

