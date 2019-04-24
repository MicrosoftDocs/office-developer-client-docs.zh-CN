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
ms.openlocfilehash: 7319f1abb4a74ee17b0a4a1220215c29434d256b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345505"
---
# <a name="imapipropcopyprops"></a>IMAPIProp::CopyProps

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
复制或移动选定的属性。 
  
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
  
> 实时指向指定要复制或移动的属性的属性标记数组的指针。 **PR_NULL**([PidTagNull](pidtagnull-canonical-property.md)) 不能包含在数组中。 _lpIncludeProps_参数不能为**null**。
    
 _ulUIParam_
  
> 实时进度指示器的父窗口的句柄。 
    
 _lpProgress_
  
> 实时指向进度指示器的实现的指针。 如果在_lpProgress_参数中传递**null** , 则将使用 MAPI 实现显示进度指示器。 除非在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 否则将忽略_lpProgress_参数。 
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示必须用于访问_lpDestObj_参数所指向的对象的接口。 _lpInterface_参数不能为**null**。
    
 _lpDestObj_
  
> 实时指向接收复制或移动的属性的对象的指针。
    
 _ulFlags_
  
> 实时用于控制复制或移动操作的标志的位掩码。 可以设置以下标志:
    
MAPI_DECLINE_OK 
  
> 如果**CopyProps**调用[IMAPISupport::D ocopyprops](imapisupport-docopyprops.md)方法来处理复制或移动操作, 则应立即返回错误值 MAPI_E_DECLINE_COPY。 MAPI_DECLINE_OK 标志由 MAPI 设置以限制递归。 客户端不设置此标志。 
    
MAPI_DIALOG 
  
> 显示进度指示器。
    
MAPI_MOVE 
  
> **CopyProps**应执行移动操作, 而不是复制操作。 如果未设置此标志, **CopyProps**将执行复制操作。 
    
MAPI_NOREPLACE 
  
> 不应覆盖目标对象中的现有属性。 如果未设置此标志, **CopyProps**将覆盖现有属性。 
    
 _lppProblems_
  
> [in, out]在输入时, 指向指向[SPropProblemArray](spropproblemarray.md)结构的指针的指针;否则**为 null**, 表示无需提供错误信息。 如果_lppProblems_是有效的输入指针, **CopyProps**将返回有关复制一个或多个属性中的错误的详细信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动属性。
    
MAPI_E_COLLISION 
  
> 无法复制子对象, 因为**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性所定义的具有相同显示名称的子对象已经存在于目标对象中。 
    
MAPI_E_DECLINE_COPY 
  
> 服务提供程序不实施复制操作。
    
MAPI_E_FOLDER_CYCLE 
  
> 执行复制或移动操作直接或间接包含目标对象的源对象。 在发现此条件之前, 可能已经执行了大量的工作, 因此源和目标对象可能被部分修改。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 目标对象不支持由_lpInterface_参数标识的接口。 
    
MAPI_E_NO_ACCESS 
  
> 试图访问呼叫者没有足够权限的对象。 如果目标对象与源对象相同, 则返回此错误。
    
以下值可在**SPropProblemArray**结构中返回, 但不能在**CopyProps**的返回值中返回。 这些错误适用于单个属性。
  
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 并且**CopyProps**不支持 unicode, 或者未设置 MAPI_UNICODE, 且**CopyProps**仅支持 UNICODE。 
    
MAPI_E_COMPUTED 
  
> 调用程序无法修改该属性, 因为它是由目标对象的所有者计算的只读属性。 此错误不严重;呼叫者应允许复制操作继续进行。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不是调用方预期的类型。
    
## <a name="remarks"></a>注解

**IMAPIProp:: CopyProps**方法将当前对象的选定属性复制或移动到目标对象。 **CopyProps**主要用于答复和转发邮件, 其中只有一些来自原始邮件的属性携带在答复或转发副本中。 
  
