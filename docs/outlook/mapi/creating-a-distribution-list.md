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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32333024"
---
# <a name="creating-a-distribution-list"></a>创建通讯组列表

**适用于**：Outlook 2013 | Outlook 2016 
  
客户端可直接在可修改的容器 (如个人通讯簿 (PAB)) 中创建通讯组列表。
  
**在 PAB 中创建通讯组列表**
  
1. 创建具有一个属性标记的大小的属性标记数组, **PR_DEF_CREATE_DL** ([PidTagDefCreateDl](pidtagdefcreatedl-canonical-property.md)), 如下所示:
    
   ```cpp
    SizedPropTagArray(1, tagaDefaultDL) =
    {
        1,
        {
            PR_DEF_CREATE_DL
        }
    };
   ```

2. 调用[IAddrBook:: GetPAB](iaddrbook-getpab.md)以检索 PAB 的条目标识符。 如果有错误或**GetPAB**返回零或 NULL, 则不会继续。 
    
   ```cpp
    LPENTRYID peidPAB = NULL;
    ULONG cbeidPAB = 0;
    lpIAddrBook->GetPAB(&cbeidPAB, &peidPAB);
   ```

3. 调用[IAddrBook:: OpenEntry](iaddrbook-openentry.md)以打开 PAB。 _ulObjType_输出参数应设置为 MAPI_ABCONT。 
    
   ```cpp
    ULONG ulObjType = 0;
    LPABCONT lpPABCont = NULL;
    lpIAddrBook->OpenEntry(cbeidPAB, peidPAB,
                    NULL,
                    MAPI_MODIFY,
                    &ulObjType,
                    &lpPABCont);
   ```

4. 调用 PAB 的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索 PR_DEF_CREATE_DL 属性, 它用于创建通讯组列表的模板。 
    
   ```cpp
    lpPABCont->GetProps(0,
                tagaDefaultDL,
                &lpspvDefDLTpl);
    
   ```

5. 如果**GetProps**失败: 
    
   1. 调用 PAB 的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法, 以使用**IMAPITable**接口打开**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。 
      
   2. 创建属性限制以搜索**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 列等于 "MAPIPDL" 的行。 
      
   3. 调用[IMAPITable:: FindRow](imapitable-findrow.md)以查找此行。 
    
6. 保存由**GetProps**或**FindRow**返回的条目标识符。
    
   ```cpp
    peidDefDLTpl = lpspvDefDLTpl->Value.bin.pb;
    cbeidDefDLTpl = lpspvDefDLTpl->Value.bin.cb;
    
   ```

7. 调用 PAB 的[IABContainer:: CreateEntry](iabcontainer-createentry.md)方法, 以使用已保存的条目标识符表示的模板创建新条目。 不要假定返回的对象将是通讯组列表, 而不是消息用户 (当此调用是远程的时)。 请注意, CREATE_CHECK_DUP 标志在_ulFlags_参数中传递, 以防止添加两次输入。 
    
   ```cpp
    lpPABCont->CreateEntry(cbeidDefDLTpl,
                    peidDefDLTPL,
                    CREATE_CHECK_DUP_STRICT,
                    &lpNewPABEntry);
   ```

8. 调用新条目的**IUnknown:: QueryInterface**方法, 将 IID_IDistList 作为接口标识符传递, 以确定该条目是否为通讯组列表并支持[IDistList: IMAPIContainer](idistlistimapicontainer.md)接口。 由于**CreateEntry**返回**IMAPIProp**指针, 而不是更具体的**IMailUser**或**IDistList**指针, 请检查是否已创建通讯组列表对象。 如果**QueryInterface**成功, 则可以确保已创建了通讯组列表, 而不是邮件用户。 
    
9. 调用通讯组列表的[IMAPIProp:: SetProps](imapiprop-setprops.md)方法以设置其显示名称和其他属性。 
    
10. 调用通讯组列表的[IABContainer:: CreateEntry](iabcontainer-createentry.md)方法以添加一个或多个邮件用户。 
    
11. 当您准备好保存通讯组列表的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法时, 调用该方法。 若要检索已保存的通讯组列表的条目标识符, 请设置 KEEP_OPEN_READWRITE 标志, 然后调用[IMAPIProp:: GetProps](imapiprop-getprops.md)请求**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。
    
12. 通过调用其**IUnknown:: release**方法来释放新的通讯组列表和 PAB。 
    
13. 调用[MAPIFreeBuffer](mapifreebuffer.md)以释放 PAB 条目标识符和大小属性标记数组的内存。 
    

