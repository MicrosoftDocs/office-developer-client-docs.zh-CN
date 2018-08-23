---
title: 删除自定义窗体定义保存一条消息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 6a270f0c-104a-84a1-9adf-aea166f89071
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: 4b12824542a1408a364452eb6587122ec66412d3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594451"
---
# <a name="remove-custom-form-definition-saved-with-a-message"></a>删除自定义窗体定义保存一条消息
  
**适用于**： Outlook 2013 |Outlook 2016 
  
本主题演示将转换为一条消息，与正则邮件不窗体定义自定义窗体定义已保存的 c + + 中的代码示例。
  
在 Microsoft Outlook 2010 或 Microsoft Outlook 2013 中，您可以共享由发布到表单库或保存相应窗体定义一条消息中包含自定义窗体页面的表单。 保存一条消息的自定义窗体通常称作"一次性窗体"，因为该窗体共享仅用于查看特定邮件作为一次性实例。 通常执行此操作时窗体不发布窗体库中，但不是想使用自定义窗体时打开项目的收件人。 您可以指定窗体是一个一次性在窗体设计器中，通过选择窗体的**属性**页上的**发送窗体定义与项目**复选框。 
  
在 Visual Basic Scripting Edition (VBScript) 中使用代码，可以自定义窗体包含窗体页。 与表单定义保存的邮件是通常更大的大小。 安全和存储原因，Outlook 2010 和 Outlook 2013 忽略与任何项目保存的表单定义。
  
要转换的保存格式对没有自定义窗体定义一条消息，您必须删除四个命名的属性：
  
- [PidLidFormStorage 规范属性](pidlidformstorage-canonical-property.md)
    
- [PidLidPageDirStream 规范属性](pidlidpagedirstream-canonical-property.md)
    
- [PidLidFormPropStream 规范属性](pidlidformpropstream-canonical-property.md)
    
- [PidLidScriptStream 规范属性](pidlidscriptstream-canonical-property.md)
    
此外，您还应该删除[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md)包含使用该邮件保存的自定义属性的定义。 删除此属性的副作用在于 Outlook 2010 或 Outlook 2013 对象模型和 Outlook 2010 或 Outlook 2013 用户界面将不再能够访问用户属性已对邮件设置。 您是仍然能够通过 MAPI 访问这些属性以及它们的值。 请注意，是否不会删除此属性，该邮件将保存与另一个窗体定义[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md)部分覆盖使用新的数据和数据完整性不能保证。 
  
如果您删除[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md)，然后您还应该**INSP_PROPDEFINITION**标志从删除[PidLidCustomFlag 规范属性](pidlidcustomflag-canonical-property.md)。
  
下面的函数， `RemoveOneOff`，接受作为输入参数指向一条消息，指示符是否删除[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md)。 使用邮件指针，它调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取相应属性的标识符，，，然后调用[IMAPIProp::DeleteProps](imapiprop-deleteprops.md)中删除命名的属性。 此外将调用[IMAPIProp::GetProps](imapiprop-getprops.md)若要获取[PidLidCustomFlag 规范属性](pidlidcustomflag-canonical-property.md)，并清除**INSP\_ONEOFFFLAGS**标志和**INSP_PROPDEFINITION**标记根据需要从该属性，因此该 Outlook 2010 和已删除这些命名属性不会查找 outlook 2013。 
  
```cpp
ULONG aulOneOffIDs[] = {dispidFormStorage,  
    dispidPageDirStream, 
    dispidFormPropStream, 
    dispidScriptStream, 
    dispidPropDefStream, // dispidPropDefStream must remain next to last in list 
    dispidCustomFlag};   // dispidCustomFlag must remain last in list 
 
#define ulNumOneOffIDs (sizeof(aulOneOffIDs)/sizeof(aulOneOffIDs[0])) 
 
HRESULT RemoveOneOff(LPMESSAGE lpMessage, BOOL bRemovePropDef) 
{ 
    if (!lpMessage) return MAPI_E_INVALID_PARAMETER; 
     
    HRESULT hRes = S_OK; 
    MAPINAMEID  rgnmid[ulNumOneOffIDs]; 
    LPMAPINAMEID rgpnmid[ulNumOneOffIDs]; 
    LPSPropTagArray lpTags = NULL; 
 
    ULONG i = 0; 
    for (i = 0 ; i < ulNumOneOffIDs ; i++) 
    { 
        rgnmid[i].lpguid = (LPGUID)&PSETID_Common; 
        rgnmid[i].ulKind = MNID_ID; 
        rgnmid[i].Kind.lID = aulOneOffIDs[i]; 
        rgpnmid[i] = &rgnmid[i]; 
    } 
   
    hRes = lpMessage->GetIDsFromNames( 
        ulNumOneOffIDs, 
        rgpnmid, 
        0, 
        &lpTags); 
    if (lpTags) 
    { 
        // The last prop is the flag value  
        // to be updated, don't count it 
        lpTags->cValues = ulNumOneOffIDs-1; 
 
        // If the prop def stream is not to be removed, don't count it 
        if (!bRemovePropDef) 
        { 
          lpTags->cValues = lpTags->cValues-1; 
        } 
 
        hRes = lpMessage->DeleteProps( 
            lpTags, 
            0); 
        if (SUCCEEDED(hRes)) 
        { 
            SPropTagArray pTag = {0}; 
            ULONG cProp = 0; 
            LPSPropValue lpCustomFlag = NULL; 
 
            // Grab dispidCustomFlag, the last tag in the array 
            pTag.cValues = 1; 
            pTag.aulPropTag[0] = CHANGE_PROP_TYPE( 
                lpTags->aulPropTag[ulNumOneOffIDs-1], 
                PT_LONG); 
 
            hRes = lpMessage->GetProps( 
                &pTag, 
                fMapiUnicode, 
                &cProp, 
                &lpCustomFlag); 
            if (SUCCEEDED(hRes) &&  
                1 == cProp && lpCustomFlag &&  
                PT_LONG == PROP_TYPE(lpCustomFlag->ulPropTag)) 
            { 
                // Clear the INSP_ONEOFFFLAGS bits so Outlook  
                // doesn't look for the props that have been deleted 
                lpCustomFlag->Value.l =  
                    lpCustomFlag->Value.l & ~(INSP_ONEOFFFLAGS); 
                if (bRemovePropDef) 
                { 
                    lpCustomFlag->Value.l =  
                        lpCustomFlag->Value.l & ~(INSP_PROPDEFINITION); 
                } 
                hRes = lpMessage->SetProps( 
                    1, 
                    lpCustomFlag, 
                    NULL); 
             } 
 
             hRes = lpMessage->SaveChanges(KEEP_OPEN_READWRITE); 
         } 
    } 
    MAPIFreeBuffer(lpTags); 
 
    return hRes; 
}
```

## <a name="see-also"></a>另请参阅

- [MAPI 常量](mapi-constants.md)

