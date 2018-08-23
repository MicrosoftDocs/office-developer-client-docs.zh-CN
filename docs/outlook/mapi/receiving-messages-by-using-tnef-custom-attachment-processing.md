---
title: 使用 TNEF 自定义附件处理接收邮件
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bb5082fa-8fe3-46fe-b2de-b6dd1af79ea7
description: 上次修改时间： 2015年12月7日
ms.openlocfilehash: 67c202e5130bd35e1277c5260bc1702043eadd95
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588025"
---
# <a name="receiving-messages-by-using-tnef-custom-attachment-processing"></a><span data-ttu-id="e2562-103">使用 TNEF 自定义附件处理接收邮件</span><span class="sxs-lookup"><span data-stu-id="e2562-103">Receiving Messages by Using TNEF Custom Attachment Processing</span></span>

 
  
<span data-ttu-id="e2562-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e2562-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e2562-105">若要将收到带有自定义的附件处理的 TNEF 邮件：</span><span class="sxs-lookup"><span data-stu-id="e2562-105">To receive a TNEF message with customized attachment processing:</span></span>
  
1. <span data-ttu-id="e2562-106">导入所有可传送的属性-邮件系统支持的那些 — 从到新的 MAPI 邮件的传入消息。</span><span class="sxs-lookup"><span data-stu-id="e2562-106">Import all the transmittable properties — those that the messaging system supports — from the incoming message into a new MAPI message.</span></span> <span data-ttu-id="e2562-107">这包括消息文本，其中包含 TNEF 数据流。</span><span class="sxs-lookup"><span data-stu-id="e2562-107">This includes the message text, which contains the TNEF data stream.</span></span>
    
2. <span data-ttu-id="e2562-108">标识并解码特殊附件包含的 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="e2562-108">Identify and decode the special attachment that contains the TNEF stream.</span></span>
    
3. <span data-ttu-id="e2562-109">到新的 MAPI 邮件上的 MAPI 附件传入邮件中提取的所有附件。</span><span class="sxs-lookup"><span data-stu-id="e2562-109">Extract all the attachments from the incoming message into MAPI attachments on the new MAPI message.</span></span> <span data-ttu-id="e2562-110">恢复的文件名或附件，其他标识标记应放置到新附件的**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性，以便的[ITnef::ExtractProps](itnef-extractprops.md)方法更高版本与编码消息文本中的附件标记关联的正确的附件。</span><span class="sxs-lookup"><span data-stu-id="e2562-110">The recovered filenames, or other identifying markers on the attachments, should be placed into the **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) property of the new attachments so that the [ITnef::ExtractProps](itnef-extractprops.md) method can later associate the correct attachment with the attachment tags encoded in the message text.</span></span> 
    
4. <span data-ttu-id="e2562-111">创建一个 OLE **IStream**接口环绕解码 TNEF 流和[OpenTnefStreamEx](opentnefstreamex.md)函数调用中使用新的 MAPI 邮件以及该对象。</span><span class="sxs-lookup"><span data-stu-id="e2562-111">Create an OLE **IStream** interface to wrap around the decoded TNEF stream and use that object along with the new MAPI message in a call to the [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
    
5. <span data-ttu-id="e2562-112">调用**ITnef::ExtractProps**方法从 TNEF 数据流恢复邮件 nontransmittable 属性。</span><span class="sxs-lookup"><span data-stu-id="e2562-112">Call the **ITnef::ExtractProps** method to recover the nontransmittable properties on the message from the TNEF data stream.</span></span> 
    
6. <span data-ttu-id="e2562-113">调用 MAPI_CREATE 和 MAPI_MODIFY 设置 flags [ITnef::OpenTaggedBody](itnef-opentaggedbody.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e2562-113">Call the [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) method with the MAPI_CREATE and MAPI_MODIFY flags set.</span></span> <span data-ttu-id="e2562-114">此呼叫从消息文本中删除附件标记，并将它们转换为附件 MAPI 消息中的位置信息。</span><span class="sxs-lookup"><span data-stu-id="e2562-114">This call removes the attachment tags from the message text and converts them into attachment position information in the MAPI message.</span></span> 
    
7. <span data-ttu-id="e2562-115">通过 MAPI 后台处理程序将邮件传递。</span><span class="sxs-lookup"><span data-stu-id="e2562-115">Deliver the message through the MAPI spooler.</span></span>
    

