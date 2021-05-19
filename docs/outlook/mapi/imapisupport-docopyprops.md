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
  
> [in]指向接口标识符的指针 (IID) 表示用于访问包含要复制或移动的属性的对象的接口。
    
 _lpSrcObj_
  
> [in]指向包含要复制或移动的属性的对象的指针。
    
 _lpIncludeProps_
  
> [in]指向 [SPropTagArray](sproptagarray.md) 结构的指针，其中包含指示要复制或移动的属性标记的计数数组。 _lpIncludeProps_ 参数不能为 NULL。 
    
 _ulUIParam_
  
> [in]进度指示器的父窗口的句柄。
    
 _lpProgress_
  
> [in]指向进度指示器的实现指针。 如果在  _lpProgress_ 参数中传递 NULL，则使用 MAPI 实现显示进度指示器。 除非在 _ulFlags_ 参数中设置了 MAPI_DIALOG 标志，否则将忽略 _lpProgress_ 参数。 
    
 _lpDestInterface_
  
> [in]指向接口标识符的指针，该标识符表示用于访问对象以接收复制或移动的属性的接口。
    
 _lpDestObj_
  
> [in]指向接收复制或移动的属性的对象的指针。
    
 _ulFlags_
  
> [in]控制复制或移动操作执行方式的标志的位掩码。 可以设置以下标志：
    
MAPI_DIALOG 
  
> 显示进度指示器。
    
MAPI_MOVE 
  
> **DoCopyProps** 应执行移动操作，而不是复制操作。 未设置此标志时 **，DoCopyProps** 将执行复制操作。 
    
MAPI_NOREPLACE 
  
> 不应覆盖目标对象中的现有属性。 未设置此标志时 **，DoCopyProps** 将覆盖现有属性。 
    
 _lppProblems_
  
> [in， out]在输入时，指向指向 [SPropProblemArray 结构的指针的](spropproblemarray.md) 指针;否则为 NULL，表示不需要错误信息。 如果  _lppProblems_ 是输入的有效指针， **则 DoCopyProps** 将返回有关复制一个或多个属性时错误的详细信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动属性。
    
MAPI_E_COLLISION 
  
> 要复制或移动的属性在目标对象中已存在，MAPI_NOREPLACE标记。 
    
MAPI_E_FOLDER_CYCLE 
  
> 源对象直接或间接包含目标对象。 在发现此条件之前，可能执行了大量工作，因此可能会部分修改源对象和目标对象。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 源对象不支持由  _lpSrcInterface_ 参数标识的接口，或者目标对象不支持  _由 lpDestInterface_ 参数标识的接口。 
    
MAPI_E_NO_ACCESS 
  
> 试图访问调用方权限不足的对象。 如果目标对象与源对象相同，则返回此错误。
    
以下值可以在 **SPropProblemArray** 结构中返回，但不能作为 **DoCopyProps 的返回值**。 这些错误适用于单个属性。
  
MAPI_E_BAD_CHARWIDTH 
  
> 设置MAPI_UNICODE **DoCopyProps** 不支持 Unicode，或者未MAPI_UNICODE **DoCopyProps** 仅支持 Unicode。 
    
MAPI_E_COMPUTED 
  
> 调用方无法修改该属性，因为它是一个只读属性，由目标对象的所有者计算。 此错误并不严重;调用方应允许复制操作继续。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不是调用方预期的类型。
    
## <a name="remarks"></a>备注

**IMAPISupport：:D oCopyProps** 方法为邮件存储提供程序支持对象实现。 邮件存储提供程序可以调用 **DoCopyProps** 来实现其文件夹和消息的 [IMAPIProp：：CopyProps](imapiprop-copyprops.md) 方法。 **DoCopyProps** 复制或移动由  _lpIncludeProps_ 指向的属性标记数组中标识的属性，以及存在于  _lpSrcObj_ 指向的对象中的属性。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在相同类型的对象（如两条消息）之间复制属性时  _，lpSrcInterface_ 和  _lpDestInterface_ 参数必须包含相同的接口标识符，  _并且 lpSrcObj_ 和  _lpDestObj_ 参数必须指向相同类型的对象。 如果  _lpDestInterface_ 设置为 NULL， **则 DoCopyProps** MAPI_E_INVALID_PARAMETER。 如果将  _lpDestInterface_ 设置为可接受的接口标识符，但将  _lpDestObj_ 设置为无效指针，则结果不可预测。 你的提供程序很可能失败。 
  
如果MAPI_NOREPLACE对象中任何属性都将被覆盖，则设置该标志。 不会删除或修改目标对象中存在于源对象中且未覆盖的属性。
  
若要复制邮件的收件人列表，在 _lpIncludeProps_ 参数指向的属性标记数组中包括 **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。 若要复制邮件的附件，请包含 PR_MESSAGE_ATTACHMENTS  ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。 
  
若要复制文件夹或通讯簿容器的层次结构或内容表，在属性标记数组中包括 **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或 **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 。 若要包含文件夹的关联内容表，PR_FOLDER_ASSOCIATED_CONTENTS ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。 
  
如果复制或移动子文件夹，则无论 **使用 SPropTagArray** 结构指示的属性如何，其内容都将完整复制或移动。 
  
 **DoCopyProps** 报告作为一个整体操作发生的全局错误，以及一个或多个属性发生的单个错误。 这些单个错误将放入 **SPropProblemArray** 结构中。 可以通过为属性问题数组结构参数传递 NULL（而不是有效指针）来禁止在属性级别报告错误。 
  
如果要接收有关错误的信息，请传递 _lppProblems_ 参数中的有效 **SPropProblemArray** 结构指针。 当 **DoCopyProps** 返回S_OK时，请检查结构中各个属性的可能错误。 当 **DoCopyProps** 返回错误时 **，SPropProblemArray** 结构中不会返回任何信息。 相反，请调用 [IMAPISupport：：GetLastError](imapisupport-getlasterror.md) 方法来检索详细的错误信息。 
  
如果 **DoCopyProps** S_OK，请通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的 **SPropProblemArray** 结构。 
  
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

