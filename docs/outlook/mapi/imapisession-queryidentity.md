---
title: IMAPISessionQueryIdentity
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.QueryIdentity
api_type:
- COM
ms.assetid: a2cdda90-5457-49a7-b98c-7273ffe5cbbc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6b64653aa87ff7ac983409978a69f59148251d7d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583412"
---
# <a name="imapisessionqueryidentity"></a>IMAPISession::QueryIdentity

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回会话中提供的主要标识的对象的项标识符。
  
```cpp
HRESULT QueryIdentity(
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a>参数

 _lpcbEntryID_
  
> [输出]一个指向_lppEntryID_参数指向该条目标识符中的字节数。 
    
 _lppEntryID_
  
> [输出]指向提供的主要标识的对象的项标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回的主标识。
    
MAPI_W_NO_SERVICE 
  
> 呼叫成功，但没有任何主标识会话。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPISession::QueryIdentity**方法检索当前会话的主标识，并返回通过_lppEntryID_参数的值。 主 identity 是一个对象，通常消息，表示用户会话的用户。  _lppEntryID_返回[IMailUser](imailuserimapiprop.md)对象，它还存储为[PidTagEntryID](pidtagentryid-canonical-property.md)属性的主标识。 您可以使用_lppEntryID_中返回的值打开使用[IMAPISession::OpenEntry](imapisession-openentry.md) **IMailUser**对象。
  
尽管在多个邮件服务中的许多服务提供商可以会话提供的主要标识，MAPI 指定单个服务提供程序。 提供的主要标识服务提供商设置以下各项：
  
- **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中 STATUS_PRIMARY_IDENTITY 标志。
    
- **PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) 属性中。
    
- **PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md)) 属性中。
    
- **PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) 属性中。
    
如果服务提供商提供的主要标识属于邮件服务，消息服务中的其他服务提供商还设置 PR_IDENTITY 属性。 在会话的状态表中发布这些属性。 
  
如果可能， **QueryIdentity**从 STATUS_PRIMARY_IDENTITY 标记的状态行返回**PR_IDENTITY_ENTRYID**属性的值。 如果主身份行中缺少**PR_IDENTITY_ENTRYID**属性， **QueryIdentity**返回构建与该行中的其他信息的一次性条目标识符。 
  
如果中的所有**PR_RESOURCE_FLAG**列在状态表中缺少 STATUS_PRIMARY_IDENTITY 标志，则**QueryIdentity**返回找到的第一个条目标识符。 当没有返回没有适当的项标识符时， **QueryIdentity**警告 MAPI_W_NO_SERVICE 成功，并_lppEntryID_指向的硬编码的项标识符。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以调用[IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)方法提供会话的主标识的任务分配的消息服务。 
  
通过搜索行的状态表设置为 STATUS_PRIMARY_IDENTITY **PR_RESOURCE_FLAGS**列与另一种方法来检索主标识。 有关此另一种方法检索标识信息的详细信息，请参阅[状态表和状态对象](status-table-and-status-objects.md)。
  
当您完成使用主标识**QueryIdentity**返回的项标识符时，通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放其内存。 
  
标识有关详细信息，请参阅[MAPI 主标识](mapi-primary-identity.md)。 
  
有关检索 MAPI 会话标识的详细信息，请参阅[检索主和提供程序的标识](retrieving-primary-and-provider-identity.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg::OnQueryIdentity  <br/> |MFCMAPI 使用**IMAPISession::QueryIdentity**方法打开主标识会话的通讯簿条目。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::OpenEntry](imapisession-openentry.md)
  
[IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 主标识](mapi-primary-identity.md)
  
[检索主要标识和提供程序标识](retrieving-primary-and-provider-identity.md)
  
[使用宏进行错误处理](using-macros-for-error-handling.md)
  
[状态表和状态对象](status-table-and-status-objects.md)

