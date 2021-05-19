---
title: 使用 TNEF 自定义附件处理发送邮件
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: da318b6f-128a-44b5-8357-a130022030a1
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: f9d154b26319f5ed72b1abd6aeef307d07a63bda
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339695"
---
# <a name="sending-messages-by-using-tnef-custom-attachment-processing"></a><span data-ttu-id="9015b-103">使用 TNEF 自定义附件处理发送邮件</span><span class="sxs-lookup"><span data-stu-id="9015b-103">Sending Messages by Using TNEF Custom Attachment Processing</span></span>

 
  
<span data-ttu-id="9015b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9015b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9015b-105">在发送邮件时自定义附件处理：</span><span class="sxs-lookup"><span data-stu-id="9015b-105">To customize attachment processing when sending a message:</span></span>
  
1. <span data-ttu-id="9015b-106">通过向 [OpenTnefStreamEx](opentnefstreamex.md)函数传递 **IStream** 接口和消息来获取 TNEF 对象。</span><span class="sxs-lookup"><span data-stu-id="9015b-106">Obtain a TNEF object by passing an **IStream** interface and a message into the [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
    
2. <span data-ttu-id="9015b-107">通过调用 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法获取邮件的所有已定义属性的列表。</span><span class="sxs-lookup"><span data-stu-id="9015b-107">Get a list of all defined properties for the message by calling the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method.</span></span> 
    
3. <span data-ttu-id="9015b-108">使用 [IMAPIProp](imapipropiunknown.md) 方法排除邮件系统支持的所有属性。</span><span class="sxs-lookup"><span data-stu-id="9015b-108">Use [IMAPIProp](imapipropiunknown.md) methods to exclude all properties supported by the messaging system.</span></span> <span data-ttu-id="9015b-109">在适当时，以邮件系统所需的格式将这些属性写入邮件系统。</span><span class="sxs-lookup"><span data-stu-id="9015b-109">At an appropriate time write those properties to the messaging system in the format required by the messaging system.</span></span> 
    
4. <span data-ttu-id="9015b-110">调用 [ITnef：：AddProps](itnef-addprops.md) 方法，通过设置"附件"标记，仅添加邮件上的属性（即，附件TNEF_PROP_MESSAGE_ONLY属性）。</span><span class="sxs-lookup"><span data-stu-id="9015b-110">Call the [ITnef::AddProps](itnef-addprops.md) method to add only the properties on the message — that is, none of the properties on the attachments — by setting the TNEF_PROP_MESSAGE_ONLY flag.</span></span> 
    
5. <span data-ttu-id="9015b-111">使用以下项目调用 [ITnef：：AddProps：TNEF_PROP_EXCLUDE](itnef-addprops.md) 标志、包含 **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 或 **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性的属性标记数组，以及指定要处理的附件的附件标识符。</span><span class="sxs-lookup"><span data-stu-id="9015b-111">Call [ITnef::AddProps](itnef-addprops.md) with these items: the TNEF_PROP_EXCLUDE flag, a property tag array that contains the **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) or **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property, and an attachment identifier that specifies the attachment to be processed.</span></span>
    
6. <span data-ttu-id="9015b-112">使用 [ITnef：：SetProps](itnef-setprops.md) 方法添加具有唯一字符串的 **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性标记，该字符串标识邮件系统的附件（如果附件具有邮件系统不支持的文件名）。</span><span class="sxs-lookup"><span data-stu-id="9015b-112">Use the [ITnef::SetProps](itnef-setprops.md) method to add the **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) property tag with a unique string that identifies the attachment to the messaging system if the attachment has a filename that the messaging system cannot support.</span></span> <span data-ttu-id="9015b-113">例如，具有同一原始文件名的多个附件，或不是邮件系统的有效文件名的文件名。</span><span class="sxs-lookup"><span data-stu-id="9015b-113">For example, multiple attachments with the same original filename, or a filename that is not a valid filename for the messaging system.</span></span> <span data-ttu-id="9015b-114">在带标记的邮件文本中写入附件标记以将附件与数据关联时，此字符串将和键号一起使用。</span><span class="sxs-lookup"><span data-stu-id="9015b-114">This string will be used with a key number when writing the attachment tags in the tagged message text to associate an attachment with its data.</span></span> <span data-ttu-id="9015b-115">有关详细信息，请参阅 [TNEF 标记的邮件文本](tnef-tagged-message-text.md)。</span><span class="sxs-lookup"><span data-stu-id="9015b-115">For more information, see, [TNEF-Tagged Message Text](tnef-tagged-message-text.md).</span></span>
    
