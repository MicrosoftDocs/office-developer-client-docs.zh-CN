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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f4ff2a3897306ebe4f77c08630782c5f2c7d5d3d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426105"
---
# <a name="imapisessionsetdefaultstore"></a>IMAPISession::SetDefaultStore

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件存储建立为会话的默认邮件存储。
  
```cpp
HRESULT SetDefaultStore(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]控制默认邮件存储设置的位掩码标志。 这些标志相互排斥;只能设置以下标志之一：
    
MAPI_DEFAULT_STORE
  
> 建立消息存储作为会话默认值。 更新邮件存储的状态表行，STATUS_DEFAULT_STORE [PidTagResourceFlags PR_RESOURCE_FLAGS (PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 标记。 
    
MAPI_PRIMARY_STORE
  
> 将邮件存储建立为登录时所使用的存储。 如果邮件存储不是默认存储，客户端应设置为默认存储。 通过设置"邮件存储"列中的"STATUS_PRIMARY_STORE"标记来更新 **PR_RESOURCE_FLAGS表行** 。 
    
MAPI_SECONDARY_STORE
  
> 建立邮件存储作为在主邮件存储不可用时在登录时所使用的存储。 如果客户端无法打开主存储，它应打开辅助存储，并设置为默认值。 通过设置"邮件存储"列中的"STATUS_SECONDARY_STORE"标记来更新邮件 **PR_RESOURCE_FLAGS行。** 
    
MAPI_SIMPLE_STORE_PERMANENT
  
> 在STATUS_SIMPLE_STORE表行、邮件存储表行和会话 **配置文件** PR_RESOURCE_FLAGS邮件存储的 PR_RESOURCE_FLAGS 属性中设置该标志。 
    
MAPI_SIMPLE_STORE_TEMPORARY
  
> 在STATUS_SIMPLE_STORE表行和邮件存储表PR_RESOURCE_FLAGS中设置邮件存储的 PR_RESOURCE_FLAGS 标记。 不修改配置文件。 
    
 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向默认的邮件存储的条目标识符的指针。 如果客户端在  _lpEntryID_ 中传递 NULL，则不选择任何邮件存储作为默认值。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
## <a name="remarks"></a>备注

**IMAPISession：：SetDefaultStore** 方法将邮件存储建立为以下操作之一： 
  
- 会话的默认邮件存储。
    
- 会话的主邮件存储。
    
- 会话的辅助邮件存储。
    
若要将邮件存储建立为默认存储，邮件存储必须在其 **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 设置以下标志：
  
- STORE_SUBMIT_OK
    
- STORE_CREATE_OK
    
- STORE_MODIFY_OK
    
## <a name="notes-to-callers"></a>给调用方的说明

您可以通过检索状态表，并搜索 STATUS_DEFAULT_STORE 列中的 STATUS_DEFAULT_STORE 标志的设置来确定 **会话的默认PR_RESOURCE_FLAGS** 存储。 具有此设置的行表示指定为会话默认值的邮件存储。 
  
当设置 MAPI_DEFAULT_STORE 或 MAPI_SIMPLE_STORE_PERMANENT 标志时，MAPI 将更新配置文件、邮件存储表和状态表。 
  
只要对邮件存储默认设置进行了更改，就会生成以下通知：
  
- 为邮件存储和状态表中的每个受影响的行发出 **fnevTableModified** 事件通知。 
    
- 向 MAPI 后台处理程序发出内部通知。 已完成进行中的操作，无需更改;涉及默认邮件存储的新操作（如邮件下载）将针对新的默认存储进行处理。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg：：OnSetDefaultStore  <br/> |MFCMAPI 使用 **IMAPISession：：SetDefaultStore** 方法将所选存储设置为默认存储。  <br/> |
   
## <a name="see-also"></a>另请参阅



[PidTagResourceFlags 规范属性](pidtagresourceflags-canonical-property.md)
  
[PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

