---
title: IMsgServiceAdmin2CreateMsgServiceEx
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin2.CreateMsgServiceEx
api_type:
- COM
ms.assetid: 4910dabd-9380-4fde-a440-5c64d74c0bba
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b7fe25491228f00f6865af963db36f27bae5d7a7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310008"
---
# <a name="imsgserviceadmin2createmsgserviceex"></a>IMsgServiceAdmin2::CreateMsgServiceEx

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件服务添加到当前配置文件, 并返回新添加的服务 UID。
  
```cpp
HRESULT CreateMsgServiceEx(
  LPSTR lpszService,
  LPSTR lpszDisplayName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags,    
  LPMAPIUID lpuidService
);
```

## <a name="parameters"></a>参数

 _lpszService_
  
> 实时指向要添加的邮件服务的名称的指针。 此邮件服务名称必须出现在 mapisvc.inf 文件的 "**服务**" 部分中。 
    
 _lpszDisplayName_
  
> 实时指向要添加的邮件服务的显示名称的指针。 如果邮件服务已在 mapisvc.inf 文件中设置了**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性, 则会忽略_lpszDisplayName_参数。
    
 _ulUIParam_
  
> 实时此方法显示的任何对话框或窗口的父窗口的句柄。
    
 _ulFlags_
  
> 实时用于控制如何安装邮件服务的标志的位掩码。 可以设置以下标志:
    
MAPI_UNICODE
  
> 应将 lpszService 和 lpszDisplayName 参数强制转换为 LPWSTR, 并将其解释为 Unicode 字符串。
    
SERVICE_NO_RESTART_WARNING
  
> 将新的邮件服务添加到配置文件时, 基于各种情况和标准的 MAPI 子系统通常会确定此操作需要重新启动 Outlook。 如果不包含 SERVICE_NO_RESTART_WARNING 标志且允许 UI (基于 SERVICE_UI_ALWAYS 和 SERVICE_UI_ALLOWED 标志), 并且至少有一个进程登录到当前配置文件, 则此函数将显示消息 "您必须重新启动 Outlook for这些更改才能生效。 " 包括 SERVICE_NO_RESTART_WARNING 标志禁止显示该警告消息。
    
SERVICE_UI_ALLOWED
  
> 如果需要, 允许使用邮件服务配置 UI。
    
SERVICE_UI_ALWAYS
  
> 邮件服务显示其配置属性表。
    
 _lpuidService_
  
> 排除指向添加的邮件服务的 UID 的指针。
    
## <a name="return-value"></a>返回值

S_OK
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_NOT_FOUND
  
> 邮件服务名称不在 mapisvc.inf 的 "**服务**" 部分中。 
    
## <a name="remarks"></a>注解

**IMsgServiceAdmin2:: CreateMsgServiceEx**方法将邮件服务添加到当前配置文件中。 **CreateMsgServiceEx**调用邮件服务的入口点函数以执行任何特定于服务的配置任务。 如果在_ulFlags_参数中设置了 SERVICE_UI_ALLOWED 标志, 则要安装的邮件服务可以显示一个属性表, 使用户可以配置其设置。 
  
mapisvc.inf 文件包含组成邮件服务的提供程序的列表以及每个提供程序的属性。 **CreateMsgServiceEx**首先为邮件服务创建一个新的配置文件部分, 然后将该服务的所有信息从 mapisvc.inf 文件复制到配置文件中, 为每个提供程序创建新的分区。 
  
从 mapisvc.inf 复制完所有信息后, 将使用_ulContext_参数中设置的 MSG_SERVICE_CREATE 值调用邮件服务的入口点函数**MSGSERVICEENTRY**。 如果在**CreateMsgServiceEx**方法的_ulFlags_参数中设置了 SERVICE_UI_ALLOWED 标志, 则在调用邮件服务的入口点函数时, 也会传递_ulUIParam_和_ulFlags_参数中的值。 服务提供商应显示其配置属性表, 以便用户可以配置邮件服务。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果**CreateMsgServiceEx** _lpuidService_参数不为 NULL, 则添加到配置文件中的邮件服务的**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性将在它所指向的**GUID**中返回。 
  
将_lpuidService_参数中的**PR_SERVICE_UID**属性的值传递给[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法以配置服务。 
  
> [!CAUTION]
> MAPI 子系统的 Microsoft Outlook 2010 实现不支持 MAPI_UNICODE, 如果使用, 将会失败。 
  
> [!IMPORTANT]
> IMsgServiceAdmin2 接口由实现 IMsgServiceAdmin 接口的同一对象公开, 并已在 outlook 2003 后使用 outlook 的 MAPI 子系统实现提供。 其 IID `#if !defined(INITGUID) || defined(USES_IID_IMsgServiceAdmin2)` >   `DEFINE_OLEGUID(IID_IMsgServiceAdmin2,0x00020387, 0, 0);`定义如下: > > _ulFlags_ SERVICE_NO_RESTART_WARNING 可能未在您当前拥有的可下载头文件中定义, 在这种情况下, 您可以使用以下值将其添加到代码中: >`#define SERVICE_NO_RESTART_WARNING 0x00000080`
  
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin2 : IMsgServiceAdmin](imsgserviceadmin2imsgserviceadmin.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

