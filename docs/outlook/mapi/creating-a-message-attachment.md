---
title: 创建邮件附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 711b6765-7763-41ae-9ff8-61ca6ddd459d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2bdba3574c962c825f45cd098efa1cba6e21a4ea
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405994"
---
# <a name="creating-a-message-attachment"></a><span data-ttu-id="3f234-103">创建邮件附件</span><span class="sxs-lookup"><span data-stu-id="3f234-103">Creating a message attachment</span></span>
  
<span data-ttu-id="3f234-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3f234-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3f234-105">邮件附件是一些可以随邮件一起发送或保存的其他数据，如文件、其他邮件或 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="3f234-105">A message attachment is some additional data, such as a file, another message, or an OLE object, that you can send or save along with a message.</span></span> <span data-ttu-id="3f234-106">每个附件都有一组属性，用于标识附件并描述其类型及其呈现方式。</span><span class="sxs-lookup"><span data-stu-id="3f234-106">Each attachment has a collection of properties that identifies it and describes its type and how it is rendered.</span></span> <span data-ttu-id="3f234-107">与收件人一样，只能通过收件人所属的邮件访问邮件附件。</span><span class="sxs-lookup"><span data-stu-id="3f234-107">Like recipients, message attachments can only be accessed through the message to which they belong.</span></span> <span data-ttu-id="3f234-108">因此，若要使附件可用，必须打开其邮件。</span><span class="sxs-lookup"><span data-stu-id="3f234-108">Therefore, for an attachment to be usable, its message must be open.</span></span>
  
## <a name="create-a-message-attachment"></a><span data-ttu-id="3f234-109">创建邮件附件</span><span class="sxs-lookup"><span data-stu-id="3f234-109">Create a message attachment</span></span>
  
1. <span data-ttu-id="3f234-110">调用邮件的 [IMessage：：CreateAttach](imessage-createattach.md) 方法，并传递 NULL 作为接口标识符。</span><span class="sxs-lookup"><span data-stu-id="3f234-110">Call the message's [IMessage::CreateAttach](imessage-createattach.md) method and pass NULL as the interface identifier.</span></span> <span data-ttu-id="3f234-111">**CreateAttach** 返回一个唯一标识邮件中新附件的编号。</span><span class="sxs-lookup"><span data-stu-id="3f234-111">**CreateAttach** returns a number that uniquely identifies the new attachment within the message.</span></span> <span data-ttu-id="3f234-112">附件编号存储在 PR_ATTACH_NUM ( [PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性中，并且仅在包含附件的邮件打开时有效。</span><span class="sxs-lookup"><span data-stu-id="3f234-112">The attachment number is stored in the **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property and is valid only as long as the message containing the attachment is open.</span></span>
    
