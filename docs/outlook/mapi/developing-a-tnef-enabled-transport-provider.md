---
title: 开发TNEF-Enabled传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7525eee1-4016-49b8-9509-5ebbe1db819f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 282b1866699b695c647caedd130ce5abc1bcbc2c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439000"
---
# <a name="developing-a-tnef-enabled-transport-provider"></a><span data-ttu-id="0031b-103">开发TNEF-Enabled传输提供程序</span><span class="sxs-lookup"><span data-stu-id="0031b-103">Developing a TNEF-Enabled Transport Provider</span></span>

  
  
<span data-ttu-id="0031b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0031b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0031b-105">为了提升支持不同 MAPI 功能集的邮件系统之间的互操作性，MAPI 提供了传输中性封装格式 (TNEF) 作为传输数据的标准方法。</span><span class="sxs-lookup"><span data-stu-id="0031b-105">To promote interoperability between messaging systems that support different sets of MAPI features, MAPI provides the Transport Neutral Encapsulation Format (TNEF) as a standard way to transfer data.</span></span> <span data-ttu-id="0031b-106">此格式将不受基础邮件系统支持的 MAPI 属性封装到二进制流中，传输提供程序发送该二进制流时，可以随邮件一起传输。</span><span class="sxs-lookup"><span data-stu-id="0031b-106">This format encapsulates MAPI properties not supported by an underlying messaging system into a binary stream that can be transferred along with the message when a transport provider sends it.</span></span> <span data-ttu-id="0031b-107">然后，接收邮件的传输提供程序可以解码二进制流以检索原始邮件的所有属性，并使它们可用于客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="0031b-107">The transport provider that receives the message can then decode the binary stream to retrieve all the properties of the original message and make them available to client applications.</span></span> <span data-ttu-id="0031b-108">TNEF 的操作模型是：</span><span class="sxs-lookup"><span data-stu-id="0031b-108">The operational model for TNEF is:</span></span>
  
- <span data-ttu-id="0031b-109">邮件客户端正常向 TNEF 传输提交和接收邮件。</span><span class="sxs-lookup"><span data-stu-id="0031b-109">Messaging clients submit and receive messages to a TNEF transport as normal.</span></span>
    
- <span data-ttu-id="0031b-110">传输将传出邮件的属性分为两类：基础邮件系统支持的属性和不支持的属性。</span><span class="sxs-lookup"><span data-stu-id="0031b-110">The transport separates the properties on outgoing messages into two categories: those that the underlying message system supports and those that it does not.</span></span> <span data-ttu-id="0031b-111">基础邮件系统支持的属性的值将转换为所需格式。</span><span class="sxs-lookup"><span data-stu-id="0031b-111">The values of the properties that are supported by the underlying messaging system are translated into the required format.</span></span>
    
- <span data-ttu-id="0031b-112">传输使用 MAPI TNEF 方法将任何不受支持的属性编码为单个数据流。</span><span class="sxs-lookup"><span data-stu-id="0031b-112">The transport uses the MAPI TNEF methods to encode any unsupported properties into a single data stream.</span></span> <span data-ttu-id="0031b-113">传输随后使用基础邮件系统的附件模型，在发送邮件之前，将该数据流转换为传出邮件上的特殊附件。</span><span class="sxs-lookup"><span data-stu-id="0031b-113">The transport then turns that data stream into a special attachment on the outgoing message, using the underlying messaging system's attachment model, before sending the message.</span></span>
    
- <span data-ttu-id="0031b-114">接收此类邮件的启用 TNEF 的传输会做两件事。</span><span class="sxs-lookup"><span data-stu-id="0031b-114">A TNEF enabled transport that receives such a message does two things.</span></span> <span data-ttu-id="0031b-115">首先，它将传入邮件的属性（基础邮件系统支持的属性）转换为 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="0031b-115">First, it translates the incoming message's properties — the ones supported by the underlying message system — into MAPI properties.</span></span> <span data-ttu-id="0031b-116">其次，如果存在特殊附件，它将使用 MAPI TNEF 方法在将邮件传递至客户端应用程序之前从附件检索其他 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="0031b-116">Second, if the special attachment is present, it uses the MAPI TNEF methods to retrieve additional MAPI properties from the attachment before delivering the message to a client application.</span></span>
    
