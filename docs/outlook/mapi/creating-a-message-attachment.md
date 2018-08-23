---
title: 创建邮件附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 711b6765-7763-41ae-9ff8-61ca6ddd459d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 34d8dbeaf101d5ebb687403a2200bd0ad73b9998
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577098"
---
# <a name="creating-a-message-attachment"></a><span data-ttu-id="8b06a-103">创建邮件附件</span><span class="sxs-lookup"><span data-stu-id="8b06a-103">Creating a message attachment</span></span>
  
<span data-ttu-id="8b06a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8b06a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8b06a-105">邮件附件是一些其他的数据，如文件、 另一条消息或 OLE 对象，您可以发送或保存以及一条消息。</span><span class="sxs-lookup"><span data-stu-id="8b06a-105">A message attachment is some additional data, such as a file, another message, or an OLE object, that you can send or save along with a message.</span></span> <span data-ttu-id="8b06a-106">每个附件具有属性的集合，它标识，并介绍了其类型和呈现方式。</span><span class="sxs-lookup"><span data-stu-id="8b06a-106">Each attachment has a collection of properties that identifies it and describes its type and how it is rendered.</span></span> <span data-ttu-id="8b06a-107">收件人，如只能通过它们属于邮件访问邮件附件。</span><span class="sxs-lookup"><span data-stu-id="8b06a-107">Like recipients, message attachments can only be accessed through the message to which they belong.</span></span> <span data-ttu-id="8b06a-108">因此，可以使用的附件，其消息必须打开。</span><span class="sxs-lookup"><span data-stu-id="8b06a-108">Therefore, for an attachment to be usable, its message must be open.</span></span>
  
## <a name="create-a-message-attachment"></a><span data-ttu-id="8b06a-109">创建邮件附件</span><span class="sxs-lookup"><span data-stu-id="8b06a-109">Create a message attachment</span></span>
  
1. <span data-ttu-id="8b06a-110">调用消息的[IMessage::CreateAttach](imessage-createattach.md)方法并将 NULL 作为接口标识传递。</span><span class="sxs-lookup"><span data-stu-id="8b06a-110">Call the message's [IMessage::CreateAttach](imessage-createattach.md) method and pass NULL as the interface identifier.</span></span> <span data-ttu-id="8b06a-111">**CreateAttach**返回一个数字，用于唯一标识新附件在邮件中。</span><span class="sxs-lookup"><span data-stu-id="8b06a-111">**CreateAttach** returns a number that uniquely identifies the new attachment within the message.</span></span> <span data-ttu-id="8b06a-112">附件数存储在**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性中，并且仅，只要包含附件的邮件已打开有效。</span><span class="sxs-lookup"><span data-stu-id="8b06a-112">The attachment number is stored in the **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property and is valid only as long as the message containing the attachment is open.</span></span>
    
2. <span data-ttu-id="8b06a-113">调用[IMAPIProp::SetProps](imapiprop-setprops.md)设置**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 以指示如何访问该附件。</span><span class="sxs-lookup"><span data-stu-id="8b06a-113">Call [IMAPIProp::SetProps](imapiprop-setprops.md) to set **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) to indicate how to access the attachment.</span></span> <span data-ttu-id="8b06a-114">**PR_ATTACH_METHOD**是必需的。</span><span class="sxs-lookup"><span data-stu-id="8b06a-114">**PR_ATTACH_METHOD** is required.</span></span> <span data-ttu-id="8b06a-115">将其设置为：</span><span class="sxs-lookup"><span data-stu-id="8b06a-115">Set it to:</span></span> 
    
   - <span data-ttu-id="8b06a-116">ATTACH_BY_VALUE 如果附件是二进制数据。</span><span class="sxs-lookup"><span data-stu-id="8b06a-116">ATTACH_BY_VALUE if the attachment is binary data.</span></span>
    
   - <span data-ttu-id="8b06a-117">ATTACH_BY_REFERENCE、 ATTACH_BY_REF_RESOLVE 或 ATTACH_BY_REF_ONLY 如果附件是一个文件。</span><span class="sxs-lookup"><span data-stu-id="8b06a-117">ATTACH_BY_REFERENCE, ATTACH_BY_REF_RESOLVE, or ATTACH_BY_REF_ONLY if the attachment is a file.</span></span>
    
   - <span data-ttu-id="8b06a-118">ATTACH_EMBEDDED_MSG 如果附件是一条消息。</span><span class="sxs-lookup"><span data-stu-id="8b06a-118">ATTACH_EMBEDDED_MSG if the attachment is a message.</span></span>
    
   - <span data-ttu-id="8b06a-119">ATTACH_OLE 如果附件是 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="8b06a-119">ATTACH_OLE if the attachment is an OLE object.</span></span>
    
