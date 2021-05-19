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
ms.openlocfilehash: a7ad27d757d4ed6df58c597bf17d9e5412f83457
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342516"
---
# <a name="pidtagsendrichinfo-canonical-property"></a><span data-ttu-id="ba9d6-103">PidTagSendRichInfo 规范属性</span><span class="sxs-lookup"><span data-stu-id="ba9d6-103">PidTagSendRichInfo Canonical Property</span></span>

  
  
<span data-ttu-id="ba9d6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ba9d6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ba9d6-105">如果收件人可以接收所有邮件内容（包括 RTF (RTF 格式) 对象链接和嵌入 OLE 对象） (TRUE) TRUE。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-105">Contains TRUE if the recipient can receive all message content, including Rich Text Format (RTF) and Object Linking and Embedding (OLE) objects.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ba9d6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ba9d6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ba9d6-107">PR_SEND_RICH_INFO</span><span class="sxs-lookup"><span data-stu-id="ba9d6-107">PR_SEND_RICH_INFO</span></span>  <br/> |
|<span data-ttu-id="ba9d6-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ba9d6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ba9d6-109">0x3A40</span><span class="sxs-lookup"><span data-stu-id="ba9d6-109">0x3A40</span></span>  <br/> |
|<span data-ttu-id="ba9d6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ba9d6-110">Data type:</span></span>  <br/> |<span data-ttu-id="ba9d6-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="ba9d6-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="ba9d6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ba9d6-112">Area:</span></span>  <br/> |<span data-ttu-id="ba9d6-113">地址</span><span class="sxs-lookup"><span data-stu-id="ba9d6-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ba9d6-114">备注</span><span class="sxs-lookup"><span data-stu-id="ba9d6-114">Remarks</span></span>

<span data-ttu-id="ba9d6-115">建议通讯组列表和消息传递用户对象公开此属性。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-115">It is recommended that distribution list and messaging user objects expose this property.</span></span> 
  
<span data-ttu-id="ba9d6-116">此属性指示发件人是否认为收件人已启用 MAPI。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-116">This property indicates whether the sender considers the recipient to be MAPI-enabled.</span></span> 
  
<span data-ttu-id="ba9d6-117">当此属性设置为 TRUE 时，传输和网关可以传输邮件的完整内容，包括 RTF 和 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-117">When this property is set to TRUE, the transport and gateway can transmit the full content of the message, including RTF and OLE objects.</span></span> <span data-ttu-id="ba9d6-118">传输提供程序和网关应该使用传输中性封装格式 (TNEF) 来封装不是涉及的所有邮件系统本机的任何属性。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-118">The transport provider and gateway should use Transport Neutral Encapsulation Format (TNEF) to encapsulate any properties that are not native to all the messaging systems involved.</span></span> 
  
<span data-ttu-id="ba9d6-119">当此属性设置为 FALSE 时，传输提供程序和网关可以随意丢弃其本机客户端无法使用的邮件内容。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-119">When this property is set to FALSE, the transport provider and gateway are free to discard message content that their native clients cannot use.</span></span> <span data-ttu-id="ba9d6-120">例如，当客户端不支持 RTF 时，传输提供程序只能发送纯文本。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-120">For example, when the clients do not support RTF, the transport provider can send only plain text.</span></span> 
  
<span data-ttu-id="ba9d6-121">未设置此属性时，默认行为由传输提供程序、邮件传输代理或网关 (MTA) 确定。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-121">When this property is not set, default behavior is determined by the implementation of the transport provider, message transfer agent (MTA), or gateway.</span></span> <span data-ttu-id="ba9d6-122">通讯簿提供程序不需要支持此属性。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-122">Address book providers are not required to support this property.</span></span> <span data-ttu-id="ba9d6-123">例如，紧密耦合的通讯簿和传输提供程序可以选择发送 TNEF，但从不使用 RTF。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-123">For example, a tightly coupled address book and transport provider can choose to send TNEF but never use RTF.</span></span> 
  
