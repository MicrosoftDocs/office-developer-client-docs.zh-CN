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
ms.openlocfilehash: 1803707b46b9b58e7372e7e58cc36241d0ebdb4d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571722"
---
# <a name="itnef--iunknown"></a><span data-ttu-id="bd49a-103">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bd49a-103">ITnef : IUnknown</span></span>

  
  
<span data-ttu-id="bd49a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bd49a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bd49a-105">提供用于封装到可附加到邮件的二进制流不支持的邮件系统的 MAPI 属性的方法。</span><span class="sxs-lookup"><span data-stu-id="bd49a-105">Provides methods for encapsulating MAPI properties that are not supported by a messaging system into binary streams that can be attached to messages.</span></span> <span data-ttu-id="bd49a-106">用于此封装的格式是传输中性封装格式 (TNEF)。</span><span class="sxs-lookup"><span data-stu-id="bd49a-106">The format used for this encapsulation is the Transport-Neutral Encapsulation Format (TNEF).</span></span> <span data-ttu-id="bd49a-107">目标传输提供程序或基于 MAPI 的客户端应用程序可以然后，在收到一条消息，包括 TNEF 附件时恢复属性附件。</span><span class="sxs-lookup"><span data-stu-id="bd49a-107">The target transport provider or MAPI-based client application can then, on receiving a message that includes a TNEF attachment, recover the properties from the attachment.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bd49a-108">头文件：</span><span class="sxs-lookup"><span data-stu-id="bd49a-108">Header file:</span></span>  <br/> |<span data-ttu-id="bd49a-109">Tnef.h</span><span class="sxs-lookup"><span data-stu-id="bd49a-109">Tnef.h</span></span>  <br/> |
|<span data-ttu-id="bd49a-110">由公开：</span><span class="sxs-lookup"><span data-stu-id="bd49a-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="bd49a-111">TNEF 对象</span><span class="sxs-lookup"><span data-stu-id="bd49a-111">TNEF objects</span></span>  <br/> |
|<span data-ttu-id="bd49a-112">通过实现：</span><span class="sxs-lookup"><span data-stu-id="bd49a-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="bd49a-113">MAPI</span><span class="sxs-lookup"><span data-stu-id="bd49a-113">MAPI</span></span>  <br/> |
|<span data-ttu-id="bd49a-114">调用：</span><span class="sxs-lookup"><span data-stu-id="bd49a-114">Called by:</span></span>  <br/> |<span data-ttu-id="bd49a-115">传输提供程序、 消息存储提供程序，和网关</span><span class="sxs-lookup"><span data-stu-id="bd49a-115">Transport providers, message store providers, and gateways</span></span>  <br/> |
|<span data-ttu-id="bd49a-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="bd49a-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="bd49a-117">IID_ITNEF</span><span class="sxs-lookup"><span data-stu-id="bd49a-117">IID_ITNEF</span></span>  <br/> |
|<span data-ttu-id="bd49a-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="bd49a-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="bd49a-119">LPTNEF</span><span class="sxs-lookup"><span data-stu-id="bd49a-119">LPTNEF</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="bd49a-120">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="bd49a-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="bd49a-121">AddProps</span><span class="sxs-lookup"><span data-stu-id="bd49a-121">AddProps</span></span>](itnef-addprops.md) <br/> |<span data-ttu-id="bd49a-122">允许将属性添加到邮件或附件封装调用服务提供商或网关。</span><span class="sxs-lookup"><span data-stu-id="bd49a-122">Enables the calling service provider or gateway to add properties to the encapsulation of a message or an attachment.</span></span>  <br/> |
|[<span data-ttu-id="bd49a-123">ExtractProps</span><span class="sxs-lookup"><span data-stu-id="bd49a-123">ExtractProps</span></span>](itnef-extractprops.md) <br/> |<span data-ttu-id="bd49a-124">从 TNEF 封装提取属性。</span><span class="sxs-lookup"><span data-stu-id="bd49a-124">Extracts the properties from a TNEF encapsulation.</span></span>  <br/> |
|[<span data-ttu-id="bd49a-125">Finish</span><span class="sxs-lookup"><span data-stu-id="bd49a-125">Finish</span></span>](itnef-finish.md) <br/> |<span data-ttu-id="bd49a-126">处理排队的所有 TNEF 操作和等待完成。</span><span class="sxs-lookup"><span data-stu-id="bd49a-126">Finishes processing for all TNEF operations that are queued and waiting.</span></span>  <br/> |
|[<span data-ttu-id="bd49a-127">OpenTaggedBody</span><span class="sxs-lookup"><span data-stu-id="bd49a-127">OpenTaggedBody</span></span>](itnef-opentaggedbody.md) <br/> |<span data-ttu-id="bd49a-128">打开上封装的消息的文本的流接口。</span><span class="sxs-lookup"><span data-stu-id="bd49a-128">Opens a stream interface on the text of an encapsulated message.</span></span>  <br/> |
|[<span data-ttu-id="bd49a-129">SetProps</span><span class="sxs-lookup"><span data-stu-id="bd49a-129">SetProps</span></span>](itnef-setprops.md) <br/> |<span data-ttu-id="bd49a-130">设置用于封装的邮件或附件的一个或多个属性的值，而无需修改原始邮件或附件。</span><span class="sxs-lookup"><span data-stu-id="bd49a-130">Sets the value of one or more properties for an encapsulated message or attachment without modifying the original message or attachment.</span></span>  <br/> |
|[<span data-ttu-id="bd49a-131">EncodeRecips</span><span class="sxs-lookup"><span data-stu-id="bd49a-131">EncodeRecips</span></span>](itnef-encoderecips.md) <br/> |<span data-ttu-id="bd49a-132">将编码 TNEF 数据流的邮件中的消息的收件人表视图。</span><span class="sxs-lookup"><span data-stu-id="bd49a-132">Encodes a view for a message's recipient table in the TNEF data stream for the message.</span></span>  <br/> |
|[<span data-ttu-id="bd49a-133">FinishComponent</span><span class="sxs-lookup"><span data-stu-id="bd49a-133">FinishComponent</span></span>](itnef-finishcomponent.md) <br/> |<span data-ttu-id="bd49a-134">到 TNEF stream 一次处理从一个一条消息的各个组件。</span><span class="sxs-lookup"><span data-stu-id="bd49a-134">Processes individual components from a message one at a time into a TNEF stream.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bd49a-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd49a-135">See also</span></span>



[<span data-ttu-id="bd49a-136">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="bd49a-136">MAPI Interfaces</span></span>](mapi-interfaces.md)

