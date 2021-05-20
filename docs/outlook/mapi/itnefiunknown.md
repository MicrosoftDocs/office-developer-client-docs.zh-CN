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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428513"
---
# <a name="itnef--iunknown"></a><span data-ttu-id="56e01-103">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="56e01-103">ITnef : IUnknown</span></span>

  
  
<span data-ttu-id="56e01-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="56e01-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="56e01-105">提供用于将邮件系统不支持的 MAPI 属性封装到可附加到邮件的二进制流的方法。</span><span class="sxs-lookup"><span data-stu-id="56e01-105">Provides methods for encapsulating MAPI properties that are not supported by a messaging system into binary streams that can be attached to messages.</span></span> <span data-ttu-id="56e01-106">用于此封装的格式是 TNEF Transport-Neutral封装 (格式) 。</span><span class="sxs-lookup"><span data-stu-id="56e01-106">The format used for this encapsulation is the Transport-Neutral Encapsulation Format (TNEF).</span></span> <span data-ttu-id="56e01-107">然后，目标传输提供程序或基于 MAPI 的客户端应用程序可以在接收包含 TNEF 附件的邮件时，从附件恢复属性。</span><span class="sxs-lookup"><span data-stu-id="56e01-107">The target transport provider or MAPI-based client application can then, on receiving a message that includes a TNEF attachment, recover the properties from the attachment.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="56e01-108">标头文件：</span><span class="sxs-lookup"><span data-stu-id="56e01-108">Header file:</span></span>  <br/> |<span data-ttu-id="56e01-109">Tnef.h</span><span class="sxs-lookup"><span data-stu-id="56e01-109">Tnef.h</span></span>  <br/> |
|<span data-ttu-id="56e01-110">公开者：</span><span class="sxs-lookup"><span data-stu-id="56e01-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="56e01-111">TNEF 对象</span><span class="sxs-lookup"><span data-stu-id="56e01-111">TNEF objects</span></span>  <br/> |
|<span data-ttu-id="56e01-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="56e01-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="56e01-113">MAPI</span><span class="sxs-lookup"><span data-stu-id="56e01-113">MAPI</span></span>  <br/> |
|<span data-ttu-id="56e01-114">调用者：</span><span class="sxs-lookup"><span data-stu-id="56e01-114">Called by:</span></span>  <br/> |<span data-ttu-id="56e01-115">传输提供程序、邮件存储提供程序和网关</span><span class="sxs-lookup"><span data-stu-id="56e01-115">Transport providers, message store providers, and gateways</span></span>  <br/> |
|<span data-ttu-id="56e01-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="56e01-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="56e01-117">IID_ITNEF</span><span class="sxs-lookup"><span data-stu-id="56e01-117">IID_ITNEF</span></span>  <br/> |
|<span data-ttu-id="56e01-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="56e01-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="56e01-119">LPTNEF</span><span class="sxs-lookup"><span data-stu-id="56e01-119">LPTNEF</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="56e01-120">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="56e01-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="56e01-121">AddProps</span><span class="sxs-lookup"><span data-stu-id="56e01-121">AddProps</span></span>](itnef-addprops.md) <br/> |<span data-ttu-id="56e01-122">允许呼叫服务提供商或网关将属性添加到邮件或附件的封装中。</span><span class="sxs-lookup"><span data-stu-id="56e01-122">Enables the calling service provider or gateway to add properties to the encapsulation of a message or an attachment.</span></span>  <br/> |
|[<span data-ttu-id="56e01-123">ExtractProps</span><span class="sxs-lookup"><span data-stu-id="56e01-123">ExtractProps</span></span>](itnef-extractprops.md) <br/> |<span data-ttu-id="56e01-124">从 TNEF 封装中提取属性。</span><span class="sxs-lookup"><span data-stu-id="56e01-124">Extracts the properties from a TNEF encapsulation.</span></span>  <br/> |
|[<span data-ttu-id="56e01-125">Finish</span><span class="sxs-lookup"><span data-stu-id="56e01-125">Finish</span></span>](itnef-finish.md) <br/> |<span data-ttu-id="56e01-126">完成排队和等待的所有 TNEF 操作的处理。</span><span class="sxs-lookup"><span data-stu-id="56e01-126">Finishes processing for all TNEF operations that are queued and waiting.</span></span>  <br/> |
|[<span data-ttu-id="56e01-127">OpenTaggedBody</span><span class="sxs-lookup"><span data-stu-id="56e01-127">OpenTaggedBody</span></span>](itnef-opentaggedbody.md) <br/> |<span data-ttu-id="56e01-128">打开封装邮件的文本上的流接口。</span><span class="sxs-lookup"><span data-stu-id="56e01-128">Opens a stream interface on the text of an encapsulated message.</span></span>  <br/> |
|[<span data-ttu-id="56e01-129">SetProps</span><span class="sxs-lookup"><span data-stu-id="56e01-129">SetProps</span></span>](itnef-setprops.md) <br/> |<span data-ttu-id="56e01-130">在不修改原始邮件或附件的情况下设置封装邮件或附件的一个或多个属性的值。</span><span class="sxs-lookup"><span data-stu-id="56e01-130">Sets the value of one or more properties for an encapsulated message or attachment without modifying the original message or attachment.</span></span>  <br/> |
|[<span data-ttu-id="56e01-131">EncodeRecips</span><span class="sxs-lookup"><span data-stu-id="56e01-131">EncodeRecips</span></span>](itnef-encoderecips.md) <br/> |<span data-ttu-id="56e01-132">对邮件的 TNEF 数据流中邮件收件人表的视图进行编码。</span><span class="sxs-lookup"><span data-stu-id="56e01-132">Encodes a view for a message's recipient table in the TNEF data stream for the message.</span></span>  <br/> |
|[<span data-ttu-id="56e01-133">FinishComponent</span><span class="sxs-lookup"><span data-stu-id="56e01-133">FinishComponent</span></span>](itnef-finishcomponent.md) <br/> |<span data-ttu-id="56e01-134">将邮件中的单个组件一次处理一个处理到 TNEF 流中。</span><span class="sxs-lookup"><span data-stu-id="56e01-134">Processes individual components from a message one at a time into a TNEF stream.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="56e01-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56e01-135">See also</span></span>



[<span data-ttu-id="56e01-136">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="56e01-136">MAPI Interfaces</span></span>](mapi-interfaces.md)

