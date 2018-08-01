---
title: 打开附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c0350698-5304-40cd-903d-279471f3c226
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3875e51868e882ca454c06949347327a21a93eb9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776547"
---
# <a name="opening-an-attachment"></a>打开附件

**适用于**： Outlook 
  
打开附件涉及显示其数据。 例如，当打开的文件附件时，将显示文件的内容。 使用其条目标识符打开邮件和文件夹，而使用其附件号码打开附件 — **PR_ATTACH_NUM**属性。 有关详细信息，请参阅**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md))。 可通过邮件的附件表都附件号码。
  
### <a name="to-open-all-attachments-in-a-message"></a>若要打开邮件中的所有附件
  
1. 调用消息的[IMessage::GetAttachmentTable](imessage-getattachmenttable.md)方法，以访问其附件表。 
    
2. 调用[HrQueryAllRows](hrqueryallrows.md)检索表中的所有行。 
    
3. 对于每个行： 
    
    1. 通过将传递表示对消息的**IMessage::OpenAttach**方法的调用的**PR_ATTACH_NUM**列中的附件号码打开附件。 有关详细信息，请参阅[IMessage::OpenAttach](imessage-openattach.md)。 **OpenAttach**提供对附件属性访问**IAttach**实现返回的指针。 
        
    2. 调用附件的**IMAPIProp::GetProps**方法来检索其**PR_ATTACH_METHOD**属性。 有关详细信息，请参阅[IMAPIProp::GetProps](imapiprop-getprops.md)和**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))。
        
    3. 如果**PR_ATTACH_METHOD**设置为 ATTACH_BY_REF_ONLY，调用**IMAPIProp::GetProps**检索**PR_ATTACH_PATHNAME**属性。 有关详细信息，请参阅**PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md))。
        
    4. 如果**PR\_ATTACH_METHOD**设置为附加\_BY_VALUE，呼叫**IMAPIProp::OpenProperty**打开**PR\_ATTACH_DATA_BIN**属性与**IStream**接口。 请参阅此过程的示例代码。 有关详细信息，请参阅[IMAPIProp::OpenProperty](imapiprop-openproperty.md)和**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md))。
        
    5. 如果**PR_ATTACH_METHOD**设置为 ATTACH_OLE 和附件是 OLE 2 对象： 
        
        1. 调用**IMAPIProp::OpenProperty**打开**PR\_ATTACH_DATA_OBJ**属性与**IStreamDocfile**接口。 试图使用此接口，因为它是**IStream**保证使用结构化存储文件以开销最少的实现。 有关详细信息，请参阅**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md))。
            
        2. 如果**OpenProperty**调用失败，可调用它再次以检索**IStreamDocfile**接口的**PR_ATTACH_DATA_BIN**属性。 
            
        3. 如果此第二个**OpenProperty**调用失败，则重试呼叫**OpenProperty**检索**PR_ATTACH_DATA_OBJ**。 但是，而不是指定**IStreamDocfile**，指定**IStorage**接口。 
    
4. 如果**PR_ATTACH_METHOD**设置为 ATTACH_EMBEDDED_MSG，则不特殊**PR_ATTACH_DATA_OBJ**包含错误的值。 这是对象的因为您并表实施没有任何办法达成一致要返回类型。 若要检索指向附加的邮件的指针，打开使用**IMessage::OpenAttach**附件。 然后通过调用其**IMAPIProp::OpenProperty**方法访问附件数据。 有关详细信息，请参阅[IMessage::OpenAttach](imessage-openattach.md)和[IMAPIProp::OpenProperty](imapiprop-openproperty.md)。
    
您可以请求的读/写或只读模式中打开的附件。 只读是默认的模式，并许多消息存储提供程序无论客户端的请求此模式中打开所有附件。 传入请求的消息存储提供程序授予的访问它可以，然后检索打开的附件的**PR_ACCESS_LEVEL**属性可以确定的实际授予的访问级别最高级别 MAPI_BEST_ACCESS 标志。 有关详细信息，请参阅**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md))。
  
下面的示例演示如何打开的附件中的数据**PR\_ATTACH_DATA_BIN**属性。 分配了指向两个流： 一个用于文件，一个附件。 **OpenStreamOnFile**函数以只读模式打开文件流。 对附件的**IMAPIProp::OpenProperty**方法的调用以读/写模式打开附件流。 有关详细信息，请参阅**PR_ATTACH_DATA_BIN**、 [OpenStreamOnFile](openstreamonfile.md)和[IMAPIProp::OpenProperty](imapiprop-openproperty.md)。 该代码，然后将文件流复制到附件流并释放两个流。
  
```cpp
LPSTREAM pStreamFile, pStreamAtt;
HRESULT hr;
hr = OpenStreamOnFile (MAPIAllocateBuffer, MAPIFreeBuffer,
                       STGM_READ, "myfile.doc", NULL, &pStreamFile);
if (HR_SUCCEEDED(hr))
{
    // Open the destination stream in the attachment object
    hr = pAttach->OpenProperty (PR_ATTACH_DATA_BIN,
                                &IID_IStream,
                                0,
                                MAPI_MODIFY | MAPI_CREATE,
                                (LPUNKNOWN *)&pStreamAtt);
    if (HR_SUCCEEDED(hr))
    {
        STATSTG StatInfo;
        pStreamFile->Stat (&StatInfo, STATFLAG_NONAME);
        hResult = pStreamFile->CopyTo (pStreamAtt, StatInfo.cbSize,
                                       NULL, NULL);
        pStreamAtt->Release();
    }
    pStreamFile->Release();
}
```