无论使用由[SPropTagArray](sproptagarray.md)结构指示的属性, 源对象中的任何子对象都会自动包含在操作中并复制或移动到整个中。 默认情况下, **CopyProps**会覆盖目标对象中与源对象的属性匹配的任何属性。 如果目标对象中已存在任何复制或移动的属性, 则新属性将覆盖现有属性, 除非在_ulFlags_参数中设置 MAPI_NOREPLACE 标志。 不会覆盖的目标对象中的现有信息将保持不变。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您可以提供**CopyProps**的完全实现, 也可以依赖 MAPI 在其支持对象中提供的实现。 如果要使用 MAPI 实现, 请调用**IMAPISupport::D ocopyprops**方法。 但是, 如果您将处理委派给**DoCopyProps** , 并且您已传递 MAPI_DECLINE_OK 标志, 请避免支持呼叫, 而改为返回 MAPI_E_DECLINE_COPY。 你将通过 MAPI 使用此标志调用, 以避免在复制文件夹时可能发生的递归。 
  
由于复制操作可能很长, 因此应显示进度指示器。 使用在_lpProgress_参数中传递的[IMAPIProgress](imapiprogressiunknown.md)实现 (如果有的话)。 如果_lpProgress_为**null**, 则调用[IMAPISupport::D oprogressdialog](imapisupport-doprogressdialog.md)方法以使用 MAPI 实现。 
  
## <a name="notes-to-callers"></a>给调用方的说明

请勿设置 MAPI_DECLINE_OK 标志;它由 MAPI 在其对邮件存储提供程序**CopyProps**实现的调用中使用。 
  
由于复制和移动操作可能需要一些时间, 因此最好通过设置 MAPI_DIALOG 标志来请求显示进度指示器。 您可以将_lpProgress_参数设置为**IMAPIProgress**的实现, 如果有, 则设置为**null**。 如果_lpProgress_为**null**, 则**CopyProps**将使用 MAPI 提供的默认进度指示器。 
  
您可以通过不设置 MAPI_DIALOG 标志来禁止显示进度指示器。 **CopyProps**将忽略_ulUIParam_和_lpProgress_参数, 并避免显示指示器。 
  
 **CopyProps**可以报告一个或多个属性出现的全局和各个错误。 这些单独的错误放在**SPropProblemArray**结构中。 您可以通过为属性问题数组结构参数传递**null**(而不是有效的指针) 来抑制属性级别的错误报告。 
  
如果要接收有关错误的信息, 请在_lppProblems_参数中传递有效的**SPropProblemArray**结构指针。 当**CopyProps**返回 S_OK 时, 检查结构中的各个属性可能存在的错误。 当**CopyProps**返回错误时, **SPropProblemArray**结构中不返回任何信息。 相反, 请调用[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)方法以检索详细的错误消息。 
  
如果**CopyProps**返回 S_OK, 请通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。 
  
如果要复制源对象类型所特有的属性, 则必须确保目标对象的类型相同。 **CopyProps**不会阻止您将通常属于一种类型的对象的属性与另一种类型的对象相关联。 您将由您来复制对目标对象有意义的属性。 例如, 不应将邮件属性复制到通讯簿容器。 
  
若要确保在同一类型的对象之间进行复制, 请通过比较对象指针或调用[IUnknown:: QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx)方法来检查源和目标对象的类型是否相同。 将_lpInterface_指向的接口标识符设置为源对象的标准接口。 此外, 请确保这两个对象的对象类型或**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性相同。 例如, 如果要从邮件中进行复制, 请将这两个对象的_lpInterface_设置为 IID_IMessage, 并将这两个对象的**PR_OBJECT_TYPE**设置为 MAPI_MESSAGE。 
  
如果在_lpDestObj_参数中传递无效的指针, 则结果是不可预知的。 
  
若要复制邮件的收件人列表, 请调用邮件的**CopyProps**方法, 并在属性标记数组中包含**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。 若要复制邮件的附件, 请包含**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。 
  
若要复制文件夹或通讯簿容器的层次结构或内容表, 请在**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 属性中添加属性标记数组。 若要包含文件夹的关联内容表, 请在数组中包含**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions  <br/> |CopyNamedProps  <br/> |MFCMAPI 使用**IMAPIProp:: CopyProps**方法将命名属性从一个邮件复制到另一个邮件。  <br/> |
|SingleMAPIPropListCtrl  <br/> |CSingleMAPIPropListCtrl:: OnPasteProperty  <br/> |MFCMAPI 使用**IMAPIProp:: CopyProps**方法粘贴已从另一个对象复制的属性。  <br/> |
   
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

