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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410180"
---
# <a name="imsgserviceadmin2createmsgserviceex"></a>IMsgServiceAdmin2::CreateMsgServiceEx

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件服务添加到当前配置文件，并返回新添加的服务 UID。
  
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
  
> [in]指向要添加的邮件服务的名称的指针。 此消息服务名称必须出现在 MapiSvc.inf 文件的 **[Services]** 部分中。 
    
 _lpszDisplayName_
  
> [in]指向要显示名称的消息服务对象的指针。 如果邮件服务在 MapiSvc.inf 文件中设置了 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性，则 _忽略 lpszDisplayName_ 参数。
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。
    
 _ulFlags_
  
> [in]控制邮件服务的安装方式的标志的位掩码。 可以设置以下标志：
    
MAPI_UNICODE
  
> lpszService 和 lpszDisplayName 参数应转换为 LPWSTR，并解释为 Unicode 字符串。
    
SERVICE_NO_RESTART_WARNING
  
> 向配置文件添加新邮件服务时，MAPI 子系统根据各种情形和条件通常确定此操作需要重新启动 Outlook。 如果未包括 SERVICE_NO_RESTART_WARNING 标志，并且允许 UI（基于 SERVICE_UI_ALWAYS 和 SERVICE_UI_ALLOWED 标志）并且至少有一个进程已登录到当前配置文件，则此函数将显示消息"必须重新启动 Outlook，这些更改才能生效"。 包括 SERVICE_NO_RESTART_WARNING 标志将禁止显示该警告消息。
    
SERVICE_UI_ALLOWED
  
> 如果需要，允许使用邮件服务配置 UI。
    
SERVICE_UI_ALWAYS
  
> 邮件服务显示其配置属性表。
    
 _lpuidService_
  
> [out]指向已添加的消息服务的 UID 的指针。
    
## <a name="return-value"></a>返回值

S_OK
  
> 调用成功并返回了预期值。
    
MAPI_E_NOT_FOUND
  
> 邮件服务名称不在 MapiSvc.inf **的 [Services]** 部分中。 
    
## <a name="remarks"></a>备注

**IMsgServiceAdmin2：：CreateMsgServiceEx** 方法向当前配置文件添加邮件服务。 **CreateMsgServiceEx** 调用邮件服务的入口点函数来执行任何特定于服务的配置任务。 如果在  _ulFlags_ 参数中设置了 SERVICE_UI_ALLOWED 标志，则所安装的邮件服务可以显示属性表用户配置其设置的信息。 
  
MapiSvc.inf 文件包含一个提供程序列表，这些提供程序包含一个邮件服务以及每个提供程序的属性。 **CreateMsgServiceEx** 首先为邮件服务创建新的配置文件节，然后将该服务的所有信息从 MapiSvc.inf 文件复制到配置文件中，并为每个提供程序创建新节。 
  
从 MapiSvc.inf 复制所有信息后，使用 _ulContext_ 参数中设置的 MSG_SERVICE_CREATE 值调用邮件服务的入口点函数 **MSGSERVICEENTRY。** 如果在 **CreateMsgServiceEx** 方法的  _ulFlags_ 参数中设置了 SERVICE_UI_ALLOWED 标志，则调用邮件服务的入口点函数时，也会传递  _ulUIParam_ 和  _ulFlags_ 参数中的值。 服务提供商应显示其配置属性表，以便用户可以配置邮件服务。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果 **CreateMsgServiceEx** _lpuidService_ 参数不为 NULL，则添加到配置文件的邮件服务的 **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性在它指向的 **GUID** 中返回。 
  
将 _lpuidService_ 参数 **中 PR_SERVICE_UID** 属性的值传递到 [IMsgServiceAdmin：：ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法以配置该服务。 
  
> [!CAUTION]
> MAPI Microsoft Outlook 2010的实现不支持MAPI_UNICODE并且使用时将失败。 
  
> [!IMPORTANT]
> IMsgServiceAdmin2 接口由实现 IMsgServiceAdmin 接口的同一对象公开，并且自 Outlook 2003 以来，已使用 Outlook 的 MAPI 子系统实现提供。 其 IID 定义如下：>> `#if !defined(INITGUID) || defined(USES_IID_IMsgServiceAdmin2)` >   `DEFINE_OLEGUID(IID_IMsgServiceAdmin2,0x00020387, 0, 0);` _ulFlags_ SERVICE_NO_RESTART_WARNING 可能未在当前具有的可下载头文件中定义，在这种情况下，您可以使用以下值将其添加到代码中：>`#define SERVICE_NO_RESTART_WARNING 0x00000080`
  
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin2 : IMsgServiceAdmin](imsgserviceadmin2imsgserviceadmin.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

