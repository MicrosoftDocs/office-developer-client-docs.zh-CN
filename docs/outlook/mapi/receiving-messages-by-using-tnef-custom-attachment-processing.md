---
title: 使用 TNEF 自定义附件处理接收消息
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bb5082fa-8fe3-46fe-b2de-b6dd1af79ea7
description: 上次修改时间： 2015 年 12 月 7 日
ms.openlocfilehash: 18fc0983554284355dcdfb301fd41a0161a860fe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778613"
---
# <a name="receiving-messages-by-using-tnef-custom-attachment-processing"></a><span data-ttu-id="5815b-103">使用 TNEF 自定义附件处理接收消息</span><span class="sxs-lookup"><span data-stu-id="5815b-103">Receiving Messages by Using TNEF Custom Attachment Processing</span></span>

 
  
<span data-ttu-id="5815b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5815b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5815b-105">若要将收到带有自定义的附件处理的 TNEF 邮件：</span><span class="sxs-lookup"><span data-stu-id="5815b-105">To receive a TNEF message with customized attachment processing:</span></span>
  
1. <span data-ttu-id="5815b-106">导入所有可传送的属性-邮件系统支持的那些 — 从到新的 MAPI 邮件的传入消息。</span><span class="sxs-lookup"><span data-stu-id="5815b-106">Import all the transmittable properties — those that the messaging system supports — from the incoming message into a new MAPI message.</span></span> <span data-ttu-id="5815b-107">这包括消息文本，其中包含 TNEF 数据流。</span><span class="sxs-lookup"><span data-stu-id="5815b-107">This includes the message text, which contains the TNEF data stream.</span></span>
    
2. <span data-ttu-id="5815b-108">标识并解码特殊附件包含的 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="5815b-108">Identify and decode the special attachment that contains the TNEF stream.</span></span>
    
3. <span data-ttu-id="5815b-109">到新的 MAPI 邮件上的 MAPI 附件传入邮件中提取的所有附件。</span><span class="sxs-lookup"><span data-stu-id="5815b-109">Extract all the attachments from the incoming message into MAPI attachments on the new MAPI message.</span></span> <span data-ttu-id="5815b-110">恢复的文件名或附件，其他标识标记应放置到新附件的**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性，以便的[ITnef::ExtractProps](itnef-extractprops.md)方法更高版本与编码消息文本中的附件标记关联的正确的附件。</span><span class="sxs-lookup"><span data-stu-id="5815b-110">The recovered filenames, or other identifying markers on the attachments, should be placed into the **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) property of the new attachments so that the [ITnef::ExtractProps](itnef-extractprops.md) method can later associate the correct attachment with the attachment tags encoded in the message text.</span></span> 
    
4. <span data-ttu-id="5815b-111">创建一个 OLE **IStream**接口环绕解码 TNEF 流和[OpenTnefStreamEx](opentnefstreamex.md)函数调用中使用新的 MAPI 邮件以及该对象。</span><span class="sxs-lookup"><span data-stu-id="5815b-111">Create an OLE **IStream** interface to wrap around the decoded TNEF stream and use that object along with the new MAPI message in a call to the [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
    
5. <span data-ttu-id="5815b-112">调用**ITnef::ExtractProps**方法从 TNEF 数据流恢复邮件 nontransmittable 属性。</span><span class="sxs-lookup"><span data-stu-id="5815b-112">Call the **ITnef::ExtractProps** method to recover the nontransmittable properties on the message from the TNEF data stream.</span></span> 
    
6. <span data-ttu-id="5815b-113">调用 MAPI_CREATE 和 MAPI_MODIFY 设置 flags [ITnef::OpenTaggedBody](itnef-opentaggedbody.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5815b-113">Call the [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) method with the MAPI_CREATE and MAPI_MODIFY flags set.</span></span> <span data-ttu-id="5815b-114">此呼叫从消息文本中删除附件标记，并将它们转换为附件 MAPI 消息中的位置信息。</span><span class="sxs-lookup"><span data-stu-id="5815b-114">This call removes the attachment tags from the message text and converts them into attachment position information in the MAPI message.</span></span> 
    
7. <span data-ttu-id="5815b-115">通过 MAPI 后台处理程序将邮件传递。</span><span class="sxs-lookup"><span data-stu-id="5815b-115">Deliver the message through the MAPI spooler.</span></span>
    

