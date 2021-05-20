---
title: 打开附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c0350698-5304-40cd-903d-279471f3c226
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 39da1e02622d81cd12a2d4673b827d49bf418128
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430621"
---
# <a name="opening-an-attachment"></a>打开附件

**适用于**：Outlook 2013 | Outlook 2016 
  
打开附件涉及显示其数据。 例如，打开文件附件时，将显示文件的内容。 虽然邮件和文件夹是使用其条目标识符打开的，但附件是使用附件编号打开的 **，PR_ATTACH_NUM** 属性。 有关详细信息，请参阅 **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 。 附件编号通过邮件的附件表提供。
  
### <a name="to-open-all-attachments-in-a-message"></a>打开邮件中所有附件
  
1. 调用邮件的 [IMessage：：GetAttachmentTable](imessage-getattachmenttable.md) 方法以访问其附件表。 
    
2. 调用 [HrQueryAllRows](hrqueryallrows.md) 以检索表中的所有行。 
    
3. 对于每一行： 
    
    1. 通过向邮件的 **IMessage：：OpenAttach** 方法的调用中传递 **PR_ATTACH_NUM** 列中表示的附件编号，打开附件。 有关详细信息，请参阅 [IMessage：：OpenAttach](imessage-openattach.md)。 **OpenAttach** 返回一个指向 **IAttach** 实现（提供对附件属性的访问）的指针。 
        
    2. 调用附件的 **IMAPIProp：：GetProps** 方法来 **检索其PR_ATTACH_METHOD** 属性。 有关详细信息，请参阅 [IMAPIProp：：GetProps](imapiprop-getprops.md) 和 **PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 。
        
    3. 如果 **PR_ATTACH_METHOD** 设置为 ATTACH_BY_REF_ONLY，请调用 **IMAPIProp：：GetProps** 以检索 **PR_ATTACH_PATHNAME** 属性。 有关详细信息，请参阅 **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 。
        
    4. 如果 **PR \_ ATTACH_METHOD** 设置为 ATTACH \_ BY_VALUE，请调用 **IMAPIProp：：OpenProperty** 以使用 **IStream** 接口打开 **PR \_ ATTACH_DATA_BIN** 属性。 请参阅此过程后的示例代码。 有关详细信息，请参阅 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 和 **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 。
        
    5. 如果 **PR_ATTACH_METHOD** 设置为 OLE 2 ATTACH_OLE附件是 OLE 2 对象： 
        
        1. 调用 **IMAPIProp：：OpenProperty** 以使用 **IStreamDocfile** **\_ ATTACH_DATA_OBJ** PR 属性打开 PR 属性。 尝试使用此接口，因为它是保证使用开销最少的结构化存储的 **IStream** 实现。 有关详细信息，请参阅 **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 。
            
        2. 如果 **OpenProperty** 调用失败，请再次调用它，以检索 **PR_ATTACH_DATA_BIN** **IStreamDocfile** 接口的 PR_ATTACH_DATA_BIN 属性。 
            
        3. 如果第二 **个 OpenProperty** 调用失败，请再次尝试调用 **OpenProperty****以检索** PR_ATTACH_DATA_OBJ。 但是，不是指定 **IStreamDocfile**，而是指定 **IStorage** 接口。 
    
4. 如果 **PR_ATTACH_METHOD** 设置为 ATTACH_EMBEDDED_MSG，则值 **PR_ATTACH_DATA_OBJ包含错误** 并不少见。 这是因为你和表实施者无法就要返回的对象类型达成一致。 若要检索指向附加邮件的指针，请用 **IMessage：：OpenAttach 打开附件**。 然后通过调用其 **IMAPIProp：：OpenProperty 方法访问附件** 数据。 有关详细信息，请参阅 [IMessage：：OpenAttach](imessage-openattach.md) 和 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)。
    
您可以请求以读/写或只读模式打开附件。 只读是默认模式，许多邮件存储提供程序在此模式下打开所有附件，而不考虑客户端请求什么。 传递 MAPI_BEST_ACCESS 标志以请求邮件存储提供程序授予其可以授予的最高访问权限级别，然后检索打开的附件 **的 PR_ACCESS_LEVEL** 属性以确定实际授予的访问级别。 有关详细信息，请参阅 **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 。
  
以下示例演示如何在附件的 PR 属性中打开ATTACH_DATA_BIN数据。 **\_** 它将指针分配给两个流：一个针对文件，一个针对附件。 **OpenStreamOnFile** 函数以只读模式打开文件流。 对附件 **的 IMAPIProp：：OpenProperty** 方法的调用将在读/写模式下打开附件流。 有关详细信息，请参阅 **PR_ATTACH_DATA_BIN** [、OpenStreamOnFile](openstreamonfile.md)和 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)。 然后，代码将文件流复制到附件流并释放这两个流。
  
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


