---
title: TNEF 处理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d324fb3-d917-4502-b3a4-179c479deb79
description: 上次修改时间： 2012 年 7 月 5 日
ms.openlocfilehash: bd9cc49f5d1d865d5d6b222677df0dd62ec36fd6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778978"
---
# <a name="tnef-processing"></a><span data-ttu-id="0f965-103">TNEF 处理</span><span class="sxs-lookup"><span data-stu-id="0f965-103">TNEF Processing</span></span>

  
  
<span data-ttu-id="0f965-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0f965-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0f965-105">以下一系列操作描述传输如何使用 TNEF 方法处理传出和传入邮件。</span><span class="sxs-lookup"><span data-stu-id="0f965-105">The following series of actions describe how transports use TNEF methods to process outgoing and incoming messages.</span></span>
  
 <span data-ttu-id="0f965-106">**发送一条消息，包括 TNEF 流**</span><span class="sxs-lookup"><span data-stu-id="0f965-106">**To send a message that includes a TNEF stream**</span></span>
  
1. <span data-ttu-id="0f965-107">处理的消息系统支持的邮件属性。</span><span class="sxs-lookup"><span data-stu-id="0f965-107">Process the message properties that are supported by the messaging system.</span></span>
    
2. <span data-ttu-id="0f965-108">将邮件标记中实现特定方式，以便接收传输提供程序可以确定邮件需要 TNEF 处理。</span><span class="sxs-lookup"><span data-stu-id="0f965-108">Mark the message in an implementation specific way so that the receiving transport provider can determine that the message requires TNEF processing.</span></span> <span data-ttu-id="0f965-109">例如，TNEF 传输提供程序将发送到 SMTP 邮件系统可能会添加一个自定义标头字段，如"X-包含-TNEF"以指示邮件包含 TNEF 数据。</span><span class="sxs-lookup"><span data-stu-id="0f965-109">For example, a TNEF transport provider sending to an SMTP messaging system might add a custom header field like "X-CONTAINS-TNEF" to indicate that the message contains TNEF data.</span></span>
    
3. <span data-ttu-id="0f965-110">获取一个 TNEF 对象并使用它来封装到 TNEF 流不支持在邮件系统的邮件属性。</span><span class="sxs-lookup"><span data-stu-id="0f965-110">Obtain a TNEF object and use it to encapsulate the message properties not supported by the messaging system into a TNEF stream.</span></span>
    
4. <span data-ttu-id="0f965-111">对使用消息系统的附件模型 TNEF 流进行编码。</span><span class="sxs-lookup"><span data-stu-id="0f965-111">Encode the TNEF stream using the messaging system's attachment model.</span></span> <span data-ttu-id="0f965-112">例如，如果基础附件模型到 uuencode 附件，并将其追加到的消息文本，然后传输提供程序必须 uuencode TNEF 流到另一个附件。</span><span class="sxs-lookup"><span data-stu-id="0f965-112">For example, if the underlying attachment model is to uuencode attachments and append them to the message text, then the transport provider must uuencode the TNEF stream into another attachment.</span></span> <span data-ttu-id="0f965-113">传输提供程序还必须实现识别哪些附件包含已编码的 TNEF 流时收到消息的方法。</span><span class="sxs-lookup"><span data-stu-id="0f965-113">The transport provider must also implement a method for recognizing which attachment contains the encoded TNEF stream when it receives a message.</span></span> <span data-ttu-id="0f965-114">标记此附件标准方式是要为其提供"WINMAIL 附件文件名。揭示数据"。</span><span class="sxs-lookup"><span data-stu-id="0f965-114">The standard way to mark this attachment is to give it an attachment filename of "WINMAIL.DAT".</span></span> <span data-ttu-id="0f965-115">如果您传输提供程序执行此操作，遵循此约定任何其他 TNEF 启用传输提供程序都将能够与之进行互操作。</span><span class="sxs-lookup"><span data-stu-id="0f965-115">If your transport provider does this, any other TNEF-enabled transport providers that follow this convention will be able to interoperate with it.</span></span>
    
5. <span data-ttu-id="0f965-116">使用[ITnef: IUnknown](itnefiunknown.md)接口方法插入标记描述消息文本中的邮件附件的位置。</span><span class="sxs-lookup"><span data-stu-id="0f965-116">Use [ITnef : IUnknown](itnefiunknown.md) interface methods to insert tags describing the positions of message attachments in the message text.</span></span> 
    
6. <span data-ttu-id="0f965-117">通过[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)方法访问已标记的邮件文本，并将其发送给邮件系统。</span><span class="sxs-lookup"><span data-stu-id="0f965-117">Access the tagged message text through [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx) methods, and send it to the messaging system.</span></span> 
    
 <span data-ttu-id="0f965-118">**若要检索封装的属性**</span><span class="sxs-lookup"><span data-stu-id="0f965-118">**To retrieve encapsulated properties**</span></span>
  
1. <span data-ttu-id="0f965-119">写入到新邮件，包括已标记的邮件文本，其中包含封装的属性支持邮件系统的属性。</span><span class="sxs-lookup"><span data-stu-id="0f965-119">Write the properties supported by the messaging system into a new message, including the tagged message text that contains the encapsulated properties.</span></span>
    
2. <span data-ttu-id="0f965-120">解码 TNEF stream 从适当的附件。</span><span class="sxs-lookup"><span data-stu-id="0f965-120">Decode the TNEF stream from the proper attachment.</span></span>
    
3. <span data-ttu-id="0f965-121">解码任何其他附件，并将它们写入新 MAPI 附件上一条消息。</span><span class="sxs-lookup"><span data-stu-id="0f965-121">Decode any other attachments and write them to new MAPI attachments on a message.</span></span>
    
4. <span data-ttu-id="0f965-122">打开 TNEF 流解码使用[OpenTnefStreamEx](opentnefstreamex.md)函数。</span><span class="sxs-lookup"><span data-stu-id="0f965-122">Open the TNEF stream for decoding using the [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
    
5. <span data-ttu-id="0f965-123">使用[ITnef::ExtractProps](itnef-extractprops.md)方法进行解码 TNEF 流，并编写封装的属性到新邮件。</span><span class="sxs-lookup"><span data-stu-id="0f965-123">Use the [ITnef::ExtractProps](itnef-extractprops.md) method to decode the TNEF stream and write the encapsulated properties into the new message.</span></span> <span data-ttu-id="0f965-124">重复 nonencoded 任何的属性编码的属性将覆盖 nonencoded 的属性时进行解码的编码的属性。</span><span class="sxs-lookup"><span data-stu-id="0f965-124">Any encoded properties that are duplicates of nonencoded properties will overwrite the nonencoded properties when the encoded properties are decoded.</span></span> 
    
6. <span data-ttu-id="0f965-125">使用[ITnef::OpenTaggedBody](itnef-opentaggedbody.md)方法解析的消息文本从消息文本中的标记中恢复附件的位置。</span><span class="sxs-lookup"><span data-stu-id="0f965-125">Use the [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) method to parse the message text to recover attachment positions from the tags in the message text.</span></span> 
    