2. <span data-ttu-id="3f234-113">调用[IMAPIProp：：SetProps PR_ATTACH_METHOD (](imapiprop-setprops.md) [PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 以指示如何访问附件。 </span><span class="sxs-lookup"><span data-stu-id="3f234-113">Call [IMAPIProp::SetProps](imapiprop-setprops.md) to set **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) to indicate how to access the attachment.</span></span> <span data-ttu-id="3f234-114">**PR_ATTACH_METHOD** 是必填项。</span><span class="sxs-lookup"><span data-stu-id="3f234-114">**PR_ATTACH_METHOD** is required.</span></span> <span data-ttu-id="3f234-115">将它设置为：</span><span class="sxs-lookup"><span data-stu-id="3f234-115">Set it to:</span></span> 
    
   - <span data-ttu-id="3f234-116">ATTACH_BY_VALUE附件是二进制数据，则显示 。</span><span class="sxs-lookup"><span data-stu-id="3f234-116">ATTACH_BY_VALUE if the attachment is binary data.</span></span>
    
   - <span data-ttu-id="3f234-117">ATTACH_BY_REFERENCE、ATTACH_BY_REF_RESOLVE或ATTACH_BY_REF_ONLY附件是一个文件，</span><span class="sxs-lookup"><span data-stu-id="3f234-117">ATTACH_BY_REFERENCE, ATTACH_BY_REF_RESOLVE, or ATTACH_BY_REF_ONLY if the attachment is a file.</span></span>
    
   - <span data-ttu-id="3f234-118">ATTACH_EMBEDDED_MSG附件是邮件，则显示 。</span><span class="sxs-lookup"><span data-stu-id="3f234-118">ATTACH_EMBEDDED_MSG if the attachment is a message.</span></span>
    
   - <span data-ttu-id="3f234-119">ATTACH_OLE附件是 OLE 对象时显示。</span><span class="sxs-lookup"><span data-stu-id="3f234-119">ATTACH_OLE if the attachment is an OLE object.</span></span>
    
3. <span data-ttu-id="3f234-120">设置适当的附件数据属性：</span><span class="sxs-lookup"><span data-stu-id="3f234-120">Set the appropriate attachment data property:</span></span>
    
   - <span data-ttu-id="3f234-121">**PR_ATTACH_DATA_BIN (** 二) OLE 1 对象的 [PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="3f234-121">**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) for binary data and OLE 1 objects.</span></span>
    
   - <span data-ttu-id="3f234-122">**PR_ATTACH_PATHNAME (** [PidTagAttachPathname)](pidtagattachpathname-canonical-property.md) 文件。</span><span class="sxs-lookup"><span data-stu-id="3f234-122">**PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) for files.</span></span>
    
   - <span data-ttu-id="3f234-123">**PR_ATTACH_DATA_OBJ (** OLE 2 对象) [PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="3f234-123">**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) for messages and OLE 2 objects.</span></span>
    
4. <span data-ttu-id="3f234-124">设置 **PR_ATTACH_RENDERING (** [PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 保留文件或二进制附件附件的图形表示形式。</span><span class="sxs-lookup"><span data-stu-id="3f234-124">Set **PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) to hold the graphic representation of the attachment for file or binary attachments.</span></span> <span data-ttu-id="3f234-125">不要为 OLE 对象（在内部存储呈现信息）或附加邮件设置它。</span><span class="sxs-lookup"><span data-stu-id="3f234-125">Do not set it for OLE objects, which store the rendering information internally, or for attached messages.</span></span> 
    
5. <span data-ttu-id="3f234-126">设置 **PR_RENDERING_POSITION (** [PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 以指示附件应显示在何处。</span><span class="sxs-lookup"><span data-stu-id="3f234-126">Set **PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) to indicate where the attachment should be displayed.</span></span> <span data-ttu-id="3f234-127">**PR_RENDERING_POSITION** 仅适用于设置 PR_BODY 属性 **的** 客户端。</span><span class="sxs-lookup"><span data-stu-id="3f234-127">**PR_RENDERING_POSITION** applies only to clients that set the **PR_BODY** property.</span></span> <span data-ttu-id="3f234-128">如果 **仅支持** PR_RTF_COMPRESSED，将以下占位符信息放在压缩流中：</span><span class="sxs-lookup"><span data-stu-id="3f234-128">If you only support **PR_RTF_COMPRESSED**, place the following placeholder information in the compressed stream:</span></span>
    
   `\objattph`

   <span data-ttu-id="3f234-129">若要设置 **PR_RENDERING_POSITION，** 请分配一个表示字符的序号偏移量，第一个字符为 0 的 **PR_BODY（** 如果需要知道附件在邮件中的呈现位置）或 **0xFFFFFFFF（** 如果不在 PR_BODY 中呈现附件）。</span><span class="sxs-lookup"><span data-stu-id="3f234-129">To set **PR_RENDERING_POSITION**, assign either a number that represents an ordinal offset in characters, with the first character of **PR_BODY** being 0, if you need to know where in the message the attachment is rendered, or 0xFFFFFFFF, if you do not render attachments within **PR_BODY**.</span></span>
    
6. <span data-ttu-id="3f234-130">设置 **PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 以指示文件附件文件的短名称，设置 **PR \_ ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) 以指示处理长文件名格式的平台上支持的文件名称。</span><span class="sxs-lookup"><span data-stu-id="3f234-130">Set **PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) to indicate the short name of the file for a file attachment and **PR\_ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) to indicate the name of the file as supported on a platform that handles the long filename format.</span></span> <span data-ttu-id="3f234-131">这两个属性都是可选的。</span><span class="sxs-lookup"><span data-stu-id="3f234-131">Both properties are optional.</span></span> <span data-ttu-id="3f234-132">但是， **如果设置** PR_ATTACH_LONG_FILENAME ，则还要设置 **PR_ATTACH_FILENAME**。</span><span class="sxs-lookup"><span data-stu-id="3f234-132">However, if you set **PR_ATTACH_LONG_FILENAME**, also set **PR_ATTACH_FILENAME**.</span></span> 
    
