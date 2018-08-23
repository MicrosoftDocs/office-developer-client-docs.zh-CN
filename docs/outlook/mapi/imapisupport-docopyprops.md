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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a30a323874c847d9a08b00512cfd30ff3cf5c5ff
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591126"
---
# <a name="imapisupportdocopyprops"></a>IMAPISupport::DoCopyProps

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
复制或移动到另一个对象的一个或多个对象的属性。
  
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
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问对象的属性复制或移动的接口的指针。
    
 _lpSrcObj_
  
> [in]指向包含属性复制或移动的对象的指针。
    
 _lpIncludeProps_
  
> [in]指向[SPropTagArray](sproptagarray.md)结构，其中包含指示要复制或移动的属性的属性标记的计数的阵列的指针。 _LpIncludeProps_参数不能为 NULL。 
    
 _ulUIParam_
  
> [in]进度指示器的父窗口句柄。
    
 _lpProgress_
  
> [in]一个指向进度指示器的实现。 如果_lpProgress_参数中传递 NULL，则是通过使用 MAPI 实现显示进度指示器。 除非 MAPI_DIALOG 标志设置_ulFlags_参数中，将忽略该_lpProgress_参数。 
    
 _lpDestInterface_
  
> [in]指向接口标识符值，该值代表要用于访问对象，以接收属性的复制或移动的接口的指针。
    
 _lpDestObj_
  
> [in]指向要接收复制或移动属性的对象的指针。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何执行复制或移动操作。 可以设置以下标志：
    
MAPI_DIALOG 
  
> 显示进度指示器。
    
MAPI_MOVE 
  
> **DoCopyProps**应执行移动操作而不是复制操作。 当未设置此标志时， **DoCopyProps**执行复制操作。 
    
MAPI_NOREPLACE 
  
> 不应覆盖目标对象中的现有属性。 如果未设置此标志， **DoCopyProps**会覆盖现有属性。 
    
 _lppProblems_
  
> [传入、 传出]在输入时，为[SPropProblemArray](spropproblemarray.md)结构; 指针的指针否则，为 NULL，表示不需要错误信息。 如果_lppProblems_上输入, 的有效指针**DoCopyProps**中复制一个或多个属性返回有关错误的详细的信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 属性已成功复制或移动。
    
MAPI_E_COLLISION 
  
> 对目标对象中存在要复制或已移动的属性并且设置 MAPI_NOREPLACE 标志。 
    
MAPI_E_FOLDER_CYCLE 
  
> 源对象直接或间接包含对目标对象。 重要工作可能已执行之前已发现这种情况，所以可能部分修改的源和目标对象。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> _LpSrcInterface_参数标识的接口不支持的源对象，或对目标对象不支持_lpDestInterface_参数标识的接口。 
    
MAPI_E_NO_ACCESS 
  
> 尝试访问其呼叫者没有足够的权限的对象。 如果目标对象是对源对象相同，则返回此错误。
    
可以为**DoCopyProps**中返回在**SPropProblemArray**结构中，但不是返回值是以下值。 这些错误应用于单个属性。
  
MAPI_E_BAD_CHARWIDTH 
  
> 可以设置该 MAPI_UNICODE 标记**DoCopyProps**不支持 Unicode，或未设置 MAPI_UNICODE 和**DoCopyProps**支持仅 Unicode。 
    
MAPI_E_COMPUTED 
  
> 该属性不能修改呼叫者，因为它是只读属性，计算目标对象的所有者。 此错误不是严重性。呼叫者应允许复制操作继续。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不是呼叫者预期的类型。
    
## <a name="remarks"></a>注解

消息存储提供程序支持对象的实现**IMAPISupport::DoCopyProps**方法。 消息存储提供程序可以调用**DoCopyProps**实现其文件夹和邮件的[IMAPIProp::CopyProps](imapiprop-copyprops.md)方法。 **DoCopyProps**复制或移动的属性所指的_lpIncludeProps_属性标记数组中的标识和指向_lpSrcObj_对象中当前存在。 
  
## <a name="notes-to-callers"></a>给调用方的说明

复制之间的相同的类型，两条消息，如对象的属性时的_lpSrcInterface_和_lpDestInterface_参数必须包含相同的界面标识符，以及_lpSrcObj_和_lpDestObj_参数必须指向同一类型的对象。 如果_lpDestInterface_设置为 NULL，则**DoCopyProps**返回 MAPI_E_INVALID_PARAMETER。 如果您将_lpDestInterface_设置为可接受的界面标识符，但设置_lpDestObj_到了无效的指针，结果将无法预料。 很可能将失败提供程序。 
  
如果您不希望任何目的对象将覆盖的属性，请设置 MAPI_NOREPLACE 标志。 对目标对象中的源对象中存在的且不会被覆盖的属性不被删除或修改。
  
要复制邮件的收件人列表，请_lpIncludeProps_参数指向该属性标记数组中包含的**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。 若要复制邮件的附件，包括**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。 
  
若要复制的文件夹或通讯簿容器层次结构或内容表，包括属性标记数组中的**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))。 若要包含的文件夹关联的内容表，该数组中包括**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。
  
如果复制或移动的子文件夹，及其内容复制或移动全部，无论使用了由**SPropTagArray**结构指示的属性。 
  
 **DoCopyProps**报告全局作为一个整体，操作发生的错误和各个错误出现的一个或多个属性。 这些单个错误保持**SPropProblemArray**结构中。 您可以隐藏错误属性级别通过传递 NULL，而不是有效的指针，property 问题数组结构参数的报告。 
  
如果您想要接收有关错误的信息，请在_lppProblems_参数中传递一个有效的**SPropProblemArray**结构指针。 时**DoCopyProps** ，则返回 S_OK，检查与结构中的各个属性的可能错误。 当**DoCopyProps**返回错误时， **SPropProblemArray**结构中不返回任何信息。 相反，调用[IMAPISupport::GetLastError](imapisupport-getlasterror.md)方法检索详细的错误信息。 
  
如果**DoCopyProps** ，则返回 S_OK，通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。 
  
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

