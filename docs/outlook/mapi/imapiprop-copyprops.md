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
  
复制或移动所选属性。 
  
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
  
> [in]指向指定要复制或移动的属性的属性标记数组的指针。 **PR_NULL (** [PidTagNull](pidtagnull-canonical-property.md)) 不能包含在数组中。 _lpIncludeProps_ 参数不能为 **null**。
    
 _ulUIParam_
  
> [in]进度指示器的父窗口的句柄。 
    
 _lpProgress_
  
> [in]指向进度指示器的实现指针。 如果在 _lpProgress_ 参数中传递 **null，** 则使用 MAPI 实现显示进度指示器。 除非在 _ulFlags_ 参数中设置了 MAPI_DIALOG 标志，否则将忽略 _lpProgress_ 参数。 
    
 _lpInterface_
  
> [in]指向接口标识符的指针 (IID) 表示接口，该接口必须用于访问  _lpDestObj_ 参数指向的对象。 _lpInterface_ 参数不能为 **null**。
    
 _lpDestObj_
  
> [in]指向接收复制或移动的属性的对象的指针。
    
 _ulFlags_
  
> [in]控制复制或移动操作的标志的位掩码。 可以设置以下标志：
    
MAPI_DECLINE_OK 
  
> 如果 **CopyProps** 调用 [IMAPISupport：:D oCopyProps](imapisupport-docopyprops.md) 方法来处理复制或移动操作，则它应立即返回错误值 MAPI_E_DECLINE_COPY。 MAPI MAPI_DECLINE_OK设置值以限制递归。 客户端不设置此标志。 
    
MAPI_DIALOG 
  
> 显示进度指示器。
    
MAPI_MOVE 
  
> **CopyProps** 应执行移动操作，而不是复制操作。 未设置此标志时 **，CopyProps** 将执行复制操作。 
    
MAPI_NOREPLACE 
  
> 不应覆盖目标对象中的现有属性。 未设置此标志时 **，CopyProps** 将覆盖现有属性。 
    
 _lppProblems_
  
> [in， out]在输入时，指向指向 [SPropProblemArray 结构的指针的](spropproblemarray.md) 指针;否则 **为 null**，表示不需要错误信息。 如果  _lppProblems_ 是输入的有效指针 **，CopyProps** 将返回有关复制一个或多个属性时错误的详细信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动属性。
    
MAPI_E_COLLISION 
  
> 无法复制子对象，因为目标对象中已存在由 PR_DISPLAY_NAME ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性定义的同一 **显示名称** 子对象。 
    
MAPI_E_DECLINE_COPY 
  
> 服务提供商不实现复制操作。
    
MAPI_E_FOLDER_CYCLE 
  
> 执行复制或移动操作的来源对象直接或间接包含目标对象。 在发现此条件之前，可能执行了大量工作，因此可能会部分修改源对象和目标对象。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 目标对象不支持由  _lpInterface_ 参数标识的接口。 
    
MAPI_E_NO_ACCESS 
  
> 试图访问调用方权限不足的对象。 如果目标对象与源对象相同，则返回此错误。
    
以下值可以在 **SPropProblemArray** 结构中返回，但不能作为 **CopyProps 的返回值**。 这些错误适用于单个属性。
  
MAPI_E_BAD_CHARWIDTH 
  
> 设置MAPI_UNICODE **CopyProps** 不支持 Unicode，或者未MAPI_UNICODE **CopyProps** 仅支持 Unicode。 
    
MAPI_E_COMPUTED 
  
> 调用方无法修改该属性，因为它是一个只读属性，由目标对象的所有者计算。 此错误并不严重;调用方应允许复制操作继续。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不是调用方预期的类型。
    
## <a name="remarks"></a>备注

**IMAPIProp：：CopyProps** 方法将所选属性从当前对象复制或移动到目标对象。 **CopyProps** 主要用于答复和转发邮件，其中只有原始邮件中的一些属性与回复或转发副本一起传输。 
  
无论 [使用 SPropTagArray](sproptagarray.md) 结构指示的属性，源对象中任何子对象都将自动包含在操作中，并复制或移动整个子对象。 默认情况下 **，CopyProps** 覆盖目标对象中与源对象中的属性匹配的任何属性。 如果目标对象中已存在任何复制或移动的属性，则现有属性将被新属性覆盖，除非在  _ulFlags_ 参数中设置了 MAPI_NOREPLACE 标志。 目标对象中未覆盖的现有信息保持不变。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

