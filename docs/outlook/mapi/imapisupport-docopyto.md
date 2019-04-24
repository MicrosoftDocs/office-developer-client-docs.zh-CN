---
title: IMAPISupportDoCopyTo
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.DoCopyTo
api_type:
- COM
ms.assetid: 84019475-5176-4fc5-a3ee-871095077498
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6f6c802f1d5ead1750c05fafc54533487fe3732a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331806"
---
# <a name="imapisupportdocopyto"></a>IMAPISupport::DoCopyTo

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将一个对象的所有属性 (特别排除的属性除外) 复制或移动到另一个对象。
  
```cpp
HRESULT DoCopyTo(
  LPCIID lpSrcInterface,
  LPVOID lpSrcObj,
  ULONG ciidExclude,
  LPCIID rgiidExclude,
  LPSPropTagArray lpExcludeProps,
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
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示用于访问具有要复制或移动的属性的对象的接口。
    
 _lpSrcObj_
  
> 实时指向对象的指针, 该对象具有要复制或移动的属性。
    
 _ciidExclude_
  
> 实时复制或移动属性时要排除的接口数。
    
 _rgiidExclude_
  
> 实时接口标识符的数组, 指示在将补充信息复制或移动到目标对象时不应使用的接口。
    
 _lpExcludeProps_
  
> 实时一个指向属性标记数组的指针, 该数组标识应从复制或移动操作中排除的属性标记。 在_lpExcludeProps_参数中传递 NULL 表示应复制或移动对象的所有属性。 当_lpExcludeProps_指向的[SPropTagArray](sproptagarray.md)结构的**cValues**成员设置为0时, **DoCopyTo**将返回 MAPI_E_INVALID_PARAMETER。 
    
 _ulUIParam_
  
> 实时进度指示器的父窗口的句柄。 
    
 _lpProgress_
  
> 实时指向进度指示器实现的指针。 如果在_lpProgress_参数中传递 NULL, MAPI 将提供进度实现。 除非在_ulFlags_参数中设置了 MAPI_DIALOG 标志, 否则将忽略_lpProgress_参数。 
    
 _lpDestInterface_
  
> 实时指向接口标识符的指针, 该标识符表示用于访问要接收复制或移动的属性的对象的接口。
    
 _lpDestObj_
  
> 实时指向接收复制或移动的属性的对象的指针。
    
 _ulFlags_
  
> 实时用于控制复制或移动操作的标志的位掩码。 可以设置以下标志:
    
MAPI_DIALOG 
  
> 显示进度指示器。 
    
MAPI_MOVE 
  
> **DoCopyTo**应执行移动操作, 而不是复制操作。 如果未设置此标志, **DoCopyTo**将执行复制操作。 
    
MAPI_NOREPLACE 
  
> 不应覆盖目标对象中的现有属性。 如果未设置此标志, **DoCopyTo**将覆盖现有属性。 
    
 _lppProblems_
  
> 排除在输入时, 指向指向[SPropProblemArray](spropproblemarray.md)结构的指针的指针;否则为 NULL, 表示无需提供错误信息。 如果_lppProblems_是有效的输入指针, **DoCopyTo**将返回有关复制一个或多个属性中的错误的详细信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动属性。
    
MAPI_E_COLLISION 
  
> 要复制或移动的属性已存在于 destination 对象中, 并且设置了 MAPI_NOREPLACE 标志。 
    
MAPI_E_FOLDER_CYCLE 
  
> 源对象直接或间接包含目标对象。 在发现此条件之前, 可能已经执行了大量的工作, 因此源和目标对象可能被部分修改。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 由_lpSrcObj_指向的对象不支持由_lpSrcInterface_参数标识的接口, 或者由 lpDestObj 指向的对象不支持由_lpDestInterface_参数标识的接口。 __. 
    
MAPI_E_NO_ACCESS 
  
> 试图访问呼叫者没有足够权限的对象。 如果目标对象与源对象相同, 则返回此错误。
    
MAPI_E_INVALID_PARAMETER 
  
> _lpSrcInterface_参数为 NULL。 
    
以下值可在**SPropProblemArray**结构中返回, 但不能在**DoCopyTo**的返回值中返回。 这些错误适用于单个属性。
  
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 并且**DoCopyTo**不支持 unicode, 或者未设置 MAPI_UNICODE, 且**DoCopyTo**仅支持 UNICODE。 
    
MAPI_E_COMPUTED 
  
> 调用程序无法修改该属性, 因为它是由目标对象的所有者计算的只读属性。 此错误不严重;呼叫者应允许复制操作继续进行。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不是调用方预期的类型。
    
## <a name="remarks"></a>注解

**IMAPISupport::D ocopyto**方法是为邮件存储提供程序支持对象而实现的。 邮件存储提供程序可以调用**DoCopyTo**以实现其文件夹和邮件的[IMAPIProp:: CopyTo](imapiprop-copyto.md)方法。 
  
默认情况下, **DoCopyTo**会将一个对象的所有属性复制或移动到另一个对象。 源对象中的任何子对象将自动包含在操作中并复制或移动到整个对象中。 
  
如果目标对象中已存在任何复制或移动的属性, 则新属性将覆盖现有属性, 除非在_ulFlags_参数中设置 MAPI_NOREPLACE 标志。 不会覆盖的目标对象中的现有信息将保持不变。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要从复制或移动操作中排除属性, 请将其属性标记包含在_lpExcludeProps_参数中。 如果您将使用[PROP_TAG](prop_tag.md)宏生成属性标记的结果从属性标记数组中的特定标识符中传递, 则将排除具有该标识符的所有属性。 例如, 属性标记数组中的以下条目将导致排除标识符为0x8002 的所有属性, 而不考虑类型: 
  
 `PROP_TAG(PT_LONG, 0x8002)`
  
若要避免在将邮件复制到其他文件夹时复制邮件的传递时间, 请在属性标记 exclude 数组中指定**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))。 若要排除邮件的收件人列表, 请将**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性添加到排除数组中。 若要排除邮件的附件, 请将**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性添加到数组中。
  
同样, 若要阻止复制或移动文件夹或通讯簿容器的层次结构或内容表, 请包含**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 在属性标记排除数组中。
  
忽略在_lppProblems_参数的**SPropProblemArray**结构中返回的 MAPI_E_COMPUTED 错误。 
  
_lpSrcInterface_指向的接口标识符通常与_lpDestInterface_指向的接口标识符相同。 
  
如果在_lpDestInterface_中传递可接受的接口标识符, 但_lpDestObj_中的指针无效, 则结果是不可预知的。 这很可能会导致提供程序失败。 
  
相反, 如果您知道不应复制或移动的补充信息, 请添加要在_rgiidExclude_参数中传递的数组中排除的接口的接口标识符。 例如, 如果要复制邮件, 而不是任何邮件附件, 则在_rgiidExclude_数组中传递 IID_IMessage。 **DoCopyTo**将忽略不识别的_rgiidExclude_中列出的任何接口。 
  
当您使用_rgiidExclude_参数来排除某个接口时, 它还会排除从该接口派生的所有接口。 例如, 排除[IMAPIContainer](imapicontainerimapiprop.md)接口会导致文件夹或通讯簿容器被排除, 具体取决于提供程序的类型。 请勿排除[IMAPIProp](imapipropiunknown.md)或[IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) , 因为如此多的接口派生自它们。 
  
 **DoCopyTo**报告全局错误, 这些错误应用于整体上的操作, 以及应用于各个属性的单个错误。 这些单独的错误放在**SPropProblemArray**结构中。 您可以通过为属性问题数组结构参数传递 NULL (而不是有效的指针) 来抑制属性级别的错误报告。 
  
如果要接收有关错误的信息, 请在_lppProblems_参数中传递有效的**SPropProblemArray**结构指针。 当**DoCopyTo**返回 S_OK 时, 检查结构中的各个属性可能存在的错误。 当**DoCopyTo**返回错误时, **SPropProblemArray**结构中不返回任何信息。 相反, 请调用[IMAPISupport:: GetLastError](imapisupport-getlasterror.md)方法以检索详细的错误消息。 
  
如果**DoCopyTo**返回 S_OK, 请通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。 
  
如果在**DoCopyTo**调用上发生全局错误, 请勿使用或释放**SPropProblemArray**结构。 提供程序应忽略**DoCopyTo**返回的**SPropProblemArray**结构中的_ulIndex_成员。
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::CopyTo](imapiprop-copyto.md)
  
[IMAPISupport::CopyFolder](imapisupport-copyfolder.md)
  
[IMAPISupport::CopyMessages](imapisupport-copymessages.md)
  
[IMAPISupport::GetLastError](imapisupport-getlasterror.md)
  
[PidTagContainerContents 规范属性](pidtagcontainercontents-canonical-property.md)
  
[PidTagContainerHierarchy 规范属性](pidtagcontainerhierarchy-canonical-property.md)
  
[PidTagMessageAttachments 规范属性](pidtagmessageattachments-canonical-property.md)
  
[PidTagMessageDeliveryTime 规范属性](pidtagmessagedeliverytime-canonical-property.md)
  
[PidTagMessageRecipients 规范属性](pidtagmessagerecipients-canonical-property.md)
  
[SPropProblemArray](spropproblemarray.md)
  
[SPropTagArray](sproptagarray.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

