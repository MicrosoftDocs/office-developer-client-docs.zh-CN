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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388579"
---
# <a name="imapipropcopyto"></a>IMAPIProp::CopyTo

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
复制或移动的所有属性，特别是排除属性除外。
  
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
  
> [in]复制或移动属性时要排除的接口的计数。
    
 _rgiidExclude_
  
> [in]指定接口的补充信息是复制或移动到目标对象时不应使用的接口标识符 (Iid) 的数组。
    
 _lpExcludeProps_
  
> [in]指向属性标记数组，标识属性标记的应排除从副本或移动操作的指针。 _LpExcludeProps_参数中传递**null**指示所有对象的属性应该可以复制或移动。 **CopyTo**返回 MAPI_E_INVALID_PARAMETER [SPropProblemArray](spropproblemarray.md)结构的**cValues**成员所指的_lpExcludeProps_时设置为 0。 
    
 _ulUIParam_
  
> [in]进度指示器的父窗口句柄。 
    
 _lpProgress_
  
> [in]指向进度指示器实现的指针。 如果_lpProgress_参数中传递**null** ，MAPI 提供进度实现。 除非 MAPI_DIALOG 标志设置_ulFlags_参数中，将忽略该_lpProgress_参数。 
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问_lpDestObj_参数指向的对象的接口的指针。 _LpInterface_参数不为**null**。
    
 _lpDestObj_
  
> [in]指向要接收复制或移动属性的对象的指针。
    
 _ulFlags_
  
> [in]位掩码的标志，用于控制复制或移动操作。 可以设置以下标志：
    
MAPI_DECLINE_OK 
  
> 如果**CopyTo**调用[IMAPISupport::DoCopyTo](imapisupport-docopyto.md)方法来处理复制或移动操作，则应改为错误值 MAPI_E_DECLINE_COPY 立即返回。 MAPI 设置 MAPI_DECLINE_OK 标志来限制递归。 客户端未设置此标志。 
    
MAPI_DIALOG 
  
> 显示进度指示器。
    
MAPI_MOVE 
  
> **CopyTo**应执行移动操作而不是复制操作。 当未设置此标志时， **CopyTo**执行复制操作。 
    
MAPI_NOREPLACE 
  
> 不应覆盖目标对象中的现有属性。 如果未设置此标志， **CopyTo**会覆盖现有属性。 
    
 _lppProblems_
  
> [传入、 传出]在输入时，为**SPropProblemArray**结构; 指针的指针否则为**为 null**，指示不需要错误信息。 如果_lppProblems_上输入的有效指针， **CopyTo**中复制一个或多个属性返回有关错误的详细的信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 属性已成功复制或移动。
    
MAPI_E_COLLISION 
  
> 不能复制的子对象，因为具有相同的子对象的显示名称 — **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性指定 — 对目标对象中已存在。 
    
MAPI_E_DECLINE_COPY 
  
> 服务提供商不实现复制操作。
    
MAPI_E_FOLDER_CYCLE 
  
> 直接或间接执行复制或移动操作的源对象包含的目标对象。 重要工作可能已执行之前已发现这种情况，所以可能部分修改的源和目标对象。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 由目标对象不支持_lpInterface_参数标识的接口。 
    
MAPI_E_NO_ACCESS 
  
> 尝试访问其呼叫者没有足够的权限的对象。 如果目标对象是对源对象相同，则返回此错误。
    
可以为**CopyTo**中返回在**SPropProblemArray**结构中，但不是返回值是以下值。 对单个属性应用以下错误：
  
MAPI_E_BAD_CHARWIDTH 
  
> 可以设置该 MAPI_UNICODE 标记**CopyTo**不支持 Unicode，或未设置 MAPI_UNICODE 和**CopyTo**支持仅 Unicode。 
    
MAPI_E_COMPUTED 
  
> 该属性不能修改呼叫者，因为它是只读属性，计算目标对象的所有者。 此错误不是严重性。呼叫者应允许复制操作继续。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不需要呼叫者的类型。
    
## <a name="remarks"></a>说明

默认情况下， **IMAPIProp::CopyTo**方法复制或移动的所有当前对象的属性对目标对象。 **CopyTo**应复制或移动完全，与所有或其属性保持不变的大多数对象时使用。 
  
自动包括在操作对源对象中的任何子对象复制或移动全部。 默认情况下， **CopyTo**会覆盖目标对象的匹配从源对象的属性的任何属性。 如果任一复制或移动属性已经存在于目标对象，除非 MAPI_NOREPLACE 标志设置_ulFlags_参数中通过新的属性，来覆盖现有属性。 保持不变，不会被覆盖的目标对象中的现有信息。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您可以提供**CopyTo**完全实现或依赖 MAPI 提供其支持对象中的实现。 如果您想要使用的 MAPI 实现，调用**IMAPISupport::DoCopyTo**。 但是，如果您执行委派到**DoCopyTo**处理和传递 MAPI_DECLINE_OK 标志，避免支持呼叫并改为返回 MAPI_E_DECLINE_COPY。 MAPI 将使用此标志以避免可能递归复制文件夹时可能发生调用。 
  
因为复制操作可能很长，您应显示进度指示器。 如果存在，请使用_lpProgress_参数中传递的[IMAPIProgress](imapiprogressiunknown.md)实现。 如果_lpProgress_为**null**，调用[IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)方法使用 MAPI 实现。 
  
