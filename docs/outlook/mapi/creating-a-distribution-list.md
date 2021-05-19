---
title: 创建通讯组列表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b63a6024-910d-4569-a3b4-c3ebf0b32c3d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7108ae215562169244100a56cc9b9208d78b1893
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424173"
---
# <a name="creating-a-distribution-list"></a>创建通讯组列表

**适用于**：Outlook 2013 | Outlook 2016 
  
客户端可以直接在可修改的容器中创建通讯组列表，例如 PAB (个人) 。
  
**在 PAB 中创建通讯组列表**
  
1. 使用一个属性标记创建大小属性标记数组，PR_DEF_CREATE_DL ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)) ，如下所示： 
    
   ```cpp
    SizedPropTagArray(1, tagaDefaultDL) =
    {
        1,
        {
            PR_DEF_CREATE_DL
        }
    };
   ```

2. 调用 [IAddrBook：：GetPAB](iaddrbook-getpab.md) 检索 PAB 的条目标识符。 如果出现错误或 **GetPAB** 返回零或 NULL，请不要继续。 
    
   ```cpp
    LPENTRYID peidPAB = NULL;
    ULONG cbeidPAB = 0;
    lpIAddrBook->GetPAB(&cbeidPAB, &peidPAB);
   ```

3. 调用 [IAddrBook：：OpenEntry](iaddrbook-openentry.md) 以打开 PAB。 _ulObjType_ 输出参数应设置为 MAPI_ABCONT。 
    
   ```cpp
    ULONG ulObjType = 0;
    LPABCONT lpPABCont = NULL;
    lpIAddrBook->OpenEntry(cbeidPAB, peidPAB,
                    NULL,
                    MAPI_MODIFY,
                    &ulObjType,
                    &lpPABCont);
   ```

4. 调用 PAB 的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索 PR_DEF_CREATE_DL 属性，该属性是它用于创建通讯组列表的模板。 
    
   ```cpp
    lpPABCont->GetProps(0,
                tagaDefaultDL,
                &lpspvDefDLTpl);
    
   ```

5. 如果 **GetProps** 失败： 
    
   1. 调用 PAB [的 IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法以使用 **IMAPITable** 接口打开 **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。 
      
   2. 创建属性限制以搜索[PidTagAddressType](pidtagaddresstype-canonical-property.md) PR_ADDRTYPE (等于"MAPIPDL") 行。  
      
   3. 调用 [IMAPITable：：FindRow](imapitable-findrow.md) 以查找此行。 
    
6. 保存 **GetProps** 或 FindRow 返回的 **条目标识符**。
    
   ```cpp
    peidDefDLTpl = lpspvDefDLTpl->Value.bin.pb;
    cbeidDefDLTpl = lpspvDefDLTpl->Value.bin.cb;
    
   ```

7. 调用 PAB 的 [IABContainer：：CreateEntry](iabcontainer-createentry.md) 方法，使用保存的条目标识符表示的模板创建新条目。 请勿假定当此调用被远程时，返回的对象将是通讯组列表而不是消息用户。 请注意，CREATE_CHECK_DUP标记在  _ulFlags_ 参数中传递，以防止条目添加两次。 
    
   ```cpp
    lpPABCont->CreateEntry(cbeidDefDLTpl,
                    peidDefDLTPL,
                    CREATE_CHECK_DUP_STRICT,
                    &lpNewPABEntry);
   ```

8. 调用新条目的 **IUnknown：：QueryInterface** 方法，将 IID_IDistList 作为接口标识符传递，以确定条目是否为通讯组列表并支持 [IDistList ： IMAPIContainer](idistlistimapicontainer.md) 接口。 由于 **CreateEntry** 返回 **IMAPIProp** 指针，而不是更具体的 **IMailUser** 或 **IDistList** 指针，请检查是否创建了通讯组列表对象。 如果 **QueryInterface** 成功，则您可以确保已创建通讯组列表，而不是邮件用户。 
    
9. 调用通讯组列表的 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法来设置其显示名称属性。 
    
10. 调用通讯组列表的 [IABContainer：：CreateEntry](iabcontainer-createentry.md) 方法以添加一个或多个邮件用户。 
    
11. 准备好保存时，调用通讯组列表的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法。 若要检索已保存通讯组列表的条目标识符，请设置 KEEP_OPEN_READWRITE 标志，然后调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 以请求 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
    
12. 通过调用其 **IUnknown：：Release** 方法释放新的通讯组列表和 PAB。 
    
13. 调用 [MAPIFreeBuffer](mapifreebuffer.md) 以释放 PAB 的条目标识符和大小属性标记数组的内存。 
    

