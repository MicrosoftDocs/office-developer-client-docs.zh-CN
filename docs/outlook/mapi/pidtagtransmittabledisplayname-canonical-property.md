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
ms.openlocfilehash: cc2704b69994cb80b15de82edad6c65423c6b5a6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591847"
---
# <a name="pidtagtransmittabledisplayname-canonical-property"></a><span data-ttu-id="fecce-103">PidTagTransmittableDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="fecce-103">PidTagTransmittableDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="fecce-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fecce-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fecce-105">包含不能更改安全窗体中的收件人的显示名称。</span><span class="sxs-lookup"><span data-stu-id="fecce-105">Contains a recipient's display name in a secure form that cannot be changed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fecce-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fecce-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fecce-107">PR_TRANSMITABLE_DISPLAY_NAME，PR_TRANSMITABLE_DISPLAY_NAME_A，PR_TRANSMITABLE_DISPLAY_NAME_W</span><span class="sxs-lookup"><span data-stu-id="fecce-107">PR_TRANSMITABLE_DISPLAY_NAME, PR_TRANSMITABLE_DISPLAY_NAME_A, PR_TRANSMITABLE_DISPLAY_NAME_W</span></span>  <br/> |
|<span data-ttu-id="fecce-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="fecce-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fecce-109">0x3A20</span><span class="sxs-lookup"><span data-stu-id="fecce-109">0x3A20</span></span>  <br/> |
|<span data-ttu-id="fecce-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fecce-110">Data type:</span></span>  <br/> |<span data-ttu-id="fecce-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="fecce-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="fecce-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fecce-112">Area:</span></span>  <br/> |<span data-ttu-id="fecce-113">Address</span><span class="sxs-lookup"><span data-stu-id="fecce-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fecce-114">注解</span><span class="sxs-lookup"><span data-stu-id="fecce-114">Remarks</span></span>

<span data-ttu-id="fecce-115">应通过所有通讯簿提供程序实现这些属性。</span><span class="sxs-lookup"><span data-stu-id="fecce-115">These properties should be implemented by all address book providers.</span></span> <span data-ttu-id="fecce-116">它们包含传输邮件的收件人的显示名称的版本。</span><span class="sxs-lookup"><span data-stu-id="fecce-116">They contain the version of the recipient's display name that is transmitted with the message.</span></span> <span data-ttu-id="fecce-117">对于大多数通讯簿提供程序这些属性具有相同的值的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="fecce-117">For most address book providers these properties have the same value as the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property.</span></span> <span data-ttu-id="fecce-118">没有返回 PT_ERROR 和 MAPI 更改的显示名称通过添加引号将名称括起来的安全的显示名称的提供程序。</span><span class="sxs-lookup"><span data-stu-id="fecce-118">Providers that do not have a secure display name return PT_ERROR and MAPI changes the display name by adding quotation marks around the name.</span></span>
  
<span data-ttu-id="fecce-119">客户端应用程序可以使用此属性，防止篡改或"假"的项。</span><span class="sxs-lookup"><span data-stu-id="fecce-119">A client application can use this property to prevent alteration or "spoofing" of entries.</span></span> <span data-ttu-id="fecce-120">欺骗的示例作为 (什么 Guy) John Doe 传输 John Doe。</span><span class="sxs-lookup"><span data-stu-id="fecce-120">An example of spoofing is transmitting John Doe as John (What a Guy) Doe.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="fecce-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="fecce-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="fecce-122">协议规范</span><span class="sxs-lookup"><span data-stu-id="fecce-122">Protocol specifications</span></span>

<span data-ttu-id="fecce-123">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fecce-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fecce-124">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="fecce-124">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="fecce-125">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fecce-125">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fecce-126">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="fecce-126">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="fecce-127">[[MS NSPI]](http://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fecce-127">[[MS-NSPI]](http://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fecce-128">处理与名称服务提供程序界面 (NSPI) 服务器的客户端的通信。</span><span class="sxs-lookup"><span data-stu-id="fecce-128">Handles a client's communications with a Name Service Provider Interface (NSPI) server.</span></span>
    
<span data-ttu-id="fecce-129">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fecce-129">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fecce-130">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="fecce-130">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="fecce-131">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="fecce-131">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="fecce-132">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="fecce-132">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="fecce-133">头文件</span><span class="sxs-lookup"><span data-stu-id="fecce-133">Header files</span></span>

<span data-ttu-id="fecce-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fecce-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="fecce-135">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fecce-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="fecce-136">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fecce-136">Mapitags.h</span></span>
  
> <span data-ttu-id="fecce-137">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fecce-137">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fecce-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fecce-138">See also</span></span>



[<span data-ttu-id="fecce-139">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fecce-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fecce-140">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fecce-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fecce-141">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fecce-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fecce-142">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fecce-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

