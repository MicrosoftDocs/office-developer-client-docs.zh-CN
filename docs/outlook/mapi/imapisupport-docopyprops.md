---
title: IMAPISupportDoCopyProps
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.DoCopyProps
api_type:
- COM
ms.assetid: 2446ef52-578a-4004-9719-de9b0207ccad
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 24107ae1926c8590da6a823a354eeae72d72f248
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405581"
---
# <a name="imapisupportdocopyprops"></a>IMAPISupport::DoCopyProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将对象的一个或多个属性复制或移动到另一个对象。
  
```cpp
HRESULT DoCopyProps(
  LPCIID lpSrcInterface,
  LPVOID lpSrcObj,
  LPSPropTagArray lpIncludeProps,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  LPCIID lpDestInterface,
  LPVOID lpDestObj,
  ULONG ulFlags,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a>参数

 _lpSrcInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示用于访问要复制或移动的属性的对象的接口。
    
 _lpSrcObj_
  
> 实时指向对象的指针, 该对象包含要复制或移动的属性。
    
 _lpIncludeProps_
  
> 实时一个指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含指明要复制或移动的属性的属性标记的计数数组。 _lpIncludeProps_参数不能为 NULL。 
    
 _ulUIParam_
  
> 实时进度指示器的父窗口的句柄。
    
 _lpProgress_
  
> 实时指向进度指示器的实现的指针。 如果在_lpProgress_参数中传递 NULL, 则将使用 MAPI 实现显示进度指示器。 除非在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 否则将忽略_lpProgress_参数。 
    
 _lpDestInterface_
  
> 实时指向接口标识符的指针, 该标识符表示要用于访问对象以接收复制或移动的属性的接口。
    
 _lpDestObj_
  
> 实时指向接收复制或移动的属性的对象的指针。
    
 _ulFlags_
  
> 实时用于控制如何执行复制或移动操作的标志的位掩码。 可以设置以下标志:
    
MAPI_DIALOG 
  
> 显示进度指示器。
    
MAPI_MOVE 
  
> **DoCopyProps**应执行移动操作, 而不是复制操作。 如果未设置此标志, **DoCopyProps**将执行复制操作。 
    
MAPI_NOREPLACE 
  
> 不应覆盖目标对象中的现有属性。 如果未设置此标志, **DoCopyProps**将覆盖现有属性。 
    
 _lppProblems_
  
> [in, out]在输入时, 指向指向[SPropProblemArray](spropproblemarray.md)结构的指针的指针;否则为 NULL, 表示无需提供错误信息。 如果_lppProblems_是有效的输入指针, **DoCopyProps**将返回有关复制一个或多个属性中的错误的详细信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动属性。
    
MAPI_E_COLLISION 
  
> 要复制或移动的属性已存在于 destination 对象中, 并且设置了 MAPI_NOREPLACE 标志。 
    
MAPI_E_FOLDER_CYCLE 
  
> 源对象直接或间接包含目标对象。 在发现此条件之前, 可能已经执行了大量的工作, 因此源和目标对象可能被部分修改。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 源对象不支持由_lpSrcInterface_参数标识的接口, 或者目标对象不支持由_lpDestInterface_参数标识的接口。 
    
MAPI_E_NO_ACCESS 
  
> 试图访问呼叫者没有足够权限的对象。 如果目标对象与源对象相同, 则返回此错误。
    
以下值可在**SPropProblemArray**结构中返回, 但不能在**DoCopyProps**的返回值中返回。 这些错误适用于单个属性。
  
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 并且**DoCopyProps**不支持 unicode, 或者未设置 MAPI_UNICODE, 且**DoCopyProps**仅支持 UNICODE。 
    
MAPI_E_COMPUTED 
  
> 调用程序无法修改该属性, 因为它是由目标对象的所有者计算的只读属性。 此错误不严重;呼叫者应允许复制操作继续进行。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不是调用方预期的类型。
    
## <a name="remarks"></a>说明

**IMAPISupport::D ocopyprops**方法是为邮件存储提供程序支持对象而实现的。 邮件存储提供程序可以调用**DoCopyProps**以实现其文件夹和邮件的[IMAPIProp:: CopyProps](imapiprop-copyprops.md)方法。 **DoCopyProps**复制或移动在由_lpIncludeProps_指向的属性标记数组中标识的属性, 以及_lpSrcObj_指向的对象中存在的属性。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当您在相同类型的对象 (如两条消息) 之间复制属性时, _lpSrcInterface_和_lpDestInterface_参数必须包含相同的接口标识符, 并且_lpSrcObj_和_lpDestObj_参数必须指向相同类型的对象。 如果将_lpDestInterface_设置为 NULL, 则**DoCopyProps**将返回 MAPI_E_INVALID_PARAMETER。 如果将_lpDestInterface_设置为可接受的接口标识符, 但将_lpDestObj_设置为无效的指针, 则结果是不可预知的。 您的提供程序很可能会失败。 
  
如果您不想覆盖 destination 对象中的任何属性, 请设置 MAPI_NOREPLACE 标志。 源对象中存在且不会被覆盖的 destination 对象中的属性不会被删除或修改。
  
若要复制邮件的收件人列表, 请在由_lpIncludeProps_参数指向的属性标记数组中包含**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。 若要复制邮件的附件, 请包含**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。 
  
若要复制文件夹或通讯簿容器的层次结构或内容表, 请在属性标记数组中包含**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))。 若要包含文件夹的关联内容表, 请在数组中包含**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。
  
如果复制或移动了子文件夹, 则无论使用的是由**SPropTagArray**结构指示的属性, 它们的内容都会完全复制或移动。 
  
 **DoCopyProps**报告作为一个整体的操作发生的全局错误, 以及一个或多个属性发生的各个错误。 这些单独的错误放在**SPropProblemArray**结构中。 您可以通过为属性问题数组结构参数传递 NULL (而不是有效的指针) 来抑制属性级别的错误报告。 
  
如果要接收有关错误的信息, 请在_lppProblems_参数中传递有效的**SPropProblemArray**结构指针。 当**DoCopyProps**返回 S_OK 时, 检查结构中的各个属性可能存在的错误。 当**DoCopyProps**返回错误时, **SPropProblemArray**结构中不返回任何信息。 相反, 请调用[IMAPISupport:: GetLastError](imapisupport-getlasterror.md)方法以检索详细的错误消息。 
  
如果**DoCopyProps**返回 S_OK, 请通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::CopyProps](imapiprop-copyprops.md)
  
[IMAPISupport::CopyMessages](imapisupport-copymessages.md)
  
[IMAPISupport::DoCopyTo](imapisupport-docopyto.md)
  
[IMAPISupport::GetLastError](imapisupport-getlasterror.md)
  
[PidTagContainerContents 规范属性](pidtagcontainercontents-canonical-property.md)
  
[PidTagContainerHierarchy 规范属性](pidtagcontainerhierarchy-canonical-property.md)
  
[PidTagFolderAssociatedContents 规范属性](pidtagfolderassociatedcontents-canonical-property.md)
  
[PidTagMessageAttachments 规范属性](pidtagmessageattachments-canonical-property.md)
  
[PidTagMessageRecipients 规范属性](pidtagmessagerecipients-canonical-property.md)
  
[SPropProblemArray](spropproblemarray.md)
  
[SPropTagArray](sproptagarray.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

