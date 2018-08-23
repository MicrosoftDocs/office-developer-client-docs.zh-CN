---
title: 开发已启用 TNEF 的传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7525eee1-4016-49b8-9509-5ebbe1db819f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4d4f7ed75bb1144b7cd4a813b0d093246a30cca5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588347"
---
# <a name="developing-a-tnef-enabled-transport-provider"></a><span data-ttu-id="f3163-103">开发已启用 TNEF 的传输提供程序</span><span class="sxs-lookup"><span data-stu-id="f3163-103">Developing a TNEF-Enabled Transport Provider</span></span>

  
  
<span data-ttu-id="f3163-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f3163-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f3163-105">提升支持不同的 MAPI 功能集的邮件系统之间的互操作性，MAPI 时，可提供传输中性封装格式 (TNEF) 作为传输数据的标准方法。</span><span class="sxs-lookup"><span data-stu-id="f3163-105">To promote interoperability between messaging systems that support different sets of MAPI features, MAPI provides the Transport Neutral Encapsulation Format (TNEF) as a standard way to transfer data.</span></span> <span data-ttu-id="f3163-106">此格式封装不支持二进制流传输提供程序将其发送时可并显示消息传输到基础的消息系统的 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="f3163-106">This format encapsulates MAPI properties not supported by an underlying messaging system into a binary stream that can be transferred along with the message when a transport provider sends it.</span></span> <span data-ttu-id="f3163-107">接收的消息的传输提供程序然后可以对要检索的原始邮件的所有属性并使其可供客户端应用程序的二进制流进行解码。</span><span class="sxs-lookup"><span data-stu-id="f3163-107">The transport provider that receives the message can then decode the binary stream to retrieve all the properties of the original message and make them available to client applications.</span></span> <span data-ttu-id="f3163-108">TNEF 的操作模型是：</span><span class="sxs-lookup"><span data-stu-id="f3163-108">The operational model for TNEF is:</span></span>
  
- <span data-ttu-id="f3163-109">消息客户端提交和接收平常一样 TNEF 传输邮件。</span><span class="sxs-lookup"><span data-stu-id="f3163-109">Messaging clients submit and receive messages to a TNEF transport as normal.</span></span>
    
- <span data-ttu-id="f3163-110">传输将传出邮件的属性分为两个类别： 基础的消息系统支持和不。</span><span class="sxs-lookup"><span data-stu-id="f3163-110">The transport separates the properties on outgoing messages into two categories: those that the underlying message system supports and those that it does not.</span></span> <span data-ttu-id="f3163-111">支持的基础邮件系统的属性的值转换为所需的格式。</span><span class="sxs-lookup"><span data-stu-id="f3163-111">The values of the properties that are supported by the underlying messaging system are translated into the required format.</span></span>
    
- <span data-ttu-id="f3163-112">传输使用 MAPI TNEF 方法编码到单个数据流的任何不受支持的属性。</span><span class="sxs-lookup"><span data-stu-id="f3163-112">The transport uses the MAPI TNEF methods to encode any unsupported properties into a single data stream.</span></span> <span data-ttu-id="f3163-113">传输然后打开该数据流成一个特殊的附件发送邮件前使用基础邮件系统的附件模型对传出邮件。</span><span class="sxs-lookup"><span data-stu-id="f3163-113">The transport then turns that data stream into a special attachment on the outgoing message, using the underlying messaging system's attachment model, before sending the message.</span></span>
    
- <span data-ttu-id="f3163-114">接收此类消息 TNEF 启用传输执行两项操作。</span><span class="sxs-lookup"><span data-stu-id="f3163-114">A TNEF enabled transport that receives such a message does two things.</span></span> <span data-ttu-id="f3163-115">首先，它将翻译传入消息的属性 — 基础的消息系统支持的那些 — 到 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="f3163-115">First, it translates the incoming message's properties — the ones supported by the underlying message system — into MAPI properties.</span></span> <span data-ttu-id="f3163-116">其次，如果存在此参数的特殊的附件，它使用 MAPI TNEF 方法从附件之前邮件传递到客户端应用程序检索其他 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="f3163-116">Second, if the special attachment is present, it uses the MAPI TNEF methods to retrieve additional MAPI properties from the attachment before delivering the message to a client application.</span></span>
    