<span data-ttu-id="ba9d6-124">客户端不应假定传输提供程序和网关将自行使用 TNEF。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-124">The client should not assume the transport provider and gateway will use TNEF on their own initiative.</span></span> <span data-ttu-id="ba9d6-125">一些支持 TNEF 的传输提供程序和网关会传输它，而不考虑此属性的值，但其他传输提供程序和网关拒绝构建或发送 TNEF（如果未设置为 TRUE）。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-125">Some transport providers and gateways that support TNEF transmit it without regard to the value of this property, but others decline to construct or send TNEF if it is not set to TRUE.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ba9d6-126">此属性的设置以及基于其值的决策基于每个收件人。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-126">The setting of this property, and the decisions based on its value, are on a per-recipient basis.</span></span> 
  
<span data-ttu-id="ba9d6-127">默认情况下，MAPI 将值设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-127">By default, MAPI sets the value to TRUE.</span></span> <span data-ttu-id="ba9d6-128">调用 [IAddrBook：：CreateOneOff](iaddrbook-createoneoff.md)的客户端或调用 [IMAPISupport：：CreateOneOff](imapisupport-createoneoff.md)的提供程序可以在 _ulFlags_ 参数中设置 **MAPI_SEND_NO_RICH_INFO** 位，这将导致 MAPI 将此属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-128">A client calling [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) or a provider calling [IMAPISupport::CreateOneOff](imapisupport-createoneoff.md) can set the **MAPI_SEND_NO_RICH_INFO** bit in the  _ulFlags_ parameter, which causes MAPI to set this property to FALSE.</span></span> <span data-ttu-id="ba9d6-129">用户界面创建的一次使用创建模板指定的值。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-129">One-offs created by the user interface use the value specified by the creating template.</span></span> 
  
<span data-ttu-id="ba9d6-130">当名称无法解析，但可以解释为 SMTP (Internet 地址时，调用 [IAddrBook：：ResolveName](iaddrbook-resolvename.md)) 时，此属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-130">On calls to the [IAddrBook::ResolveName](iaddrbook-resolvename.md) method when the name cannot be resolved but can be interpreted as an Internet address (SMTP), this property is set to FALSE.</span></span> <span data-ttu-id="ba9d6-131">要解释为 Internet 地址，显示名称条目的名称必须采用 X@Y。Z，例如"pete@pinecone.com"。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-131">To be construed as an Internet address, the display name of the unresolved entry must be in the format X@Y.Z, such as "pete@pinecone.com".</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ba9d6-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="ba9d6-132">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ba9d6-133">协议规范</span><span class="sxs-lookup"><span data-stu-id="ba9d6-133">Protocol specifications</span></span>

<span data-ttu-id="ba9d6-134">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ba9d6-134">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ba9d6-135">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-135">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ba9d6-136">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ba9d6-136">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ba9d6-137">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-137">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="ba9d6-138">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ba9d6-138">[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ba9d6-139">指定电子邮件对象允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-139">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
<span data-ttu-id="ba9d6-140">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ba9d6-140">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ba9d6-141">从 Internet 标准电子邮件约定到邮件对象。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-141">from Internet standard email conventions to message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ba9d6-142">头文件</span><span class="sxs-lookup"><span data-stu-id="ba9d6-142">Header files</span></span>

<span data-ttu-id="ba9d6-143">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ba9d6-143">Mapidefs.h</span></span>
  
> <span data-ttu-id="ba9d6-144">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-144">Provides data type definitions.</span></span>
    
<span data-ttu-id="ba9d6-145">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ba9d6-145">Mapitags.h</span></span>
  
> <span data-ttu-id="ba9d6-146">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ba9d6-146">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ba9d6-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba9d6-147">See also</span></span>



[<span data-ttu-id="ba9d6-148">PidTagAttachDataObject 规范属性</span><span class="sxs-lookup"><span data-stu-id="ba9d6-148">PidTagAttachDataObject Canonical Property</span></span>](pidtagattachdataobject-canonical-property.md)


[<span data-ttu-id="ba9d6-149">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ba9d6-149">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ba9d6-150">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ba9d6-150">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ba9d6-151">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ba9d6-151">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ba9d6-152">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ba9d6-152">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

