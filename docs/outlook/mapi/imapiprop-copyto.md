---
title: IMAPIPropCopyTo
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.CopyTo
api_type:
- COM
ms.assetid: e56042e9-5bb7-4a99-b6de-1546d4ca07f0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f76b0a5482647fe3e181a36d7dcd8cb60ffc8985
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356390"
---
# <a name="imapipropcopyto"></a>IMAPIProp::CopyTo

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
复制或移动所有属性，但专门排除的属性除外。
  
```cpp
HRESULT CopyTo(
 ULONG ciidExclude,
 LPCIID rgiidExclude,
 LPSPropTagArray lpExcludeProps,
 ULONG_PTR ulUIParam,
 LPMAPIPROGRESS lpProgress,
 LPCIID lpInterface,
 LPVOID lpDestObj,
 ULONG ulFlags,
 LPSPropProblemArray FAR * lppProblems
);
```

## <a name="parameters"></a>参数

 _ciidExclude_
  
> [in]复制或移动属性时要排除的接口计数。
    
 _rgiidExclude_
  
> [in]一组接口标识符 (IID) ，用于指定在将补充信息复制或移动到目标对象时不应使用的接口。
    
 _lpExcludeProps_
  
> [in]指向属性标记数组的指针，该数组标识应从复制或移动操作中排除的属性标记。 在 _lpExcludeProps_ 参数中传递 **null** 指示应复制或移动对象的所有属性。 **CopyTo** MAPI_E_INVALID_PARAMETER _lpExcludeProps_ 指向 [的 SPropProblemArray](spropproblemarray.md)结构的 **cValues** 成员设置为 0 时返回值。 
    
 _ulUIParam_
  
> [in]进度指示器的父窗口的句柄。 
    
 _lpProgress_
  
> [in]指向进度指示器实现的指针。 如果在 _lpProgress_ 参数中传递 null，MAPI 将提供进度实现。 除非在 _ulFlags_ 参数中设置了 MAPI_DIALOG 标志，否则将忽略 _lpProgress_ 参数。 
    
 _lpInterface_
  
> [in]指向接口标识符 (IID) 表示用于访问  _lpDestObj_ 参数指向的对象的接口的指针。 _lpInterface_ 参数不能为 **null**。
    
 _lpDestObj_
  
> [in]指向接收复制或移动的属性的对象的指针。
    
 _ulFlags_
  
> [in]控制复制或移动操作的标志的位掩码。 可以设置以下标志：
    
MAPI_DECLINE_OK 
  
> 如果 **CopyTo** 调用 [IMAPISupport：:D oCopyTo](imapisupport-docopyto.md) 方法来处理复制或移动操作，它应改为立即返回错误值 MAPI_E_DECLINE_COPY。 MAPI MAPI_DECLINE_OK设置值以限制递归。 客户端不设置此标志。 
    
MAPI_DIALOG 
  
> 显示进度指示器。
    
MAPI_MOVE 
  
> **CopyTo** 应执行移动操作，而不是复制操作。 未设置此标志时 **，CopyTo** 将执行复制操作。 
    
MAPI_NOREPLACE 
  
> 不应覆盖目标对象中的现有属性。 未设置此标志时 **，CopyTo** 将覆盖现有属性。 
    
 _lppProblems_
  
> [in， out]在输入时，指向指向 **SPropProblemArray 结构的指针的** 指针;否则为 **null**，表示不需要错误信息。 如果  _lppProblems_ 是输入的有效指针 **，CopyTo** 将返回有关复制一个或多个属性时错误的详细信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动属性。
    
MAPI_E_COLLISION 
  
> 无法复制子对象，因为目标对象中已存在具有同一 显示名称 的子对象（由 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性指定）。 
    
MAPI_E_DECLINE_COPY 
  
> 服务提供商不实现复制操作。
    
MAPI_E_FOLDER_CYCLE 
  
> 执行复制或移动操作的来源对象直接或间接包含目标对象。 在发现此条件之前，可能执行了大量工作，因此可能会部分修改源对象和目标对象。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 目标对象不支持由  _lpInterface_ 参数标识的接口。 
    
MAPI_E_NO_ACCESS 
  
> 试图访问调用方权限不足的对象。 如果目标对象与源对象相同，则返回此错误。
    
以下值可以在 **SPropProblemArray** 结构中返回，但不能作为 **CopyTo 的返回值**。 以下错误适用于单个属性：
  
