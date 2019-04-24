---
title: 使用 TNEF 自定义附件处理接收邮件
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bb5082fa-8fe3-46fe-b2de-b6dd1af79ea7
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 046b537d41b318fa857ef77f1906edcf2c3aa2bf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328425"
---
# <a name="receiving-messages-by-using-tnef-custom-attachment-processing"></a><span data-ttu-id="9f0c4-103">使用 TNEF 自定义附件处理接收邮件</span><span class="sxs-lookup"><span data-stu-id="9f0c4-103">Receiving Messages by Using TNEF Custom Attachment Processing</span></span>

 
  
<span data-ttu-id="9f0c4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9f0c4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9f0c4-105">若要接收自定义附件处理的 TNEF 邮件, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="9f0c4-105">To receive a TNEF message with customized attachment processing:</span></span>
  
1. <span data-ttu-id="9f0c4-106">将传入邮件中的所有传输属性 (邮件系统支持的属性) 从传入邮件导入到新 MAPI 邮件中。</span><span class="sxs-lookup"><span data-stu-id="9f0c4-106">Import all the transmittable properties — those that the messaging system supports — from the incoming message into a new MAPI message.</span></span> <span data-ttu-id="9f0c4-107">这包括包含 TNEF 数据流的邮件文本。</span><span class="sxs-lookup"><span data-stu-id="9f0c4-107">This includes the message text, which contains the TNEF data stream.</span></span>
    
2. <span data-ttu-id="9f0c4-108">标识和解码包含 TNEF 流的特殊附件。</span><span class="sxs-lookup"><span data-stu-id="9f0c4-108">Identify and decode the special attachment that contains the TNEF stream.</span></span>
    
3. <span data-ttu-id="9f0c4-109">将传入邮件中的所有附件提取到新 mapi 邮件的 mapi 附件中。</span><span class="sxs-lookup"><span data-stu-id="9f0c4-109">Extract all the attachments from the incoming message into MAPI attachments on the new MAPI message.</span></span> <span data-ttu-id="9f0c4-110">已恢复的文件名或附件上的其他标识标记应放入新附件的**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性中, 以便[ITnef:: ExtractProps](itnef-extractprops.md)方法以后可以将正确的附件与在邮件文本中编码的附件标记相关联。</span><span class="sxs-lookup"><span data-stu-id="9f0c4-110">The recovered filenames, or other identifying markers on the attachments, should be placed into the **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) property of the new attachments so that the [ITnef::ExtractProps](itnef-extractprops.md) method can later associate the correct attachment with the attachment tags encoded in the message text.</span></span> 
    
4. <span data-ttu-id="9f0c4-111">创建 OLE **IStream**接口以回绕解码的 TNEF 流, 并在调用[OpenTnefStreamEx](opentnefstreamex.md)函数的同时将该对象与新 MAPI 邮件一起使用。</span><span class="sxs-lookup"><span data-stu-id="9f0c4-111">Create an OLE **IStream** interface to wrap around the decoded TNEF stream and use that object along with the new MAPI message in a call to the [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
    
5. <span data-ttu-id="9f0c4-112">调用**ITnef:: ExtractProps**方法, 从 TNEF 数据流恢复邮件的 nontransmittable 属性。</span><span class="sxs-lookup"><span data-stu-id="9f0c4-112">Call the **ITnef::ExtractProps** method to recover the nontransmittable properties on the message from the TNEF data stream.</span></span> 
    
6. <span data-ttu-id="9f0c4-113">使用 MAPI_CREATE 和 MAPI_MODIFY 标志集调用[ITnef:: OpenTaggedBody](itnef-opentaggedbody.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9f0c4-113">Call the [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) method with the MAPI_CREATE and MAPI_MODIFY flags set.</span></span> <span data-ttu-id="9f0c4-114">此调用将从邮件文本中删除附件标记, 并将其转换为 MAPI 邮件中的附件位置信息。</span><span class="sxs-lookup"><span data-stu-id="9f0c4-114">This call removes the attachment tags from the message text and converts them into attachment position information in the MAPI message.</span></span> 
    
7. <span data-ttu-id="9f0c4-115">通过 MAPI 后台处理程序传递邮件。</span><span class="sxs-lookup"><span data-stu-id="9f0c4-115">Deliver the message through the MAPI spooler.</span></span>
    

