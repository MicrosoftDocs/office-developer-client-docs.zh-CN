---
title: IMsgServiceAdminConfigureMsgService
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.ConfigureMsgService
api_type:
- COM
ms.assetid: a08f5905-2585-49ca-abb7-a77f2736f604
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f58d0f5cd7dfe74d3859d4f06a41aad6c3a55ac4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775828"
---
# <a name="imsgserviceadminconfiguremsgservice"></a>IMsgServiceAdmin::ConfigureMsgService

  
  
**适用于**： Outlook 
  
重新配置的消息服务。
  
```cpp
HRESULT ConfigureMsgService(
  LPMAPIUID lpUID,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  ULONG cValues,
  LPSPropValue lpProps
);
```

## <a name="parameters"></a>参数

 _lpUID_
  
> [in]一个指向[MAPIUID](mapiuid.md)结构，其中包含要配置的消息服务的唯一标识符。 
    
 _ulUIParam_
  
> [in]配置属性表的父窗口句柄。
    
 _ulFlags_
  
> [in]位掩码的标志的控件显示的属性表。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。
    
MSG_SERVICE_UI_READ_ONLY 
  
> 邮件服务应显示其配置属性表，但不是使用户能够更改它。 大多数消息服务忽略此标志。
    
SERVICE_UI_ALLOWED 
  
> 邮件服务应显示其配置属性表，仅当不完全配置该服务。
    
SERVICE_UI_ALWAYS 
  
> 邮件服务必须始终显示其配置属性表。 如果未设置 SERVICE_UI_ALWAYS，配置属性表可以仍显示如果 SERVICE_UI_ALLOWED 设置且_lpProps_参数中的属性值数组中没有有效的配置信息。 SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 必须为要显示的属性表。 
    
 _cValues_
  
> [in]由_lpProps_指向[SPropValue](spropvalue.md)结构中的属性值的计数。 
    
 _lpProps_
  
> [in]一个指向介绍要在属性表中显示的属性的属性值的数组。 如果邮件服务应配置的用户界面的情况下， _lpProps_参数不应为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功配置邮件服务。
    
MAPI_E_EXTENDED_ERROR 
  
> 特定于邮件服务返回一个错误。 若要获取描述错误的[MAPIERROR](mapierror.md)结构，客户端应用程序应调用[IMsgServiceAdmin::GetLastError](imsgserviceadmin-getlasterror.md)方法。 
    
MAPI_E_NOT_FOUND 
  
> 所指的_lpUID_ **MAPIUID**不匹配的现有邮件服务。 
    
MAPI_E_NOT_INITIALIZED 
  
> 邮件服务没有入口点函数。
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击属性表中的**取消**按钮。 
    
## <a name="remarks"></a>说明

**IMsgServiceAdmin::ConfigureMsgService**方法使邮件服务能够使用或不配置属性表进行配置。 
  
若要允许没有属性表显示配置，消息服务通常准备标头文件，其中包括所有必需的和可选属性以及它们的值的常量。
  
## <a name="notes-to-callers"></a>给调用方的说明

若要检索要配置的消息服务的**MAPIUID**结构，请从邮件服务表中的消息服务的行中检索**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列。 有关详细信息，请参阅[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)方法中概述的过程。 
  
您可以配置邮件服务，而不向用户显示属性表，仅当您具有要设置的属性值的高级信息。 如果您要配置的消息服务，而不显示属性表、 _lpProps_参数中传递有效的属性值和未设置 MSG_SERVICE_UI_READ_ONLY，SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 的标志。 
  
如果您收到来自用户通过属性表的全部或部分的配置信息，请在_ulFlags_中设置 SERVICE_UI_ALLOWED。 如果您使用现有的属性信息仅用于默认设置，并且用户能够更改的设置，请在_ulFlags_中设置 SERVICE_UI_ALWAYS。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIProfileFunctions.cpp  <br/> |HrAddServiceToProfile  <br/> |MFCMAPI 使用**IMsgServiceAdmin::ConfigureMsgService**方法配置已添加到一个配置文件服务。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[SPropValue](spropvalue.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

