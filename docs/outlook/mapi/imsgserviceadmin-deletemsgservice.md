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
ms.openlocfilehash: 0a3021ed386aa00777694452a755693fc4078093
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775836"
---
# <a name="imsgserviceadmindeletemsgservice"></a>IMsgServiceAdmin::DeleteMsgService

  
  
**适用于**： Outlook 
  
从配置文件中删除的消息服务。
  
```cpp
HRESULT DeleteMsgService(
  LPMAPIUID lpuid
);
```

## <a name="parameters"></a>参数

 _lpuid_
  
> [in]一个指向[MAPIUID](mapiuid.md)结构，其中包含要删除的消息服务的唯一标识符。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已删除邮件服务。
    
MAPI_E_NOT_FOUND 
  
> 指向_lpuid_ **MAPIUID**与现有邮件服务不匹配。 
    
## <a name="remarks"></a>说明

**IMsgServiceAdmin::DeleteMsgService**方法从一个配置文件中删除的消息服务。 **DeleteMsgService**删除所有与邮件服务相关的配置文件部分。 
  
 **DeleteMsgService**执行以下步骤删除消息服务： 
  
1. 与之前删除的配置文件部分设置为 MSG_SERVICE_DELETE _ulContext_参数调用消息服务的入口点函数。 这样，该服务以执行任何特定于服务的任务。 
    
2. 删除邮件服务。
    
3. 删除消息服务的配置文件一节。
    
删除服务后消息服务的入口点函数不再次调用。
  
## <a name="notes-to-callers"></a>给调用方的说明

若要检索要删除的消息服务的**MAPIUID**结构，请从邮件服务表中的消息服务的行中检索**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性列。 有关详细信息，请参阅[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)方法中概述的过程。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MsgServiceTableDlg.cpp  <br/> |CMsgServiceTableDlg::OnDeleteSelectedItem  <br/> |MFCMAPI 使用**IMsgServiceAdmin::DeleteMsgService**方法删除选定的服务。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

