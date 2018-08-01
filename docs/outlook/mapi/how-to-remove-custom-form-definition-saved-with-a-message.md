---
title: 删除自定义窗体定义保存一条消息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 6a270f0c-104a-84a1-9adf-aea166f89071
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: 9581656c40af39338f8919903f6d0de29c20a061
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775123"
---
# <a name="remove-custom-form-definition-saved-with-a-message"></a><span data-ttu-id="2a4be-103">删除自定义窗体定义保存一条消息</span><span class="sxs-lookup"><span data-stu-id="2a4be-103">Remove custom form definition saved with a message</span></span>
  
<span data-ttu-id="2a4be-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2a4be-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2a4be-105">本主题演示将转换为一条消息，与正则邮件不窗体定义自定义窗体定义已保存的 c + + 中的代码示例。</span><span class="sxs-lookup"><span data-stu-id="2a4be-105">This topic shows a code sample in C++ that converts a message that has been saved with a custom form definition to a regular message without the form definition.</span></span>
  
<span data-ttu-id="2a4be-106">在 Microsoft Outlook 2010 或 Microsoft Outlook 2013 中，您可以共享由发布到表单库或保存相应窗体定义一条消息中包含自定义窗体页面的表单。</span><span class="sxs-lookup"><span data-stu-id="2a4be-106">In Microsoft Outlook 2010 or Microsoft Outlook 2013, you can share forms containing custom form pages by either publishing them to a forms library or saving the corresponding form definition with a message.</span></span> <span data-ttu-id="2a4be-107">保存一条消息的自定义窗体通常称作"一次性窗体"，因为该窗体共享仅用于查看特定邮件作为一次性实例。</span><span class="sxs-lookup"><span data-stu-id="2a4be-107">A custom form saved with a message is commonly referred as a "one-off form", since the form is shared only for viewing that specific message as a one-off instance.</span></span> <span data-ttu-id="2a4be-108">通常执行此操作时窗体不发布窗体库中，但不是想使用自定义窗体时打开项目的收件人。</span><span class="sxs-lookup"><span data-stu-id="2a4be-108">You typically do this when the form is not published in a forms library but you want the recipient to use the custom form when opening the item.</span></span> <span data-ttu-id="2a4be-109">您可以指定窗体是一个一次性在窗体设计器中，通过选择窗体的**属性**页上的**发送窗体定义与项目**复选框。</span><span class="sxs-lookup"><span data-stu-id="2a4be-109">You can specify a form is a one-off in the Forms Designer, by selecting the **Send form definition with item** check box on the **Properties** page of the form.</span></span> 
  
<span data-ttu-id="2a4be-110">在 Visual Basic Scripting Edition (VBScript) 中使用代码，可以自定义窗体包含窗体页。</span><span class="sxs-lookup"><span data-stu-id="2a4be-110">Forms containing form pages can be customized with code in Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="2a4be-111">与表单定义保存的邮件是通常更大的大小。</span><span class="sxs-lookup"><span data-stu-id="2a4be-111">Messages that are saved with form definitions are generally bigger in size.</span></span> <span data-ttu-id="2a4be-112">安全和存储原因，Outlook 2010 和 Outlook 2013 忽略与任何项目保存的表单定义。</span><span class="sxs-lookup"><span data-stu-id="2a4be-112">For security and storage reasons, Outlook 2010 and Outlook 2013 ignore form definitions saved with any item.</span></span>
  
<span data-ttu-id="2a4be-113">要转换的保存格式对没有自定义窗体定义一条消息，您必须删除四个命名的属性：</span><span class="sxs-lookup"><span data-stu-id="2a4be-113">To convert a message that is saved with a custom form definition to one without, you must remove four named properties:</span></span>
  
- [<span data-ttu-id="2a4be-114">PidLidFormStorage 规范属性</span><span class="sxs-lookup"><span data-stu-id="2a4be-114">PidLidFormStorage Canonical Property</span></span>](pidlidformstorage-canonical-property.md)
    
- [<span data-ttu-id="2a4be-115">PidLidPageDirStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="2a4be-115">PidLidPageDirStream Canonical Property</span></span>](pidlidpagedirstream-canonical-property.md)
    
- [<span data-ttu-id="2a4be-116">PidLidFormPropStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="2a4be-116">PidLidFormPropStream Canonical Property</span></span>](pidlidformpropstream-canonical-property.md)
    
