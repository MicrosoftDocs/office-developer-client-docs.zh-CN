---
title: PidTagResponsibility 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagResponsibility
api_type:
- COM
ms.assetid: 1e8ccef1-db0a-4230-9bd0-87540b53e890
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9dba26ab6948d7190521ff31a8732c4b058ab7c9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778231"
---
# <a name="pidtagresponsibility-canonical-property"></a><span data-ttu-id="ffed8-103">PidTagResponsibility 规范属性</span><span class="sxs-lookup"><span data-stu-id="ffed8-103">PidTagResponsibility Canonical Property</span></span>

  
  
<span data-ttu-id="ffed8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ffed8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ffed8-105">包含 TRUE 如果某些传输提供程序已经接受邮件传递到此收件人和 FALSE，如果 MAPI 后台处理程序认为该传输提供程序应接受责任的责任。</span><span class="sxs-lookup"><span data-stu-id="ffed8-105">Contains TRUE if some transport provider has already accepted responsibility for delivering the message to this recipient, and FALSE if the MAPI spooler considers that this transport provider should accept responsibility.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ffed8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ffed8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ffed8-107">PR_RESPONSIBILITY</span><span class="sxs-lookup"><span data-stu-id="ffed8-107">PR_RESPONSIBILITY</span></span>  <br/> |
|<span data-ttu-id="ffed8-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="ffed8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ffed8-109">0x0E0F</span><span class="sxs-lookup"><span data-stu-id="ffed8-109">0x0E0F</span></span>  <br/> |
|<span data-ttu-id="ffed8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ffed8-110">Data type:</span></span>  <br/> |<span data-ttu-id="ffed8-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="ffed8-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="ffed8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ffed8-112">Area:</span></span>  <br/> |<span data-ttu-id="ffed8-113">MAPI 非可传送</span><span class="sxs-lookup"><span data-stu-id="ffed8-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ffed8-114">说明</span><span class="sxs-lookup"><span data-stu-id="ffed8-114">Remarks</span></span>

<span data-ttu-id="ffed8-115">当 MAPI 后台处理程序提供的出站邮件到传输提供程序，通过[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)，它将该属性设置为 FALSE 的所有收件人为其 MAPI 后台处理程序认为该传输提供程序负责，和 TRUE 所有其他收件人。</span><span class="sxs-lookup"><span data-stu-id="ffed8-115">When the MAPI spooler presents an outbound message to a transport provider, through [IXPLogon::SubmitMessage](ixplogon-submitmessage.md), it sets this property to FALSE for all recipients for which the MAPI spooler considers that transport provider responsible, and TRUE for all other recipients.</span></span> <span data-ttu-id="ffed8-116">传输提供程序应尝试处理与**PR_RESPONSIBILITY**设置为 FALSE 的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="ffed8-116">The transport provider should attempt to handle all recipients with **PR_RESPONSIBILITY** set to FALSE.</span></span> <span data-ttu-id="ffed8-117">成功发送，或最终发送给收件人，出现故障后传输提供程序应将此属性设置为 TRUE 源消息以指示它已接受该收件人的责任。</span><span class="sxs-lookup"><span data-stu-id="ffed8-117">After successfully sending, or conclusively failing to send, to a recipient, the transport provider should set this property to TRUE in the source message to indicate that it has accepted responsibility for that recipient.</span></span> 
  
<span data-ttu-id="ffed8-118">如果在检查收件人后, 传输提供程序决定它无法或不应该处理，传输提供程序应保留**PR_RESPONSIBILITY**设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="ffed8-118">If, after examining a recipient, a transport provider decides that it cannot or should not handle it, the transport provider should leave **PR_RESPONSIBILITY** set to FALSE.</span></span> <span data-ttu-id="ffed8-119">然后 MAPI 后台处理程序将查找另一个传输提供程序可以处理该收件人。</span><span class="sxs-lookup"><span data-stu-id="ffed8-119">The MAPI spooler will then look for another transport provider that can handle that recipient.</span></span> <span data-ttu-id="ffed8-120">MAPI 后台处理程序的任何传输提供程序为其接受责任任何收件人最终会创建原件报告。</span><span class="sxs-lookup"><span data-stu-id="ffed8-120">The MAPI spooler ultimately creates a nondelivery report for any recipients for which no transport provider accepts responsibility.</span></span> 
  
<span data-ttu-id="ffed8-121">如果传输提供程序尝试，并且无法将邮件传递，它应调用[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)方法，以指示为 MAPI 失败的原因，以便 MAPI 可以生成原件报告。</span><span class="sxs-lookup"><span data-stu-id="ffed8-121">If the transport provider attempts and fails to deliver the message, it should call the [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) method to indicate to MAPI the reasons for the failure, so that MAPI can generate a nondelivery report.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ffed8-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="ffed8-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ffed8-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="ffed8-123">Protocol specifications</span></span>

<span data-ttu-id="ffed8-124">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ffed8-124">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ffed8-125">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="ffed8-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ffed8-126">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ffed8-126">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ffed8-127">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="ffed8-127">Handles the order and flow for data transfers between a client and server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ffed8-128">头文件</span><span class="sxs-lookup"><span data-stu-id="ffed8-128">Header files</span></span>

<span data-ttu-id="ffed8-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ffed8-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="ffed8-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ffed8-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="ffed8-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ffed8-131">Mapitags.h</span></span>
  
> <span data-ttu-id="ffed8-132">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ffed8-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ffed8-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffed8-133">See also</span></span>



[<span data-ttu-id="ffed8-134">PidTagDeleteAfterSubmit 规范属性</span><span class="sxs-lookup"><span data-stu-id="ffed8-134">PidTagDeleteAfterSubmit Canonical Property</span></span>](pidtagdeleteaftersubmit-canonical-property.md)


[<span data-ttu-id="ffed8-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ffed8-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ffed8-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ffed8-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ffed8-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ffed8-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ffed8-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ffed8-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

