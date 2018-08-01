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
ms.openlocfilehash: eef42a8c7d19af313316bea68624ac67fb1ab4e8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774735"
---
# <a name="creating-a-message-attachment"></a>创建邮件附件
  
**适用于**： Outlook 
  
邮件附件是一些其他的数据，如文件、 另一条消息或 OLE 对象，您可以发送或保存以及一条消息。 每个附件具有属性的集合，它标识，并介绍了其类型和呈现方式。 收件人，如只能通过它们属于邮件访问邮件附件。 因此，可以使用的附件，其消息必须打开。
  
## <a name="create-a-message-attachment"></a>创建邮件附件
  
1. 调用消息的[IMessage::CreateAttach](imessage-createattach.md)方法并将 NULL 作为接口标识传递。 **CreateAttach**返回一个数字，用于唯一标识新附件在邮件中。 附件数存储在**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性中，并且仅，只要包含附件的邮件已打开有效。
    
2. 调用[IMAPIProp::SetProps](imapiprop-setprops.md)设置**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 以指示如何访问该附件。 **PR_ATTACH_METHOD**是必需的。 将其设置为： 
    
   - ATTACH_BY_VALUE 如果附件是二进制数据。
    
   - ATTACH_BY_REFERENCE、 ATTACH_BY_REF_RESOLVE 或 ATTACH_BY_REF_ONLY 如果附件是一个文件。
    
   - ATTACH_EMBEDDED_MSG 如果附件是一条消息。
    
   - ATTACH_OLE 如果附件是 OLE 对象。
    
3. 将相应的附件数据属性的设置：
    
   - **PR_ATTACH_DATA_BIN**([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 二进制数据和 OLE 1 对象。
    
   - **PR_ATTACH_PATHNAME**([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 的文件。
    
   - **PR_ATTACH_DATA_OBJ**([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 消息和 OLE 2 对象。
    
4. 设置**PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 来保存的文件附件或二进制附件的图形表示形式。 未设置它的 OLE 对象，内部存储呈现信息，或附加的邮件。 
    
5. 设置**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 以指示附件的显示位置。 **PR_RENDERING_POSITION**仅适用于将**PR_BODY**属性设置的客户端。 如果您仅支持**PR_RTF_COMPRESSED**，压缩用于将 stream 中放置占位符中的以下信息：
    
   `\objattph`

   若要设置**PR_RENDERING_POSITION**，分配的任一数字值，该值代表序号偏移量以字符为单位，与**PR_BODY**正在 0，如果您需要知道呈现附件，邮件中的第一个字符或 0xFFFFFFFF，如果您不呈现**PR_BODY**中的附件。
    
6. 设置**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 以指示的文件附件的文件的短名称和**PR\_ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) 以指示所支持的文件的名称在平台上的处理长文件名格式。 这两个属性是可选的。 但是，如果您设置**PR_ATTACH_LONG_FILENAME**，还要设置**PR_ATTACH_FILENAME**。 
    
7. 设置**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 以指示可以显示在对话框中的附件的名称。 PR_DISPLAY_NAME 是可选的。 
    
## <a name="set-prattachdatabin"></a>设置 PR_ATTACH_DATA_BIN
  
1. 调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)使用**IStream**接口打开属性。 
    
2. 如果文件包含的数据和处于打开状态或者您需要显式控制缓冲区大小，请调用**IStream::Write**循环将数据放入流。 
    
3. 另一种选择是调用**OpenStreamOnFile**创建一个流以访问数据文件，然后调用该流的**IStream::CopyTo**方法将数据复制到**OpenProperty**返回的流。
    
4. 调用新的流**IStream::Commit**方法。 
    
## <a name="set-prattachdataobj"></a>设置 PR_ATTACH_DATA_OBJ
  
1. 调用**IMAPIProp::OpenProperty** **IStreamDocfile**界面，以创建与结构化存储工作流使用打开属性。 **IStreamDocfile**由消息存储提供程序，使客户端可以存储和检索结构化的存储性能更高的方式实现。 **IStreamDocfile**接口是**IStream**，相同，但保证 stream 的内容将转换为结构化存储文件格式。 如果此调用成功，请使用用于设置**PR_ATTACH_DATA_BIN**相同的步骤创建流。
    
2. 如果**OpenProperty**失败： 
    
   1. 调用**OpenProperty**再次询问**IStorage**。 
      
   2. 调用**StgOpenStorage**打开 OLE 对象并返回存储对象。 
      
   3. 调用返回的存储对象的**IStorage::CopyTo**方法以将复制到**OpenProperty**从返回的存储对象。
      
   4. 调用新的存储对象**IStorage::Commit**方法。 
    
## <a name="set-prattachpathname"></a>设置 PR_ATTACH_PATHNAME
  
1. 分配到**PR_ATTACH_PATHNAME**和**Value.LPSZ**成员为字符的字符串值，该值代表文件名设置**ulPropTag**成员[SPropValue](spropvalue.md)结构。 
    
2. 调用附件的[IMAPIProp::SetProps](imapiprop-setprops.md)方法。 
    
> [!NOTE]
> 如果您的平台支持长文件名，则**PR_ATTACH_PATHNAME**和**PR_ATTACH_LONG_PATHNAME**的设置。 可能需要进行呼叫，以检索短文件名操作系统。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 附件](mapi-attachments.md)

