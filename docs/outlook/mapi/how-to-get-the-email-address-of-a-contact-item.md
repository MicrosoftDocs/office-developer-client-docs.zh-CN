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
  
本主题演示如何获取命名属性的值, 该属性表示 Microsoft outlook 2010 或 microsoft outlook 2013 联系人项的电子邮件地址。
  
您最大可以将三个电子邮件地址与 outlook 2010 和 outlook 2013 中的联系人项目关联。 每个电子邮件地址与 outlook 2010 和 outlook 2013 对象模型中的 outlook 2010 或 outlook 2013 **ContactItem**对象的属性相对应。 outlook 2010 和 outlook 2013 内部的电子邮件地址也对应于 MAPI 命名属性。 例如, 联系人的第一个电子邮件地址对应于 outlook 2010 和 outlook 2013 对象模型中**ContactItem**的**Email1Address**属性, 以及 outlook 2010 和 outlook 2013 internal (名为[PidLidEmail1EmailAddress 规范属性](pidlidemail1emailaddress-canonical-property.md)。
  
若要获取联系人项目的电子邮件地址的值, 可以使用 Outlook 2010 或 outlook 2013 对象模型的**PropertyAccessor**对象, 或者先使用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)获取命名属性的属性标记, 然后在[IMAPIProp:: GetProps](imapiprop-getprops.md)中指定此属性标记以获取值。 调用**IMAPIProp:: GetIDsFromNames**时, 请为输入参数_lppPropNames_所指向的[MAPINAMEID](mapinameid.md)结构指定适当的值。 下面的代码示例演示如何使用`lpContact` **GetIDsFromNames**和**GetProps**获取指定联系人的第一个电子邮件地址。 
  
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


