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
  
> [in]指向新配置文件的名称的指针。
    
 _lpszPassword_
  
> [in]指向新配置文件的密码的指针。 
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。
    
 _ulFlags_
  
> [in]控制配置文件创建方式的标志的位掩码。 可以设置以下标志：
    
MAPI_DEFAULT_SERVICES 
  
> MAPI 应该使用 Mapisvc.inf 文件的 [默认服务] 部分中包含的邮件服务填充新配置文件。
    
MAPI_DIALOG 
  
> 可以显示要添加的邮件服务中每个提供程序的配置属性表。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已创建新配置文件。
    
MAPI_E_NO_ACCESS 
  
> 指定的新配置文件已存在。
    
## <a name="remarks"></a>备注

**IProfAdmin：：CreateProfile** 方法创建新的配置文件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以在应用程序安装时或在会话期间随时调用 **CreateProfile。** 在安装时调用此方法时，许多配置设置都来自 Mapisvc.inf 配置文件。 在活动会话期间调用此方法时，设置来自通过一系列属性表提示的用户。 
  
如果在  _ulFlags_ 参数中设置了 MAPI_DEFAULT_SERVICES 标志 **，CreateProfile** 将调用 Mapisvc.inf 文件的 [Default Services] 部分中每个邮件服务的邮件服务入口点函数。 调用每个邮件服务入口点函数时  _，ulContext_ 参数设置为 MSG_SERVICE_CREATE。 
  
如果同时设置了 MAPI_DIALOG 和 MAPI_DEFAULT_SERVICES 标志，  _则 ulUIParam_ 和  _ulFlags_ 参数中的值也会传递给邮件服务入口点函数。 仅在将 Mapisvc.inf 文件的所有可用信息添加到配置文件后，才调用邮件服务入口点函数。 
  
新配置文件的名称及其密码的长度最多为 64 个字符，可以包含下列字符：
  
- 所有字母数字字符，包括重音字符和下划线字符。
    
- 嵌入空格，但不包括前导或尾随空格。
    
_lpszPassword_ 参数必须为 NULL 或指向零长度字符串的指针。 
  
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)
  
[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)
  
[MSGSERVICEENTRY](msgserviceentry.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)

