---
title: PidTagSendRichInfo 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSendRichInfo
api_type:
- COM
ms.assetid: e85fc766-197a-484f-b600-68cd28a052a2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a1db4ba7a70695b17631ca13f1728043be8164bd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575964"
---
# <a name="pidtagsendrichinfo-canonical-property"></a><span data-ttu-id="6dde3-103">PidTagSendRichInfo 规范属性</span><span class="sxs-lookup"><span data-stu-id="6dde3-103">PidTagSendRichInfo Canonical Property</span></span>

  
  
<span data-ttu-id="6dde3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6dde3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6dde3-105">如果收件人可以接收所有的消息内容，包括富文本格式 (RTF) 和对象链接与嵌入 (OLE) 对象，包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="6dde3-105">Contains TRUE if the recipient can receive all message content, including Rich Text Format (RTF) and Object Linking and Embedding (OLE) objects.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6dde3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6dde3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6dde3-107">PR_SEND_RICH_INFO</span><span class="sxs-lookup"><span data-stu-id="6dde3-107">PR_SEND_RICH_INFO</span></span>  <br/> |
|<span data-ttu-id="6dde3-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="6dde3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6dde3-109">0x3A40</span><span class="sxs-lookup"><span data-stu-id="6dde3-109">0x3A40</span></span>  <br/> |
|<span data-ttu-id="6dde3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6dde3-110">Data type:</span></span>  <br/> |<span data-ttu-id="6dde3-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="6dde3-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="6dde3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6dde3-112">Area:</span></span>  <br/> |<span data-ttu-id="6dde3-113">Address</span><span class="sxs-lookup"><span data-stu-id="6dde3-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6dde3-114">注解</span><span class="sxs-lookup"><span data-stu-id="6dde3-114">Remarks</span></span>

<span data-ttu-id="6dde3-115">建议通讯组列表和邮件用户对象公开此属性。</span><span class="sxs-lookup"><span data-stu-id="6dde3-115">It is recommended that distribution list and messaging user objects expose this property.</span></span> 
  
<span data-ttu-id="6dde3-116">此属性指示发件人是否考虑要启用了 MAPI 的收件人。</span><span class="sxs-lookup"><span data-stu-id="6dde3-116">This property indicates whether the sender considers the recipient to be MAPI-enabled.</span></span> 
  
<span data-ttu-id="6dde3-117">此属性设置为 TRUE 时, 的传输和网关可以传输邮件，包括 RTF 和 OLE 对象的全部内容。</span><span class="sxs-lookup"><span data-stu-id="6dde3-117">When this property is set to TRUE, the transport and gateway can transmit the full content of the message, including RTF and OLE objects.</span></span> <span data-ttu-id="6dde3-118">传输提供程序和网关应使用传输中性封装格式 (TNEF) 来封装不涉及的所有消息系统的本机任何属性。</span><span class="sxs-lookup"><span data-stu-id="6dde3-118">The transport provider and gateway should use Transport Neutral Encapsulation Format (TNEF) to encapsulate any properties that are not native to all the messaging systems involved.</span></span> 
  
<span data-ttu-id="6dde3-119">当此属性设置为 FALSE 时，则传输提供程序和网关可以自由地放弃其本机客户端不能使用的消息内容。</span><span class="sxs-lookup"><span data-stu-id="6dde3-119">When this property is set to FALSE, the transport provider and gateway are free to discard message content that their native clients cannot use.</span></span> <span data-ttu-id="6dde3-120">例如，当客户端不支持 RTF，传输提供程序可以发送纯文本。</span><span class="sxs-lookup"><span data-stu-id="6dde3-120">For example, when the clients do not support RTF, the transport provider can send only plain text.</span></span> 
  
<span data-ttu-id="6dde3-121">当未设置此属性时，由传输提供程序、 邮件传输代理 (MTA)，或网关实现确定默认行为。</span><span class="sxs-lookup"><span data-stu-id="6dde3-121">When this property is not set, default behavior is determined by the implementation of the transport provider, message transfer agent (MTA), or gateway.</span></span> <span data-ttu-id="6dde3-122">通讯簿提供程序不需要支持此属性。</span><span class="sxs-lookup"><span data-stu-id="6dde3-122">Address book providers are not required to support this property.</span></span> <span data-ttu-id="6dde3-123">例如，可以选择紧密耦合的通讯簿和传输提供程序发送 TNEF 但从未使用 rtf 格式。</span><span class="sxs-lookup"><span data-stu-id="6dde3-123">For example, a tightly coupled address book and transport provider can choose to send TNEF but never use RTF.</span></span> 
  
