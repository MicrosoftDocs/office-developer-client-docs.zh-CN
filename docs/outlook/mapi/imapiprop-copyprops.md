---
title: IMAPIPropCopyProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.CopyProps
api_type:
- COM
ms.assetid: f65da1c8-d49b-44e8-8c66-9c53d088d334
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ee6fcaf2fa168f6be91b798efa249799f738bfa0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571078"
---
# <a name="imapipropcopyprops"></a>IMAPIProp::CopyProps

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
复制或移动所选的属性。 
  
```cpp
HRESULT CopyProps(
  LPSPropTagArray lpIncludeProps,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  LPCIID lpInterface,
  LPVOID lpDestObj,
  ULONG ulFlags,
  LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a>参数

 _lpIncludeProps_
  
> [in]一个指向属性标记数组，它指定要复制或移动的属性。 **PR_NULL**不能包含数组 ([PidTagNull](pidtagnull-canonical-property.md))。 _LpIncludeProps_参数不能为**null**。
    
 _ulUIParam_
  
> [in]进度指示器的父窗口句柄。 
    
 _lpProgress_
  
> [in]一个指向进度指示器的实现。 如果_lpProgress_参数中传递**null** ，是通过使用 MAPI 实现显示进度指示器。 除非 MAPI_DIALOG 标志设置_ulFlags_参数中，将忽略该_lpProgress_参数。 
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 表示必须用于访问_lpDestObj_参数指向的对象的接口的指针。 _LpInterface_参数不为**null**。
    
 _lpDestObj_
  
> [in]指向要接收复制或移动属性的对象的指针。
    
 _ulFlags_
  
> [in]位掩码的标志，用于控制复制或移动操作。 可以设置以下标志：
    
MAPI_DECLINE_OK 
  
> 如果**CopyProps**调用[IMAPISupport::DoCopyProps](imapisupport-docopyprops.md)方法来处理复制或移动操作，则应改为错误值 MAPI_E_DECLINE_COPY 立即返回。 MAPI 设置 MAPI_DECLINE_OK 标志来限制递归。 客户端未设置此标志。 
    
MAPI_DIALOG 
  
> 显示进度指示器。
    
MAPI_MOVE 
  
> **CopyProps**应执行移动操作而不是复制操作。 当未设置此标志时， **CopyProps**执行复制操作。 
    
MAPI_NOREPLACE 
  
> 不应覆盖目标对象中的现有属性。 如果未设置此标志， **CopyProps**会覆盖现有属性。 
    
 _lppProblems_
  
> [传入、 传出]在输入时，为[SPropProblemArray](spropproblemarray.md)结构; 指针的指针否则为**为 null**，指示存在错误信息不需要。 如果_lppProblems_上输入, 的有效指针**CopyProps**中复制一个或多个属性返回有关错误的详细的信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 属性已成功复制或移动。
    
MAPI_E_COLLISION 
  
> 不能复制的子对象，因为目标对象中已存在具有相同的显示名称，由**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性中，定义的子对象。 
    
MAPI_E_DECLINE_COPY 
  
> 服务提供商不实现复制操作。
    
MAPI_E_FOLDER_CYCLE 
  
> 直接或间接执行复制或移动操作的源对象包含的目标对象。 重要工作可能已执行之前已发现这种情况，所以可能部分修改的源和目标对象。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 由目标对象不支持_lpInterface_参数标识的接口。 
    
MAPI_E_NO_ACCESS 
  
> 尝试访问其呼叫者没有足够的权限的对象。 如果目标对象是对源对象相同，则返回此错误。
    
可以为**CopyProps**中返回在**SPropProblemArray**结构中，但不是返回值是以下值。 这些错误应用于单个属性。
  
MAPI_E_BAD_CHARWIDTH 
  
> 可以设置该 MAPI_UNICODE 标记**CopyProps**不支持 Unicode，或未设置 MAPI_UNICODE 和**CopyProps**支持仅 Unicode。 
    
MAPI_E_COMPUTED 
  
> 该属性不能修改呼叫者，因为它是只读属性，计算目标对象的所有者。 此错误不是严重性。呼叫者应允许复制操作继续。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不需要呼叫者的类型。
    
## <a name="remarks"></a>注解

**IMAPIProp::CopyProps**方法复制，或将所选的属性从当前对象移动到目标对象。 **CopyProps**主要用于答复或转发的邮件，其中只将某些从原始邮件属性的差旅与答复或转发副本。 
  
源对象中的任何子对象自动包括在操作并复制或移动全部，无论使用了由[SPropTagArray](sproptagarray.md)结构指示的属性。 默认情况下**CopyProps**覆盖目标对象的匹配从源对象的属性的任何属性。 如果任一复制或移动属性已经存在于目标对象，除非 MAPI_NOREPLACE 标志设置_ulFlags_参数中通过新的属性，来覆盖现有属性。 保持不变，不会被覆盖的目标对象中的现有信息。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

您可以提供**CopyProps**完全实现或依赖 MAPI 提供其支持对象中的实现。 如果您想要使用的 MAPI 实现，调用**IMAPISupport::DoCopyProps**方法。 但是，如果您执行委派到**DoCopyProps**处理和传递 MAPI_DECLINE_OK 标志，避免支持呼叫并改为返回 MAPI_E_DECLINE_COPY。 您将使用此标志由调用 MAPI 以避免可能递归复制文件夹时可能发生的。 
  
因为复制操作可能很长，您应显示进度指示器。 如果存在，请使用_lpProgress_参数中传递的[IMAPIProgress](imapiprogressiunknown.md)实现。 如果_lpProgress_为**null**，调用[IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)方法使用 MAPI 实现。 
  
## <a name="notes-to-callers"></a>给调用方的说明

不设置 MAPI_DECLINE_OK 标志;它用于通过 MAPI 其呼叫消息存储提供程序**CopyProps**实现。 
  
因为复制和移动操作可能需要花费时间，则最好通过设置 MAPI_DIALOG 标志请求的进度指示器显示。 您可以将_lpProgress_参数设置的**IMAPIProgress**，如果您没有实现或**null**。 如果_lpProgress_为**null**， **CopyProps**将使用 MAPI 提供默认进度指示器。 
  
您可以通过不设置 MAPI_DIALOG 标志来禁止显示进度指示器。 **CopyProps**将忽略的_ulUIParam_和_lpProgress_参数，并避免显示指示器。 
  
 **CopyProps**可以报告全局和单个错误，或者与一个或多个属性发生的错误。 这些单个错误保持**SPropProblemArray**结构中。 您可以隐藏错误属性级别通过传递**null**，而不是有效的指针，property 问题数组结构参数的报告。 
  
如果您想要接收有关错误的信息，请在_lppProblems_参数中传递一个有效的**SPropProblemArray**结构指针。 时**CopyProps** ，则返回 S_OK，检查与结构中的各个属性的可能错误。 当**CopyProps**返回错误时， **SPropProblemArray**结构中不返回任何信息。 相反，调用[IMAPIProp::GetLastError](imapiprop-getlasterror.md)方法检索详细的错误信息。 
  
如果**CopyProps** ，则返回 S_OK，通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。 
  
如果要复制对源对象类型是唯一的属性，您必须确保目标对象属于同一类型。 **CopyProps**不阻止您关联通常属于一种类型的对象与其他类型的对象的属性。 由您要复制对目标对象有意义的属性。 例如，不应将消息属性复制到通讯簿容器。 
  
若要确保您要复制的相同类型的对象之间，检查源和目标对象相同的类型，通过比较对象指针或调用[IUnknown::QueryInterface](http://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)方法。 设置所指的源对象的标准接口_lpInterface_接口标识符。 此外，还要确保**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性的对象类型是相同的两个对象。 例如，如果您从一条消息中进行复制，则可设置为 IID_IMessage 和**PR_OBJECT_TYPE** MAPI_MESSAGE 这两个对象的_lpInterface_ 。 
  
如果_lpDestObj_参数中传递了无效的指针，则结果将无法预料。 
  
要复制邮件的收件人列表，请调用消息的**CopyProps**方法和属性标记数组中包含的**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。 若要复制邮件的附件，包括**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。 
  
要复制的文件夹或通讯簿容器层次结构或内容表，包含**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 中的属性属性标记数组。 若要包含的文件夹关联的内容表，该数组中包括**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |CopyNamedProps  <br/> |MFCMAPI 使用**IMAPIProp::CopyProps**方法将命名的属性复制到另一条消息。  <br/> |
|SingleMAPIPropListCtrl.cpp  <br/> |CSingleMAPIPropListCtrl::OnPasteProperty  <br/> |MFCMAPI 使用**IMAPIProp::CopyProps**方法粘贴已复制从另一个对象的属性。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFolder::CopyMessages](imapifolder-copymessages.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)
  
[IMAPIProp::CopyTo](imapiprop-copyto.md)
  
[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[IMAPISupport::DoCopyProps](imapisupport-docopyprops.md)
  
[IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[PidTagContainerContents 规范属性](pidtagcontainercontents-canonical-property.md)
  
[PidTagContainerHierarchy 规范属性](pidtagcontainerhierarchy-canonical-property.md)
  
[PidTagDisplayName 规范属性](pidtagdisplayname-canonical-property.md)
  
[PidTagFolderAssociatedContents 规范属性](pidtagfolderassociatedcontents-canonical-property.md)
  
[PidTagMessageAttachments 规范属性](pidtagmessageattachments-canonical-property.md)
  
[PidTagMessageRecipients 规范属性](pidtagmessagerecipients-canonical-property.md)
  
[PidTagObjectType 规范属性](pidtagobjecttype-canonical-property.md)
  
[SPropProblemArray](spropproblemarray.md)
  
[SPropTagArray](sproptagarray.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