MAPI_E_BAD_CHARWIDTH 
  
> 设置MAPI_UNICODE **CopyTo** 不支持 Unicode，或者未MAPI_UNICODE **CopyTo** 仅支持 Unicode。 
    
MAPI_E_COMPUTED 
  
> 调用方无法修改该属性，因为它是一个只读属性，由目标对象的所有者计算。 此错误并不严重;调用方应允许复制操作继续。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不是调用方预期的类型。
    
## <a name="remarks"></a>备注

默认情况下 **，IMAPIProp：：CopyTo** 方法将当前对象的所有属性复制或移动到目标对象。 **CopyTo** 用于完全复制或移动对象，其所有或大部分属性保持不变。 
  
源对象中任何子对象都将自动包含在操作中，并全部复制或移动。 默认情况下 **，CopyTo** 覆盖目标对象中与源对象中的属性匹配的任何属性。 如果目标对象中已存在任何复制或移动的属性，则现有属性将被新属性覆盖，除非在  _ulFlags_ 参数中设置了 MAPI_NOREPLACE 标志。 目标对象中未覆盖的现有信息保持不变。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

你可以提供 **CopyTo** 的完整实现或依赖于 MAPI 在其支持对象中提供的实现。 如果要使用 MAPI 实现，请调用 **IMAPISupport：:D oCopyTo**。 但是，如果您将处理委派给 **DoCopyTo，** 并且您被传递到 MAPI_DECLINE_OK 标志，请避免致电支持人员，并MAPI_E_DECLINE_COPY消息。 MAPI 将调用此标志以避免复制文件夹时可能发生的递归。 
  
由于复制操作可能很长，因此应显示进度指示器。 使用 [在 lpProgress](imapiprogressiunknown.md) 参数中传递的  _IMAPIProgress_ 实现（如果有）。 如果  _lpProgress_ 为 **null，** 则调用 [IMAPISupport：:D oProgressDialog](imapisupport-doprogressdialog.md) 方法以使用 MAPI 实现。 
  
不要尝试在目标对象中设置任何已知的只读属性;返回MAPI_E_NO_ACCESS。
  
源对象和目标对象应使用相同的接口。 如果未MAPI_E_INVALID_PARAMETER  _lpInterface，_ 则返回值。 
  
如果MAPI_E_INTERFACE_NOT_SUPPORTED所有已知接口，则返回返回值。
  
## <a name="notes-to-callers"></a>给调用方的说明

不要设置MAPI_DECLINE_OK标志;MAPI 在消息存储提供程序 CopyTo 实现调用 **中使用它** 。 
  
由于复制和移动操作可能需要一些时间，因此应该通过设置进度指示器标记来MAPI_DIALOG显示。 可以将  _lpProgress_ 参数设置为 **IMAPIProgress** 的实现（如果有）或 **设置为 null**。 如果 _lpProgress_ **为 null，****则 CopyTo** 将使用 MAPI 提供的默认进度指示器。 
  
可以通过不设置进度指示器标记来禁止显示MAPI_DIALOG标记。 **CopyTo** 将忽略  _ulUIParam_ 和  _lpProgress_ 参数，并且不显示指示器。 
  
 **CopyTo** 可以报告全局和单个错误，或者一个或多个属性发生的错误。 这些单个错误放置在 **SPropProblemArray** 结构中。 可以通过为属性问题数组结构参数传递 **null（** 而不是有效指针）来禁止在属性级别报告错误。 
  
如果要接收有关错误的信息，请传递 _lppProblems_ 参数中的有效 **SPropProblemArray** 结构指针。 当 **CopyTo** 返回S_OK时，请检查结构中各个属性的可能错误。 当 **CopyTo** 返回错误时 **，SPropProblemArray** 结构中不会返回任何信息。 相反，调用 [IMAPIProp：：GetLastError](imapiprop-getlasterror.md) 以检索详细的错误信息。 
  
如果 **CopyTo** S_OK，请通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的 **SPropProblemArray** 结构。 
  
如果复制源对象特有的属性对象类型，必须确保目标对象的类型相同。 **CopyTo** 不会阻止您将通常属于一种对象类型的属性与另一种类型的对象关联。 由你复制对目标对象有意义的属性。 例如，不应将邮件属性复制到通讯簿容器。 
  
