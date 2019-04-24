---
title: 删除随邮件一起保存的自定义表单定义
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 6a270f0c-104a-84a1-9adf-aea166f89071
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: ac162cb73cfdee83bf034de32064c5ed9df3bc02
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345932"
---
# <a name="remove-custom-form-definition-saved-with-a-message"></a>删除随邮件一起保存的自定义表单定义
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本主题显示 c + + 中的代码示例, 该示例将与自定义窗体定义一起保存的邮件转换为常规邮件, 而不使用窗体定义。
  
在 microsoft outlook 2010 或 microsoft outlook 2013 中, 可以通过将表单发布到表单库或使用邮件保存相应的表单定义来共享包含自定义表单页面的表单。 与邮件一起保存的自定义窗体通常称为 "一次性窗体", 因为只共享该窗体以将该特定邮件作为一次性实例进行查看。 当窗体未在窗体库中发布, 但希望收件人在打开项目时使用自定义窗体时, 通常可以执行此操作。 通过选中窗体的 "**属性**" 页上的 "**将窗体定义与项目发送**" 复选框, 可以指定窗体在窗体设计器中是一次性的。 
  
包含表单页面的表单可使用 Visual Basic 脚本版本 (VBScript) 中的代码进行自定义。 与表单定义一起保存的邮件的大小通常较大。 出于安全性和存储方面的原因, Outlook 2010 和 outlook 2013 忽略与任何项目一起保存的表单定义。
  
若要将使用自定义窗体定义保存的邮件转换为一个, 则必须删除四个命名属性:
  
- [PidLidFormStorage 规范属性](pidlidformstorage-canonical-property.md)
    
- [PidLidPageDirStream 规范属性](pidlidpagedirstream-canonical-property.md)
    
- [PidLidFormPropStream 规范属性](pidlidformpropstream-canonical-property.md)
    
- [PidLidScriptStream 规范属性](pidlidscriptstream-canonical-property.md)
    
此外, 还应删除[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md), 其中包含与该邮件一起保存的自定义属性的定义。 删除此属性的副作用是 outlook 2010 或 outlook 2013 对象模型和 outlook 2010 或 outlook 2013 用户界面将无法再访问已在邮件上设置的用户属性。 您仍可以通过 MAPI 访问这些属性及其值。 请注意, 如果不删除该属性, 并且该邮件与其他表单定义一起保存, 则[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md)将被部分覆盖, 并不保证数据完整性。 
  
如果删除[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md), 则还应从[PidLidCustomFlag 规范属性](pidlidcustomflag-canonical-property.md)中删除**INSP_PROPDEFINITION**标志。
  
以下函数, `RemoveOneOff`接受为输入参数指向邮件的指针以及是否删除[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md)的指示器。 使用消息指针, 它调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)获取相应的属性标识符, 然后调用[IMAPIProp::D eleteprops](imapiprop-deleteprops.md)删除命名属性。 它还会调用[IMAPIProp:: GetProps](imapiprop-getprops.md)获取[PidLidCustomFlag 规范属性](pidlidcustomflag-canonical-property.md), 并根据该属性清除**INSP\_ONEOFFFLAGS**标志和**INSP_PROPDEFINITION**标志, 以便 Outlook 2010 和Outlook 2013 将不会查找那些已删除的已命名属性。 
  
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

