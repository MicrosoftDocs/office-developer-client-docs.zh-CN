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
  
邮件附件是一些附加的数据, 如文件、另一封邮件或 OLE 对象, 可以随邮件一起发送或保存。 每个附件都有一个用于标识它的属性集合, 并描述其类型以及它的呈现方式。 与收件人一样, 邮件附件只可通过其所属的邮件进行访问。 因此, 要使附件可用, 必须打开其邮件。
  
## <a name="create-a-message-attachment"></a>创建邮件附件
  
1. 调用邮件的[IMessage:: CreateAttach](imessage-createattach.md)方法, 并传递 NULL 作为接口标识符。 **CreateAttach**返回一个数字, 用于唯一标识邮件中的新附件。 附件编号存储在**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性中, 并且只有在包含附件的邮件处于打开状态时才有效。
    
2. 调用[IMAPIProp:: SetProps](imapiprop-setprops.md)设置**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 以指示如何访问附件。 **PR_ATTACH_METHOD**是必需的。 将其设置为: 
    
   - ATTACH_BY_VALUE 如果附件是二进制数据, 则为。
    
   - ATTACH_BY_REFERENCE、ATTACH_BY_REF_RESOLVE 或 ATTACH_BY_REF_ONLY (如果附件是文件)。
    
   - ATTACH_EMBEDDED_MSG 如果附件是一封邮件。
    
   - ATTACH_OLE 如果附件是 OLE 对象, 则为。
    
3. 设置适当的附件数据属性:
    
   - **PR_ATTACH_DATA_BIN**([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)), 用于二进制数据和 OLE 1 对象。
    
   - **PR_ATTACH_PATHNAME**([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 的文件。
    
   - **PR_ATTACH_DATA_OBJ**([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 用于邮件和 OLE 2 对象。
    
4. 设置**PR_ATTACH_RENDERING** ([PidTagAttachRendering](pidtagattachrendering-canonical-property.md)) 以保存文件或二进制附件的附件的图形表示形式。 请勿将其设置为 OLE 对象, 用于在内部存储呈现信息或附加的邮件。 
    
5. 设置**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md)) 以指示附件应显示的位置。 **PR_RENDERING_POSITION**仅适用于设置**PR_BODY**属性的客户端。 如果只支持**PR_RTF_COMPRESSED**, 请在压缩的流中放置以下占位符信息:
    
   `\objattph`

   若要设置**PR_RENDERING_POSITION**, 请将代表序号偏移量的数字指定为字符, 第一个**PR_BODY**的第一个字符为 0, 如果您需要了解邮件中呈现附件的位置, 则为 0xffffffff; 如果您不在**PR_BODY**中呈现附件。
    
6. 设置**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 以指示文件附件和**PR\_ATTACH_LONG_FILENAME** ([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) 的文件的短名称, 以指示受支持的文件的名称在处理长文件名格式的平台上。 这两个属性都是可选的。 但是, 如果设置**PR_ATTACH_LONG_FILENAME**, 还要设置**PR_ATTACH_FILENAME**。 
    
7. 设置**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 以指示可在对话框中显示的附件的名称。 PR_DISPLAY_NAME 是可选的。 
    
## <a name="set-prattachdatabin"></a>设置 PR_ATTACH_DATA_BIN
  
1. 调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)以使用**IStream**接口打开属性。 
    
2. 如果文件包含数据且已打开, 或者您需要显式控制缓冲区大小, 则调用**IStream::** 在循环中写入以将数据放入流中。 
    
3. 另一种方法是调用**OpenStreamOnFile**以创建流以访问数据文件, 然后调用此流的**IStream:: CopyTo**方法将数据复制到**OpenProperty**返回的流中。
    
4. 调用新流的**IStream:: Commit**方法。 
    
## <a name="set-prattachdataobj"></a>设置 PR_ATTACH_DATA_OBJ
  
1. 调用**IMAPIProp:: OpenProperty**以使用**IStreamDocfile**接口打开属性, 以创建可处理结构化存储的流。 **IStreamDocfile**由邮件存储提供程序实现, 以便为客户端提供更高的性能方式来存储和检索结构化存储。 **IStreamDocfile**接口与**IStream**相同, 但可以保证流的内容的格式设置为结构化存储。 如果此调用成功, 请创建具有与设置**PR_ATTACH_DATA_BIN**相同的步骤的流。
    
2. 如果**OpenProperty**失败: 
    
   1. 再次调用**OpenProperty** , 要求**IStorage**。 
      
   2. 调用**StgOpenStorage**以打开 OLE 对象, 并返回一个存储对象。 
      
   3. 调用返回的存储对象的**IStorage:: CopyTo**方法复制到从**OpenProperty**返回的存储对象。
      
   4. 调用新的存储对象的**IStorage:: Commit**方法。 
    
## <a name="set-prattachpathname"></a>设置 PR_ATTACH_PATHNAME
  
1. 分配[SPropValue](spropvalue.md)结构, 将**ulPropTag**成员设置为**PR_ATTACH_PATHNAME** , 并将**值 LPSZ**成员设置为表示文件名的字符串。 
    
2. 调用附件的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法。 
    
> [!NOTE]
> 如果您的平台支持长文件名, 请设置**PR_ATTACH_PATHNAME**和**PR_ATTACH_LONG_PATHNAME**。 可能需要进行操作系统调用以检索短文件名。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 附件](mapi-attachments.md)

