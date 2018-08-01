---
title: IProfAdminDeleteProfile
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.DeleteProfile
api_type:
- COM
ms.assetid: 730af2da-4c4a-42a7-9d52-56d914107d64
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 249d2dcf3a298abde85bdc53620680146d43c168
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776013"
---
# <a name="iprofadmindeleteprofile"></a>IProfAdmin::DeleteProfile

  
  
**适用于**： Outlook 
  
删除配置文件。
  
```cpp
HRESULT DeleteProfile(
  LPSTR lpszProfileName,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpszProfileName_
  
> [in]指针，指向要删除的配置文件的名称。
    
 _ulFlags_
  
> [in]始终为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除配置文件。
    
MAPI_E_NOT_FOUND 
  
> 指定的配置文件不存在。
    
## <a name="remarks"></a>说明

**IProfAdmin::DeleteProfile**方法删除配置文件。 如果要删除的配置文件正在使用中，调用**DeleteProfile**时， **DeleteProfile** ，则返回 S_OK，但不会立即删除配置文件。 相反， **DeleteProfile**标记为删除的配置文件并将不再正在时使用它，所有其活动会话结束后将其删除。 
  
使用_ulContext_参数中设置的 MSG_SERVICE_DELETE 值调用入口点函数的配置文件中的每个邮件服务。 首先，此函数删除该服务，，然后它删除该服务的配置文件一节。 删除服务后邮件服务入口点函数不再次调用。 
  
不需要密码删除配置文件。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIProfileFunctions.cpp  <br/> |HrRemoveProfile  <br/> |MFCMAPI 使用**IProfAdmin::DeleteProfile**方法删除选定的配置文件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::DeleteMsgService](imsgserviceadmin-deletemsgservice.md)
  
[MSGSERVICEENTRY](msgserviceentry.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

