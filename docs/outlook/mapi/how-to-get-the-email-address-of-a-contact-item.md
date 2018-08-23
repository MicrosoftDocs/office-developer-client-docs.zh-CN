---
title: 获取联系人项目的电子邮件地址
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 032f7242-5500-1e21-06d3-b2d947eb1043
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: f9c6766c934632a83fa0388ac2bc4c2c397eead6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575551"
---
# <a name="get-the-email-address-of-a-contact-item"></a>获取联系人项目的电子邮件地址

**适用于**： Outlook 2013 |Outlook 2016 
  
本主题演示如何获取表示 Microsoft Outlook 2010 或 Microsoft Outlook 2013 联系人项目的电子邮件地址的命名属性的值。
  
可以将三个电子邮件地址与 Outlook 2010 和 Outlook 2013 中的联系人项目关联。 每个电子邮件地址对应于 Outlook 2010 和 Outlook 2013 对象模型中的 Outlook 2010 或 Outlook 2013 **ContactItem**对象的属性。 为 Outlook 2010 和 Outlook 2013 内部，电子邮件地址还对应于 MAPI 命名属性。 例如，联系人的第一个电子邮件地址对应于 Outlook 2010 和 Outlook 2013 对象模型和 Outlook 2010 和 Outlook 2013 的内部命名的[中**ContactItem**的**Email1Address**属性PidLidEmail1EmailAddress 规范属性](pidlidemail1emailaddress-canonical-property.md)。
  
若要获取电子邮件地址的联系人项目的值，您可以使用**PropertyAccessor**对象的 Outlook 2010 或 Outlook 2013 对象模型，或首先使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取属性的命名属性的属性标记，然后指定此属性标记中[IMAPIProp::GetProps](imapiprop-getprops.md)获取值。 调用**IMAPIProp::GetIDsFromNames**时, 指定指向通过输入的参数_lppPropNames_ [MAPINAMEID](mapinameid.md)结构的相应值。 下面的代码示例演示如何获取指定的联系人的第一个电子邮件地址`lpContact`，使用**GetIDsFromNames**和**GetProps**。 
  
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


