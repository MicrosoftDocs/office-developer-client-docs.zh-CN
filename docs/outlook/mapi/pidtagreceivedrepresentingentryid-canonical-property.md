---
title: PidTagReceivedRepresentingEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagReceivedRepresentingEntryId
api_type:
- COM
ms.assetid: 2ae2266c-f093-41e5-b4d0-e12aa0f03190
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 33e41343e0c159be20ed1499fc24223947975e1d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359092"
---
# <a name="pidtagreceivedrepresentingentryid-canonical-property"></a><span data-ttu-id="5299a-103">PidTagReceivedRepresentingEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="5299a-103">PidTagReceivedRepresentingEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="5299a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5299a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5299a-105">包含接收用户所代表的消息用户的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="5299a-105">Contains the entry identifier for the messaging user who is represented by the receiving user.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5299a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5299a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5299a-107">PR_RCVD_REPRESENTING_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="5299a-107">PR_RCVD_REPRESENTING_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="5299a-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5299a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5299a-109">0x0043</span><span class="sxs-lookup"><span data-stu-id="5299a-109">0x0043</span></span>  <br/> |
|<span data-ttu-id="5299a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5299a-110">Data type:</span></span>  <br/> |<span data-ttu-id="5299a-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="5299a-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="5299a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5299a-112">Area:</span></span>  <br/> |<span data-ttu-id="5299a-113">地址</span><span class="sxs-lookup"><span data-stu-id="5299a-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5299a-114">备注</span><span class="sxs-lookup"><span data-stu-id="5299a-114">Remarks</span></span>

<span data-ttu-id="5299a-115">此属性是接收用户所代表的邮件用户的地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="5299a-115">This property is one of the address properties for the messaging user who is being represented by the receiving user.</span></span> <span data-ttu-id="5299a-116">它必须由传入传输提供程序进行设置，该提供商还负责委派的授权或验证。</span><span class="sxs-lookup"><span data-stu-id="5299a-116">It must be set by the incoming transport provider, which is also responsible for authorization or verification of the delegate.</span></span> <span data-ttu-id="5299a-117">如果未表示任何消息用户，则此属性应设置为 **PR_RECEIVED_BY_ENTRYID** ([PidTagReceivedByEntryId](pidtagreceivedbyentryid-canonical-property.md)) 标识符。</span><span class="sxs-lookup"><span data-stu-id="5299a-117">If no messaging user is being represented, this property should be set to the entry identifier contained in the **PR_RECEIVED_BY_ENTRYID** ([PidTagReceivedByEntryId](pidtagreceivedbyentryid-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="5299a-118">答复代表其他客户端接收的邮件的客户端应用程序应该将此属性从接收的邮件复制到 **PR_SENT_REPRESENTING_ENTRYID** ([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md)) 属性中用于回复。</span><span class="sxs-lookup"><span data-stu-id="5299a-118">A client application replying to a message received on behalf of another client should copy this property from the received message into the **PR_SENT_REPRESENTING_ENTRYID** ([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md)) property for the reply.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5299a-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="5299a-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5299a-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="5299a-120">Protocol specifications</span></span>

<span data-ttu-id="5299a-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5299a-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5299a-122">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="5299a-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5299a-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5299a-123">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5299a-124">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="5299a-124">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="5299a-125">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5299a-125">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5299a-126">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="5299a-126">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="5299a-127">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5299a-127">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5299a-128">指定用于连接邮箱和将邮箱配置为代理的方法，以及代表其他用户操作时与邮件和日历对象的交互的方法。</span><span class="sxs-lookup"><span data-stu-id="5299a-128">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5299a-129">头文件</span><span class="sxs-lookup"><span data-stu-id="5299a-129">Header files</span></span>

<span data-ttu-id="5299a-130">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5299a-130">Mapidefs.h</span></span>
  
> <span data-ttu-id="5299a-131">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5299a-131">Provides data type definitions.</span></span>
    
<span data-ttu-id="5299a-132">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="5299a-132">Mapitags.h</span></span>
  
> <span data-ttu-id="5299a-133">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5299a-133">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5299a-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5299a-134">See also</span></span>



[<span data-ttu-id="5299a-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5299a-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5299a-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5299a-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5299a-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5299a-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5299a-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5299a-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

