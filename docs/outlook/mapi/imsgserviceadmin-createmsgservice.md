---
title: IMsgServiceAdminCreateMsgService
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgServiceAdmin.CreateMsgService
api_type:
- COM
ms.assetid: 0135f049-0311-45e5-9685-78597d599a4e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e7d30c1aba8ddc1419045c1caa8524f7d2063dc5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434975"
---
# <a name="imsgserviceadmincreatemsgservice"></a>IMsgServiceAdmin::CreateMsgService

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
弃用: 建议使用[IMsgServiceAdmin2:: CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md) 。 向当前配置文件添加邮件服务。 
  
```cpp
HRESULT CreateMsgService(
  LPSTR lpszService,
  LPSTR lpszDisplayName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags    
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
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_NOT_FOUND 
  
> 邮件服务名称不在 mapisvc.inf 的 "**服务**" 部分中。 
    
## <a name="remarks"></a>说明

**IMsgServiceAdmin:: CreateMsgService**方法将邮件服务添加到当前配置文件中。 **CreateMsgService**调用邮件服务的入口点函数以执行任何特定于服务的配置任务。 如果在_ulFlags_参数中设置了 SERVICE_UI_ALLOWED 标志, 则要安装的邮件服务可以显示属性表以使用户能够配置其设置。 
  
mapisvc.inf 文件包含组成邮件服务的提供程序的列表以及每个提供程序的属性。 **CreateMsgService**首先为邮件服务创建一个新的配置文件部分, 然后将该服务的所有信息从 mapisvc.inf 文件复制到配置文件中, 为每个提供程序创建新的分区。 
  
从 mapisvc.inf 复制所有信息后, 将使用_ulContext_参数中设置的 MSG_SERVICE_CREATE 值调用邮件服务的入口点函数。 如果在**CreateMsgService**方法的_ulFlags_参数中设置了 SERVICE_UI_ALLOWED 标志, 则在调用邮件服务的入口点函数时, 也会传递_ulUIParam_和_ulFlags_参数中的值。 服务提供商应显示其配置属性表, 以便用户可以配置邮件服务。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **CreateMsgService**不会为已添加到配置文件中的邮件服务返回[MAPIUID](mapiuid.md)结构。 
  
若要检索创建的邮件服务的**MAPIUID** , 请使用以下过程: 
  
1. 调用[IMsgServiceAdmin:: GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)方法以获取邮件服务管理表。 
    
2. 通过在与**PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) 属性与邮件服务名称相匹配的表上放置限制, 找到表示邮件服务的行。 
    
3. 检索服务的**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性。 
    
4. 将_lpUid_参数中的**PR_SERVICE_UID**属性的值传递给[IMsgServiceAdmin:: ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法以配置服务。 
    
> [!CAUTION]
> MAPI 子系统的 Microsoft Outlook 2010 实现不支持 MAPI_UNICODE, 如果使用, 将会失败。 
  
> [!IMPORTANT]
> _ulFlags_ SERVICE_NO_RESTART_WARNING 可能未在您当前拥有的可下载头文件中定义, 在这种情况下, 您可以使用以下值将其添加到代码中: >`#define SERVICE_NO_RESTART_WARNING 0x00000080`
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIProfileFunctions  <br/> |HrAddServiceToProfile  <br/> |MFCMAPI 使用**IMsgServiceAdmin:: CreateMsgService**方法将服务添加到配置文件中。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

