---
title: IProfAdminCreateProfile
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.CreateProfile
api_type:
- COM
ms.assetid: 10cda14a-8f93-41e0-b1fb-500098bdc392
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b104c62eb617e6c68f85dea4ef6379c831733844
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404398"
---
# <a name="iprofadmincreateprofile"></a>IProfAdmin::CreateProfile

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建新的配置文件。
  
```cpp
HRESULT CreateProfile(
  LPSTR lpszProfileName,
  LPSTR lpszPassword,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpszProfileName_
  
> 实时指向新配置文件的名称的指针。
    
 _lpszPassword_
  
> 实时指向新配置文件的密码的指针。 
    
 _ulUIParam_
  
> 实时此方法显示的任何对话框或窗口的父窗口的句柄。
    
 _ulFlags_
  
> 实时用于控制如何创建配置文件的标志的位掩码。 可以设置以下标志:
    
MAPI_DEFAULT_SERVICES 
  
> MAPI 应使用包含在 mapisvc.inf 文件的 [默认服务] 部分中的邮件服务来填充新配置文件。
    
MAPI_DIALOG 
  
> 可以显示要添加的邮件服务中每个提供程序的配置属性表。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已创建新的配置文件。
    
MAPI_E_NO_ACCESS 
  
> 指定的新配置文件已存在。
    
## <a name="remarks"></a>说明

**IProfAdmin:: CreateProfile**方法创建一个新的配置文件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以在应用程序安装时或在会话过程中的任何时间调用**CreateProfile** 。 在安装时调用此方法时, 许多配置设置来自 mapisvc.inf 配置文件。 在活动会话过程中调用此方法时, 这些设置将来自通过一系列属性表提示的用户。 
  
如果在_ulFlags_参数中设置了 MAPI_DEFAULT_SERVICES 标志, 则**CreateProfile**会为 mapisvc.inf 文件中的 [默认服务] 部分中的每个邮件服务调用邮件服务入口点函数。 调用每个邮件服务入口点函数时, _ulContext_参数设置为 MSG_SERVICE_CREATE。 
  
如果同时设置了 MAPI_DIALOG 和 MAPI_DEFAULT_SERVICES 标志, 则_ulUIParam_和_ulFlags_参数中的值也会传递给邮件服务入口点函数。 仅在将 mapisvc.inf 文件中的所有可用信息添加到配置文件后, 才会调用邮件服务入口点函数。 
  
新配置文件的名称及其密码的长度最长为64个字符, 并且可以包含以下字符:
  
- 所有字母数字字符, 包括重音字符和下划线字符。
    
- 嵌入空格, 但不能是前导空格或尾随空格。
    
_lpszPassword_参数必须为 NULL 或指向零长度字符串的指针。 
  
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)
  
[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)
  
[MSGSERVICEENTRY](msgserviceentry.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)

