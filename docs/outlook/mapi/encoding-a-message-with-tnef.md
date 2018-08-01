---
title: 编码与 TNEF 邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6b86d9a9-6876-4885-ae1e-8571b25b85cc
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2cb5c9a971f95e309f0a91cf477eefe98fe3bd64
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774892"
---
# <a name="encoding-a-message-with-tnef"></a><span data-ttu-id="ac271-103">编码与 TNEF 邮件</span><span class="sxs-lookup"><span data-stu-id="ac271-103">Encoding a message with TNEF</span></span>

<span data-ttu-id="ac271-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ac271-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ac271-105">提交一条消息时, 传输提供程序可以创建用于在传输过程包含邮件文件。</span><span class="sxs-lookup"><span data-stu-id="ac271-105">When a message is submitted, the transport provider can create a file that is used to contain the message during transmission.</span></span> <span data-ttu-id="ac271-106">接下来， [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)接口环绕该文件。</span><span class="sxs-lookup"><span data-stu-id="ac271-106">Next, an [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx) interface is wrapped around the file.</span></span> <span data-ttu-id="ac271-107">传输提供程序然后使用[ITnef](itnefiunknown.md)方法使属性可以轻松地进行解码接收传输提供程序的已标记格式的流中写入消息属性。</span><span class="sxs-lookup"><span data-stu-id="ac271-107">The transport provider then uses [ITnef](itnefiunknown.md) methods to write the message properties to the stream in a tagged format that enables the properties to be easily decoded by the receiving transport providers.</span></span> 
  
<span data-ttu-id="ac271-108">**表示单个文件中的整个邮件**</span><span class="sxs-lookup"><span data-stu-id="ac271-108">**To represent an entire message in a single file**</span></span>
  
1. <span data-ttu-id="ac271-109">通过将[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)对象和消息传递到[OpenTnefStreamEx](opentnefstreamex.md)函数获取 TNEF 对象。</span><span class="sxs-lookup"><span data-stu-id="ac271-109">Obtain a TNEF object by passing an [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx) object and a message into the [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
    
2. <span data-ttu-id="ac271-110">通过调用[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法获得邮件的所有定义属性的列表。</span><span class="sxs-lookup"><span data-stu-id="ac271-110">Get a list of all defined properties for the message by calling the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method.</span></span> 
    
3. <span data-ttu-id="ac271-111">使用[IMAPIProp](imapipropiunknown.md)方法来排除在邮件系统支持的所有属性。</span><span class="sxs-lookup"><span data-stu-id="ac271-111">Use [IMAPIProp](imapipropiunknown.md) methods to exclude all properties supported by the messaging system.</span></span> <span data-ttu-id="ac271-112">在适当的时间，将这些属性写入邮件系统中的消息的系统要求的格式。</span><span class="sxs-lookup"><span data-stu-id="ac271-112">At an appropriate time, write those properties to the messaging system in the format required by the messaging system.</span></span> 
    
4. <span data-ttu-id="ac271-113">调用[ITnef::AddProps](itnef-addprops.md)进行编码其余的属性，包括所有附件。</span><span class="sxs-lookup"><span data-stu-id="ac271-113">Call [ITnef::AddProps](itnef-addprops.md) to encode the remaining properties, including all attachments.</span></span> 
    
5. <span data-ttu-id="ac271-114">调用[ITnef::Finish](itnef-finish.md)方法后所有请求的属性将被添加到 TNEF 流编码邮件。</span><span class="sxs-lookup"><span data-stu-id="ac271-114">Call the [ITnef::Finish](itnef-finish.md) method to encode the message into the TNEF stream after all the requested properties are added.</span></span> 
    
6. <span data-ttu-id="ac271-115">调用[ITnef::OpenTaggedBody](itnef-opentaggedbody.md)方法以获取的已标记的消息文本。</span><span class="sxs-lookup"><span data-stu-id="ac271-115">Call the [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) method to obtain the tagged message text.</span></span> <span data-ttu-id="ac271-116">此标记的文本是写出到邮件系统使用从 OLE [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)接口的方法。</span><span class="sxs-lookup"><span data-stu-id="ac271-116">This tagged text is written out to the messaging system using methods from the OLE [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx) interface.</span></span> 
    
7. <span data-ttu-id="ac271-117">调用[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28VS.85%29.aspx)方法以释放**ITnef**对象。</span><span class="sxs-lookup"><span data-stu-id="ac271-117">Call the [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28VS.85%29.aspx) method to release the **ITnef** object.</span></span> 
    
<span data-ttu-id="ac271-118">**处理入站的 TNEF 邮件**</span><span class="sxs-lookup"><span data-stu-id="ac271-118">**To process an inbound TNEF message**</span></span>
  
1. <span data-ttu-id="ac271-119">从 MAPI 后台处理程序中获取 MAPI 邮件对象和写入到新的 MAPI 邮件的邮件头属性。</span><span class="sxs-lookup"><span data-stu-id="ac271-119">Get a MAPI message object from the MAPI spooler and write message header properties into the new MAPI message.</span></span>
    
2. <span data-ttu-id="ac271-120">创建并初始化[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)对象以包含从入站邮件的 TNEF 数据。</span><span class="sxs-lookup"><span data-stu-id="ac271-120">Create and initialize an [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx) object to contain the TNEF data from the inbound message.</span></span> 
    
3. <span data-ttu-id="ac271-121">传递给[OpenTnefStreamEx](opentnefstreamex.md)函数的 MAPI 邮件和[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)对象。</span><span class="sxs-lookup"><span data-stu-id="ac271-121">Pass the MAPI message and the [IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx) object to the [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
    
4. <span data-ttu-id="ac271-122">通过调用[ITnef::ExtractProps](itnef-extractprops.md)方法解码 TNEF 数据中的信息。</span><span class="sxs-lookup"><span data-stu-id="ac271-122">Decode the information in the TNEF data by calling the [ITnef::ExtractProps](itnef-extractprops.md) method.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="ac271-123">任何由**ExtractProps**解码将覆盖从传入邮件信封进行解码的属性。</span><span class="sxs-lookup"><span data-stu-id="ac271-123">Anything decoded by **ExtractProps** will overwrite properties decoded from the incoming message's envelope.</span></span> <span data-ttu-id="ac271-124">即提取的 TNEF 属性将覆盖一条消息中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="ac271-124">That is, extracted TNEF properties will overwrite the existing properties in a message.</span></span> 
  
5. <span data-ttu-id="ac271-125">通过调用[ITnef::OpenTaggedBody](itnef-opentaggedbody.md)处理已标记的邮件文本，并分析文本以恢复附件的位置。</span><span class="sxs-lookup"><span data-stu-id="ac271-125">Process the tagged message text by calling [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) and parse the text to recover attachment positions.</span></span> 
    
6. <span data-ttu-id="ac271-126">通过调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)保存邮件。</span><span class="sxs-lookup"><span data-stu-id="ac271-126">Save the message by calling [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span>
    
7. <span data-ttu-id="ac271-127">通过调用[IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28VS.85%29.aspx)方法释放 TNEF 对象。</span><span class="sxs-lookup"><span data-stu-id="ac271-127">Release the TNEF object by calling the [IUnknown::Release](http://msdn.microsoft.com/en-us/library/ms682317%28VS.85%29.aspx) method.</span></span> 
    

