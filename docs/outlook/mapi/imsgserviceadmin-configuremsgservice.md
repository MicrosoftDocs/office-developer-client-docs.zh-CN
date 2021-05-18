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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422185"
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
  
> [in]指向 [MAPIUID](mapiuid.md) 结构的指针，其中包含要配置的邮件服务的唯一标识符。 
    
 _ulUIParam_
  
> [in]配置窗口的父窗口的属性表。
    
 _ulFlags_
  
> [in]控制屏幕显示的标志的位掩码属性表。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 传入字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
MSG_SERVICE_UI_READ_ONLY 
  
> 邮件服务应显示其配置属性表但不允许用户更改它。 大多数邮件服务会忽略此标志。
    
SERVICE_UI_ALLOWED 
  
> 邮件服务应仅在服务属性表配置时显示其配置。
    
SERVICE_UI_ALWAYS 
  
> 邮件服务必须始终显示其配置属性表。 如果未SERVICE_UI_ALWAYS，如果属性表设置 SERVICE_UI_ALLOWED，并且  _lpProps_ 参数中的属性值数组中未提供有效的配置信息，则仍可显示配置信息。 必须SERVICE_UI_ALLOWED或SERVICE_UI_ALWAYS设置选项，属性表显示内容。 
    
 _cValues_
  
> [in] [SPropValue](spropvalue.md) 结构中由  _lpProps_ 指向的属性值计数。 
    
 _lpProps_
  
> [in]指向属性值数组的指针，这些属性值描述要显示在属性表。 如果应在没有用户界面的情况下配置邮件服务，则  _lpProps_ 参数不应为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功配置邮件服务。
    
MAPI_E_EXTENDED_ERROR 
  
> 特定于邮件服务的错误。 若要获取描述错误的 [MAPIERROR](mapierror.md) 结构，客户端应用程序应调用 [IMsgServiceAdmin：：GetLastError](imsgserviceadmin-getlasterror.md) 方法。 
    
MAPI_E_NOT_FOUND 
  
> _lpUID_ 指向的 **MAPIUID** 与现有邮件服务不匹配。 
    
MAPI_E_NOT_INITIALIZED 
  
> 邮件服务没有入口点功能。
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击"取消"按钮来取消属性表。  
    
## <a name="remarks"></a>备注

**IMsgServiceAdmin：：ConfigureMsgService** 方法使邮件服务可以配置，也可以不配置属性表。 
  
为了允许在不显示属性表配置，邮件服务通常会准备一个头文件，其中包含所有必需和可选属性及其值的常量。
  
## <a name="notes-to-callers"></a>给调用方的说明

若要检索要配置的邮件服务的 **MAPIUID** 结构，请从邮件服务表中邮件服务的行中检索 **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列。 有关详细信息，请参阅 [IMsgServiceAdmin：：CreateMsgService 方法中概述](imsgserviceadmin-createmsgservice.md) 的过程。 
  
只有在有要设置的属性值的预先信息属性表，才能配置邮件服务，而不向用户显示通知。 如果要配置邮件服务而不显示 属性表，请传递  _lpProps_ 参数中的有效属性值，并且不要设置 MSG_SERVICE_UI_READ_ONLY、SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 标志。 
  
如果您通过安装方法从用户收到所有或部分配置信息，属性表  _ulFlags_ SERVICE_UI_ALLOWED设置配置信息。 如果您使用现有属性信息来建立默认设置，并且用户能够更改设置，则SERVICE_UI_ALWAYS  _ulFlags_ 中。
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProfileFunctions.cpp  <br/> |HrAddServiceToProfile  <br/> |MFCMAPI 使用 **IMsgServiceAdmin：：ConfigureMsgService** 方法配置已添加到配置文件的服务。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[SPropValue](spropvalue.md)
  
[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