7. <span data-ttu-id="3f234-133">设置 **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) ，以指示可以在对话框中出现的附件的名称。</span><span class="sxs-lookup"><span data-stu-id="3f234-133">Set **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) to indicate the name for the attachment that can appear in a dialog box.</span></span> <span data-ttu-id="3f234-134">PR_DISPLAY_NAME可选。</span><span class="sxs-lookup"><span data-stu-id="3f234-134">PR_DISPLAY_NAME is optional.</span></span> 
    
## <a name="set-pr_attach_data_bin"></a><span data-ttu-id="3f234-135">设置PR_ATTACH_DATA_BIN</span><span class="sxs-lookup"><span data-stu-id="3f234-135">Set PR_ATTACH_DATA_BIN</span></span>
  
1. <span data-ttu-id="3f234-136">调用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 以使用 **IStream** 接口打开属性。</span><span class="sxs-lookup"><span data-stu-id="3f234-136">Call [IMAPIProp::OpenProperty](imapiprop-openproperty.md) to open the property with the **IStream** interface.</span></span> 
    
2. <span data-ttu-id="3f234-137">如果文件包含数据并且文件已打开，或者如果您需要显式控制缓冲区大小，请循环调用 **IStream：：Write** 以将数据放置到流中。</span><span class="sxs-lookup"><span data-stu-id="3f234-137">If a file contains the data and it is open or if you need explicit control over buffer size, call **IStream::Write** in a loop to place the data in the stream.</span></span> 
    
3. <span data-ttu-id="3f234-138">另一个选项是调用 **OpenStreamOnFile** 以创建访问数据文件的流，然后调用此流的 **IStream：：CopyTo** 方法将数据复制到 **OpenProperty** 返回的流。</span><span class="sxs-lookup"><span data-stu-id="3f234-138">Another option is to call **OpenStreamOnFile** to create a stream to access the data file and then call this stream's **IStream::CopyTo** method to copy the data to the stream returned by **OpenProperty**.</span></span>
    
4. <span data-ttu-id="3f234-139">调用新流的 **IStream：：Commit** 方法。</span><span class="sxs-lookup"><span data-stu-id="3f234-139">Call the new stream's **IStream::Commit** method.</span></span> 
    
## <a name="set-pr_attach_data_obj"></a><span data-ttu-id="3f234-140">设置PR_ATTACH_DATA_OBJ</span><span class="sxs-lookup"><span data-stu-id="3f234-140">Set PR_ATTACH_DATA_OBJ</span></span>
  
