---
title: 使用 TNEF 自定义附件处理发送邮件
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: da318b6f-128a-44b5-8357-a130022030a1
description: 上次修改时间： 2015年12月7日
ms.openlocfilehash: f9d154b26319f5ed72b1abd6aeef307d07a63bda
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388565"
---
# <a name="sending-messages-by-using-tnef-custom-attachment-processing"></a><span data-ttu-id="70741-103">使用 TNEF 自定义附件处理发送邮件</span><span class="sxs-lookup"><span data-stu-id="70741-103">Sending Messages by Using TNEF Custom Attachment Processing</span></span>

 
  
<span data-ttu-id="70741-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="70741-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="70741-105">发送邮件时，自定义附件处理：</span><span class="sxs-lookup"><span data-stu-id="70741-105">To customize attachment processing when sending a message:</span></span>
  
1. <span data-ttu-id="70741-106">通过将一个**IStream**接口和消息传递到[OpenTnefStreamEx](opentnefstreamex.md)函数获取 TNEF 对象。</span><span class="sxs-lookup"><span data-stu-id="70741-106">Obtain a TNEF object by passing an **IStream** interface and a message into the [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
    
2. <span data-ttu-id="70741-107">通过调用[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法获得邮件的所有定义属性的列表。</span><span class="sxs-lookup"><span data-stu-id="70741-107">Get a list of all defined properties for the message by calling the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method.</span></span> 
    
3. <span data-ttu-id="70741-108">使用[IMAPIProp](imapipropiunknown.md)方法来排除在邮件系统支持的所有属性。</span><span class="sxs-lookup"><span data-stu-id="70741-108">Use [IMAPIProp](imapipropiunknown.md) methods to exclude all properties supported by the messaging system.</span></span> <span data-ttu-id="70741-109">在适当的时间将这些属性写入邮件系统中的消息的系统要求的格式。</span><span class="sxs-lookup"><span data-stu-id="70741-109">At an appropriate time write those properties to the messaging system in the format required by the messaging system.</span></span> 
    
4. <span data-ttu-id="70741-110">调用[ITnef::AddProps](itnef-addprops.md)方法来添加对邮件仅属性 — 即，没有对附件的属性，通过设置 TNEF_PROP_MESSAGE_ONLY 标志。</span><span class="sxs-lookup"><span data-stu-id="70741-110">Call the [ITnef::AddProps](itnef-addprops.md) method to add only the properties on the message — that is, none of the properties on the attachments — by setting the TNEF_PROP_MESSAGE_ONLY flag.</span></span> 
    
5. <span data-ttu-id="70741-111">使用这些项目调用[ITnef::AddProps](itnef-addprops.md) : TNEF_PROP_EXCLUDE 标志、 属性标记数组包含**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 或**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md))属性，并指定要处理的附件的附件标识符。</span><span class="sxs-lookup"><span data-stu-id="70741-111">Call [ITnef::AddProps](itnef-addprops.md) with these items: the TNEF_PROP_EXCLUDE flag, a property tag array that contains the **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) or **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property, and an attachment identifier that specifies the attachment to be processed.</span></span>
    
6. <span data-ttu-id="70741-112">使用[ITnef::SetProps](itnef-setprops.md)方法添加**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性标记与标识邮件系统的附件，如果附件文件名的唯一字符串的无法支持邮件系统。</span><span class="sxs-lookup"><span data-stu-id="70741-112">Use the [ITnef::SetProps](itnef-setprops.md) method to add the **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) property tag with a unique string that identifies the attachment to the messaging system if the attachment has a filename that the messaging system cannot support.</span></span> <span data-ttu-id="70741-113">例如，多个附件具有相同的原始文件名或不是有效的文件名为邮件系统的文件名。</span><span class="sxs-lookup"><span data-stu-id="70741-113">For example, multiple attachments with the same original filename, or a filename that is not a valid filename for the messaging system.</span></span> <span data-ttu-id="70741-114">此字符串将用于与主要号码已标记的消息文本中写入的附件标记时其数据相关联的附件。</span><span class="sxs-lookup"><span data-stu-id="70741-114">This string will be used with a key number when writing the attachment tags in the tagged message text to associate an attachment with its data.</span></span> <span data-ttu-id="70741-115">有关详细信息，请参阅[TNEF-Tagged 消息文本](tnef-tagged-message-text.md)。</span><span class="sxs-lookup"><span data-stu-id="70741-115">For more information, see, [TNEF-Tagged Message Text](tnef-tagged-message-text.md).</span></span>
    
7. <span data-ttu-id="70741-116">每个附件重复**AddProps**和**SetProps**呼叫。</span><span class="sxs-lookup"><span data-stu-id="70741-116">Repeat the **AddProps** and **SetProps** calls for each attachment.</span></span> 
    
8. <span data-ttu-id="70741-117">调用[ITnef::Finish](itnef-finish.md)方法后所有请求的属性将被添加到 TNEF 流编码邮件。</span><span class="sxs-lookup"><span data-stu-id="70741-117">Call the [ITnef::Finish](itnef-finish.md) method to encode the message into the TNEF stream after all the requested properties are added.</span></span> 
    
9. <span data-ttu-id="70741-118">通过调用[ITnef::OpenTaggedBody](itnef-opentaggedbody.md)方法来获取标记的消息文本。</span><span class="sxs-lookup"><span data-stu-id="70741-118">Obtain the tagged message text by calling the [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) method.</span></span> <span data-ttu-id="70741-119">从**IStream**接口，使用消息系统的附件模型编码和写出到邮件系统使用方法读取此标记的文本。</span><span class="sxs-lookup"><span data-stu-id="70741-119">This tagged text is read using methods from the **IStream** interface, encoded using the messaging system's attachment model, and written out to the messaging system.</span></span> 
    
10. <span data-ttu-id="70741-120">调用[IUnknown::Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法以释放[ITnef](itnefiunknown.md)对象。</span><span class="sxs-lookup"><span data-stu-id="70741-120">Call the [IUnknown::Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) method to release the [ITnef](itnefiunknown.md) object.</span></span> 
    
11. <span data-ttu-id="70741-121">编写邮件系统的附件模型通过在邮件系统的其余附件。</span><span class="sxs-lookup"><span data-stu-id="70741-121">Write the remaining attachments to the messaging system through the messaging system's attachment model.</span></span>
    
<span data-ttu-id="70741-122">传输提供程序应使用过程附件前面所述的过程。</span><span class="sxs-lookup"><span data-stu-id="70741-122">Your transport provider should use the previously described procedure to process attachments.</span></span> <span data-ttu-id="70741-123">如果这是不可能的传输提供程序应进行自定义的附件处理使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="70741-123">If that is not possible, the transport provider should use the following steps for customized attachment processing:</span></span>
  
1. <span data-ttu-id="70741-124">传输提供程序可确保所有附件的**PR_ATTACH_TRANSPORT_NAME**属性包含唯一值都是有效的附件的邮件系统的标识符。</span><span class="sxs-lookup"><span data-stu-id="70741-124">The transport provider ensures that the **PR_ATTACH_TRANSPORT_NAME** properties of all the attachments contain unique values that are valid attachment identifiers for the messaging system.</span></span> 
    
2. <span data-ttu-id="70741-125">传输提供程序并将每个附件，TNEF_PROP_CONTAINED 标志中传递到**ITnef::AddProps**单个呼叫。</span><span class="sxs-lookup"><span data-stu-id="70741-125">The transport provider then uses a single call to **ITnef::AddProps** for each attachment, passing in the TNEF_PROP_CONTAINED flag.</span></span> 
    

