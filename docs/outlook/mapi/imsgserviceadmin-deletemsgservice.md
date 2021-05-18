---
title: IMsgServiceAdminDeleteMsgService
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.DeleteMsgService
api_type:
- COM
ms.assetid: 3a6b34eb-9d46-488f-8d02-91b27c35de67
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6cef03e33abab81a407698b73a007f247ef88194
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407380"
---
# <a name="imsgserviceadmindeletemsgservice"></a>IMsgServiceAdmin::DeleteMsgService

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从配置文件中删除邮件服务。
  
```cpp
HRESULT DeleteMsgService(
  LPMAPIUID lpuid
);
```

## <a name="parameters"></a>参数

 _lpuid_
  
> [in]指向 [MAPIUID](mapiuid.md) 结构的指针，其中包含要删除的邮件服务的唯一标识符。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件服务已删除。
    
MAPI_E_NOT_FOUND 
  
> _lpuid_ 指向的 **MAPIUID** 与现有的邮件服务不匹配。 
    
## <a name="remarks"></a>备注

**IMsgServiceAdmin：:D eleteMsgService** 方法从配置文件中删除邮件服务。 **DeleteMsgService** 删除与邮件服务相关的所有配置文件部分。 
  
 **DeleteMsgService** 执行以下步骤来删除邮件服务： 
  
1. 调用邮件服务的入口点函数，将  _ulContext_ 参数设置为 MSG_SERVICE_DELETE删除配置文件节之前。 这允许服务执行任何特定于服务的任务。 
    
2. 删除邮件服务。
    
3. 删除邮件服务的配置文件部分。
    
在删除邮件服务后，不会再次调用邮件服务的入口点函数。
  
## <a name="notes-to-callers"></a>给调用方的说明

若要检索要删除的邮件服务的 **MAPIUID** 结构，请从邮件服务表中邮件服务的行中检索 **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性列。 有关详细信息，请参阅 [IMsgServiceAdmin：：CreateMsgService 方法中概述](imsgserviceadmin-createmsgservice.md) 的过程。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MsgServiceTableDlg.cpp  <br/> |CMsgServiceTableDlg：：OnDeleteSelectedItem  <br/> |MFCMAPI 使用 **IMsgServiceAdmin：:D eleteMsgService** 方法删除所选服务。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

