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
ms.openlocfilehash: 7c649680d1d04e210ac4d90779e9a4e57aaab25a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579863"
---
# <a name="imsgserviceadmincreatemsgservice"></a>IMsgServiceAdmin::CreateMsgService

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
不建议使用： 建议使用[IMsgServiceAdmin2::CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md) 。 向当前配置文件的消息服务。 
  
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
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_NOT_FOUND 
  
> 消息服务名称不在的 MapiSvc.inf **[服务]** 部分。 
    
## <a name="remarks"></a>注解

**IMsgServiceAdmin::CreateMsgService**方法将消息服务添加到当前配置文件。 **CreateMsgService**调用消息服务的入口点函数，以执行任何特定于服务的配置任务。 _UlFlags_参数中设置 SERVICE_UI_ALLOWED 标志，如果要安装的消息服务可以显示属性表可让用户能够配置其设置。 
  
MapiSvc.inf 文件包含每个组成的消息服务和属性的提供程序的列表。 **CreateMsgService**首先创建新的配置文件部分消息服务，然后复制该服务的信息的所有从 MapiSvc.inf 文件到配置文件，为每个提供程序创建新的部分。 
  
已从 MapiSvc.inf 复制所有信息后，使用_ulContext_参数中设置的 MSG_SERVICE_CREATE 值调用消息服务的入口点函数。 如果**CreateMsgService**方法的_ulFlags_参数中设置 SERVICE_UI_ALLOWED 标志，消息服务的入口点函数调用时还传递的_ulUIParam_和_ulFlags_参数中的值。 服务提供商应显示其配置属性表，以便用户可以配置邮件服务。 
  
## <a name="notes-to-callers"></a>给调用方的说明

 **CreateMsgService**不返回邮件服务已添加到配置文件的[MAPIUID](mapiuid.md)结构。 
  
若要检索**MAPIUID**创建的消息服务，请使用以下过程： 
  
1. 调用[IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)方法以获取邮件服务管理表。 
    
2. 找到表示邮件服务通过将限制放在表的**PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md)) 属性与消息服务的名称相匹配的行。 
    
3. 检索服务的**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性。 
    
4. 将**PR_SERVICE_UID**属性的值_lpUid_参数中传递给[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)方法，以配置服务。 
    
> [!CAUTION]
> Microsoft Outlook 2010 实现的 MAPI 子系统不支持 MAPI_UNICODE，如果使用它将失败。 
  
> [!IMPORTANT]
> _UlFlags_ SERVICE_NO_RESTART_WARNING 可能未定义当前具有可下载头文件中，在这种情况下您可以将其添加到代码中使用以下值： >`#define SERVICE_NO_RESTART_WARNING 0x00000080`
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIProfileFunctions.cpp  <br/> |HrAddServiceToProfile  <br/> |MFCMAPI 使用**IMsgServiceAdmin::CreateMsgService**方法向一个配置文件中添加服务。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