1. <span data-ttu-id="3f234-141">调用 **IMAPIProp：：OpenProperty** 以使用 **IStreamDocfile** 接口打开 属性，以创建使用结构化存储的流。</span><span class="sxs-lookup"><span data-stu-id="3f234-141">Call **IMAPIProp::OpenProperty** to open the property with the **IStreamDocfile** interface to create a stream that works with structured storage.</span></span> <span data-ttu-id="3f234-142">**IStreamDocfile** 由邮件存储提供程序实现，为客户端提供存储和检索结构化存储的更高性能方法。</span><span class="sxs-lookup"><span data-stu-id="3f234-142">**IStreamDocfile** is implemented by message store providers to give clients a higher-performance way to store and retrieve structured storage.</span></span> <span data-ttu-id="3f234-143">**IStreamDocfile** 接口与 **IStream** 相同，但流的内容保证格式化为结构化存储。</span><span class="sxs-lookup"><span data-stu-id="3f234-143">The **IStreamDocfile** interface is the same as **IStream**, but the content of the stream is guaranteed to be formatted as structured storage.</span></span> <span data-ttu-id="3f234-144">如果此调用成功，请创建流，步骤与 **设置PR_ATTACH_DATA_BIN** 相同。</span><span class="sxs-lookup"><span data-stu-id="3f234-144">If this call succeeds, create the stream with the same steps outlined for setting **PR_ATTACH_DATA_BIN**.</span></span>
    
2. <span data-ttu-id="3f234-145">如果 **OpenProperty** 失败：</span><span class="sxs-lookup"><span data-stu-id="3f234-145">If **OpenProperty** fails:</span></span> 
    
   1. <span data-ttu-id="3f234-146">再次 **调用 OpenProperty** 以请求 **IStorage**。</span><span class="sxs-lookup"><span data-stu-id="3f234-146">Call **OpenProperty** again asking for **IStorage**.</span></span> 
      
   2. <span data-ttu-id="3f234-147">调用 **StgOpenStorage** 以打开 OLE 对象并返回存储对象。</span><span class="sxs-lookup"><span data-stu-id="3f234-147">Call **StgOpenStorage** to open the OLE object and return a storage object.</span></span> 
      
   3. <span data-ttu-id="3f234-148">调用返回的存储对象的 **IStorage：：CopyTo** 方法以复制到从 **OpenProperty 返回的存储对象**。</span><span class="sxs-lookup"><span data-stu-id="3f234-148">Call the returned storage object's **IStorage::CopyTo** method to copy to the storage object returned from **OpenProperty**.</span></span>
      
   4. <span data-ttu-id="3f234-149">调用新存储对象的 **IStorage：：Commit** 方法。</span><span class="sxs-lookup"><span data-stu-id="3f234-149">Call the new storage object's **IStorage::Commit** method.</span></span> 
    
## <a name="set-pr_attach_pathname"></a><span data-ttu-id="3f234-150">设置PR_ATTACH_PATHNAME</span><span class="sxs-lookup"><span data-stu-id="3f234-150">Set PR_ATTACH_PATHNAME</span></span>
  
1. <span data-ttu-id="3f234-151">分配 [SPropValue](spropvalue.md)结构，将 **ulPropTag** 成员设置为 PR_ATTACH_PATHNAME **Value.LPSZ** 成员设置为表示文件名的字符串。</span><span class="sxs-lookup"><span data-stu-id="3f234-151">Allocate an [SPropValue](spropvalue.md) structure, setting the **ulPropTag** member to **PR_ATTACH_PATHNAME** and the **Value.LPSZ** member to the character string that represents the filename.</span></span> 
    
2. <span data-ttu-id="3f234-152">调用附件的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="3f234-152">Call the attachment's [IMAPIProp::SetProps](imapiprop-setprops.md) method.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="3f234-153">如果你的平台支持长文件名， **请同时设置** PR_ATTACH_PATHNAME 和 **PR_ATTACH_LONG_PATHNAME**。</span><span class="sxs-lookup"><span data-stu-id="3f234-153">If your platform supports long filenames, set both **PR_ATTACH_PATHNAME** and **PR_ATTACH_LONG_PATHNAME**.</span></span> <span data-ttu-id="3f234-154">可能需要执行操作系统调用来检索短文件名。</span><span class="sxs-lookup"><span data-stu-id="3f234-154">It might be necessary to make an operating system call to retrieve the short filename.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3f234-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f234-155">See also</span></span>

- [<span data-ttu-id="3f234-156">MAPI 附件</span><span class="sxs-lookup"><span data-stu-id="3f234-156">MAPI Attachments</span></span>](mapi-attachments.md)