3. <span data-ttu-id="8b06a-120">将相应的附件数据属性的设置：</span><span class="sxs-lookup"><span data-stu-id="8b06a-120">Set the appropriate attachment data property:</span></span>
    
   - <span data-ttu-id="8b06a-121">**PR_ATTACH_DATA_BIN**([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 二进制数据和 OLE 1 对象。</span><span class="sxs-lookup"><span data-stu-id="8b06a-121">**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) for binary data and OLE 1 objects.</span></span>
    
   - <span data-ttu-id="8b06a-122">**PR_ATTACH_PATHNAME**([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 的文件。</span><span class="sxs-lookup"><span data-stu-id="8b06a-122">**PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) for files.</span></span>
    
   - <span data-ttu-id="8b06a-123">**PR_ATTACH_DATA_OBJ**([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 消息和 OLE 2 对象。</span><span class="sxs-lookup"><span data-stu-id="8b06a-123">**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) for messages and OLE 2 objects.</span></span>
    
4. <span data-ttu-id="8b06a-124">设置**PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 来保存的文件附件或二进制附件的图形表示形式。</span><span class="sxs-lookup"><span data-stu-id="8b06a-124">Set **PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) to hold the graphic representation of the attachment for file or binary attachments.</span></span> <span data-ttu-id="8b06a-125">未设置它的 OLE 对象，内部存储呈现信息，或附加的邮件。</span><span class="sxs-lookup"><span data-stu-id="8b06a-125">Do not set it for OLE objects, which store the rendering information internally, or for attached messages.</span></span> 
    
5. <span data-ttu-id="8b06a-126">设置**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 以指示附件的显示位置。</span><span class="sxs-lookup"><span data-stu-id="8b06a-126">Set **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) to indicate where the attachment should be displayed.</span></span> <span data-ttu-id="8b06a-127">**PR_RENDERING_POSITION**仅适用于将**PR_BODY**属性设置的客户端。</span><span class="sxs-lookup"><span data-stu-id="8b06a-127">**PR_RENDERING_POSITION** applies only to clients that set the **PR_BODY** property.</span></span> <span data-ttu-id="8b06a-128">如果您仅支持**PR_RTF_COMPRESSED**，压缩用于将 stream 中放置占位符中的以下信息：</span><span class="sxs-lookup"><span data-stu-id="8b06a-128">If you only support **PR_RTF_COMPRESSED**, place the following placeholder information in the compressed stream:</span></span>
    
   `\objattph`

   <span data-ttu-id="8b06a-129">若要设置**PR_RENDERING_POSITION**，分配的任一数字值，该值代表序号偏移量以字符为单位，与**PR_BODY**正在 0，如果您需要知道呈现附件，邮件中的第一个字符或 0xFFFFFFFF，如果您不呈现**PR_BODY**中的附件。</span><span class="sxs-lookup"><span data-stu-id="8b06a-129">To set **PR_RENDERING_POSITION**, assign either a number that represents an ordinal offset in characters, with the first character of **PR_BODY** being 0, if you need to know where in the message the attachment is rendered, or 0xFFFFFFFF, if you do not render attachments within **PR_BODY**.</span></span>
    
6. <span data-ttu-id="8b06a-130">设置**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 以指示的文件附件的文件的短名称和**PR\_ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) 以指示所支持的文件的名称在平台上的处理长文件名格式。</span><span class="sxs-lookup"><span data-stu-id="8b06a-130">Set **PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) to indicate the short name of the file for a file attachment and **PR\_ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) to indicate the name of the file as supported on a platform that handles the long filename format.</span></span> <span data-ttu-id="8b06a-131">这两个属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="8b06a-131">Both properties are optional.</span></span> <span data-ttu-id="8b06a-132">但是，如果您设置**PR_ATTACH_LONG_FILENAME**，还要设置**PR_ATTACH_FILENAME**。</span><span class="sxs-lookup"><span data-stu-id="8b06a-132">However, if you set **PR_ATTACH_LONG_FILENAME**, also set **PR_ATTACH_FILENAME**.</span></span> 
    
