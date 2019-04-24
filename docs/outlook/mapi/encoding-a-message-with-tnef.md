---
title: 使用 TNEF 对邮件编码
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6b86d9a9-6876-4885-ae1e-8571b25b85cc
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: cdaa03cfbc0bbd0fcf6a320ecf8fae9f372d5781
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336699"
---
# <a name="encoding-a-message-with-tnef"></a><span data-ttu-id="0cb55-103">使用 TNEF 对邮件编码</span><span class="sxs-lookup"><span data-stu-id="0cb55-103">Encoding a message with TNEF</span></span>

<span data-ttu-id="0cb55-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0cb55-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0cb55-105">提交邮件时, 传输提供程序可以创建用于在传输过程中包含邮件的文件。</span><span class="sxs-lookup"><span data-stu-id="0cb55-105">When a message is submitted, the transport provider can create a file that is used to contain the message during transmission.</span></span> <span data-ttu-id="0cb55-106">接下来, 将在文件周围封装[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口。</span><span class="sxs-lookup"><span data-stu-id="0cb55-106">Next, an [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) interface is wrapped around the file.</span></span> <span data-ttu-id="0cb55-107">然后, 传输提供程序使用[ITnef](itnefiunknown.md)方法将邮件属性以标记格式写入流, 从而使接收传输提供程序可以轻松地对属性进行解码。</span><span class="sxs-lookup"><span data-stu-id="0cb55-107">The transport provider then uses [ITnef](itnefiunknown.md) methods to write the message properties to the stream in a tagged format that enables the properties to be easily decoded by the receiving transport providers.</span></span> 
  
<span data-ttu-id="0cb55-108">**表示单个文件中的整个邮件**</span><span class="sxs-lookup"><span data-stu-id="0cb55-108">**To represent an entire message in a single file**</span></span>
  
1. <span data-ttu-id="0cb55-109">通过将[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)对象和邮件传递到[OpenTnefStreamEx](opentnefstreamex.md)函数来获取 TNEF 对象。</span><span class="sxs-lookup"><span data-stu-id="0cb55-109">Obtain a TNEF object by passing an [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) object and a message into the [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
    
2. <span data-ttu-id="0cb55-110">通过调用[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法获取邮件的所有已定义属性的列表。</span><span class="sxs-lookup"><span data-stu-id="0cb55-110">Get a list of all defined properties for the message by calling the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method.</span></span> 
    
3. <span data-ttu-id="0cb55-111">使用[IMAPIProp](imapipropiunknown.md)方法排除邮件系统支持的所有属性。</span><span class="sxs-lookup"><span data-stu-id="0cb55-111">Use [IMAPIProp](imapipropiunknown.md) methods to exclude all properties supported by the messaging system.</span></span> <span data-ttu-id="0cb55-112">在适当的时间, 将这些属性以邮件系统所需的格式写入邮件系统。</span><span class="sxs-lookup"><span data-stu-id="0cb55-112">At an appropriate time, write those properties to the messaging system in the format required by the messaging system.</span></span> 
    
4. <span data-ttu-id="0cb55-113">调用[ITnef:: AddProps](itnef-addprops.md)对其余的属性 (包括所有附件) 进行编码。</span><span class="sxs-lookup"><span data-stu-id="0cb55-113">Call [ITnef::AddProps](itnef-addprops.md) to encode the remaining properties, including all attachments.</span></span> 
    
5. <span data-ttu-id="0cb55-114">在添加所有请求的属性后, 调用[ITnef:: Finish](itnef-finish.md)方法将邮件编码到 TNEF 流中。</span><span class="sxs-lookup"><span data-stu-id="0cb55-114">Call the [ITnef::Finish](itnef-finish.md) method to encode the message into the TNEF stream after all the requested properties are added.</span></span> 
    
6. <span data-ttu-id="0cb55-115">调用[ITnef:: OpenTaggedBody](itnef-opentaggedbody.md)方法以获取带标记的邮件文本。</span><span class="sxs-lookup"><span data-stu-id="0cb55-115">Call the [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) method to obtain the tagged message text.</span></span> <span data-ttu-id="0cb55-116">使用 OLE [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口中的方法将此标记的文本写入邮件系统。</span><span class="sxs-lookup"><span data-stu-id="0cb55-116">This tagged text is written out to the messaging system using methods from the OLE [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) interface.</span></span> 
    
7. <span data-ttu-id="0cb55-117">调用[IUnknown:: release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx)方法以释放**ITnef**对象。</span><span class="sxs-lookup"><span data-stu-id="0cb55-117">Call the [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx) method to release the **ITnef** object.</span></span> 
    
<span data-ttu-id="0cb55-118">**处理入站 TNEF 邮件**</span><span class="sxs-lookup"><span data-stu-id="0cb55-118">**To process an inbound TNEF message**</span></span>
  
1. <span data-ttu-id="0cb55-119">从 mapi 后台处理程序获取 mapi 邮件对象, 并将邮件头属性写入新 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="0cb55-119">Get a MAPI message object from the MAPI spooler and write message header properties into the new MAPI message.</span></span>
    
2. <span data-ttu-id="0cb55-120">创建并初始化[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)对象以包含入站邮件中的 TNEF 数据。</span><span class="sxs-lookup"><span data-stu-id="0cb55-120">Create and initialize an [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) object to contain the TNEF data from the inbound message.</span></span> 
    
3. <span data-ttu-id="0cb55-121">将 MAPI 邮件和[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)对象传递到[OpenTnefStreamEx](opentnefstreamex.md)函数。</span><span class="sxs-lookup"><span data-stu-id="0cb55-121">Pass the MAPI message and the [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) object to the [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
    
4. <span data-ttu-id="0cb55-122">通过调用[ITnef:: ExtractProps](itnef-extractprops.md)方法, 对 TNEF 数据中的信息进行解码。</span><span class="sxs-lookup"><span data-stu-id="0cb55-122">Decode the information in the TNEF data by calling the [ITnef::ExtractProps](itnef-extractprops.md) method.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="0cb55-123">由**ExtractProps**解码的任何内容都将覆盖从传入邮件的信封解码的属性。</span><span class="sxs-lookup"><span data-stu-id="0cb55-123">Anything decoded by **ExtractProps** will overwrite properties decoded from the incoming message's envelope.</span></span> <span data-ttu-id="0cb55-124">也就是说, 提取的 TNEF 属性将覆盖邮件中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="0cb55-124">That is, extracted TNEF properties will overwrite the existing properties in a message.</span></span> 
  
5. <span data-ttu-id="0cb55-125">通过调用[ITnef:: OpenTaggedBody](itnef-opentaggedbody.md)并分析文本来恢复附件位置, 以处理带标记的邮件文本。</span><span class="sxs-lookup"><span data-stu-id="0cb55-125">Process the tagged message text by calling [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) and parse the text to recover attachment positions.</span></span> 
    
6. <span data-ttu-id="0cb55-126">通过调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)保存邮件。</span><span class="sxs-lookup"><span data-stu-id="0cb55-126">Save the message by calling [IMAPIProp::SaveChanges](imapiprop-savechanges.md).</span></span>
    
7. <span data-ttu-id="0cb55-127">通过调用[IUnknown:: release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx)方法释放 TNEF 对象。</span><span class="sxs-lookup"><span data-stu-id="0cb55-127">Release the TNEF object by calling the [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx) method.</span></span> 
    