<span data-ttu-id="0031b-117">MAPI 提供 **ITnef 接口** 的实现，供 MAPI 传输提供程序在使用 TNEF 对象时使用。</span><span class="sxs-lookup"><span data-stu-id="0031b-117">MAPI supplies an implementation of the **ITnef** interface for use by MAPI transport providers when working with TNEF objects.</span></span> <span data-ttu-id="0031b-118">[OpenTnefStreamEx](opentnefstreamex.md)函数用于创建 TNEF 对象并将其与消息关联。</span><span class="sxs-lookup"><span data-stu-id="0031b-118">The [OpenTnefStreamEx](opentnefstreamex.md) function is used to create TNEF objects and associate them with a message.</span></span> <span data-ttu-id="0031b-119">TNEF 流构建于 OLE **IStream 接口** 的顶部</span><span class="sxs-lookup"><span data-stu-id="0031b-119">TNEF streams are built on top of the OLE **IStream** interface</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0031b-120">使用 **OpenTnefStreamEx** 创建 TNEF 对象。</span><span class="sxs-lookup"><span data-stu-id="0031b-120">You use **OpenTnefStreamEx** to create TNEF objects.</span></span> <span data-ttu-id="0031b-121">旧的 **OpenTnefStream** 函数仍然存在，以与旧源代码兼容，不应用于任何新内容。</span><span class="sxs-lookup"><span data-stu-id="0031b-121">The old **OpenTnefStream** function still exists for compatibility with old source code and should not be used in anything new.</span></span> 
  
<span data-ttu-id="0031b-122">**ITnef** 接口提供以下方法：</span><span class="sxs-lookup"><span data-stu-id="0031b-122">The **ITnef** interface provides the following methods:</span></span> 
  
- [<span data-ttu-id="0031b-123">AddProps</span><span class="sxs-lookup"><span data-stu-id="0031b-123">AddProps</span></span>](itnef-addprops.md)
    
- [<span data-ttu-id="0031b-124">EncodeRecips</span><span class="sxs-lookup"><span data-stu-id="0031b-124">EncodeRecips</span></span>](itnef-encoderecips.md)
    
- [<span data-ttu-id="0031b-125">ExtractProps</span><span class="sxs-lookup"><span data-stu-id="0031b-125">ExtractProps</span></span>](itnef-extractprops.md)
    
- [<span data-ttu-id="0031b-126">Finish</span><span class="sxs-lookup"><span data-stu-id="0031b-126">Finish</span></span>](itnef-finish.md)
    
- [<span data-ttu-id="0031b-127">FinishComponent</span><span class="sxs-lookup"><span data-stu-id="0031b-127">FinishComponent</span></span>](itnef-finishcomponent.md)
    
- [<span data-ttu-id="0031b-128">OpenTaggedBody</span><span class="sxs-lookup"><span data-stu-id="0031b-128">OpenTaggedBody</span></span>](itnef-opentaggedbody.md)
    
- [<span data-ttu-id="0031b-129">SetProps</span><span class="sxs-lookup"><span data-stu-id="0031b-129">SetProps</span></span>](itnef-setprops.md)
    
<span data-ttu-id="0031b-130">MAPI TNEF 实现模型支持：</span><span class="sxs-lookup"><span data-stu-id="0031b-130">The MAPI TNEF implementation model supports:</span></span>
  
