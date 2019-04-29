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
# <a name="get-the-email-address-of-a-contact-item"></a><span data-ttu-id="659ee-103">获取联系人项的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="659ee-103">Get the email address of a Contact item</span></span>

<span data-ttu-id="659ee-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="659ee-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="659ee-105">本主题演示如何获取命名属性的值, 该属性表示 Microsoft outlook 2010 或 microsoft outlook 2013 联系人项的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="659ee-105">This topic shows how to obtain the value of a named property that represents the email address of an Microsoft Outlook 2010 or Microsoft Outlook 2013 Contact item.</span></span>
  
<span data-ttu-id="659ee-106">您最大可以将三个电子邮件地址与 outlook 2010 和 outlook 2013 中的联系人项目关联。</span><span class="sxs-lookup"><span data-stu-id="659ee-106">You can associate up to three email addresses with a Contact item in Outlook 2010 and Outlook 2013.</span></span> <span data-ttu-id="659ee-107">每个电子邮件地址与 outlook 2010 和 outlook 2013 对象模型中的 outlook 2010 或 outlook 2013 **ContactItem**对象的属性相对应。</span><span class="sxs-lookup"><span data-stu-id="659ee-107">Each email address corresponds to a property of the Outlook 2010 or Outlook 2013 **ContactItem** object in the Outlook 2010 and Outlook 2013 object models.</span></span> <span data-ttu-id="659ee-108">outlook 2010 和 outlook 2013 内部的电子邮件地址也对应于 MAPI 命名属性。</span><span class="sxs-lookup"><span data-stu-id="659ee-108">Internal to Outlook 2010 and Outlook 2013, the email address also corresponds to a MAPI named property.</span></span> <span data-ttu-id="659ee-109">例如, 联系人的第一个电子邮件地址对应于 outlook 2010 和 outlook 2013 对象模型中**ContactItem**的**Email1Address**属性, 以及 outlook 2010 和 outlook 2013 internal (名为[PidLidEmail1EmailAddress 规范属性](pidlidemail1emailaddress-canonical-property.md)。</span><span class="sxs-lookup"><span data-stu-id="659ee-109">For example, the first email address of a contact corresponds to the **Email1Address** property of the **ContactItem** in the Outlook 2010 and Outlook 2013 object models, and the Outlook 2010 and Outlook 2013 internal named [PidLidEmail1EmailAddress Canonical Property](pidlidemail1emailaddress-canonical-property.md).</span></span>
  
<span data-ttu-id="659ee-110">若要获取联系人项目的电子邮件地址的值, 可以使用 Outlook 2010 或 outlook 2013 对象模型的**PropertyAccessor**对象, 或者先使用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)获取命名属性的属性标记, 然后在[IMAPIProp:: GetProps](imapiprop-getprops.md)中指定此属性标记以获取值。</span><span class="sxs-lookup"><span data-stu-id="659ee-110">To obtain the value of an email address of a contact item, you can use the **PropertyAccessor** object of the Outlook 2010 or Outlook 2013 object model, or first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag of the named property, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="659ee-111">调用**IMAPIProp:: GetIDsFromNames**时, 请为输入参数_lppPropNames_所指向的[MAPINAMEID](mapinameid.md)结构指定适当的值。</span><span class="sxs-lookup"><span data-stu-id="659ee-111">When calling **IMAPIProp::GetIDsFromNames**, specify the appropriate values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_.</span></span> <span data-ttu-id="659ee-112">下面的代码示例演示如何使用`lpContact` **GetIDsFromNames**和**GetProps**获取指定联系人的第一个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="659ee-112">The following code sample shows how to obtain the first email address of a specified contact,  `lpContact`, using **GetIDsFromNames** and **GetProps**.</span></span> 
  
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


