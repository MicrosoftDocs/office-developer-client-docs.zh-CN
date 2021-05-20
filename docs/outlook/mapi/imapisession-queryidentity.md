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
ms.openlocfilehash: 396320c6b39553da09aa1f45d0c755f40a939382
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428219"
---
# <a name="imapisessionqueryidentity"></a>IMAPISession::QueryIdentity

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回提供会话的主标识的对象的条目标识符。
  
```cpp
HRESULT QueryIdentity(
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a>参数

 _lpcbEntryID_
  
> [out]指向  _lppEntryID_ 参数指向的条目标识符中的字节计数的指针。 
    
 _lppEntryID_
  
> [out]指向指向提供主标识的对象的条目标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回主标识。
    
MAPI_W_NO_SERVICE 
  
> 调用成功，但没有会话的主标识。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPISession：：QueryIdentity** 方法检索当前会话的主标识，并通过 _lppEntryID_ 参数返回值。 主标识是一个对象，通常为消息用户，表示会话的用户。  _lppEntryID_ 返回 [IMailUser](imailuserimapiprop.md) 对象的主标识，该对象也存储为 [PidTagEntryID](pidtagentryid-canonical-property.md) 属性。 可以使用 _lppEntryID_ 中返回的值，使用 [IMAPISession：：OpenEntry](imapisession-openentry.md)打开 **IMailUser** 对象。
  
尽管多个邮件服务中的许多服务提供商可以为会话提供主标识，但 MAPI 指定单个服务提供商。 提供主标识的服务提供商将设置以下项：
  
- STATUS_PRIMARY_IDENTITY [PidTagResourceFlags](pidtagresourceflags-canonical-property.md) PR_RESOURCE_FLAGS (标记) 标记。 
    
- The **PR_IDENTITY_DISPLAY (** [PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) property.
    
- The **PR_IDENTITY_ENTRYID (** [PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md)) property.
    
- The **PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) property.
    
如果提供主标识的服务提供商属于邮件服务，则邮件服务中的其他服务提供商也会设置PR_IDENTITY属性。 这些属性在会话的状态表中发布。 
  
如果可能 **，QueryIdentity** 会从用PR_IDENTITY_ENTRYID 标记的状态行中返回 STATUS_PRIMARY_IDENTITY。 如果 **主PR_IDENTITY_ENTRYID** 行中缺少属性 **，QueryIdentity** 将返回使用该行中其他信息构建的一键式条目标识符。 
  
如果STATUS_PRIMARY_IDENTITY表中的所有列都缺少 PR_RESOURCE_FLAG 标志 **，QueryIdentity** 将返回它找到的第一个条目标识符。  如果没有要返回的适当条目标识符 **，QueryIdentity** 将成功返回警告MAPI_W_NO_SERVICE将  _lppEntryID_ 指向硬编码的条目标识符。 
  
## <a name="notes-to-callers"></a>给调用方的说明

可以调用 [IMsgServiceAdmin：：SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md) 方法为邮件服务分配提供会话的主标识的任务。 
  
另一种检索主标识的方式是，在状态表中搜索行，PR_RESOURCE_FLAGS **列设置为** STATUS_PRIMARY_IDENTITY。 有关检索标识信息的备用方法详细信息，请参阅 [状态表和状态对象](status-table-and-status-objects.md)。
  
使用 **QueryIdentity** 返回的主标识的条目标识符完成后，通过调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数释放内存。 
  
有关标识的一般详细信息，请参阅 [MAPI Primary Identity](mapi-primary-identity.md)。 
  
有关检索 MAPI 会话标识的信息，请参阅检索 [主标识和提供程序标识](retrieving-primary-and-provider-identity.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg：：OnQueryIdentity  <br/> |MFCMAPI 使用 **IMAPISession：：QueryIdentity** 方法打开会话的主标识的通讯簿条目。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::OpenEntry](imapisession-openentry.md)
  
[IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 主标识](mapi-primary-identity.md)
  
[检索主标识和提供程序标识](retrieving-primary-and-provider-identity.md)
  
[使用宏处理错误](using-macros-for-error-handling.md)
  
[状态表和状态对象](status-table-and-status-objects.md)

