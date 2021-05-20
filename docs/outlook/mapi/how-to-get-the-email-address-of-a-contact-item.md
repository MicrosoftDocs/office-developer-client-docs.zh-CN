---
title: 获取联系人项的电子邮件地址
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 032f7242-5500-1e21-06d3-b2d947eb1043
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: fab09d0c594bac1374973f523abe6ff0b9c09dd0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429591"
---
# <a name="get-the-email-address-of-a-contact-item"></a>获取联系人项的电子邮件地址

**适用于**：Outlook 2013 | Outlook 2016 
  
本主题演示如何获取表示联系人项目或联系人项目的电子邮件地址的Microsoft Outlook 2010 Microsoft Outlook 2013属性的值。
  
您最多可以将三个电子邮件地址与 2010 和 Outlook 2013 中的联系人Outlook关联。 每个电子邮件地址对应于 Outlook 2010 和 Outlook 2013 对象模型中的 Outlook 2010 或 Outlook 2013 **ContactItem** 对象的属性。 在 2010 Outlook 2013 Outlook内部，电子邮件地址还对应于 MAPI 命名属性。 例如，联系人的第一个电子邮件地址对应于 Outlook 2010 和 Outlook 2013 对象模型中 **ContactItem** 的 **Email1Address** 属性，以及名为 [PidLidEmail1EmailAddress](pidlidemail1emailaddress-canonical-property.md)规范属性 的内部 Outlook 2010 和 Outlook 2013。
  
若要获取联系人项目的电子邮件地址的值，可以使用 Outlook 2010 或 Outlook 2013 对象模型的 **PropertyAccessor** 对象，或者首先使用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md)获取命名属性的属性标记，然后在 [IMAPIProp：：GetProps](imapiprop-getprops.md)中指定此属性标记以获取值。 调用 **IMAPIProp：：GetIDsFromNames** 时，指定输入参数 _lppPropNames_ 指向的 [MAPINAMEID](mapinameid.md)结构的适当值。 下面的代码示例演示如何使用  `lpContact` **GetIDsFromNames** 和 **GetProps** 获取指定联系人的第一个电子邮件地址。 
  
```cpp
HRESULT HrGetEmail1(LPMESSAGE lpContact) 
{ 
    HRESULT hRes = S_OK; 
    LPSPropTagArray lpNamedPropTags = NULL; 
    MAPINAMEID NamedID = {0}; 
    LPMAPINAMEID lpNamedID = &NamedID; 
    NamedID.lpguid = (LPGUID)&PSETID_Address; 
    NamedID.ulKind = MNID_ID; 
    NamedID.Kind.lID = dispidEmailEmailAddress; 
 
    hRes = lpContact->GetIDsFromNames( 
           1,  
           &lpNamedID,  
           NULL,  
           &lpNamedPropTags); 
 
    if (SUCCEEDED(hRes) && lpNamedPropTags) 
    { 
        SPropTagArray sPropTagArray; 
 
        sPropTagArray.cValues = 1; 
        sPropTagArray.aulPropTag[0] = CHANGE_PROP_TYPE(lpNamedPropTags->aulPropTag[0],PT_STRING8); 
        LPSPropValue lpProps = NULL; 
        ULONG cProps = 0; 
 
        hRes = lpContact->GetProps( 
               &sPropTagArray, 
               NULL, 
               &cProps, 
               &lpProps); 
        if (SUCCEEDED(hRes) &&  
            1 == cProps &&  
            lpProps &&  
            PT_STRING8 == PROP_TYPE(lpProps[0].ulPropTag) && 
            lpProps[0].Value.lpszA) 
        { 
            printf("Email address 1 = \"%s\"\n",lpProps[0].Value.lpszA); 
        } 
        MAPIFreeBuffer(lpProps); 
        MAPIFreeBuffer(lpNamedPropTags); 
     } 
     return hRes; 
}
```