请务尝试对目标对象; 中设置任何已知的只读属性改为返回 MAPI_E_NO_ACCESS。
  
源和目标对象应使用相同的接口。 如果未设置_lpInterface_ ，返回 MAPI_E_INVALID_PARAMETER。 
  
如果排除所有已知的接口，则返回 MAPI_E_INTERFACE_NOT_SUPPORTED。
  
## <a name="notes-to-callers"></a>给调用方的说明

不设置 MAPI_DECLINE_OK 标志;MAPI 使用它在其呼叫消息存储提供程序**CopyTo**实现。 
  
因为复制和移动操作可能需要花费时间，您应通过设置 MAPI_DIALOG 标志请求的进度指示器显示。 您可以将_lpProgress_参数设置的**IMAPIProgress**，如果您没有实现或**null**。 如果_lpProgress_为**null**， **CopyTo**将使用 MAPI 提供默认进度指示器。 
  
您可以通过不设置 MAPI_DIALOG 标志来禁止显示进度指示器。 **CopyTo**将忽略的_ulUIParam_和_lpProgress_参数，将不会显示该标记。 
  
 **CopyTo**可以报告全局和单个错误，或者与一个或多个属性发生的错误。 这些单个错误被放在**SPropProblemArray**结构中。 您可以隐藏错误属性级别通过传递**null**，而不是有效的指针，property 问题数组结构参数的报告。 
  
如果您想要接收有关错误的信息，请在_lppProblems_参数中传递一个有效的**SPropProblemArray**结构指针。 时**CopyTo** ，则返回 S_OK，检查与结构中的各个属性的可能错误。 当**CopyTo**返回错误时， **SPropProblemArray**结构中不返回任何信息。 相反，调用[IMAPIProp::GetLastError](imapiprop-getlasterror.md)检索详细的错误信息。 
  
如果**CopyTo** ，则返回 S_OK，通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。 
  
如果您要复制对源对象类型是唯一的属性，您必须确保对目标对象类型相同。 **CopyTo**不阻止您关联通常属于一种类型的对象与其他类型的对象的属性。 由您要复制对目标对象有意义的属性。 例如，不应将消息属性复制到通讯簿容器。 
  
若要确保您复制之间的相同类型的对象，检查源和目标对象相同的类型，通过比较对象指针或调用[IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)。 设置所指的源对象的标准接口_lpInterface_接口标识符。 另外，确保**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性的对象类型是相同的两个对象。 例如，如果复制从一条消息，则可设置为 IID_IMessage 和**PR_OBJECT_TYPE** MAPI_MESSAGE 这两个对象的_lpInterface_ 。 
  
如果_lpDestObj_参数中传递了无效的指针，则结果将无法预料。 
  
排除属性**CopyTo**呼叫会很有用。 例如，某些对象具有特定于该对象，如的日期和时间的邮件传递的单个实例的属性。 若要避免复制邮件的传递时间时将邮件复制到另一个文件夹，指定属性标记排除数组中的**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))。 若要排除邮件的收件人列表，请向排除数组添加**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。 若要排除邮件的附件，添加到数组**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。
  
同样，以阻止复制或移动的文件夹或通讯簿容器层次结构或内容表包括**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 的属性中标记排除数组。
  
若要从副本排除属性或移动操作，其属性标记中包含的_lpExcludeProps_参数。 如果传递**PROP_TAG**宏生成从一个特定的标识符，该属性标记数组中的属性标记的结果，与该标识符的所有属性都将被都排除。 例如，属性标记数组中的以下条目 0x8002 排除，无论类型的标识符的原因是了所有属性： 
  
 `PROP_TAG(PT_LONG, 0x8002)`
  
不能**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 属性标记包含_lpExcludeProps_数组中。 
  
排除接口的**CopyTo**功能的用途是可能不明显，排除属性的有效性。 复制到不知道的一组属性对象时，您可以排除接口。 例如，如果将属性从文件夹复制到附件中时，附件可以使用的唯一属性将是具有任何[IMAPIProp](imapipropiunknown.md)实现的泛型属性。 通过复制操作从排除[IMAPIFolder](imapifolderimapicontainer.md) ，附件不会收到任何更具体的文件夹属性。 
  
当_rgiidExclude_参数用于排除一个接口时，它还不包括所有接口派生自的接口。 例如，不包括[IMAPIContainer](imapicontainerimapiprop.md)使文件夹或通讯簿容器排除，具体取决于提供程序的类型。 因为太多接口从它们派生，不要排除**IMAPIProp**或[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) 。 
  
忽略 MAPI_E_COMPUTED _lppProblems_参数中**SPropProblemArray**结构中返回的错误。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|File.cpp  <br/> |LoadFromMSG  <br/> |MFCMAPI 使用**IMAPIProp::CopyTo**方法将属性从.msg 文件复制到[IMAPIMessageSite](imapimessagesiteiunknown.md)对象。  <br/> |
|FolderDlg.cpp  <br/> |CFolderDlg::HandlePaste  <br/> |MFCMAPI 使用**IMAPIProp::CopyTo**方法将属性复制源邮件到目标邮件在粘贴操作过程。  <br/> |
   
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

