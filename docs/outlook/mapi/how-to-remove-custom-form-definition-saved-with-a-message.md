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
# <a name="remove-custom-form-definition-saved-with-a-message"></a><span data-ttu-id="1c6eb-103">删除随邮件一起保存的自定义表单定义</span><span class="sxs-lookup"><span data-stu-id="1c6eb-103">Remove custom form definition saved with a message</span></span>
  
<span data-ttu-id="1c6eb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1c6eb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1c6eb-105">本主题显示 c + + 中的代码示例, 该示例将与自定义窗体定义一起保存的邮件转换为常规邮件, 而不使用窗体定义。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-105">This topic shows a code sample in C++ that converts a message that has been saved with a custom form definition to a regular message without the form definition.</span></span>
  
<span data-ttu-id="1c6eb-106">在 microsoft outlook 2010 或 microsoft outlook 2013 中, 可以通过将表单发布到表单库或使用邮件保存相应的表单定义来共享包含自定义表单页面的表单。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-106">In Microsoft Outlook 2010 or Microsoft Outlook 2013, you can share forms containing custom form pages by either publishing them to a forms library or saving the corresponding form definition with a message.</span></span> <span data-ttu-id="1c6eb-107">与邮件一起保存的自定义窗体通常称为 "一次性窗体", 因为只共享该窗体以将该特定邮件作为一次性实例进行查看。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-107">A custom form saved with a message is commonly referred as a "one-off form", since the form is shared only for viewing that specific message as a one-off instance.</span></span> <span data-ttu-id="1c6eb-108">当窗体未在窗体库中发布, 但希望收件人在打开项目时使用自定义窗体时, 通常可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-108">You typically do this when the form is not published in a forms library but you want the recipient to use the custom form when opening the item.</span></span> <span data-ttu-id="1c6eb-109">通过选中窗体的 "**属性**" 页上的 "**将窗体定义与项目发送**" 复选框, 可以指定窗体在窗体设计器中是一次性的。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-109">You can specify a form is a one-off in the Forms Designer, by selecting the **Send form definition with item** check box on the **Properties** page of the form.</span></span> 
  
<span data-ttu-id="1c6eb-110">包含表单页面的表单可使用 Visual Basic 脚本版本 (VBScript) 中的代码进行自定义。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-110">Forms containing form pages can be customized with code in Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="1c6eb-111">与表单定义一起保存的邮件的大小通常较大。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-111">Messages that are saved with form definitions are generally bigger in size.</span></span> <span data-ttu-id="1c6eb-112">出于安全性和存储方面的原因, Outlook 2010 和 outlook 2013 忽略与任何项目一起保存的表单定义。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-112">For security and storage reasons, Outlook 2010 and Outlook 2013 ignore form definitions saved with any item.</span></span>
  
<span data-ttu-id="1c6eb-113">若要将使用自定义窗体定义保存的邮件转换为一个, 则必须删除四个命名属性:</span><span class="sxs-lookup"><span data-stu-id="1c6eb-113">To convert a message that is saved with a custom form definition to one without, you must remove four named properties:</span></span>
  
- [<span data-ttu-id="1c6eb-114">PidLidFormStorage 规范属性</span><span class="sxs-lookup"><span data-stu-id="1c6eb-114">PidLidFormStorage Canonical Property</span></span>](pidlidformstorage-canonical-property.md)
    
- [<span data-ttu-id="1c6eb-115">PidLidPageDirStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="1c6eb-115">PidLidPageDirStream Canonical Property</span></span>](pidlidpagedirstream-canonical-property.md)
    
- [<span data-ttu-id="1c6eb-116">PidLidFormPropStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="1c6eb-116">PidLidFormPropStream Canonical Property</span></span>](pidlidformpropstream-canonical-property.md)
    
- [<span data-ttu-id="1c6eb-117">PidLidScriptStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="1c6eb-117">PidLidScriptStream Canonical Property</span></span>](pidlidscriptstream-canonical-property.md)
    