7. <span data-ttu-id="8b06a-133">设置**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 以指示可以显示在对话框中的附件的名称。</span><span class="sxs-lookup"><span data-stu-id="8b06a-133">Set **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) to indicate the name for the attachment that can appear in a dialog box.</span></span> <span data-ttu-id="8b06a-134">PR_DISPLAY_NAME 是可选的。</span><span class="sxs-lookup"><span data-stu-id="8b06a-134">PR_DISPLAY_NAME is optional.</span></span> 
    
## <a name="set-prattachdatabin"></a><span data-ttu-id="8b06a-135">设置 PR_ATTACH_DATA_BIN</span><span class="sxs-lookup"><span data-stu-id="8b06a-135">Set PR_ATTACH_DATA_BIN</span></span>
  
1. <span data-ttu-id="8b06a-136">调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)使用**IStream**接口打开属性。</span><span class="sxs-lookup"><span data-stu-id="8b06a-136">Call [IMAPIProp::OpenProperty](imapiprop-openproperty.md) to open the property with the **IStream** interface.</span></span> 
    
2. <span data-ttu-id="8b06a-137">如果文件包含的数据和处于打开状态或者您需要显式控制缓冲区大小，请调用**IStream::Write**循环将数据放入流。</span><span class="sxs-lookup"><span data-stu-id="8b06a-137">If a file contains the data and it is open or if you need explicit control over buffer size, call **IStream::Write** in a loop to place the data in the stream.</span></span> 
    
3. <span data-ttu-id="8b06a-138">另一种选择是调用**OpenStreamOnFile**创建一个流以访问数据文件，然后调用该流的**IStream::CopyTo**方法将数据复制到**OpenProperty**返回的流。</span><span class="sxs-lookup"><span data-stu-id="8b06a-138">Another option is to call **OpenStreamOnFile** to create a stream to access the data file and then call this stream's **IStream::CopyTo** method to copy the data to the stream returned by **OpenProperty**.</span></span>
    
4. <span data-ttu-id="8b06a-139">调用新的流**IStream::Commit**方法。</span><span class="sxs-lookup"><span data-stu-id="8b06a-139">Call the new stream's **IStream::Commit** method.</span></span> 
    
## <a name="set-prattachdataobj"></a><span data-ttu-id="8b06a-140">设置 PR_ATTACH_DATA_OBJ</span><span class="sxs-lookup"><span data-stu-id="8b06a-140">Set PR_ATTACH_DATA_OBJ</span></span>
  
