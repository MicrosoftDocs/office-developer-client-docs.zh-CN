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
  
将一个对象的所有属性（专门排除的属性除外）复制或移动到另一个对象。
  
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
  
> [in]指向接口标识符的指针 (IID) 表示用于访问具有要复制或移动的属性的对象的接口。
    
 _lpSrcObj_
  
> [in]指向具有要复制或移动的属性的对象的指针。
    
 _ciidExclude_
  
> [in]复制或移动属性时要排除的接口计数。
    
 _rgiidExclude_
  
> [in]接口标识符的数组，指示在将补充信息复制或移动到目标对象时不应使用的接口。
    
 _lpExcludeProps_
  
> [in]指向属性标记数组的指针，该数组标识应从复制或移动操作中排除的属性标记。 在  _lpExcludeProps_ 参数中传递 NULL 指示应复制或移动对象的所有属性。 **DoCopyTo** MAPI_E_INVALID_PARAMETER _lpExcludeProps_ 指向 [的 SPropTagArray](sproptagarray.md)结构的 **cValues** 成员设置为 0 时返回值。 
    
 _ulUIParam_
  
> [in]进度指示器的父窗口的句柄。 
    
 _lpProgress_
  
> [in]指向进度指示器实现的指针。 如果在  _lpProgress_ 参数中传递 NULL，MAPI 将提供进度实现。 除非在 _ulFlags_ 参数中设置了 MAPI_DIALOG 标志，否则将忽略 _lpProgress_ 参数。 
    
 _lpDestInterface_
  
> [in]指向接口标识符的指针，该标识符表示用于访问对象以接收复制或移动的属性的接口。
    
 _lpDestObj_
  
> [in]指向接收复制或移动的属性的对象的指针。
    
 _ulFlags_
  
> [in]控制复制或移动操作的标志的位掩码。 可以设置以下标志：
    
MAPI_DIALOG 
  
> 显示进度指示器。 
    
MAPI_MOVE 
  
> **DoCopyTo** 应执行移动操作，而不是复制操作。 未设置此标志时 **，DoCopyTo** 将执行复制操作。 
    
MAPI_NOREPLACE 
  
> 不应覆盖目标对象中的现有属性。 未设置此标志时 **，DoCopyTo** 将覆盖现有属性。 
    
 _lppProblems_
  
> [out]在输入时，指向指向 [SPropProblemArray 结构的指针的](spropproblemarray.md) 指针;否则为 NULL，表示不需要错误信息。 如果  _lppProblems_ 是输入的有效指针， **则 DoCopyTo** 返回有关复制一个或多个属性时错误的详细信息。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动属性。
    
MAPI_E_COLLISION 
  
> 要复制或移动的属性在目标对象中已存在，MAPI_NOREPLACE标记。 
    
MAPI_E_FOLDER_CYCLE 
  
> 源对象直接或间接包含目标对象。 在发现此条件之前，可能执行了大量工作，因此可能会部分修改源对象和目标对象。 
    
MAPI_E_INTERFACE_NOT_SUPPORTED 
  
> _lpSrcInterface_ 参数标识的接口不受 _lpSrcObj_ 指向的对象支持，或者 _lpDestObj_ 指向的对象不支持 _由 lpDestInterface_ 参数标识的接口。 
    
MAPI_E_NO_ACCESS 
  
> 试图访问调用方权限不足的对象。 如果目标对象与源对象相同，则返回此错误。
    
MAPI_E_INVALID_PARAMETER 
  
> _lpSrcInterface_ 参数为 NULL。 
    
以下值可以在 **SPropProblemArray** 结构中返回，但不能作为 **DoCopyTo** 的返回值。 这些错误适用于单个属性。
  
MAPI_E_BAD_CHARWIDTH 
  
> 设置MAPI_UNICODE **DoCopyTo** 不支持 Unicode，或者未MAPI_UNICODE **DoCopyTo** 仅支持 Unicode。 
    
MAPI_E_COMPUTED 
  
> 调用方无法修改该属性，因为它是一个只读属性，由目标对象的所有者计算。 此错误并不严重;调用方应允许复制操作继续。
    
MAPI_E_INVALID_TYPE 
  
> 属性类型无效。
    
MAPI_E_UNEXPECTED_TYPE 
  
