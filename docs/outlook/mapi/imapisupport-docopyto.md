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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1040a0730c4b26b51d3c2b7763488502b2c5323c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775623"
---
# <a name="imapisupportdocopyto"></a>IMAPISupport::DoCopyTo

  
  
**适用于**： Outlook 
  
复制或移动到另一个对象的一个对象，特别是排除的属性，除外的所有属性。
  
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
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问具有要复制或移动的属性的对象的接口的指针。
    
 _lpSrcObj_
  
> [in]指向具有要复制或移动的属性的对象的指针。
    
 _ciidExclude_
  
> [in]复制或移动属性时要排除的接口的计数。
    
 _rgiidExclude_
  
> [in]指示当您复制或移动到的目标对象的附加信息不应使用的接口的接口标识符数组。
    
 _lpExcludeProps_
  
> [in]指向属性标记数组，标识属性标记的应排除从副本或移动操作的指针。 _LpExcludeProps_参数中传递 NULL 指示所有对象的属性应该可以复制或移动。 **DoCopyTo**返回 MAPI_E_INVALID_PARAMETER [SPropTagArray](sproptagarray.md)结构的**cValues**成员所指的_lpExcludeProps_时设置为 0。 
    
 _ulUIParam_
  
> [in]进度指示器的父窗口句柄。 
    
 _lpProgress_
  
> [in]指向进度指示器实现的指针。 如果_lpProgress_参数中传递 NULL，则 MAPI 提供进度实现。 除非 MAPI_DIALOG 标志设置_ulFlags_参数中，将忽略该_lpProgress_参数。 
    
 _lpDestInterface_
  
> [in]指向接口标识符值，该值代表要用于访问对象，以接收复制或移动属性的接口的指针。
    
 _lpDestObj_
  
> [in]指向要接收复制或移动属性的对象的指针。
    
 _ulFlags_
  
> [in]位掩码的标志，用于控制复制或移动操作。 可以设置以下标志：
    
MAPI_DIALOG 
  
> 显示进度指示器。 
    
MAPI_MOVE 
  
> **DoCopyTo**应执行移动操作而不是复制操作。 当未设置此标志时， **DoCopyTo**执行复制操作。 
    
MAPI_NOREPLACE 
  
> 不应覆盖目标对象中的现有属性。 如果未设置此标志， **DoCopyTo**会覆盖现有属性。 
    
 _lppProblems_
  
> [输出]在输入时，为[SPropProblemArray](spropproblemarray.md)结构; 指针的指针否则，为 NULL，表示不需要错误信息。 如果_lppProblems_上输入, 的有效指针**DoCopyTo**中复制一个或多个属性返回有关错误的详细的信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 属性已成功复制或移动。
    
MAPI_E_COLLISION 
  
> 对目标对象中存在要复制或已移动的属性并且设置 MAPI_NOREPLACE 标志。 
    
MAPI_E_FOLDER_CYCLE 
  
> 源对象直接或间接包含对目标对象。 重要工作可能已执行之前已发现这种情况，所以可能部分修改的源和目标对象。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> 指向_lpSrcObj_，对象不支持_lpSrcInterface_参数标识的接口或指向_lpDestObj 对象不支持_lpDestInterface_参数标识的接口_. 
    
MAPI_E_NO_ACCESS 
  
> 尝试访问其呼叫者没有足够的权限的对象。 如果目标对象是对源对象相同，则返回此错误。
    
MAPI_E_INVALID_PARAMETER 
  
> _LpSrcInterface_参数为 NULL。 
    
可以为**DoCopyTo**中返回在**SPropProblemArray**结构中，但不是返回值是以下值。 这些错误应用于单个属性。
  
MAPI_E_BAD_CHARWIDTH 
  
> 可以设置该 MAPI_UNICODE 标记**DoCopyTo**不支持 Unicode，或未设置 MAPI_UNICODE 和**DoCopyTo**支持仅 Unicode。 
    
MAPI_E_COMPUTED 
  
