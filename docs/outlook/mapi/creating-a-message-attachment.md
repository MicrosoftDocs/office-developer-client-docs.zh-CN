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
# <a name="creating-a-message-attachment"></a>创建邮件附件
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件附件是一些可以随邮件一起发送或保存的其他数据，如文件、其他邮件或 OLE 对象。 每个附件都有一组属性，用于标识附件并描述其类型及其呈现方式。 与收件人一样，只能通过收件人所属的邮件访问邮件附件。 因此，若要使附件可用，必须打开其邮件。
  
## <a name="create-a-message-attachment"></a>创建邮件附件
  
1. 调用邮件的 [IMessage：：CreateAttach](imessage-createattach.md) 方法，并传递 NULL 作为接口标识符。 **CreateAttach** 返回一个唯一标识邮件中新附件的编号。 附件编号存储在 PR_ATTACH_NUM ( [PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性中，并且仅在包含附件的邮件打开时有效。
    
2. 调用[IMAPIProp：：SetProps PR_ATTACH_METHOD (](imapiprop-setprops.md) [PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 以指示如何访问附件。  **PR_ATTACH_METHOD** 是必填项。 将它设置为： 
    
   - ATTACH_BY_VALUE附件是二进制数据，则显示 。
    
   - ATTACH_BY_REFERENCE、ATTACH_BY_REF_RESOLVE或ATTACH_BY_REF_ONLY附件是一个文件，
    
   - ATTACH_EMBEDDED_MSG附件是邮件，则显示 。
    
   - ATTACH_OLE附件是 OLE 对象时显示。
    
3. 设置适当的附件数据属性：
    
   - **PR_ATTACH_DATA_BIN (** 二) OLE 1 对象的 [PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md) 对象。
    
   - **PR_ATTACH_PATHNAME (** [PidTagAttachPathname)](pidtagattachpathname-canonical-property.md) 文件。
    
   - **PR_ATTACH_DATA_OBJ (** OLE 2 对象) [PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md) 对象。
    
4. 设置 **PR_ATTACH_RENDERING (** [PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 保留文件或二进制附件附件的图形表示形式。 不要为 OLE 对象（在内部存储呈现信息）或附加邮件设置它。 
    
5. 设置 **PR_RENDERING_POSITION (** [PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 以指示附件应显示在何处。 **PR_RENDERING_POSITION** 仅适用于设置 PR_BODY 属性 **的** 客户端。 如果 **仅支持** PR_RTF_COMPRESSED，将以下占位符信息放在压缩流中：
    
   `\objattph`

   若要设置 **PR_RENDERING_POSITION，** 请分配一个表示字符的序号偏移量，第一个字符为 0 的 **PR_BODY（** 如果需要知道附件在邮件中的呈现位置）或 **0xFFFFFFFF（** 如果不在 PR_BODY 中呈现附件）。
    
6. 设置 **PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 以指示文件附件文件的短名称，设置 **PR \_ ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) 以指示处理长文件名格式的平台上支持的文件名称。 这两个属性都是可选的。 但是， **如果设置** PR_ATTACH_LONG_FILENAME ，则还要设置 **PR_ATTACH_FILENAME**。 
    
7. 设置 **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) ，以指示可以在对话框中出现的附件的名称。 PR_DISPLAY_NAME可选。 
    
## <a name="set-pr_attach_data_bin"></a>设置PR_ATTACH_DATA_BIN
  
1. 调用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 以使用 **IStream** 接口打开属性。 
    
2. 如果文件包含数据并且文件已打开，或者如果您需要显式控制缓冲区大小，请循环调用 **IStream：：Write** 以将数据放置到流中。 
    
3. 另一个选项是调用 **OpenStreamOnFile** 以创建访问数据文件的流，然后调用此流的 **IStream：：CopyTo** 方法将数据复制到 **OpenProperty** 返回的流。
    
4. 调用新流的 **IStream：：Commit** 方法。 
    
## <a name="set-pr_attach_data_obj"></a>设置PR_ATTACH_DATA_OBJ
  
1. 调用 **IMAPIProp：：OpenProperty** 以使用 **IStreamDocfile** 接口打开 属性，以创建使用结构化存储的流。 **IStreamDocfile** 由邮件存储提供程序实现，为客户端提供存储和检索结构化存储的更高性能方法。 **IStreamDocfile** 接口与 **IStream** 相同，但流的内容保证格式化为结构化存储。 如果此调用成功，请创建流，步骤与 **设置PR_ATTACH_DATA_BIN** 相同。
    
2. 如果 **OpenProperty** 失败： 
    
   1. 再次 **调用 OpenProperty** 以请求 **IStorage**。 
      
   2. 调用 **StgOpenStorage** 以打开 OLE 对象并返回存储对象。 
      
   3. 调用返回的存储对象的 **IStorage：：CopyTo** 方法以复制到从 **OpenProperty 返回的存储对象**。
      
   4. 调用新存储对象的 **IStorage：：Commit** 方法。 
    
## <a name="set-pr_attach_pathname"></a>设置PR_ATTACH_PATHNAME
  
1. 分配 [SPropValue](spropvalue.md)结构，将 **ulPropTag** 成员设置为 PR_ATTACH_PATHNAME **Value.LPSZ** 成员设置为表示文件名的字符串。 
    
2. 调用附件的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法。 
    
> [!NOTE]
> 如果你的平台支持长文件名， **请同时设置** PR_ATTACH_PATHNAME 和 **PR_ATTACH_LONG_PATHNAME**。 可能需要执行操作系统调用来检索短文件名。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 附件](mapi-attachments.md)

