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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335691"
---
# <a name="imapisessionqueryidentity"></a>IMAPISession::QueryIdentity

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回为会话提供主要标识的对象的条目标识符。
  
```cpp
HRESULT QueryIdentity(
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a>参数

 _lpcbEntryID_
  
> 排除指向条目标识符中由_lppEntryID_参数指向的字节计数的指针。 
    
 _lppEntryID_
  
> 排除指向提供主要标识的对象的条目标识符的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回主标识。
    
MAPI_W_NO_SERVICE 
  
> 调用成功, 但没有会话的主标识。 返回此警告时, 应以成功的方式处理该调用。 若要测试此警告, 请使用**HR_FAILED**宏。 有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>注解

**IMAPISession:: QueryIdentity**方法检索当前会话的主标识, 并通过_lppEntryID_参数返回值。 主要标识是一个对象 (通常是邮件用户), 代表会话的用户。  _lppEntryID_返回[IMailUser](imailuserimapiprop.md)对象的主标识, 该标识也存储为[PidTagEntryID](pidtagentryid-canonical-property.md)属性。 您可以使用_lppEntryID_中返回的值, 通过[IMAPISession:: OpenEntry](imapisession-openentry.md)打开**IMailUser**对象。
  
虽然多个邮件服务中的许多服务提供商可以为会话提供主要标识, 但 MAPI 指定了单个服务提供商。 提供主标识的服务提供程序将设置以下各项:
  
- **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中的 STATUS_PRIMARY_IDENTITY 标志。
    
- **PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) 属性。
    
- **PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md)) 属性。
    
- **PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) 属性。
    
如果提供主标识的服务提供商属于某个邮件服务, 则邮件服务中的其他服务提供商也会设置 PR_IDENTITY 属性。 这些属性在会话的状态表中发布。 
  
如果可能, **QueryIdentity**将从使用 STATUS_PRIMARY_IDENTITY 标记的状态行返回**PR_IDENTITY_ENTRYID**属性的值。 如果主标识行中缺少**PR_IDENTITY_ENTRYID**属性, 则**QueryIdentity**将返回使用该行中的其他信息生成的一次性条目标识符。 
  
如果状态表中的所有**PR_RESOURCE_FLAG**列中缺少 STATUS_PRIMARY_IDENTITY 标志, 则**QueryIdentity**将返回找到的第一个条目标识符。 当没有合适的条目标识符返回时, **QueryIdentity**将成功并将警告 MAPI_W_NO_SERVICE, 并将_lppEntryID_指向硬编码的条目标识符。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以调用[IMsgServiceAdmin:: SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)方法将邮件服务分配给提供会话的主要标识的任务。 
  
检索主标识的另一种方法是, 在状态表中搜索**PR_RESOURCE_FLAGS**列设置为 STATUS_PRIMARY_IDENTITY 的行。 有关检索标识信息的其他方法的详细信息, 请参阅[状态表和状态对象](status-table-and-status-objects.md)。
  
使用**QueryIdentity**返回的主标识的条目标识符后, 通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放其内存。 
  
有关标识一般的详细信息, 请参阅[MAPI 主标识](mapi-primary-identity.md)。 
  
有关检索 MAPI 会话标识的详细信息, 请参阅[检索主标识和提供程序标识](retrieving-primary-and-provider-identity.md)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg  <br/> |CMainDlg:: OnQueryIdentity  <br/> |MFCMAPI 使用**IMAPISession:: QueryIdentity**方法打开会话主要标识的通讯簿条目。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPISession::OpenEntry](imapisession-openentry.md)
  
[IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 主标识](mapi-primary-identity.md)
  
[检索主标识和提供程序标识](retrieving-primary-and-provider-identity.md)
  
[使用宏进行错误处理](using-macros-for-error-handling.md)
  
[状态表和状态对象](status-table-and-status-objects.md)

