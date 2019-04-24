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
  
复制或移动所有属性, 但特殊排除的属性除外。
  
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
  
> 实时复制或移动属性时要排除的接口数。
    
 _rgiidExclude_
  
> 实时一个接口标识符 (IIDs) 的数组, 该数组指定在将补充信息复制或移动到目标对象时不应使用的接口。
    
 _lpExcludeProps_
  
> 实时一个指向属性标记数组的指针, 该数组标识应从复制或移动操作中排除的属性标记。 在_lpExcludeProps_参数中传递**null**表示应复制或移动对象的所有属性。 当_lpExcludeProps_指向的[SPropProblemArray](spropproblemarray.md)结构的**cValues**成员设置为0时, **CopyTo**将返回 MAPI_E_INVALID_PARAMETER。 
    
 _ulUIParam_
  
> 实时进度指示器的父窗口的句柄。 
    
 _lpProgress_
  
> 实时指向进度指示器实现的指针。 如果在_lpProgress_参数中传递**null** , MAPI 将提供进度实现。 除非在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 否则将忽略_lpProgress_参数。 
    
 _lpInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示用于访问_lpDestObj_参数所指向的对象的接口。 _lpInterface_参数不能为**null**。
    
 _lpDestObj_
  
> 实时指向接收复制或移动的属性的对象的指针。
    
 _ulFlags_
  
> 实时用于控制复制或移动操作的标志的位掩码。 可以设置以下标志:
    
MAPI_DECLINE_OK 
  
> 如果**CopyTo**调用[IMAPISupport::D ocopyto](imapisupport-docopyto.md)方法来处理复制或移动操作, 则应立即返回错误值 MAPI_E_DECLINE_COPY。 MAPI_DECLINE_OK 标志由 MAPI 设置以限制递归。 客户端不设置此标志。 
    
MAPI_DIALOG 
  
> 显示进度指示器。
    
MAPI_MOVE 
  
> **CopyTo**应执行移动操作, 而不是复制操作。 如果未设置此标志, **CopyTo**将执行复制操作。 
    
MAPI_NOREPLACE 
  
> 不应覆盖目标对象中的现有属性。 如果未设置此标志, **CopyTo**将覆盖现有属性。 
    
 _lppProblems_
  
> [in, out]在输入时, 指向指向**SPropProblemArray**结构的指针的指针;否则**为 null**, 表示无需错误信息。 如果_lppProblems_是有效的输入指针, **CopyTo**将返回有关复制一个或多个属性中的错误的详细信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动属性。
    
MAPI_E_COLLISION 
  
> 无法复制子对象, 因为目标对象中已存在具有相同显示名称 (由**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性指定) 的子对象。 
    
MAPI_E_DECLINE_COPY 
  
> 服务提供程序不实施复制操作。
    
MAPI_E_FOLDER_CYCLE 
  
> 执行复制或移动操作直接或间接包含目标对象的源对象。 在发现此条件之前, 可能已经执行了大量的工作, 因此源和目标对象可能被部分修改。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 目标对象不支持由_lpInterface_参数标识的接口。 
    
MAPI_E_NO_ACCESS 
  
> 试图访问呼叫者没有足够权限的对象。 如果目标对象与源对象相同, 则返回此错误。
    
以下值可在**SPropProblemArray**结构中返回, 但不能在**CopyTo**的返回值中返回。 以下错误适用于单个属性:
  
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 并且**copyto**不支持 unicode, 或者未设置 MAPI_UNICODE, **CopyTo**仅支持 UNICODE。 
    
MAPI_E_COMPUTED 
  
> 调用程序无法修改该属性, 因为它是由目标对象的所有者计算的只读属性。 此错误不严重;呼叫者应允许复制操作继续进行。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不是调用方预期的类型。
    
## <a name="remarks"></a>注解

默认情况下, **IMAPIProp:: CopyTo**方法将当前对象的所有属性复制或移动到目标对象。 当对象应完全复制或移动时, 使用其全部或大部分属性保持不变时使用的**CopyTo** 。 
  
源对象中的任何子对象将自动包含在操作中, 并将完全复制或移动。 默认情况下, **CopyTo**会覆盖目标对象中与源对象的属性相匹配的任何属性。 如果目标对象中已存在任何复制或移动的属性, 则新属性将覆盖现有属性, 除非在_ulFlags_参数中设置 MAPI_NOREPLACE 标志。 不会覆盖的目标对象中的现有信息将保持不变。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您可以提供**CopyTo**的完全实现, 也可以依赖 MAPI 在其支持对象中提供的实现。 如果要使用 MAPI 实现, 请调用**IMAPISupport::D ocopyto**。 但是, 如果您将处理委派给**DoCopyTo** , 并且您已传递 MAPI_DECLINE_OK 标志, 请避免支持呼叫, 而改为返回 MAPI_E_DECLINE_COPY。 MAPI 将使用此标志进行呼叫, 以避免在复制文件夹时可能发生的递归。 
  
由于复制操作可能很长, 因此应显示进度指示器。 使用在_lpProgress_参数中传递的[IMAPIProgress](imapiprogressiunknown.md)实现 (如果有的话)。 如果_lpProgress_为**null**, 则调用[IMAPISupport::D oprogressdialog](imapisupport-doprogressdialog.md)方法以使用 MAPI 实现。 
  