你可以提供 **CopyProps 的完整实现或** 依赖于 MAPI 在其支持对象中提供的实现。 如果要使用 MAPI 实现，请调用 **IMAPISupport：:D oCopyProps** 方法。 但是，如果您将处理委派给 **DoCopyProps，** 并且您被传递到 MAPI_DECLINE_OK 标志，请避免支持调用并返回MAPI_E_DECLINE_COPY。 MAPI 将用此标志调用你，以避免复制文件夹时可能发生的递归。 
  
由于复制操作可能很长，因此应显示进度指示器。 使用在 lpProgress 参数中传递的[IMAPIProgress](imapiprogressiunknown.md)实现（如果有）。  如果  _lpProgress_ 为 **null，** 则调用 [IMAPISupport：:D oProgressDialog](imapisupport-doprogressdialog.md) 方法以使用 MAPI 实现。 
  
## <a name="notes-to-callers"></a>给调用方的说明

不要设置MAPI_DECLINE_OK标志;MAPI 在调用消息存储提供程序 **CopyProps** 实现时会使用它。 
  
由于复制和移动操作可能需要一些时间，因此建议通过设置进度指示器的 MAPI_DIALOG 显示。 可以将  _lpProgress_ 参数设置为 **IMAPIProgress** 的实现（如果有）或 **设置为 null**。 如果 _lpProgress_ **为 null，****则 CopyProps** 将使用 MAPI 提供的默认进度指示器。 
  
可以通过不设置进度指示器标记来禁止显示MAPI_DIALOG标记。 **CopyProps** 将忽略  _ulUIParam_ 和  _lpProgress_ 参数，并避免显示指示器。 
  
 **CopyProps** 可以报告全局和单个错误，或者一个或多个属性发生的错误。 这些单个错误将放入 **SPropProblemArray** 结构中。 可以通过为属性问题数组结构参数传递 **null（** 而不是有效指针）来禁止在属性级别报告错误。 
  
如果要接收有关错误的信息，请传递 _lppProblems_ 参数中的有效 **SPropProblemArray** 结构指针。 当 **CopyProps** 返回S_OK时，请检查结构中各个属性的可能错误。 当 **CopyProps** 返回错误时 **，SPropProblemArray** 结构中不会返回任何信息。 请改为调用 [IMAPIProp：：GetLastError](imapiprop-getlasterror.md) 方法来检索详细的错误信息。 
  
如果 **CopyProps** S_OK，请通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的 **SPropProblemArray** 结构。 
  
如果要复制源对象特有的属性对象类型，必须确保目标对象的类型相同。 **CopyProps** 不会阻止您将通常属于一种类型的对象的属性与另一种类型的对象关联。 由你复制对目标对象有意义的属性。 例如，不应将邮件属性复制到通讯簿容器。 
  
若要确保在相同类型的对象之间复制，请检查源对象和目标对象是否相同，方法是比较对象指针或调用 [IUnknown：：QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) 方法。 将  _lpInterface_ 指向的接口标识符设置为源对象的标准接口。 此外，请确保 对象类型[PidTagObjectType PR_OBJECT_TYPE (PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性相同。  例如，如果要从邮件复制，将 _lpInterface_ 设置为 IID_IMessage，PR_OBJECT_TYPE两个对象的MAPI_MESSAGE。 
  
如果在  _lpDestObj_ 参数中传递无效指针，则结果不可预测。 
  
若要复制邮件的收件人列表，请调用邮件的 **CopyProps** 方法，在属性标记数组中包括 **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。 若要复制邮件的附件，请包含 PR_MESSAGE_ATTACHMENTS  ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。 
  
若要复制文件夹或通讯簿容器的层次结构或内容表，在属性标记数组中包括 **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或 **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 属性。 若要包含文件夹的关联内容表，PR_FOLDER_ASSOCIATED_CONTENTS ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。  
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |CopyNamedProps  <br/> |MFCMAPI 使用 **IMAPIProp：：CopyProps** 方法将命名属性从一条消息复制到另一条消息。  <br/> |
|SingleMAPIPropListCtrl.cpp  <br/> |CSingleMAPIPropListCtrl：：OnPasteProperty  <br/> |MFCMAPI 使用 **IMAPIProp：：CopyProps** 方法粘贴从另一个对象复制的属性。  <br/> |
   
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