1. <span data-ttu-id="8b06a-141">调用**IMAPIProp::OpenProperty** **IStreamDocfile**界面，以创建与结构化存储工作流使用打开属性。</span><span class="sxs-lookup"><span data-stu-id="8b06a-141">Call **IMAPIProp::OpenProperty** to open the property with the **IStreamDocfile** interface to create a stream that works with structured storage.</span></span> <span data-ttu-id="8b06a-142">**IStreamDocfile**由消息存储提供程序，使客户端可以存储和检索结构化的存储性能更高的方式实现。</span><span class="sxs-lookup"><span data-stu-id="8b06a-142">**IStreamDocfile** is implemented by message store providers to give clients a higher-performance way to store and retrieve structured storage.</span></span> <span data-ttu-id="8b06a-143">**IStreamDocfile**接口是**IStream**，相同，但保证 stream 的内容将转换为结构化存储文件格式。</span><span class="sxs-lookup"><span data-stu-id="8b06a-143">The **IStreamDocfile** interface is the same as **IStream**, but the content of the stream is guaranteed to be formatted as structured storage.</span></span> <span data-ttu-id="8b06a-144">如果此调用成功，请使用用于设置**PR_ATTACH_DATA_BIN**相同的步骤创建流。</span><span class="sxs-lookup"><span data-stu-id="8b06a-144">If this call succeeds, create the stream with the same steps outlined for setting **PR_ATTACH_DATA_BIN**.</span></span>
    
2. <span data-ttu-id="8b06a-145">如果**OpenProperty**失败：</span><span class="sxs-lookup"><span data-stu-id="8b06a-145">If **OpenProperty** fails:</span></span> 
    
   1. <span data-ttu-id="8b06a-146">调用**OpenProperty**再次询问**IStorage**。</span><span class="sxs-lookup"><span data-stu-id="8b06a-146">Call **OpenProperty** again asking for **IStorage**.</span></span> 
      
   2. <span data-ttu-id="8b06a-147">调用**StgOpenStorage**打开 OLE 对象并返回存储对象。</span><span class="sxs-lookup"><span data-stu-id="8b06a-147">Call **StgOpenStorage** to open the OLE object and return a storage object.</span></span> 
      
   3. <span data-ttu-id="8b06a-148">调用返回的存储对象的**IStorage::CopyTo**方法以将复制到**OpenProperty**从返回的存储对象。</span><span class="sxs-lookup"><span data-stu-id="8b06a-148">Call the returned storage object's **IStorage::CopyTo** method to copy to the storage object returned from **OpenProperty**.</span></span>
      
   4. <span data-ttu-id="8b06a-149">调用新的存储对象**IStorage::Commit**方法。</span><span class="sxs-lookup"><span data-stu-id="8b06a-149">Call the new storage object's **IStorage::Commit** method.</span></span> 
    
## <a name="set-prattachpathname"></a><span data-ttu-id="8b06a-150">设置 PR_ATTACH_PATHNAME</span><span class="sxs-lookup"><span data-stu-id="8b06a-150">Set PR_ATTACH_PATHNAME</span></span>
  
1. <span data-ttu-id="8b06a-151">分配到**PR_ATTACH_PATHNAME**和**Value.LPSZ**成员为字符的字符串值，该值代表文件名设置**ulPropTag**成员[SPropValue](spropvalue.md)结构。</span><span class="sxs-lookup"><span data-stu-id="8b06a-151">Allocate an [SPropValue](spropvalue.md) structure, setting the **ulPropTag** member to **PR_ATTACH_PATHNAME** and the **Value.LPSZ** member to the character string that represents the filename.</span></span> 
    
2. <span data-ttu-id="8b06a-152">调用附件的[IMAPIProp::SetProps](imapiprop-setprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8b06a-152">Call the attachment's [IMAPIProp::SetProps](imapiprop-setprops.md) method.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8b06a-153">如果您的平台支持长文件名，则**PR_ATTACH_PATHNAME**和**PR_ATTACH_LONG_PATHNAME**的设置。</span><span class="sxs-lookup"><span data-stu-id="8b06a-153">If your platform supports long filenames, set both **PR_ATTACH_PATHNAME** and **PR_ATTACH_LONG_PATHNAME**.</span></span> <span data-ttu-id="8b06a-154">可能需要进行呼叫，以检索短文件名操作系统。</span><span class="sxs-lookup"><span data-stu-id="8b06a-154">It might be necessary to make an operating system call to retrieve the short filename.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8b06a-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b06a-155">See also</span></span>

- [<span data-ttu-id="8b06a-156">MAPI 附件</span><span class="sxs-lookup"><span data-stu-id="8b06a-156">MAPI Attachments</span></span>](mapi-attachments.md)