- [<span data-ttu-id="2a4be-117">PidLidScriptStream 规范属性</span><span class="sxs-lookup"><span data-stu-id="2a4be-117">PidLidScriptStream Canonical Property</span></span>](pidlidscriptstream-canonical-property.md)
    
<span data-ttu-id="2a4be-118">此外，您还应该删除[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md)包含使用该邮件保存的自定义属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2a4be-118">In addition, you should also remove the [PidLidPropertyDefinitionStream Canonical Property](pidlidpropertydefinitionstream-canonical-property.md) that contains the definitions of custom properties saved with that message.</span></span> <span data-ttu-id="2a4be-119">删除此属性的副作用在于 Outlook 2010 或 Outlook 2013 对象模型和 Outlook 2010 或 Outlook 2013 用户界面将不再能够访问用户属性已对邮件设置。</span><span class="sxs-lookup"><span data-stu-id="2a4be-119">A side effect of removing this property is that the Outlook 2010 or Outlook 2013 object models and the Outlook 2010 or Outlook 2013 user interface will no longer be able to access user properties that have been set on the message.</span></span> <span data-ttu-id="2a4be-120">您是仍然能够通过 MAPI 访问这些属性以及它们的值。</span><span class="sxs-lookup"><span data-stu-id="2a4be-120">You are still able to access these properties and their values through MAPI.</span></span> <span data-ttu-id="2a4be-121">请注意，是否不会删除此属性，该邮件将保存与另一个窗体定义[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md)部分覆盖使用新的数据和数据完整性不能保证。</span><span class="sxs-lookup"><span data-stu-id="2a4be-121">Note that if you do not remove this property and the message is saved with another form definition, the [PidLidPropertyDefinitionStream Canonical Property](pidlidpropertydefinitionstream-canonical-property.md) is partially overwritten with new data and data integrity is not guaranteed.</span></span> 
  
<span data-ttu-id="2a4be-122">如果您删除[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md)，然后您还应该**INSP_PROPDEFINITION**标志从删除[PidLidCustomFlag 规范属性](pidlidcustomflag-canonical-property.md)。</span><span class="sxs-lookup"><span data-stu-id="2a4be-122">If you remove the [PidLidPropertyDefinitionStream Canonical Property](pidlidpropertydefinitionstream-canonical-property.md), then you should also remove the **INSP_PROPDEFINITION** flag from the [PidLidCustomFlag Canonical Property](pidlidcustomflag-canonical-property.md).</span></span>
  
<span data-ttu-id="2a4be-123">下面的函数， `RemoveOneOff`，接受作为输入参数指向一条消息，指示符是否删除[PidLidPropertyDefinitionStream 规范属性](pidlidpropertydefinitionstream-canonical-property.md)。</span><span class="sxs-lookup"><span data-stu-id="2a4be-123">The following function,  `RemoveOneOff`, accepts as input parameters a pointer to a message and an indicator whether to remove the [PidLidPropertyDefinitionStream Canonical Property](pidlidpropertydefinitionstream-canonical-property.md).</span></span> <span data-ttu-id="2a4be-124">使用邮件指针，它调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取相应属性的标识符，，，然后调用[IMAPIProp::DeleteProps](imapiprop-deleteprops.md)中删除命名的属性。</span><span class="sxs-lookup"><span data-stu-id="2a4be-124">Using the message pointer, it calls [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the appropriate property identifiers, and then calls [IMAPIProp::DeleteProps](imapiprop-deleteprops.md) to remove the named properties.</span></span> <span data-ttu-id="2a4be-125">此外将调用[IMAPIProp::GetProps](imapiprop-getprops.md)若要获取[PidLidCustomFlag 规范属性](pidlidcustomflag-canonical-property.md)，并清除**INSP\_ONEOFFFLAGS**标志和**INSP_PROPDEFINITION**标记根据需要从该属性，因此该 Outlook 2010 和已删除这些命名属性不会查找 outlook 2013。</span><span class="sxs-lookup"><span data-stu-id="2a4be-125">It also calls [IMAPIProp::GetProps](imapiprop-getprops.md) to get the [PidLidCustomFlag Canonical Property](pidlidcustomflag-canonical-property.md) and clears the **INSP\_ONEOFFFLAGS** flag and **INSP_PROPDEFINITION** flag as appropriate from that property, so that Outlook 2010 and Outlook 2013 will not look for those named properties that have been removed.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="2a4be-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a4be-126">See also</span></span>

- [<span data-ttu-id="2a4be-127">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="2a4be-127">MAPI Constants</span></span>](mapi-constants.md)

