---
title: IMAPIContainerGetContentsTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIContainer.GetContentsTable
api_type:
- COM
ms.assetid: 88c7a666-875d-473a-b126-dbbb7009f7d9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 28315c5a09eba32816a0b63513cb98d1c30a96bb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431104"
---
# <a name="imapicontainergetcontentstable"></a>IMAPIContainer::GetContentsTable

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回指向容器的内容表的指针。
  
```cpp
HRESULT GetContentsTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时用于控制如何返回内容表的标志的位掩码。 可以设置以下标志:
    
MAPI_ASSOCIATED 
  
> 应返回容器的关联内容表, 而不是标准内容表。 此标志仅用于文件夹。 "关联的内容" 表中包含的邮件是在对[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法的调用中设置的 MAPI_ASSOCIATED 标志创建的。 客户端通常使用关联的内容表检索表单、视图和其他隐藏邮件。 
    
ACLTABLE_FREEBUSY
  
> 启用对**PR_MEMBER_RIGHTS**中的 frightsFreeBusySimple 和 frightsFreeBusyDetailed 权限的访问。
    
MAPI_DEFERRED_ERRORS 
  
> 在将表提供给调用程序之前, 可能会成功返回**GetContentsTable** 。 如果该表不可用, 则进行后续的表调用可能会引发错误。 
    
MAPI_UNICODE 
  
> 请求以 Unicode 格式返回包含字符串数据的列。 如果未设置 MAPI_UNICODE 标志, 则应以 ANSI 格式返回字符串。 
    
SHOW_SOFT_DELETES
  
> 显示当前标记为软删除的项目, 即它们处于 "已删除邮件" 保留时间阶段。
    
 _lppTable_
  
> 排除指向内容表的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索内容表。
    
MAPI_E_BAD_CHARWIDTH 
  
> 设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。
    
MAPI_E_NO_SUPPORT 
  
> 容器没有内容, 无法提供内容表。
    
## <a name="remarks"></a>说明

**IMAPIContainer:: GetContentsTable**方法返回指向容器的内容表的指针。 内容表包含容器中对象的摘要信息。 
  
内容表具有冗长的列集。 有关内容表中必填和可选的列的完整列表, 请参阅[内容表](contents-tables.md)。 
  
某些容器可能不包含任何内容。 这些容器从其**GetContentsTable**的实现返回 MAPI_E_NO_SUPPORT。
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果您支持容器的内容表, 还必须执行以下操作:
  
- 支持对容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法的调用, 以打开**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 属性。
    
- 返回**PR_CONTAINER_CONTENTS**以响应对容器的调用 
    
    [IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法。 
    
远程传输提供程序的此方法的实现必须在传递给**GetContentsTable**方法的_ppTable_参数中返回指向[IMAPITable: IUnknown](imapitableiunknown.md)接口的指针。 如果您的传输提供程序具有现有的内容表, 则可以返回指向它的指针。 如果不是, 则此方法必须创建一个新的[IMAPITable: IUnknown](imapitableiunknown.md)对象, 使用邮件头填充该表 (如果有的话), 并返回指向新表的指针。 [ITableData:: HrGetView](itabledata-hrgetview.md)方法用于生成返回值并将表指针存储在_ppTable_参数中。 "内容" 表必须至少支持下列属性列: 
  
- **PR_ENTRYID**([PidTagEntryID](pidtagentryid-canonical-property.md))
    
- **PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))
    
- **PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))
    
- **PR_DISPLAY_TO**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))
    
- **PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))
    
- **PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md))
    
- **PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))
    
- **PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md))
    
- **PR_PRIORITY**([PidTagPriority](pidtagpriority-canonical-property.md))
    
- **PR_IMPORTANCE**([PidTagImportance](pidtagimportance-canonical-property.md))
    
- **PR_SENSITIVITY**([PidTagSensitivity](pidtagsensitivity-canonical-property.md))
    
- **PR_MESSAGE_DELIVERY_TIME**([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))
    
- **PR_MSG_STATUS**([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md))
    
- **PR_MESSAGE_DOWNLOAD_TIME**([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))
    
- **PR_HASATTACH**([PidTagHasAttachments](pidtaghasattachments-canonical-property.md))
    
- **PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))
    
- **PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))
    
- **PR_NORMALIZED_SUBJECT**([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))
    
## <a name="notes-to-callers"></a>给调用方的说明

字符串和二进制内容表中的列可以被截断。 通常, 提供程序返回255个字符。 由于您无法事先知道表是否包括截断的列, 因此假定列的长度为255或510字节时, 将截断列。 如果需要, 您始终可以从对象中直接检索已截断列的完整值, 方法是使用其条目标识符将其打开, 然后调用**IMAPIProp:: GetProps**方法。 
  
根据提供程序的实现, 限制和排序操作可应用于所有字符串或该字符串的截断版本。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableDialog  <br/> |CContentsTableDlg:: CContentsTableDlg  <br/> |**CContentsTableDlg**类使用**GetContentsTable**获取内容表中的项。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetPropList](imapiprop-getproplist.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)
  
[PidTagContainerContents 规范属性](pidtagcontainercontents-canonical-property.md)
  
[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

