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
ms.openlocfilehash: 8aafb849a98028efb37646752a7b49fa5e6ef2ff
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419588"
---
# <a name="iprofadmindeleteprofile"></a>IProfAdmin::DeleteProfile

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
删除配置文件。
  
```cpp
HRESULT DeleteProfile(
  LPSTR lpszProfileName,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpszProfileName_
  
> [in]指向要删除的配置文件的名称的指针。
    
 _ulFlags_
  
> [in]始终为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功删除配置文件。
    
MAPI_E_NOT_FOUND 
  
> 指定的配置文件不存在。
    
## <a name="remarks"></a>备注

**IProfAdmin：:D eleteProfile** 方法删除配置文件。 如果在调用 **DeleteProfile** 时要使用要删除的配置文件 **，DeleteProfile** S_OK但不会立即删除该配置文件。 但 **DeleteProfile** 会标记配置文件进行删除，并在其所有活动会话结束时在不再使用配置文件后将其删除。 
  
使用  _ulContext_ 参数中设置的 MSG_SERVICE_DELETE 调用配置文件中每个邮件服务的入口点函数。 首先，函数删除服务，然后删除服务的配置文件部分。 在删除邮件服务后，不会再次调用邮件服务入口点函数。 
  
删除配置文件不需要密码。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProfileFunctions.cpp  <br/> |HrRemoveProfile  <br/> |MFCMAPI 使用 **IProfAdmin：:D eleteProfile** 方法删除所选的配置文件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::DeleteMsgService](imsgserviceadmin-deletemsgservice.md)
  
[MSGSERVICEENTRY](msgserviceentry.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

