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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335803"
---
# <a name="imapisessionsetdefaultstore"></a>IMAPISession::SetDefaultStore

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件存储区建立为会话的默认邮件存储区。
  
```cpp
HRESULT SetDefaultStore(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时用于控制默认邮件存储的设置的标志的位掩码。 这些标志是互斥的;只能设置下列标志之一:
    
MAPI_DEFAULT_STORE
  
> 将邮件存储区建立为会话默认值。 通过在**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 列中设置 STATUS_DEFAULT_STORE 标志来更新邮件存储区的状态表行。
    
MAPI_PRIMARY_STORE
  
> 建立要在登录时使用的存储区的邮件存储区。 如果邮件存储不是默认存储, 客户端应将其设为默认值。 通过在**PR_RESOURCE_FLAGS**列中设置 STATUS_PRIMARY_STORE 标志来更新邮件存储区的状态表行。 
    
MAPI_SECONDARY_STORE
  
> 将邮件存储区建立为当主邮件存储不可用时在登录时使用的存储区。 如果客户端无法打开主存储, 则应打开辅助存储并将其设置为默认存储。 通过在**PR_RESOURCE_FLAGS**列中设置 STATUS_SECONDARY_STORE 标志来更新邮件存储区的状态表行。 
    
MAPI_SIMPLE_STORE_PERMANENT
  
> 在邮件存储区的**PR_RESOURCE_FLAGS**属性中设置其状态表行、邮件存储表行和会话配置文件中的 STATUS_SIMPLE_STORE 标志。 
    
MAPI_SIMPLE_STORE_TEMPORARY
  
> 在邮件存储的**PR_RESOURCE_FLAGS**属性中的状态表格行和邮件存储表行中设置 STATUS_SIMPLE_STORE 标志。 不修改配置文件。 
    
 _cbEntryID_
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向邮件存储的条目标识符的指针, 该邮件存储将作为默认值。 如果客户端在_lpEntryID_中传递了 NULL, 则不会选择任何邮件存储区作为默认值。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
## <a name="remarks"></a>注解

**IMAPISession:: SetDefaultStore**方法将邮件存储区建立为以下内容之一: 
  
- 会话的默认邮件存储区。
    
- 会话的主邮件存储区。
    
- 会话的辅助邮件存储区。
    
若要将邮件存储区设置为默认值, 邮件存储区的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中必须设置以下标志:
  
- STORE_SUBMIT_OK
    
- STORE_CREATE_OK
    
- STORE_MODIFY_OK
    
## <a name="notes-to-callers"></a>给调用方的说明

您可以通过检索状态表并在**PR_RESOURCE_FLAGS**列中搜索 STATUS_DEFAULT_STORE 标志的设置来确定会话的默认邮件存储。 具有此设置的行表示指定为会话默认值的邮件存储区。 
  
如果设置了 MAPI_DEFAULT_STORE 或 MAPI_SIMPLE_STORE_PERMANENT 标志, MAPI 将更新配置文件、邮件存储表和状态表。 
  
每当对邮件存储库默认设置进行更改时, 都会生成以下通知:
  
- 对于邮件存储和状态表中的每个受影响的行, 都会发出一个**fnevTableModified**事件通知。 
    
- 向 MAPI 后台处理程序发出内部通知。 已在进行中的操作已完成, 无需更改;将为新的默认存储区处理涉及默认邮件存储 (如邮件下载) 的新操作。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg  <br/> |CMainDlg:: OnSetDefaultStore  <br/> |MFCMAPI 使用**IMAPISession:: SetDefaultStore**方法将选定存储区设置为默认存储区。  <br/> |
   
## <a name="see-also"></a>另请参阅



[PidTagResourceFlags 规范属性](pidtagresourceflags-canonical-property.md)
  
[PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)
  
[TABLE_NOTIFICATION](table_notification.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