<span data-ttu-id="1c6eb-118">此外, 还应删除[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md), 其中包含与该邮件一起保存的自定义属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-118">In addition, you should also remove the [PidLidPropertyDefinitionStream Canonical Property](pidlidpropertydefinitionstream-canonical-property.md) that contains the definitions of custom properties saved with that message.</span></span> <span data-ttu-id="1c6eb-119">删除此属性的副作用是 outlook 2010 或 outlook 2013 对象模型和 outlook 2010 或 outlook 2013 用户界面将无法再访问已在邮件上设置的用户属性。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-119">A side effect of removing this property is that the Outlook 2010 or Outlook 2013 object models and the Outlook 2010 or Outlook 2013 user interface will no longer be able to access user properties that have been set on the message.</span></span> <span data-ttu-id="1c6eb-120">您仍可以通过 MAPI 访问这些属性及其值。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-120">You are still able to access these properties and their values through MAPI.</span></span> <span data-ttu-id="1c6eb-121">请注意, 如果不删除该属性, 并且该邮件与其他表单定义一起保存, 则[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md)将被部分覆盖, 并不保证数据完整性。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-121">Note that if you do not remove this property and the message is saved with another form definition, the [PidLidPropertyDefinitionStream Canonical Property](pidlidpropertydefinitionstream-canonical-property.md) is partially overwritten with new data and data integrity is not guaranteed.</span></span> 
  
<span data-ttu-id="1c6eb-122">如果删除[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md), 则还应从[PidLidCustomFlag 规范属性](pidlidcustomflag-canonical-property.md)中删除**INSP_PROPDEFINITION**标志。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-122">If you remove the [PidLidPropertyDefinitionStream Canonical Property](pidlidpropertydefinitionstream-canonical-property.md), then you should also remove the **INSP_PROPDEFINITION** flag from the [PidLidCustomFlag Canonical Property](pidlidcustomflag-canonical-property.md).</span></span>
  
<span data-ttu-id="1c6eb-123">以下函数, `RemoveOneOff`接受为输入参数指向邮件的指针以及是否删除[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md)的指示器。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-123">The following function,  `RemoveOneOff`, accepts as input parameters a pointer to a message and an indicator whether to remove the [PidLidPropertyDefinitionStream Canonical Property](pidlidpropertydefinitionstream-canonical-property.md).</span></span> <span data-ttu-id="1c6eb-124">使用消息指针, 它调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)获取相应的属性标识符, 然后调用[IMAPIProp::D eleteprops](imapiprop-deleteprops.md)删除命名属性。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-124">Using the message pointer, it calls [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the appropriate property identifiers, and then calls [IMAPIProp::DeleteProps](imapiprop-deleteprops.md) to remove the named properties.</span></span> <span data-ttu-id="1c6eb-125">它还会调用[IMAPIProp:: GetProps](imapiprop-getprops.md)获取[PidLidCustomFlag 规范属性](pidlidcustomflag-canonical-property.md), 并根据该属性清除**INSP\_ONEOFFFLAGS**标志和**INSP_PROPDEFINITION**标志, 以便 Outlook 2010 和Outlook 2013 将不会查找那些已删除的已命名属性。</span><span class="sxs-lookup"><span data-stu-id="1c6eb-125">It also calls [IMAPIProp::GetProps](imapiprop-getprops.md) to get the [PidLidCustomFlag Canonical Property](pidlidcustomflag-canonical-property.md) and clears the **INSP\_ONEOFFFLAGS** flag and **INSP_PROPDEFINITION** flag as appropriate from that property, so that Outlook 2010 and Outlook 2013 will not look for those named properties that have been removed.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="1c6eb-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c6eb-126">See also</span></span>

- [<span data-ttu-id="1c6eb-127">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="1c6eb-127">MAPI Constants</span></span>](mapi-constants.md)

