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
ms.openlocfilehash: 87ac394f9ab77b092cdfcd44f65b040a039319e7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317407"
---
# <a name="imsgserviceadminconfiguremsgservice"></a>IMsgServiceAdmin::ConfigureMsgService

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
重新配置邮件服务。
  
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
  
> 实时指向[MAPIUID](mapiuid.md)结构的指针, 该结构包含要配置的邮件服务的唯一标识符。 
    
 _ulUIParam_
  
> 实时配置属性表的父窗口的句柄。
    
 _ulFlags_
  
> 实时用于控制属性表的显示的标志的位掩码。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 传入的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
MSG_SERVICE_UI_READ_ONLY 
  
> 邮件服务应显示其配置属性表, 但不允许用户对其进行更改。 大多数邮件服务都会忽略此标志。
    
SERVICE_UI_ALLOWED 
  
> 仅当未完全配置服务时, 邮件服务才应显示其配置属性表。
    
SERVICE_UI_ALWAYS 
  
> 邮件服务必须始终显示其 "配置" 属性表。 如果未设置 SERVICE_UI_ALWAYS, 则在设置 SERVICE_UI_ALLOWED 并在_lpProps_参数的属性值数组中不提供有效的配置信息时, 仍可以显示配置属性表。 必须设置 SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS, 才能显示属性表。 
    
 _cValues_
  
> 实时由_lpProps_指向的[SPropValue](spropvalue.md)结构中的属性值的计数。 
    
 _lpProps_
  
> 实时指向描述要在属性表中显示的属性的属性值数组的指针。 如果应在不使用用户界面的情况下配置邮件服务, 则_lpProps_参数不应为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件服务已成功配置。
    
MAPI_E_EXTENDED_ERROR 
  
> 特定于邮件服务的错误。 若要获取描述错误的[MAPIERROR](mapierror.md)结构, 客户端应用程序应调用[IMsgServiceAdmin:: GetLastError](imsgserviceadmin-getlasterror.md)方法。 
    
MAPI_E_NOT_FOUND 
  
> lpUID 指向的**MAPIUID**与现有邮件服务的__ 不匹配。 
    
MAPI_E_NOT_INITIALIZED 
  
> 邮件服务没有入口点函数。
    
MAPI_E_USER_CANCEL 
  
> 用户取消了操作, 通常是单击属性表中的 "**取消**" 按钮。 
    
## <a name="remarks"></a>注解

**IMsgServiceAdmin:: ConfigureMsgService**方法允许使用或不使用配置属性表来配置邮件服务。 
  
若要允许在不显示属性表的情况下进行配置, 邮件服务通常准备一个头文件, 其中包含所有必需属性和可选属性及其值的常量。
  
## <a name="notes-to-callers"></a>给调用方的说明

若要检索要配置的邮件服务的**MAPIUID**结构, 请从邮件服务表中的邮件服务行检索**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列。 有关详细信息, 请参阅[IMsgServiceAdmin:: CreateMsgService](imsgserviceadmin-createmsgservice.md)方法中概述的过程。 
  
只有在您具有有关要设置的属性值的高级信息的情况下, 才能将邮件服务配置为不向用户显示属性表。 如果要配置邮件服务而不显示属性表, 请在_lpProps_参数中传递有效的属性值, 不要设置 MSG_SERVICE_UI_READ_ONLY、SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 标志。 
  
如果通过属性表从用户处接收全部或部分配置信息, 请在_ulFlags_中设置 SERVICE_UI_ALLOWED。 如果您仅使用现有属性信息来建立默认设置, 并且用户能够更改设置, 请在_ulFlags_中设置 SERVICE_UI_ALWAYS。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProfileFunctions  <br/> |HrAddServiceToProfile  <br/> |MFCMAPI 使用**IMsgServiceAdmin:: ConfigureMsgService**方法配置已添加到配置文件中的服务。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[SPropValue](spropvalue.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

