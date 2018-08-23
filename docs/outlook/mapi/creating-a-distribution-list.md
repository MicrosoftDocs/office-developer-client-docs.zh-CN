---
title: 创建通讯组列表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b63a6024-910d-4569-a3b4-c3ebf0b32c3d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f0a6b7af196073d52ce98037b443569dcd1f41e6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582544"
---
# <a name="creating-a-distribution-list"></a>创建通讯组列表

**适用于**： Outlook 2013 |Outlook 2016 
  
客户端可以直接在如个人通讯簿 (PAB) 可修改容器中创建通讯组列表。
  
**在 PAB 中创建通讯组列表**
  
1. 使用一个属性标记， **PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md))，创建调整的属性标记数组，如下所示：
    
   ```cpp
    SizedPropTagArray(1, tagaDefaultDL) =
    {
        1,
        {
            PR_DEF_CREATE_DL
        }
    };
   ```

2. 调用[IAddrBook::GetPAB](iaddrbook-getpab.md)检索 PAB 的项标识符。 如果出现错误或**GetPAB**返回零或为空，请不要继续。 
    
   ```cpp
    LPENTRYID peidPAB = NULL;
    ULONG cbeidPAB = 0;
    lpIAddrBook->GetPAB(&cbeidPAB, &peidPAB);
   ```

3. 调用[IAddrBook::OpenEntry](iaddrbook-openentry.md)打开 PAB。 _UlObjType_输出参数应设置为 MAPI_ABCONT。 
    
   ```cpp
    ULONG ulObjType = 0;
    LPABCONT lpPABCont = NULL;
    lpIAddrBook->OpenEntry(cbeidPAB, peidPAB,
                    NULL,
                    MAPI_MODIFY,
                    &ulObjType,
                    &lpPABCont);
   ```

4. 调用 PAB [IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索 PR_DEF_CREATE_DL 属性，它使用创建通讯组列表的模板。 
    
   ```cpp
    lpPABCont->GetProps(0,
                tagaDefaultDL,
                &lpspvDefDLTpl);
    
   ```

5. 如果**GetProps**失败： 
    
   1. 调用 PAB [IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法使用**IMAPITable**接口打开**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。 
      
   2. 创建属性限制搜索行与**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 列等于"MAPIPDL。" 
      
   3. 调用[IMAPITable::FindRow](imapitable-findrow.md)以找到此行。 
    
6. 保存由**GetProps**或**FindRow**返回的项标识符。
    
   ```cpp
    peidDefDLTpl = lpspvDefDLTpl->Value.bin.pb;
    cbeidDefDLTpl = lpspvDefDLTpl->Value.bin.cb;
    
   ```

7. 调用 PAB [IABContainer::CreateEntry](iabcontainer-createentry.md)方法，以创建新的项使用由已保存的项标识符的模板。 不要假定返回的对象将是通讯组列表，而不是邮件用户，此呼叫为远程类型时。 请注意，防止输入两次添加_ulFlags_参数中传递 CREATE_CHECK_DUP 标志。 
    
   ```cpp
    lpPABCont->CreateEntry(cbeidDefDLTpl,
                    peidDefDLTPL,
                    CREATE_CHECK_DUP_STRICT,
                    &lpNewPABEntry);
   ```

8. 调用新条目的**IUnknown::QueryInterface**方法，将作为接口标识符，以确定是否条目是通讯组列表，以及支持传递 IID_IDistList [IDistList: IMAPIContainer](idistlistimapicontainer.md)接口。 由于**CreateEntry**返回**IMAPIProp**指针，而不是更具体的**IMailUser**或**IDistList**指针，检查已创建通讯组列表对象。 如果**QueryInterface**成功，您可以确保您已创建通讯组列表，而不是邮件用户。 
    
9. 调用该通讯组列表[IMAPIProp::SetProps](imapiprop-setprops.md)方法，以设置其显示名称和其他属性。 
    
10. 调用该通讯组列表[IABContainer::CreateEntry](iabcontainer-createentry.md)方法，以添加一个或多个邮件用户。 
    
11. 您已经准备将其保存时调用的通讯组列表[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。 若要检索的已保存的通讯组列表项标识符，设置 KEEP_OPEN_READWRITE 标记，然后调用[IMAPIProp::GetProps](imapiprop-getprops.md)请求**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
    
12. 通过调用其**IUnknown::Release**方法释放新通讯组列表和 PAB。 
    
13. 调用[MAPIFreeBuffer](mapifreebuffer.md)释放 PAB 和调整的属性标记数组的项标识符的内存。 
    