请勿尝试在目标对象中设置任何已知的只读属性;改为返回 MAPI_E_NO_ACCESS。
  
源和目标对象应使用相同的接口。 如果未设置_lpInterface_ , 则返回 MAPI_E_INVALID_PARAMETER。 
  
如果排除了所有已知接口, 则返回 MAPI_E_INTERFACE_NOT_SUPPORTED。
  
## <a name="notes-to-callers"></a>给调用方的说明

请勿设置 MAPI_DECLINE_OK 标志;MAPI 在其对邮件存储提供程序的**CopyTo**实现中使用它。 
  
由于复制和移动操作可能需要一些时间, 因此您应通过设置 MAPI_DIALOG 标志来请求显示进度指示器。 您可以将_lpProgress_参数设置为**IMAPIProgress**的实现, 如果有, 则设置为**null**。 如果_lpProgress_为**null**, 则**CopyTo**将使用 MAPI 提供的默认进度指示器。 
  
您可以通过不设置 MAPI_DIALOG 标志来禁止显示进度指示器。 **CopyTo**将忽略_ulUIParam_和_lpProgress_参数, 并且不会显示指示器。 
  
 **CopyTo**可以报告全局和单个错误, 或一个或多个属性发生的错误。 这些单独的错误放在**SPropProblemArray**结构中。 您可以通过为属性问题数组结构参数传递**null**(而不是有效的指针) 来抑制属性级别的错误报告。 
  
如果要接收有关错误的信息, 请在_lppProblems_参数中传递有效的**SPropProblemArray**结构指针。 当**CopyTo**返回 S_OK 时, 检查结构中的各个属性可能存在的错误。 当**CopyTo**返回错误时, 不会在**SPropProblemArray**结构中返回任何信息。 而是调用[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)检索详细的错误信息。 
  
如果**CopyTo**返回 S_OK, 请通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。 
  
如果复制源对象类型所特有的属性, 则必须确保目标对象的类型相同。 **CopyTo**不会阻止您将通常属于一种类型的对象的属性与另一种类型的对象相关联。 您将由您来复制对目标对象有意义的属性。 例如, 不应将邮件属性复制到通讯簿容器。 
  
若要确保在相同类型的对象之间进行复制, 请通过比较对象指针或调用[IUnknown:: QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)来检查源对象和目标对象是否为相同的类型。 将_lpInterface_指向的接口标识符设置为源对象的标准接口。 此外, 请确保这两个对象的对象类型或**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 属性相同。 例如, 如果从邮件中复制, 请将这两个对象的_lpInterface_设置为 IID_IMessage, 并将这两个对象的**PR_OBJECT_TYPE**设置为 MAPI_MESSAGE。 
  
如果在_lpDestObj_参数中传递无效的指针, 则结果是不可预知的。 
  
排除**CopyTo**调用中的属性可能有用。 例如, 某些对象具有特定于单个对象实例的属性, 例如邮件传递的日期和时间。 若要避免在将邮件复制到其他文件夹时复制邮件的传递时间, 请在属性标记 exclude 数组中指定**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))。 若要排除邮件的收件人列表, 请将**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性添加到排除数组中。 若要排除邮件的附件, 请将**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性添加到数组中。
  
同样, 通过包括**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或**PR_CONTAINER_CONTENTS** , 阻止复制或移动文件夹或通讯簿容器的层次结构或内容表 ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 在属性标记排除数组中。
  
若要从复制或移动操作中排除属性, 请将其属性标记包含在_lpExcludeProps_参数中。 如果将**PROP_TAG**宏的结果传递给属性标记数组中的特定标识符, 则将排除包含该标识符的所有属性。 例如, 属性标记数组中的以下条目将导致排除标识符为0x8002 的所有属性, 而不考虑类型: 
  
 `PROP_TAG(PT_LONG, 0x8002)`
  
**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 属性标记不能包含在_lpExcludeProps_数组中。 
  
用于排除接口的**CopyTo**功能的有用性可能并不像排除属性的有用性那样明显。 当您复制到不知道一组属性的对象时, 可以排除接口。 例如, 如果将文件夹中的属性复制到附件中, 则附件可以使用的属性就是可用于任何[IMAPIProp](imapipropiunknown.md)实现的通用属性。 通过从复制操作中排除[IMAPIFolder](imapifolderimapicontainer.md) , 附件将不会收到任何更具体的文件夹属性。 
  
当您使用_rgiidExclude_参数来排除某个接口时, 它还会排除从该接口派生的所有接口。 例如, 排除[IMAPIContainer](imapicontainerimapiprop.md)会导致文件夹或通讯簿容器被排除, 具体取决于提供程序的类型。 请勿排除**IMAPIProp**或[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) , 因为如此多的接口派生自它们。 
  
忽略在_lppProblems_参数的**SPropProblemArray**结构中返回的 MAPI_E_COMPUTED 错误。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|文件 .cpp  <br/> |LoadFromMSG  <br/> |MFCMAPI 使用**IMAPIProp:: CopyTo**方法将属性从 .msg 文件复制到[IMAPIMessageSite](imapimessagesiteiunknown.md)对象。  <br/> |
|FolderDlg  <br/> |CFolderDlg:: HandlePaste  <br/> |在粘贴操作过程中, MFCMAPI 使用**IMAPIProp:: CopyTo**方法将属性从源邮件复制到目标邮件。  <br/> |
   
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