7. <span data-ttu-id="9015b-116">对每个 **附件重复 AddProps** 和 **SetProps** 调用。</span><span class="sxs-lookup"><span data-stu-id="9015b-116">Repeat the **AddProps** and **SetProps** calls for each attachment.</span></span> 
    
8. <span data-ttu-id="9015b-117">在添加 [所有请求的属性后，调用 ITnef：：Finish](itnef-finish.md) 方法将邮件编码到 TNEF 流中。</span><span class="sxs-lookup"><span data-stu-id="9015b-117">Call the [ITnef::Finish](itnef-finish.md) method to encode the message into the TNEF stream after all the requested properties are added.</span></span> 
    
9. <span data-ttu-id="9015b-118">通过调用 [ITnef：：OpenTaggedBody](itnef-opentaggedbody.md) 方法获取带标记的邮件文本。</span><span class="sxs-lookup"><span data-stu-id="9015b-118">Obtain the tagged message text by calling the [ITnef::OpenTaggedBody](itnef-opentaggedbody.md) method.</span></span> <span data-ttu-id="9015b-119">此标记文本使用 **IStream** 接口中的方法读取，使用邮件系统的附件模型进行编码，并写入邮件系统。</span><span class="sxs-lookup"><span data-stu-id="9015b-119">This tagged text is read using methods from the **IStream** interface, encoded using the messaging system's attachment model, and written out to the messaging system.</span></span> 
    
10. <span data-ttu-id="9015b-120">调用 [IUnknown：：Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) 方法来释放 [ITnef](itnefiunknown.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="9015b-120">Call the [IUnknown::Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) method to release the [ITnef](itnefiunknown.md) object.</span></span> 
    
11. <span data-ttu-id="9015b-121">通过邮件系统的附件模型将剩余附件写入邮件系统。</span><span class="sxs-lookup"><span data-stu-id="9015b-121">Write the remaining attachments to the messaging system through the messaging system's attachment model.</span></span>
    
<span data-ttu-id="9015b-122">传输提供程序应该使用前面介绍的过程处理附件。</span><span class="sxs-lookup"><span data-stu-id="9015b-122">Your transport provider should use the previously described procedure to process attachments.</span></span> <span data-ttu-id="9015b-123">如果不可能，传输提供程序应执行以下步骤进行自定义附件处理：</span><span class="sxs-lookup"><span data-stu-id="9015b-123">If that is not possible, the transport provider should use the following steps for customized attachment processing:</span></span>
  
1. <span data-ttu-id="9015b-124">传输提供程序可确保所有 **PR_ATTACH_TRANSPORT_NAME** 的附件属性包含唯一值，这些值是邮件系统的有效附件标识符。</span><span class="sxs-lookup"><span data-stu-id="9015b-124">The transport provider ensures that the **PR_ATTACH_TRANSPORT_NAME** properties of all the attachments contain unique values that are valid attachment identifiers for the messaging system.</span></span> 
    
2. <span data-ttu-id="9015b-125">然后，传输提供程序将单个调用用于每个附件的 **ITnef：：AddProps，** 并传递TNEF_PROP_CONTAINED标记。</span><span class="sxs-lookup"><span data-stu-id="9015b-125">The transport provider then uses a single call to **ITnef::AddProps** for each attachment, passing in the TNEF_PROP_CONTAINED flag.</span></span> 
    