<span data-ttu-id="f3163-117">使用 TNEF 对象时，MAPI 提供**ITnef**接口以供 MAPI 传输提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="f3163-117">MAPI supplies an implementation of the **ITnef** interface for use by MAPI transport providers when working with TNEF objects.</span></span> <span data-ttu-id="f3163-118">[OpenTnefStreamEx](opentnefstreamex.md)函数用于创建 TNEF 对象并将它们与一条消息。</span><span class="sxs-lookup"><span data-stu-id="f3163-118">The [OpenTnefStreamEx](opentnefstreamex.md) function is used to create TNEF objects and associate them with a message.</span></span> <span data-ttu-id="f3163-119">TNEF 流基础之上的 OLE **IStream**接口</span><span class="sxs-lookup"><span data-stu-id="f3163-119">TNEF streams are built on top of the OLE **IStream** interface</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f3163-120">您可以使用**OpenTnefStreamEx**创建 TNEF 对象。</span><span class="sxs-lookup"><span data-stu-id="f3163-120">You use **OpenTnefStreamEx** to create TNEF objects.</span></span> <span data-ttu-id="f3163-121">旧**OpenTnefStream**函数仍然存在与旧的源代码的兼容性，并且不应使用任何新。</span><span class="sxs-lookup"><span data-stu-id="f3163-121">The old **OpenTnefStream** function still exists for compatibility with old source code and should not be used in anything new.</span></span> 
  
<span data-ttu-id="f3163-122">**ITnef**接口提供下列方法：</span><span class="sxs-lookup"><span data-stu-id="f3163-122">The **ITnef** interface provides the following methods:</span></span> 
  
- [<span data-ttu-id="f3163-123">AddProps</span><span class="sxs-lookup"><span data-stu-id="f3163-123">AddProps</span></span>](itnef-addprops.md)
    
- [<span data-ttu-id="f3163-124">EncodeRecips</span><span class="sxs-lookup"><span data-stu-id="f3163-124">EncodeRecips</span></span>](itnef-encoderecips.md)
    
- [<span data-ttu-id="f3163-125">ExtractProps</span><span class="sxs-lookup"><span data-stu-id="f3163-125">ExtractProps</span></span>](itnef-extractprops.md)
    
- [<span data-ttu-id="f3163-126">Finish</span><span class="sxs-lookup"><span data-stu-id="f3163-126">Finish</span></span>](itnef-finish.md)
    
- [<span data-ttu-id="f3163-127">FinishComponent</span><span class="sxs-lookup"><span data-stu-id="f3163-127">FinishComponent</span></span>](itnef-finishcomponent.md)
    
- [<span data-ttu-id="f3163-128">OpenTaggedBody</span><span class="sxs-lookup"><span data-stu-id="f3163-128">OpenTaggedBody</span></span>](itnef-opentaggedbody.md)
    
- [<span data-ttu-id="f3163-129">SetProps</span><span class="sxs-lookup"><span data-stu-id="f3163-129">SetProps</span></span>](itnef-setprops.md)
    
<span data-ttu-id="f3163-130">MAPI TNEF 实施模型支持：</span><span class="sxs-lookup"><span data-stu-id="f3163-130">The MAPI TNEF implementation model supports:</span></span>
  
