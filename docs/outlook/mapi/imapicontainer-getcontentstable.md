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
ms.openlocfilehash: 9fb8919287420038b5c9165bb14b7d33d1ad2fe1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578862"
---
# <a name="imapicontainergetcontentstable"></a>IMAPIContainer::GetContentsTable

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回到容器的内容表的指针。
  
```cpp
HRESULT GetContentsTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志，控制如何返回的内容表。 可以设置以下标志：
    
MAPI_ASSOCIATED 
  
> 应返回容器的关联的内容表而不是标准内容表。 此标志仅用于文件夹。 对[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法的调用中设置 MAPI_ASSOCIATED 标志创建关联的内容表中包含的邮件。 客户端通常使用关联的内容表检索窗体、 视图和其他隐藏的邮件。 
    
ACLTABLE_FREEBUSY
  
> 允许访问 frightsFreeBusySimple 和 frightsFreeBusyDetailed **PR_MEMBER_RIGHTS**中的权限。
    
MAPI_DEFERRED_ERRORS 
  
> **GetContentsTable**可以成功，可能之前返回表可用于将呼叫者。 如果表不可用，则进行后续表呼叫会引发错误。 
    
MAPI_UNICODE 
  
> Unicode 格式返回包含字符串数据的列的请求。 如果未设置 MAPI_UNICODE 标志，应以 ANSI 格式返回字符串。 
    
SHOW_SOFT_DELETES
  
> 显示项目的当前标记为软删除 — 即，它们是中已删除的邮件保留时间阶段。
    
 _lppTable_
  
> [输出]指向内容表格的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索内容表。
    
MAPI_E_BAD_CHARWIDTH 
  
> 既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。
    
MAPI_E_NO_SUPPORT 
  
> 容器未包含任何内容，并不能提供内容表。
    
## <a name="remarks"></a>注解

**IMAPIContainer::GetContentsTable**方法返回容器的内容表格的指针。 内容表包含有关容器中的对象的摘要信息。 
  
内容表包含冗长列集。 有关内容表中的必需的和可选的列的完整列表，请参阅[内容表](contents-tables.md)。 
  
很可能为一些容器具有任何内容。 这些容器返回 MAPI_E_NO_SUPPORT 从**GetContentsTable**其实现。
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如果您为您的容器支持内容表，还必须执行以下操作：
  
- 支持对容器的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法的调用，以打开**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 属性。
    
- 对容器的呼叫的响应中返回**PR_CONTAINER_CONTENTS** 
    
    [IMAPIProp::GetProps](imapiprop-getprops.md)和[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法。 
    
远程传输提供程序实现此方法必须返回一个指向[IMAPITable: IUnknown](imapitableiunknown.md) _ppTable_参数传递到**GetContentsTable**方法中的接口。 如果您传输提供程序具有现有内容表，它就足以返回指向它的指针。 如果没有，此方法必须创建一个新[IMAPITable: IUnknown](imapitableiunknown.md)对象、 填充 （如果可用） 的邮件头，具有表和一个指针返回到新表。 [ITableData::HrGetView](itabledata-hrgetview.md)方法可用于生成的返回值和_ppTable_参数中存储表指针。 将目录必须至少支持下列属性： 
  
- **PR_ENTRYID**([PidTagEntryID](pidtagentryid-canonical-property.md))
    
- **PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))
    
- **PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))
    
- **仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))
    
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

可以截断字符串和二进制内容表格列。 通常情况下，提供程序返回 255 个字符。 因为您无法知道提前是否表包含截断的列，假定一列被截断如果列的长度为 255 个或 510 字节。 直接从通过使用其条目标识符来打开它，然后调用**IMAPIProp::GetProps**方法的对象，总是可以检索有必要，截断列中的完整值。 
  
具体取决于提供程序的实现、 限制和排序操作可以应用于所有字符串或该字符串的截断版本。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableDialog.cpp  <br/> |CContentsTableDlg::CContentsTableDlg  <br/> |**CContentsTableDlg**类使用**GetContentsTable**获取内容表中的条目。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetPropList](imapiprop-getproplist.md)
  
[IMAPIProp::GetProps](imapiprop-getprops.md)
  
[IMAPIProp::OpenProperty](imapiprop-openproperty.md)
  
[IMAPITable : IUnknown](imapitableiunknown.md)
  
[PidTagContainerContents 规范属性](pidtagcontainercontents-canonical-property.md)
  
[IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