> 该属性不能修改呼叫者，因为它是只读属性，计算目标对象的所有者。 此错误不是严重性。呼叫者应允许复制操作继续。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不需要呼叫者的类型。
    
## <a name="remarks"></a>说明

消息存储提供程序支持对象的实现**IMAPISupport::DoCopyTo**方法。 消息存储提供程序可以调用**DoCopyTo**实现其文件夹和邮件的[IMAPIProp::CopyTo](imapiprop-copyto.md)方法。 
  
默认情况下， **DoCopyTo**复制或移动到另一个对象的所有一个对象的属性。 源对象中的任何子对象自动包括在操作并复制或移动全部。 
  
如果任一复制或移动属性已经存在于目标对象，除非 MAPI_NOREPLACE 标志设置_ulFlags_参数中通过新的属性，来覆盖现有属性。 保持不变，不会被覆盖的目标对象中的现有信息。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要从副本排除属性或移动操作，其属性标记中包含的_lpExcludeProps_参数。 如果您通过使用[PROP_TAG](prop_tag.md)宏生成从一个特定的标识符，该属性标记数组中的属性标记的结果，与该标识符的所有属性都将被都排除。 例如，属性标记数组中的以下条目 0x8002 排除，无论类型的标识符的原因是了所有属性： 
  
 `PROP_TAG(PT_LONG, 0x8002)`
  
若要避免复制邮件的传递时间时将邮件复制到另一个文件夹，指定属性标记排除数组中的**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))。 若要排除邮件的收件人列表，请向排除数组添加**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。 若要排除邮件的附件，添加到数组**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 属性。
  
同样，要阻止的复制或移动的文件夹或通讯簿容器层次结构或内容表，包括**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 的属性中标记排除数组。
  
忽略 MAPI_E_COMPUTED _lppProblems_参数中**SPropProblemArray**结构中返回的错误。 
  
_LpSrcInterface_指向通常是相同的界面标识符_lpDestInterface_指向接口标识符。 
  
如果传递_lpDestInterface_中的可接受的界面标识符而_lpDestObj_中无效的指针，结果将无法预料。 很可能这将导致您的提供商失败。 
  
相反，如果您所知的补充信息的不应复制或移动，添加排除_rgiidExclude_参数中传递的数组中的接口的界面标识符。 例如，如果要复制的邮件，但不是任何其邮件附件， _rgiidExclude_数组中传递 IID_IMessage。 **DoCopyTo**忽略它无法识别的_rgiidExclude_中列出的任何接口。 
  
当_rgiidExclude_参数用于排除一个接口时，它还不包括所有接口派生自的接口。 例如，不包括[IMAPIContainer](imapicontainerimapiprop.md)界面使文件夹或通讯簿容器排除，具体取决于提供程序的类型。 因为太多接口从它们派生，不要排除[IMAPIProp](imapipropiunknown.md)或[IUnknown](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) 。 
  
 **DoCopyTo**报告应用于作为一个整体，该操作的全局错误和的各个属性应用于单个错误。 这些单个错误保持**SPropProblemArray**结构中。 您可以隐藏错误属性级别通过传递 NULL，而不是有效的指针，property 问题数组结构参数的报告。 
  
如果您想要接收有关错误的信息，请在_lppProblems_参数中传递一个有效的**SPropProblemArray**结构指针。 时**DoCopyTo** ，则返回 S_OK，检查与结构中的各个属性的可能错误。 当**DoCopyTo**返回错误时， **SPropProblemArray**结构中不返回任何信息。 相反，调用[IMAPISupport::GetLastError](imapisupport-getlasterror.md)方法检索详细的错误信息。 
  
如果**DoCopyTo** ，则返回 S_OK，通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的**SPropProblemArray**结构。 
  
如果一个全局错误出现**DoCopyTo**呼叫，不要使用或释放**SPropProblemArray**结构。 提供程序应忽略返回**DoCopyTo** **SPropProblemArray**结构中的作为_ulIndex_成员。
  
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