- <span data-ttu-id="f3163-131">而不影响其他邮件属性的所有 MAPI 属性。</span><span class="sxs-lookup"><span data-stu-id="f3163-131">All MAPI properties without affecting other message properties.</span></span> <span data-ttu-id="f3163-132">为了使忞眦通过消息系统传输的 MAPI 邮件，必须封装无法编码为消息系统的属性的所有属性。</span><span class="sxs-lookup"><span data-stu-id="f3163-132">In order for MAPI messages to survive transport through a messaging system, all properties that cannot be encoded as properties of the messaging system must be encapsulated.</span></span> <span data-ttu-id="f3163-133">封装方案因为几乎从不已知 MAPI 兼容的客户端会收到消息发送邮件时，允许传输提供程序进行编码仅在邮件系统不这些 MAPI 邮件属性本身支持。</span><span class="sxs-lookup"><span data-stu-id="f3163-133">Because it is almost never known at the time a message is sent whether or not a MAPI-compliant client will receive the message, the encapsulation scheme allows a transport provider to encode only those MAPI message properties that the messaging system does not natively support.</span></span> <span data-ttu-id="f3163-134">这意味着不"透明"不基于 MAPI，如基于 SMTP UNIX 的消息系统使用 TNEF 邮件消息系统。</span><span class="sxs-lookup"><span data-stu-id="f3163-134">This means that messages which use TNEF are not "opaque" to messaging systems that are not based on MAPI such as SMTP-based UNIX messaging systems.</span></span> <span data-ttu-id="f3163-135">这些系统接收它们支持在任何方式是典型的作为编码的 TNEF 数据流接收其，和其他属性的属性。</span><span class="sxs-lookup"><span data-stu-id="f3163-135">These systems receive the properties they support in whatever manner is typical for them, and other properties are received as an encoded TNEF data stream.</span></span> <span data-ttu-id="f3163-136">TNEF 传输提供程序负责为区分这两组的属性和支持的一组发送邮件系统的适当的方式。</span><span class="sxs-lookup"><span data-stu-id="f3163-136">The TNEF transport provider is responsible for differentiating between these two sets of properties and sending the supported set in the proper manner for the messaging system.</span></span> <span data-ttu-id="f3163-137">TNEF 进行无假设来对的消息系统提供的支持级别。</span><span class="sxs-lookup"><span data-stu-id="f3163-137">TNEF makes no assumptions as to the level of support provided by a messaging system.</span></span> <span data-ttu-id="f3163-138">但是，在包含本节中的 TNEF 用法的示例中，假定都由邮件系统支持除了邮件至少一个单独的附件。</span><span class="sxs-lookup"><span data-stu-id="f3163-138">However, in the examples of TNEF usage included in this section, the assumption is made that the messaging system supports at least one single attachment aside from the message.</span></span> <span data-ttu-id="f3163-139">在某些情况下，附件可以仅支持通过 uuencoded 流和传输消息文本的一部分。</span><span class="sxs-lookup"><span data-stu-id="f3163-139">In some cases, the attachment can only be supported through a uuencoded stream and transmitted as part of the message text.</span></span> <span data-ttu-id="f3163-140">仅在极少数情况下将在邮件系统具有因此很少支持邮件属性的所有属性的完整 TNEF 编码必要。</span><span class="sxs-lookup"><span data-stu-id="f3163-140">Only in very rare circumstances will the messaging system have so little support for message properties that full TNEF encoding of all properties is necessary.</span></span>
    
- <span data-ttu-id="f3163-141">一种机制，确定是否对传入邮件 TNEF 流属于邮件，基于 MAPI 属性**PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="f3163-141">A mechanism for determining whether a TNEF stream on an incoming message belongs to the message, based on the MAPI property **PR_TNEF_CORRELATION_KEY** ([PidTagTnefCorrelationKey](pidtagtnefcorrelationkey-canonical-property.md)).</span></span> <span data-ttu-id="f3163-142">此属性应在 TNEF 流和相应的邮件头中找到。</span><span class="sxs-lookup"><span data-stu-id="f3163-142">This property should be found both in the TNEF stream and in an appropriate message header.</span></span> <span data-ttu-id="f3163-143">如果属性在两个位置，有相同的值，或者缺少处于任一位置，则假定 TNEF 流属于邮件。</span><span class="sxs-lookup"><span data-stu-id="f3163-143">If the property has the same value in both places, or is missing in either place, the TNEF stream is assumed to belong to the message.</span></span> <span data-ttu-id="f3163-144">否则，将忽略 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="f3163-144">Otherwise, the TNEF stream is ignored.</span></span> <span data-ttu-id="f3163-145">TNEF 启用传输负责选择对出站邮件此属性的值和相应的邮件头中对其进行编码 (例如，消息 ID: SMTP 邮件的标头) 和 TNEF 流中。</span><span class="sxs-lookup"><span data-stu-id="f3163-145">TNEF enabled transports are responsible for choosing a value for this property on outbound messages and encoding it in an appropriate message header (for example, the Message-ID: header for SMTP messages) and in the TNEF stream.</span></span>
    

