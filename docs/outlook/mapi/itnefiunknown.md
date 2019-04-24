---
title: ITnef IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef
api_type:
- COM
ms.assetid: eddca896-9497-4425-9904-87ef3cbae298
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1f815a914deb5e21f3d913abe46a84cc7a32b4ee
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315034"
---
# <a name="itnef--iunknown"></a><span data-ttu-id="1b42a-103">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1b42a-103">ITnef : IUnknown</span></span>

  
  
<span data-ttu-id="1b42a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1b42a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1b42a-105">提供将邮件系统不支持的 MAPI 属性封装为可附加到邮件的二进制流的方法。</span><span class="sxs-lookup"><span data-stu-id="1b42a-105">Provides methods for encapsulating MAPI properties that are not supported by a messaging system into binary streams that can be attached to messages.</span></span> <span data-ttu-id="1b42a-106">用于此封装的格式是不带传输的非特定封装格式 (TNEF)。</span><span class="sxs-lookup"><span data-stu-id="1b42a-106">The format used for this encapsulation is the Transport-Neutral Encapsulation Format (TNEF).</span></span> <span data-ttu-id="1b42a-107">然后, 目标传输提供程序或基于 MAPI 的客户端应用程序可以在收到包含 TNEF 附件的邮件的情况下恢复附件中的属性。</span><span class="sxs-lookup"><span data-stu-id="1b42a-107">The target transport provider or MAPI-based client application can then, on receiving a message that includes a TNEF attachment, recover the properties from the attachment.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1b42a-108">标头文件：</span><span class="sxs-lookup"><span data-stu-id="1b42a-108">Header file:</span></span>  <br/> |<span data-ttu-id="1b42a-109">Tnef</span><span class="sxs-lookup"><span data-stu-id="1b42a-109">Tnef.h</span></span>  <br/> |
|<span data-ttu-id="1b42a-110">公开者:</span><span class="sxs-lookup"><span data-stu-id="1b42a-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="1b42a-111">TNEF 对象</span><span class="sxs-lookup"><span data-stu-id="1b42a-111">TNEF objects</span></span>  <br/> |
|<span data-ttu-id="1b42a-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="1b42a-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="1b42a-113">MAPI</span><span class="sxs-lookup"><span data-stu-id="1b42a-113">MAPI</span></span>  <br/> |
|<span data-ttu-id="1b42a-114">调用者：</span><span class="sxs-lookup"><span data-stu-id="1b42a-114">Called by:</span></span>  <br/> |<span data-ttu-id="1b42a-115">传输提供程序、邮件存储提供程序和网关</span><span class="sxs-lookup"><span data-stu-id="1b42a-115">Transport providers, message store providers, and gateways</span></span>  <br/> |
|<span data-ttu-id="1b42a-116">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="1b42a-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="1b42a-117">IID_ITNEF</span><span class="sxs-lookup"><span data-stu-id="1b42a-117">IID_ITNEF</span></span>  <br/> |
|<span data-ttu-id="1b42a-118">指针类型:</span><span class="sxs-lookup"><span data-stu-id="1b42a-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="1b42a-119">LPTNEF</span><span class="sxs-lookup"><span data-stu-id="1b42a-119">LPTNEF</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="1b42a-120">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="1b42a-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="1b42a-121">AddProps</span><span class="sxs-lookup"><span data-stu-id="1b42a-121">AddProps</span></span>](itnef-addprops.md) <br/> |<span data-ttu-id="1b42a-122">启用呼叫服务提供程序或网关以将属性添加到邮件或附件的封装。</span><span class="sxs-lookup"><span data-stu-id="1b42a-122">Enables the calling service provider or gateway to add properties to the encapsulation of a message or an attachment.</span></span>  <br/> |
|[<span data-ttu-id="1b42a-123">ExtractProps</span><span class="sxs-lookup"><span data-stu-id="1b42a-123">ExtractProps</span></span>](itnef-extractprops.md) <br/> |<span data-ttu-id="1b42a-124">从 TNEF 封装中提取属性。</span><span class="sxs-lookup"><span data-stu-id="1b42a-124">Extracts the properties from a TNEF encapsulation.</span></span>  <br/> |
|[<span data-ttu-id="1b42a-125">Finish</span><span class="sxs-lookup"><span data-stu-id="1b42a-125">Finish</span></span>](itnef-finish.md) <br/> |<span data-ttu-id="1b42a-126">完成对排队和等待的所有 TNEF 操作的处理。</span><span class="sxs-lookup"><span data-stu-id="1b42a-126">Finishes processing for all TNEF operations that are queued and waiting.</span></span>  <br/> |
|[<span data-ttu-id="1b42a-127">OpenTaggedBody</span><span class="sxs-lookup"><span data-stu-id="1b42a-127">OpenTaggedBody</span></span>](itnef-opentaggedbody.md) <br/> |<span data-ttu-id="1b42a-128">打开封装的邮件的文本上的流接口。</span><span class="sxs-lookup"><span data-stu-id="1b42a-128">Opens a stream interface on the text of an encapsulated message.</span></span>  <br/> |
|[<span data-ttu-id="1b42a-129">SetProps</span><span class="sxs-lookup"><span data-stu-id="1b42a-129">SetProps</span></span>](itnef-setprops.md) <br/> |<span data-ttu-id="1b42a-130">设置封装的邮件或附件的一个或多个属性的值, 而不修改原始邮件或附件。</span><span class="sxs-lookup"><span data-stu-id="1b42a-130">Sets the value of one or more properties for an encapsulated message or attachment without modifying the original message or attachment.</span></span>  <br/> |
|[<span data-ttu-id="1b42a-131">EncodeRecips</span><span class="sxs-lookup"><span data-stu-id="1b42a-131">EncodeRecips</span></span>](itnef-encoderecips.md) <br/> |<span data-ttu-id="1b42a-132">在邮件的 TNEF 数据流中对邮件的收件人表的视图进行编码。</span><span class="sxs-lookup"><span data-stu-id="1b42a-132">Encodes a view for a message's recipient table in the TNEF data stream for the message.</span></span>  <br/> |
|[<span data-ttu-id="1b42a-133">FinishComponent</span><span class="sxs-lookup"><span data-stu-id="1b42a-133">FinishComponent</span></span>](itnef-finishcomponent.md) <br/> |<span data-ttu-id="1b42a-134">将邮件中的单个组件一次性处理为 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="1b42a-134">Processes individual components from a message one at a time into a TNEF stream.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1b42a-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b42a-135">See also</span></span>



[<span data-ttu-id="1b42a-136">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="1b42a-136">MAPI Interfaces</span></span>](mapi-interfaces.md)

