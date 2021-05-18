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
ms.openlocfilehash: 15bf61e71a2c230f7891c738661f839ecddb52e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330119"
---
# <a name="pidtagresponsibility-canonical-property"></a><span data-ttu-id="4df80-103">PidTagResponsibility 规范属性</span><span class="sxs-lookup"><span data-stu-id="4df80-103">PidTagResponsibility Canonical Property</span></span>

  
  
<span data-ttu-id="4df80-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4df80-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4df80-105">如果某些传输提供程序已接受将邮件传送给此收件人的责任，则包含 TRUE;如果 MAPI 后台处理程序认为此传输提供程序应接受责任，则包含 FALSE。</span><span class="sxs-lookup"><span data-stu-id="4df80-105">Contains TRUE if some transport provider has already accepted responsibility for delivering the message to this recipient, and FALSE if the MAPI spooler considers that this transport provider should accept responsibility.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4df80-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4df80-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4df80-107">PR_RESPONSIBILITY</span><span class="sxs-lookup"><span data-stu-id="4df80-107">PR_RESPONSIBILITY</span></span>  <br/> |
|<span data-ttu-id="4df80-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4df80-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4df80-109">0x0E0F</span><span class="sxs-lookup"><span data-stu-id="4df80-109">0x0E0F</span></span>  <br/> |
|<span data-ttu-id="4df80-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4df80-110">Data type:</span></span>  <br/> |<span data-ttu-id="4df80-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="4df80-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="4df80-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4df80-112">Area:</span></span>  <br/> |<span data-ttu-id="4df80-113">MAPI 不可传输</span><span class="sxs-lookup"><span data-stu-id="4df80-113">MAPI non-transmittable</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4df80-114">备注</span><span class="sxs-lookup"><span data-stu-id="4df80-114">Remarks</span></span>

<span data-ttu-id="4df80-115">当 MAPI 后台处理程序通过 [IXPLogon：：SubmitMessage](ixplogon-submitmessage.md)向传输提供程序显示出站邮件时，它将 MAPI 后台处理程序认为其负责传输提供程序的所有收件人的此属性都为 FALSE，对于所有其他收件人，此属性为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="4df80-115">When the MAPI spooler presents an outbound message to a transport provider, through [IXPLogon::SubmitMessage](ixplogon-submitmessage.md), it sets this property to FALSE for all recipients for which the MAPI spooler considers that transport provider responsible, and TRUE for all other recipients.</span></span> <span data-ttu-id="4df80-116">传输提供程序应尝试处理所有收件人，PR_RESPONSIBILITY **设置为** FALSE。</span><span class="sxs-lookup"><span data-stu-id="4df80-116">The transport provider should attempt to handle all recipients with **PR_RESPONSIBILITY** set to FALSE.</span></span> <span data-ttu-id="4df80-117">成功向收件人发送或成功发送后，传输提供程序应在源邮件中将此属性设置为 TRUE，以指示其已接受该收件人的责任。</span><span class="sxs-lookup"><span data-stu-id="4df80-117">After successfully sending, or conclusively failing to send, to a recipient, the transport provider should set this property to TRUE in the source message to indicate that it has accepted responsibility for that recipient.</span></span> 
  
<span data-ttu-id="4df80-118">如果在检查收件人之后，传输提供程序决定不能或不应处理该收件人，则传输提供程序应 **PR_RESPONSIBILITY设置为** FALSE。</span><span class="sxs-lookup"><span data-stu-id="4df80-118">If, after examining a recipient, a transport provider decides that it cannot or should not handle it, the transport provider should leave **PR_RESPONSIBILITY** set to FALSE.</span></span> <span data-ttu-id="4df80-119">然后，MAPI 后台处理程序将查找另一个可以处理该收件人的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="4df80-119">The MAPI spooler will then look for another transport provider that can handle that recipient.</span></span> <span data-ttu-id="4df80-120">MAPI 后台处理程序最终会为任何传输提供程序不承担责任的收件人创建未送达报告。</span><span class="sxs-lookup"><span data-stu-id="4df80-120">The MAPI spooler ultimately creates a nondelivery report for any recipients for which no transport provider accepts responsibility.</span></span> 
  
<span data-ttu-id="4df80-121">如果传输提供程序尝试传递邮件但失败，则它应调用 [IMAPISupport：：StatusRecips](imapisupport-statusrecips.md) 方法向 MAPI 指示失败的原因，以便 MAPI 可以生成未送达报告。</span><span class="sxs-lookup"><span data-stu-id="4df80-121">If the transport provider attempts and fails to deliver the message, it should call the [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) method to indicate to MAPI the reasons for the failure, so that MAPI can generate a nondelivery report.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="4df80-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="4df80-122">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4df80-123">协议规范</span><span class="sxs-lookup"><span data-stu-id="4df80-123">Protocol specifications</span></span>

<span data-ttu-id="4df80-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4df80-124">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4df80-125">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="4df80-125">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4df80-126">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4df80-126">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4df80-127">处理客户端和服务器之间数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="4df80-127">Handles the order and flow for data transfers between a client and server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4df80-128">头文件</span><span class="sxs-lookup"><span data-stu-id="4df80-128">Header files</span></span>

<span data-ttu-id="4df80-129">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4df80-129">Mapidefs.h</span></span>
  
> <span data-ttu-id="4df80-130">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4df80-130">Provides data type definitions.</span></span>
    
<span data-ttu-id="4df80-131">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4df80-131">Mapitags.h</span></span>
  
> <span data-ttu-id="4df80-132">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4df80-132">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4df80-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4df80-133">See also</span></span>



[<span data-ttu-id="4df80-134">PidTagDeleteAfterSubmit 规范属性</span><span class="sxs-lookup"><span data-stu-id="4df80-134">PidTagDeleteAfterSubmit Canonical Property</span></span>](pidtagdeleteaftersubmit-canonical-property.md)


[<span data-ttu-id="4df80-135">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4df80-135">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4df80-136">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4df80-136">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4df80-137">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4df80-137">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4df80-138">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4df80-138">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

