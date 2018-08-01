---
title: 获取联系人项目的电子邮件地址
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 032f7242-5500-1e21-06d3-b2d947eb1043
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: ce9579cb6b07336cae7d69fe503c918d96946b0c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775096"
---
# <a name="get-the-email-address-of-a-contact-item"></a><span data-ttu-id="41a1d-103">获取联系人项目的电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="41a1d-103">Get the email address of a Contact item</span></span>

<span data-ttu-id="41a1d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="41a1d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="41a1d-105">本主题演示如何获取表示 Microsoft Outlook 2010 或 Microsoft Outlook 2013 联系人项目的电子邮件地址的命名属性的值。</span><span class="sxs-lookup"><span data-stu-id="41a1d-105">This topic shows how to obtain the value of a named property that represents the email address of an Microsoft Outlook 2010 or Microsoft Outlook 2013 Contact item.</span></span>
  
<span data-ttu-id="41a1d-106">可以将三个电子邮件地址与 Outlook 2010 和 Outlook 2013 中的联系人项目关联。</span><span class="sxs-lookup"><span data-stu-id="41a1d-106">You can associate up to three email addresses with a Contact item in Outlook 2010 and Outlook 2013.</span></span> <span data-ttu-id="41a1d-107">每个电子邮件地址对应于 Outlook 2010 和 Outlook 2013 对象模型中的 Outlook 2010 或 Outlook 2013 **ContactItem**对象的属性。</span><span class="sxs-lookup"><span data-stu-id="41a1d-107">Each email address corresponds to a property of the Outlook 2010 or Outlook 2013 **ContactItem** object in the Outlook 2010 and Outlook 2013 object models.</span></span> <span data-ttu-id="41a1d-108">为 Outlook 2010 和 Outlook 2013 内部，电子邮件地址还对应于 MAPI 命名属性。</span><span class="sxs-lookup"><span data-stu-id="41a1d-108">Internal to Outlook 2010 and Outlook 2013, the email address also corresponds to a MAPI named property.</span></span> <span data-ttu-id="41a1d-109">例如，联系人的第一个电子邮件地址对应于 Outlook 2010 和 Outlook 2013 对象模型和 Outlook 2010 和 Outlook 2013 的内部命名的[中**ContactItem**的**Email1Address**属性PidLidEmail1EmailAddress 规范属性](pidlidemail1emailaddress-canonical-property.md)。</span><span class="sxs-lookup"><span data-stu-id="41a1d-109">For example, the first email address of a contact corresponds to the **Email1Address** property of the **ContactItem** in the Outlook 2010 and Outlook 2013 object models, and the Outlook 2010 and Outlook 2013 internal named [PidLidEmail1EmailAddress Canonical Property](pidlidemail1emailaddress-canonical-property.md).</span></span>
  
<span data-ttu-id="41a1d-110">若要获取电子邮件地址的联系人项目的值，您可以使用**PropertyAccessor**对象的 Outlook 2010 或 Outlook 2013 对象模型，或首先使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取属性的命名属性的属性标记，然后指定此属性标记中[IMAPIProp::GetProps](imapiprop-getprops.md)获取值。</span><span class="sxs-lookup"><span data-stu-id="41a1d-110">To obtain the value of an email address of a contact item, you can use the **PropertyAccessor** object of the Outlook 2010 or Outlook 2013 object model, or first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag of the named property, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="41a1d-111">调用**IMAPIProp::GetIDsFromNames**时, 指定指向通过输入的参数_lppPropNames_ [MAPINAMEID](mapinameid.md)结构的相应值。</span><span class="sxs-lookup"><span data-stu-id="41a1d-111">When calling **IMAPIProp::GetIDsFromNames**, specify the appropriate values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_.</span></span> <span data-ttu-id="41a1d-112">下面的代码示例演示如何获取指定的联系人的第一个电子邮件地址`lpContact`，使用**GetIDsFromNames**和**GetProps**。</span><span class="sxs-lookup"><span data-stu-id="41a1d-112">The following code sample shows how to obtain the first email address of a specified contact,  `lpContact`, using **GetIDsFromNames** and **GetProps**.</span></span> 
  
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