若要确保在相同类型的对象之间复制，请检查源对象和目标对象是否相同，方法为比较对象指针或调用[IUnknown：：QueryInterface。](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) 将  _lpInterface_ 指向的接口标识符设置为源对象的标准接口。 此外，请确保 PidTagObjectType对象类型 或 PR_OBJECT_TYPE ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性是相同的。 例如，如果从邮件中复制，将 _lpInterface_ 设置为 IID_IMessage，PR_OBJECT_TYPE两个对象的 MAPI_MESSAGE。 
  
如果在  _lpDestObj_ 参数中传递无效指针，则结果不可预测。 
  
在 **CopyTo 调用中排除** 属性可能很有用。 例如，某些对象具有特定于对象的单个实例的属性，如邮件传递的日期和时间。 为避免在将邮件复制到其他文件夹时复制邮件的传递时间，请指定 **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) 属性标记排除数组。 若要排除邮件的收件人列表，PR_MESSAGE_RECIPIENTS ([PidTagMessageRecipients) PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)属性添加到排除数组。  若要排除邮件的附件，PR_MESSAGE_ATTACHMENTS ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 添加到数组。 
  
同样，在属性标记排除数组中包括 **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或 **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) ，防止复制或移动文件夹或通讯簿容器的层次结构或内容表。
  
若要从复制或移动操作中排除属性，请将其属性标记包括在  _lpExcludeProps_ 参数中。 如果传递 PROP_TAG 宏的结果，以从属性标记数组中的特定标识符构建属性标记，那么将排除具有该标识符的所有属性。 例如，属性标记数组中的以下条目会导致排除标识符为 0x8002的所有属性，无论类型如何： 
  
 `PROP_TAG(PT_LONG, 0x8002)`
  
_lpExcludeProps_ PR_NULL ([PidTagNull](pidtagnull-canonical-property.md)) 属性标记中。  
  
**CopyTo** 功能用于排除接口的实用性可能没有排除属性的有用性那么明显。 当复制到一个不了解一组属性的对象时，可以排除接口。 例如，如果将属性从文件夹复制到附件，则附件可以使用的唯一属性是可用于 [任何 IMAPIProp](imapipropiunknown.md) 实现的通用属性。 通过从 [复制操作中排除 IMAPIFolder，](imapifolderimapicontainer.md) 附件将不会收到任何更具体的文件夹属性。 
  
使用  _rgiidExclude_ 参数排除接口时，它还排除从该接口派生的所有接口。 例如，排除 [IMAPIContainer](imapicontainerimapiprop.md) 会导致排除文件夹或通讯簿容器，具体取决于提供程序的类型。 不要排除 **IMAPIProp** 或 [IUnknown，](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) 因为有很多接口派生自它们。 
  
忽略MAPI_E_COMPUTED _lppProblems_ 参数 **的 SPropProblemArray** 结构中返回的错误。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|File.cpp  <br/> |LoadFromMSG  <br/> |MFCMAPI 使用 **IMAPIProp：：CopyTo** 方法将属性从 .msg 文件复制到 [IMAPIMessageSite](imapimessagesiteiunknown.md) 对象。  <br/> |
|FolderDlg.cpp  <br/> |CFolderDlg：：HandlePaste  <br/> |在粘贴操作期间，MFCMAPI 使用 **IMAPIProp：：CopyTo** 方法将属性从源邮件复制到目标邮件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFolder::CopyMessages](imapifolder-copymessages.md)
  
[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md)
  
[IMAPIProgress : IUnknown](imapiprogressiunknown.md)
  
[IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)
  
[IMAPISupport::DoCopyTo](imapisupport-docopyto.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[PidTagContainerContents 规范属性](pidtagcontainercontents-canonical-property.md)
  
[PidTagContainerHierarchy 规范属性](pidtagcontainerhierarchy-canonical-property.md)
  
[PidTagMessageAttachments 规范属性](pidtagmessageattachments-canonical-property.md)
  
[PidTagMessageDeliveryTime 规范属性](pidtagmessagedeliverytime-canonical-property.md)
  
[PidTagMessageRecipients 规范属性](pidtagmessagerecipients-canonical-property.md)
  
[PidTagObjectType 规范属性](pidtagobjecttype-canonical-property.md)
  
[SPropProblemArray](spropproblemarray.md)
  
[SPropTagArray](sproptagarray.md)
  
[IMAPIProp : IUnknown](imapipropiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

