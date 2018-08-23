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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 92d5dcdf3e5e3fbdb7490d777a24976c9ae4af1a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582789"
---
# <a name="iprofadmincreateprofile"></a>IProfAdmin::CreateProfile

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
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
  
> [in]一个指向新的配置文件的名称。
    
 _lpszPassword_
  
> [in]一个指向新的配置文件的密码。 
    
 _ulUIParam_
  
> [in]任何对话框的父窗口或该方法显示的窗口句柄。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何创建配置文件。 可以设置以下标志：
    
MAPI_DEFAULT_SERVICES 
  
> MAPI 应该填充 Mapisvc.inf 文件的 [默认服务] 节中包含了消息服务的新配置文件。
    
MAPI_DIALOG 
  
> 可显示每个中消息服务提供程序，要添加的配置属性工作表。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 创建新的配置文件。
    
MAPI_E_NO_ACCESS 
  
> 指定新的配置文件已存在。
    
## <a name="remarks"></a>注解

**IProfAdmin::CreateProfile**方法创建一个新的配置文件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在应用程序安装时或在会话过程中的任何时候，您可以调用**CreateProfile** 。 在安装时调用此方法，许多的配置设置将来自 Mapisvc.inf 配置文件。 当活动会话过程中调用此方法时，设置来自提示通过一系列的属性表的用户。 
  
如果_ulFlags_参数中设置 MAPI_DEFAULT_SERVICES 标志， **CreateProfile** Mapisvc.inf 文件中的 [默认服务] 一节中每个邮件服务调用消息服务入口点函数。 使用_ulContext_参数设置为 MSG_SERVICE_CREATE 调用每个邮件服务入口点函数。 
  
如果设置 MAPI_DIALOG 和 MAPI_DEFAULT_SERVICES 标志中的_ulUIParam_和_ulFlags_参数值还传递给消息服务入口点函数。 仅 Mapisvc.inf 文件中的所有可用信息添加到配置文件之后，也称为消息服务入口点函数。 
  
新的配置文件和其密码的名称的长度最多为 64 个字符，并可以包含下列字符：
  
- 所有字母数字字符，包括重音字符和下划线字符。
    
- 嵌入的空格，但不是前导或尾随空格。
    
_LpszPassword_参数必须为空或为零长度字符串的指针。 
  
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)
  
[IMsgServiceAdmin::CreateMsgService](imsgserviceadmin-createmsgservice.md)
  
[MSGSERVICEENTRY](msgserviceentry.md)
  
[IProfAdmin : IUnknown](iprofadminiunknown.md)