<span data-ttu-id="6dde3-124">客户端不应假定传输提供程序和网关将使用 TNEF 自己的计划。</span><span class="sxs-lookup"><span data-stu-id="6dde3-124">The client should not assume the transport provider and gateway will use TNEF on their own initiative.</span></span> <span data-ttu-id="6dde3-125">某些传输提供程序和支持 TNEF 的网关传输而不考虑此属性的值，但其他人拒绝来构建或发送 TNEF，如果它未设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="6dde3-125">Some transport providers and gateways that support TNEF transmit it without regard to the value of this property, but others decline to construct or send TNEF if it is not set to TRUE.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6dde3-126">此属性，并基于及其值的决策的设置位于单独对每个收件人。</span><span class="sxs-lookup"><span data-stu-id="6dde3-126">The setting of this property, and the decisions based on its value, are on a per-recipient basis.</span></span> 
  
<span data-ttu-id="6dde3-127">默认情况下，MAPI 将值设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="6dde3-127">By default, MAPI sets the value to TRUE.</span></span> <span data-ttu-id="6dde3-128">调用[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)或调用[IMAPISupport::CreateOneOff](imapisupport-createoneoff.md)提供商的客户端可以设置**MAPI_SEND_NO_RICH_INFO**位_ulFlags_参数，这将导致 MAPI 将此属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="6dde3-128">A client calling [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) or a provider calling [IMAPISupport::CreateOneOff](imapisupport-createoneoff.md) can set the **MAPI_SEND_NO_RICH_INFO** bit in the  _ulFlags_ parameter, which causes MAPI to set this property to FALSE.</span></span> <span data-ttu-id="6dde3-129">One-offs 通过用户界面创建使用指定的创建模板的值。</span><span class="sxs-lookup"><span data-stu-id="6dde3-129">One-offs created by the user interface use the value specified by the creating template.</span></span> 
  
<span data-ttu-id="6dde3-130">在调用[IAddrBook::ResolveName](iaddrbook-resolvename.md)方法时名称无法解析，但可以被解释为 Internet 地址 (SMTP)，此属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="6dde3-130">On calls to the [IAddrBook::ResolveName](iaddrbook-resolvename.md) method when the name cannot be resolved but can be interpreted as an Internet address (SMTP), this property is set to FALSE.</span></span> <span data-ttu-id="6dde3-131">若要将其视为 Internet 地址，未解析的显示名称必须是项的格式 X@Y。Z，如"pete@pinecone.com"。</span><span class="sxs-lookup"><span data-stu-id="6dde3-131">To be construed as an Internet address, the display name of the unresolved entry must be in the format X@Y.Z, such as "pete@pinecone.com".</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="6dde3-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="6dde3-132">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="6dde3-133">协议规范</span><span class="sxs-lookup"><span data-stu-id="6dde3-133">Protocol specifications</span></span>

<span data-ttu-id="6dde3-134">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6dde3-134">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6dde3-135">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="6dde3-135">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="6dde3-136">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6dde3-136">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6dde3-137">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="6dde3-137">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="6dde3-138">[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6dde3-138">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6dde3-139">指定的属性和操作所允许的电子邮件消息对象。</span><span class="sxs-lookup"><span data-stu-id="6dde3-139">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="6dde3-140">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6dde3-140">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="6dde3-141">从 Internet 标准电子邮件消息对象的约定。</span><span class="sxs-lookup"><span data-stu-id="6dde3-141">from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="6dde3-142">头文件</span><span class="sxs-lookup"><span data-stu-id="6dde3-142">Header files</span></span>

<span data-ttu-id="6dde3-143">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6dde3-143">Mapidefs.h</span></span>
  
> <span data-ttu-id="6dde3-144">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6dde3-144">Provides data type definitions.</span></span>
    
<span data-ttu-id="6dde3-145">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6dde3-145">Mapitags.h</span></span>
  
> <span data-ttu-id="6dde3-146">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6dde3-146">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6dde3-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6dde3-147">See also</span></span>



[<span data-ttu-id="6dde3-148">PidTagAttachDataObject 规范属性</span><span class="sxs-lookup"><span data-stu-id="6dde3-148">PidTagAttachDataObject Canonical Property</span></span>](pidtagattachdataobject-canonical-property.md)


[<span data-ttu-id="6dde3-149">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6dde3-149">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6dde3-150">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6dde3-150">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6dde3-151">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6dde3-151">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6dde3-152">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6dde3-152">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