> 属性类型不是调用方预期的类型。
    
## <a name="remarks"></a>备注

**IMAPISupport：:D oCopyTo** 方法为邮件存储提供程序支持对象实现。 邮件存储提供程序可以调用 **DoCopyTo** 来实现其文件夹和消息的 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 方法。 
  
默认情况下 **，DoCopyTo** 将一个对象的所有属性复制或移动到另一个对象。 源对象中任何子对象都将自动包含在操作中，并完整复制或移动。 
  
如果目标对象中已存在任何复制或移动的属性，则现有属性将被新属性覆盖，除非在  _ulFlags_ 参数中设置了 MAPI_NOREPLACE 标志。 目标对象中未覆盖的现有信息保持不变。 
  
## <a name="notes-to-callers"></a>给调用方的说明

若要从复制或移动操作中排除属性，请将其属性标记包括在  _lpExcludeProps_ 参数中。 如果传递使用 PROP_TAG 宏从[](prop_tag.md)属性标记数组中的特定标识符构建属性标记的结果，将排除具有该标识符的所有属性。 例如，属性标记数组中的以下条目会导致排除标识符为 0x8002的所有属性，无论类型如何： 
  
 `PROP_TAG(PT_LONG, 0x8002)`
  
为避免在将邮件复制到其他文件夹时复制邮件的传递时间，请指定 **PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) 属性标记排除数组。 若要排除邮件的收件人列表，PR_MESSAGE_RECIPIENTS ([PidTagMessageRecipients) PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)属性添加到排除数组。  若要排除邮件的附件，PR_MESSAGE_ATTACHMENTS ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md)) 添加到数组。 
  
同样，若要防止复制或移动文件夹或通讯簿容器的层次结构或内容表，在属性标记排除数组中包括 **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 或 **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 。
  
忽略MAPI_E_COMPUTED _lppProblems_ 参数 **的 SPropProblemArray** 结构中返回的错误。 
  
_lpSrcInterface_ 指向的接口标识符通常与 _lpDestInterface_ 指向的接口标识符相同。 
  
如果在  _lpDestInterface 中_ 传递可接受的接口标识符，但  _lpDestObj_ 中的指针无效，则结果不可预测。 这很可能会导致提供程序失败。 
  
相反，如果您知道不应复制或移动的补充信息，请添加接口标识符，以在  _rgiidExclude_ 参数传递的数组中排除这些接口。 例如，如果要复制邮件，但不复制其任何邮件附件，IID_IMessage  _rgiidExclude 数组中传递_ 邮件。 **DoCopyTo** 忽略  _rgiidExclude_ 中未识别的任何接口。 
  
使用  _rgiidExclude_ 参数排除接口时，它还排除从该接口派生的所有接口。 例如，排除 [IMAPIContainer](imapicontainerimapiprop.md) 接口会导致排除文件夹或通讯簿容器，具体取决于提供程序的类型。 不要排除 [IMAPIProp](imapipropiunknown.md) 或 [IUnknown，](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) 因为有很多接口派生自它们。 
  
 **DoCopyTo** 报告应用于整个运算的全局错误，以及适用于单个属性的单个错误。 这些单个错误将放入 **SPropProblemArray** 结构中。 可以通过为属性问题数组结构参数传递 NULL（而不是有效指针）来禁止在属性级别报告错误。 
  
如果要接收有关错误的信息，请传递 _lppProblems_ 参数中的有效 **SPropProblemArray** 结构指针。 当 **DoCopyTo** S_OK时，请检查结构中各个属性的可能错误。 当 **DoCopyTo** 返回错误时 **，SPropProblemArray** 结构中不会返回任何信息。 相反，请调用 [IMAPISupport：：GetLastError](imapisupport-getlasterror.md) 方法来检索详细的错误信息。 
  
如果 **DoCopyTo** S_OK，请通过调用 [MAPIFreeBuffer](mapifreebuffer.md)函数释放返回的 **SPropProblemArray** 结构。 
  
如果在 **DoCopyTo** 调用上发生全局错误，请不要使用或释放 **SPropProblemArray** 结构。 提供程序应忽略 **DoCopyTo** 返回 **的 SPropProblemArray** 结构中的 _ulIndex_ 成员。
  
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

