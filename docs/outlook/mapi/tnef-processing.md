---
title: TNEF 处理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d324fb3-d917-4502-b3a4-179c479deb79
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: 066ad3dfb64161e326b92fef7774d5b3b9461d8a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339597"
---
# <a name="tnef-processing"></a><span data-ttu-id="4a052-103">TNEF 处理</span><span class="sxs-lookup"><span data-stu-id="4a052-103">TNEF Processing</span></span>

  
  
<span data-ttu-id="4a052-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4a052-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4a052-105">以下一系列操作介绍了传输如何使用 TNEF 方法来处理传出和传入的邮件。</span><span class="sxs-lookup"><span data-stu-id="4a052-105">The following series of actions describe how transports use TNEF methods to process outgoing and incoming messages.</span></span>
  
 <span data-ttu-id="4a052-106">**发送包含 TNEF 流的消息**</span><span class="sxs-lookup"><span data-stu-id="4a052-106">**To send a message that includes a TNEF stream**</span></span>
  
1. <span data-ttu-id="4a052-107">处理邮件系统支持的邮件属性。</span><span class="sxs-lookup"><span data-stu-id="4a052-107">Process the message properties that are supported by the messaging system.</span></span>
    
2. <span data-ttu-id="4a052-108">以特定实现方式标记邮件，以便接收传输提供程序可以确定邮件需要 TNEF 处理。</span><span class="sxs-lookup"><span data-stu-id="4a052-108">Mark the message in an implementation specific way so that the receiving transport provider can determine that the message requires TNEF processing.</span></span> <span data-ttu-id="4a052-109">例如，发送到 SMTP 邮件系统的 TNEF 传输提供程序可能会添加自定义头字段（如"X-CONTAINS-TNEF"）以指示邮件包含 TNEF 数据。</span><span class="sxs-lookup"><span data-stu-id="4a052-109">For example, a TNEF transport provider sending to an SMTP messaging system might add a custom header field like "X-CONTAINS-TNEF" to indicate that the message contains TNEF data.</span></span>
    
3. <span data-ttu-id="4a052-110">获取一个 TNEF 对象，并使用它将邮件系统不支持的邮件属性封装到 TNEF 流中。</span><span class="sxs-lookup"><span data-stu-id="4a052-110">Obtain a TNEF object and use it to encapsulate the message properties not supported by the messaging system into a TNEF stream.</span></span>
    
4. <span data-ttu-id="4a052-111">使用邮件系统的附件模型对 TNEF 流进行编码。</span><span class="sxs-lookup"><span data-stu-id="4a052-111">Encode the TNEF stream using the messaging system's attachment model.</span></span> <span data-ttu-id="4a052-112">例如，如果基础附件模型是 uuencode 附件并将其附加到邮件文本，则传输提供程序必须将 TNEF 流编码为其他附件。</span><span class="sxs-lookup"><span data-stu-id="4a052-112">For example, if the underlying attachment model is to uuencode attachments and append them to the message text, then the transport provider must uuencode the TNEF stream into another attachment.</span></span> <span data-ttu-id="4a052-113">传输提供程序还必须实现一种方法，用于识别在接收邮件时包含编码 TNEF 流的附件。</span><span class="sxs-lookup"><span data-stu-id="4a052-113">The transport provider must also implement a method for recognizing which attachment contains the encoded TNEF stream when it receives a message.</span></span> <span data-ttu-id="4a052-114">标记此附件的标准方法为，为附件提供"WINMAIL"文件名。DAT"。</span><span class="sxs-lookup"><span data-stu-id="4a052-114">The standard way to mark this attachment is to give it an attachment filename of "WINMAIL.DAT".</span></span> <span data-ttu-id="4a052-115">如果传输提供程序这样做，则遵循此约定的其他任何启用 TNEF 的传输提供程序将能够与它进行互操作。</span><span class="sxs-lookup"><span data-stu-id="4a052-115">If your transport provider does this, any other TNEF-enabled transport providers that follow this convention will be able to interoperate with it.</span></span>
    
5. <span data-ttu-id="4a052-116">使用 [ITnef ： IUnknown](itnefiunknown.md) 接口方法插入描述邮件文本中邮件附件位置的标记。</span><span class="sxs-lookup"><span data-stu-id="4a052-116">Use [ITnef : IUnknown](itnefiunknown.md) interface methods to insert tags describing the positions of message attachments in the message text.</span></span> 
    
6. <span data-ttu-id="4a052-117">通过 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 方法访问带标记的邮件文本，并将其发送到邮件系统。</span><span class="sxs-lookup"><span data-stu-id="4a052-117">Access the tagged message text through [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) methods, and send it to the messaging system.</span></span> 
    
 <span data-ttu-id="4a052-118">**检索封装的属性**</span><span class="sxs-lookup"><span data-stu-id="4a052-118">**To retrieve encapsulated properties**</span></span>
  
1. <span data-ttu-id="4a052-119">将邮件系统支持的属性写入新邮件，包括包含封装属性的带标记的邮件文本。</span><span class="sxs-lookup"><span data-stu-id="4a052-119">Write the properties supported by the messaging system into a new message, including the tagged message text that contains the encapsulated properties.</span></span>
    
2. <span data-ttu-id="4a052-120">从正确的附件解码 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="4a052-120">Decode the TNEF stream from the proper attachment.</span></span>
    
3. <span data-ttu-id="4a052-121">解码任何其他附件，并写入邮件上的新 MAPI 附件。</span><span class="sxs-lookup"><span data-stu-id="4a052-121">Decode any other attachments and write them to new MAPI attachments on a message.</span></span>
    
4. <span data-ttu-id="4a052-122">使用 [OpenTnefStreamEx](opentnefstreamex.md) 函数打开 TNEF 流进行解码。</span><span class="sxs-lookup"><span data-stu-id="4a052-122">Open the TNEF stream for decoding using the [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
    
5. <span data-ttu-id="4a052-123">使用 [ITnef：：ExtractProps](itnef-extractprops.md) 方法可解码 TNEF 流，将封装的属性写入新消息中。</span><span class="sxs-lookup"><span data-stu-id="4a052-123">Use the [ITnef::ExtractProps](itnef-extractprops.md) method to decode the TNEF stream and write the encapsulated properties into the new message.</span></span> <span data-ttu-id="4a052-124">解码编码属性时，任何为非编码属性重复的编码属性都将覆盖非编码属性。</span><span class="sxs-lookup"><span data-stu-id="4a052-124">Any encoded properties that are duplicates of nonencoded properties will overwrite the nonencoded properties when the encoded properties are decoded.</span></span> 
    
6. <span data-ttu-id="4a052-125">使用 [ITnef：：OpenTaggedBody](itnef-opentaggedbody.md) 方法分析邮件文本，以从邮件文本中的标记恢复附件位置。</span><span class="sxs-lookup"><span data-stu-id="4a052-125">Use the [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) method to parse the message text to recover attachment positions from the tags in the message text.</span></span> 
    

