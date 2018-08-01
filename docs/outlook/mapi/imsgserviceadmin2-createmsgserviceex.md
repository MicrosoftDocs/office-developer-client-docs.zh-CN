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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3aae61f7b21c507da7955dbb4393d13bfb5fa24c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775850"
---
# <a name="imsgserviceadmin2createmsgserviceex"></a>IMsgServiceAdmin2::CreateMsgServiceEx

  
  
**适用于**： Outlook 
  
向当前配置文件和新添加的服务 UID 的返回的消息服务。
  
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
  
> [in]一个指向要添加的消息服务的名称。 此消息服务名称必须出现在 MapiSvc.inf 文件的 **[服务]** 节中。 
    
 _lpszDisplayName_
  
> [in]指向要添加的消息服务的显示名称的指针。 如果邮件服务具有 MapiSvc.inf 文件中设置**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性，则忽略_lpszDisplayName_参数。
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何安装邮件服务。 可以设置以下标志：
    
MAPI_UNICODE
  
> LpszService 和 lpszDisplayName 参数应强制转换为 LPWSTR 和解释为 Unicode 字符串。
    
SERVICE_NO_RESTART_WARNING
  
> 添加到配置文件的新消息服务时, MAPI 子系统，基于各种情况和条件，通常决定了此操作需要重新启动 Outlook。 如果 SERVICE_NO_RESTART_WARNING 标志不包括允许用户界面-基于 SERVICE_UI_ALWAYS 和 SERVICE_UI_ALLOWED 标志-和至少一个过程登录当前配置文件，此函数显示消息"您必须重新启动 Outlook这些更改才会生效。" 包括 SERVICE_NO_RESTART_WARNING 标志禁止显示该警告消息。
    
SERVICE_UI_ALLOWED
  
> 消息服务配置根据需要允许 UI。
    
SERVICE_UI_ALWAYS
  
> 邮件服务显示其配置属性表。
    
 _lpuidService_
  
> [输出]指向的 UID 添加消息服务的指针。
    
## <a name="return-value"></a>返回值

S_OK
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_NOT_FOUND
  
> 消息服务名称不在的 MapiSvc.inf **[服务]** 部分。 
    
## <a name="remarks"></a>说明

**IMsgServiceAdmin2::CreateMsgServiceEx**方法将消息服务添加到当前配置文件。 **CreateMsgServiceEx**调用消息服务的入口点函数，以执行任何特定于服务的配置任务。 如果_ulFlags_参数中设置 SERVICE_UI_ALLOWED 标志，指示正在安装该消息服务可以显示使用户可以配置其设置的属性表。 
  
MapiSvc.inf 文件包含每个组成的消息服务和属性的提供程序的列表。 **CreateMsgServiceEx**首先创建新的配置文件部分消息服务，然后复制该服务的信息的所有从 MapiSvc.inf 文件到配置文件，为每个提供程序创建新的部分。 
  
已从 MapiSvc.inf 复制所有信息后，该消息服务的入口点函数， **MSGSERVICEENTRY**，使用_ulContext_参数中设置的 MSG_SERVICE_CREATE 值调用。 如果**CreateMsgServiceEx**方法的_ulFlags_参数中设置 SERVICE_UI_ALLOWED 标志，消息服务的入口点函数调用时还传递的_ulUIParam_和_ulFlags_参数中的值。 服务提供商应显示其配置属性表，以便用户可以配置邮件服务。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果**CreateMsgServiceEx** _lpuidService_参数不是 NULL，邮件服务已添加到配置文件的**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性将返回它指向的**GUID** 。 
  
将**PR_SERVICE_UID**属性的值_lpuidService_参数中传递给[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法，以配置服务。 
  
> [!CAUTION]
> Microsoft Outlook 2010 实现的 MAPI 子系统不支持 MAPI_UNICODE，如果使用它将失败。 
  
> [!IMPORTANT]
> IMsgServiceAdmin2 接口将公开相同对象实现 IMsgServiceAdmin 接口，并已可使用的 MAPI 子系统相 Outlook 2003 的 Outlook 的实现。 其 IID，如下所示定义： > `#if !defined(INITGUID) || defined(USES_IID_IMsgServiceAdmin2)` >   `DEFINE_OLEGUID(IID_IMsgServiceAdmin2,0x00020387, 0, 0);`> _ulFlags_ SERVICE_NO_RESTART_WARNING 可能未定义当前具有可下载头文件中，在这种情况下您可以将其添加到代码中使用以下值： >`#define SERVICE_NO_RESTART_WARNING 0x00000080`
  
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin2 : IMsgServiceAdmin](imsgserviceadmin2imsgserviceadmin.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

