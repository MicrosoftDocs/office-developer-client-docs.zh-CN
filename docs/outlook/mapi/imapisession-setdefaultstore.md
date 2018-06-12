---
title: IMAPISessionSetDefaultStore
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.SetDefaultStore
api_type:
- COM
ms.assetid: 456c207f-5d41-4d0c-94b6-0c58893a6bed
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: e3c4125bf4fcf1881a0cba9b04a8bb6aa71f527d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775569"
---
# <a name="imapisessionsetdefaultstore"></a>IMAPISession::SetDefaultStore

  
  
**适用于**： Outlook 
  
建立会话，作为默认的邮件存储的消息存储。
  
```cpp
HRESULT SetDefaultStore(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]位掩码的标志控制默认的邮件存储的设置的。 这些标志为相互排斥;可以设置以下标志的唯一之一：
    
MAPI_DEFAULT_STORE
  
> 为会话默认建立的邮件存储区。 通过设置 STATUS_DEFAULT_STORE 标志**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 列中更新的消息存储状态表格行。
    
MAPI_PRIMARY_STORE
  
> 作为存储用于登录建立的邮件存储区。 如果消息存储不是默认存储，客户端应使其默认值。 通过设置 STATUS_PRIMARY_STORE 标志**PR_RESOURCE_FLAGS**列中更新的消息存储状态表格行。 
    
MAPI_SECONDARY_STORE
  
> 建立的邮件存储组作为存储用于登录时如果主消息存储不可用。 如果客户端无法打开主存储区，它应打开辅助存储，并将其设置为默认值。 通过设置 STATUS_SECONDARY_STORE 标志**PR_RESOURCE_FLAGS**列中更新的消息存储状态表格行。 
    
MAPI_SIMPLE_STORE_PERMANENT
  
> 消息存储表格行，其状态表格行和会话配置文件中的消息存储**PR_RESOURCE_FLAGS**属性中设置 STATUS_SIMPLE_STORE 标志。 
    
MAPI_SIMPLE_STORE_TEMPORARY
  
> 其状态表行和消息存储表行中的消息存储**PR_RESOURCE_FLAGS**属性中设置 STATUS_SIMPLE_STORE 标志。 未修改配置文件。 
    
 _cbEntryID_
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向专为默认的消息存储的项标识符的指针。 如果客户端传入_lpEntryID_NULL，没有消息存储在为默认情况下处于选中状态。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
## <a name="remarks"></a>备注

**IMAPISession::SetDefaultStore**方法建立的消息存储为下列选项之一： 
  
- 默认的邮件存储会话。
    
- 用于会话的主邮件存储。
    
- 会话辅助消息存储。
    
要建立为默认的消息存储，消息存储库必须具有以下标志在其**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中设置：
  
- STORE_SUBMIT_OK
    
- STORE_CREATE_OK
    
- STORE_MODIFY_OK
    
## <a name="notes-to-callers"></a>给调用方的说明

您可以通过检索状态表和搜索**PR_RESOURCE_FLAGS**列中的 STATUS_DEFAULT_STORE 标志设置为会话确定默认邮件存储区。 此设置的行代表被指定为会话默认的消息存储。 
  
当设置 MAPI_DEFAULT_STORE 或 MAPI_SIMPLE_STORE_PERMANENT 标志时，MAPI 更新配置文件、 消息存储表和状态表。 
  
消息存储默认设置进行更改时，只要将生成以下通知：
  
- **FnevTableModified**事件通知发出的消息存储和状态表中的每个受影响的行。 
    
- 内部通知颁发给 MAPI 后台处理程序。 正在进行的操作完成后，无更改;新的默认存储处理涉及默认的邮件存储，如消息下载的新操作。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg::OnSetDefaultStore  <br/> |MFCMAPI 使用**IMAPISession::SetDefaultStore**方法将所选的商店设置为默认存储。  <br/> |
   
## <a name="see-also"></a>另请参阅



[PidTagResourceFlags 规范属性](pidtagresourceflags-canonical-property.md)
  
[PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[IMAPISession: IUnknown](imapisessioniunknown.md)


[MFCMAPI 作为的代码示例](mfcmapi-as-a-code-sample.md)

