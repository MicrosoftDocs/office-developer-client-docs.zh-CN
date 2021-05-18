---
title: 删除随邮件一起保存的自定义表单定义
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 6a270f0c-104a-84a1-9adf-aea166f89071
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: ac162cb73cfdee83bf034de32064c5ed9df3bc02
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408465"
---
# <a name="remove-custom-form-definition-saved-with-a-message"></a>删除随邮件一起保存的自定义表单定义
  
**适用于**：Outlook 2013 | Outlook 2016 
  
本主题显示了一个 C++ 代码示例，该示例将已使用自定义窗体定义保存的邮件转换为不带表单定义的常规邮件。
  
在 Microsoft Outlook 2010 或 Microsoft Outlook 2013 中，可以通过将包含自定义表单页的表单发布到表单库或用邮件保存相应的表单定义来共享这些表单。 与邮件一起保存的自定义窗体通常称为"一次窗体"，因为共享该窗体只能作为一次实例查看该特定邮件。 通常，当窗体未在窗体库中发布，但您希望收件人在打开项目时使用自定义窗体时，会这样做。 通过在窗体的"属性"页上选中"将窗体定义与项目一起发送"复选框，可以在窗体设计器中指定窗体为一次窗体。 
  
可以使用 Visual Basic Scripting Edition (VBScript) 中自定义包含表单页的表单。 与表单定义一起保存的邮件的大小通常更大。 出于安全和存储原因，Outlook 2010 和 Outlook 2013 将忽略随任何项目一起保存的表单定义。
  
若要将随自定义窗体定义一起保存的邮件转换为不带自定义窗体定义的邮件，必须删除四个命名属性：
  
- [PidLidFormStorage 规范属性](pidlidformstorage-canonical-property.md)
    
- [PidLidPageDirStream 规范属性](pidlidpagedirstream-canonical-property.md)
    
- [PidLidFormPropStream 规范属性](pidlidformpropstream-canonical-property.md)
    
- [PidLidScriptStream 规范属性](pidlidscriptstream-canonical-property.md)
    
此外，还应删除包含随邮件一起保存的自定义属性定义的 [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md) 规范属性。 删除此属性的副作用是，Outlook 2010 或 Outlook 2013 对象模型和 Outlook 2010 或 Outlook 2013 用户界面将无法再访问已在邮件上设置的用户属性。 你仍然能够通过 MAPI 访问这些属性及其值。 请注意，如果不删除此属性，并且将邮件另存为另一个表单定义，则 [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md) 规范属性将被新数据部分覆盖，并且无法保证数据完整性。 
  
如果删除 [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)规范属性，则还应从 [PidLidCustomFlag](pidlidcustomflag-canonical-property.md)规范属性 中删除 **INSP_PROPDEFINITION** 标志。
  
以下函数 接受 作为输入参数、指向消息的指针以及是否删除  `RemoveOneOff` [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)规范属性的指示器。 它使用消息指针调用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 以获取相应的属性标识符，然后调用 [IMAPIProp：:D eleteProps](imapiprop-deleteprops.md) 以删除命名属性。 它还调用 [IMAPIProp：：GetProps](imapiprop-getprops.md)获取 [PidLidCustomFlag](pidlidcustomflag-canonical-property.md)规范属性，并适当地从该属性清除 **INSP \_ ONEOFFFLAGS** 标志和 **INSP_PROPDEFINITION** 标志，以便 Outlook 2010 和 Outlook 2013 不会查找已删除的命名属性。 
  
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