- <span data-ttu-id="0031b-131">所有 MAPI 属性都不会影响其他邮件属性。</span><span class="sxs-lookup"><span data-stu-id="0031b-131">All MAPI properties without affecting other message properties.</span></span> <span data-ttu-id="0031b-132">为了使 MAPI 邮件在通过邮件系统传输时能保留下来，必须封装无法编码为邮件系统属性的所有属性。</span><span class="sxs-lookup"><span data-stu-id="0031b-132">In order for MAPI messages to survive transport through a messaging system, all properties that cannot be encoded as properties of the messaging system must be encapsulated.</span></span> <span data-ttu-id="0031b-133">由于在发送消息时几乎永远不会知道符合 MAPI 的客户端是否将接收邮件，因此封装方案允许传输提供程序仅对邮件系统不支持的 MAPI 邮件属性进行编码。</span><span class="sxs-lookup"><span data-stu-id="0031b-133">Because it is almost never known at the time a message is sent whether or not a MAPI-compliant client will receive the message, the encapsulation scheme allows a transport provider to encode only those MAPI message properties that the messaging system does not natively support.</span></span> <span data-ttu-id="0031b-134">这意味着使用 TNEF 的邮件对于不基于 MAPI 的邮件系统（如基于 SMTP 的邮件系统）UNIX不透明。</span><span class="sxs-lookup"><span data-stu-id="0031b-134">This means that messages which use TNEF are not "opaque" to messaging systems that are not based on MAPI such as SMTP-based UNIX messaging systems.</span></span> <span data-ttu-id="0031b-135">这些系统以他们典型的任何方式接收支持的属性，其他属性作为编码的 TNEF 数据流接收。</span><span class="sxs-lookup"><span data-stu-id="0031b-135">These systems receive the properties they support in whatever manner is typical for them, and other properties are received as an encoded TNEF data stream.</span></span> <span data-ttu-id="0031b-136">TNEF 传输提供程序负责区分这两组属性，并正确发送邮件系统支持的属性集。</span><span class="sxs-lookup"><span data-stu-id="0031b-136">The TNEF transport provider is responsible for differentiating between these two sets of properties and sending the supported set in the proper manner for the messaging system.</span></span> <span data-ttu-id="0031b-137">TNEF 对邮件系统提供的支持级别不做任何假设。</span><span class="sxs-lookup"><span data-stu-id="0031b-137">TNEF makes no assumptions as to the level of support provided by a messaging system.</span></span> <span data-ttu-id="0031b-138">但是，在本节包含的 TNEF 用法示例中，假定邮件系统支持邮件之外至少一个附件。</span><span class="sxs-lookup"><span data-stu-id="0031b-138">However, in the examples of TNEF usage included in this section, the assumption is made that the messaging system supports at least one single attachment aside from the message.</span></span> <span data-ttu-id="0031b-139">在某些情况下，附件只能通过 uuencoded 流获得支持，并作为邮件文本的一部分进行传输。</span><span class="sxs-lookup"><span data-stu-id="0031b-139">In some cases, the attachment can only be supported through a uuencoded stream and transmitted as part of the message text.</span></span> <span data-ttu-id="0031b-140">仅在极少数情况下，邮件系统才对邮件属性的支持非常少，因此需要所有属性的完整 TNEF 编码。</span><span class="sxs-lookup"><span data-stu-id="0031b-140">Only in very rare circumstances will the messaging system have so little support for message properties that full TNEF encoding of all properties is necessary.</span></span>
    
- <span data-ttu-id="0031b-141">一种根据 MAPI 属性 **PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)) 确定传入邮件上的 TNEF 流是否属于邮件的机制。</span><span class="sxs-lookup"><span data-stu-id="0031b-141">A mechanism for determining whether a TNEF stream on an incoming message belongs to the message, based on the MAPI property **PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)).</span></span> <span data-ttu-id="0031b-142">此属性应同时在 TNEF 流和相应的邮件头中找到。</span><span class="sxs-lookup"><span data-stu-id="0031b-142">This property should be found both in the TNEF stream and in an appropriate message header.</span></span> <span data-ttu-id="0031b-143">如果属性在两处具有相同的值，或者任一位置都缺失，则假定 TNEF 流属于邮件。</span><span class="sxs-lookup"><span data-stu-id="0031b-143">If the property has the same value in both places, or is missing in either place, the TNEF stream is assumed to belong to the message.</span></span> <span data-ttu-id="0031b-144">否则，TNEF 流将被忽略。</span><span class="sxs-lookup"><span data-stu-id="0031b-144">Otherwise, the TNEF stream is ignored.</span></span> <span data-ttu-id="0031b-145">启用 TNEF 的传输负责为出站邮件上的此属性选择一个值，并在适当的邮件头 (例如，SMTP 邮件的 Message-ID： 标头) 以及 TNEF 流中对该值进行编码。</span><span class="sxs-lookup"><span data-stu-id="0031b-145">TNEF enabled transports are responsible for choosing a value for this property on outbound messages and encoding it in an appropriate message header (for example, the Message-ID: header for SMTP messages) and in the TNEF stream.</span></span>
    

