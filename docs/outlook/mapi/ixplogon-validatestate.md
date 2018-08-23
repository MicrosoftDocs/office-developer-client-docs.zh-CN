---
title: IXPLogonValidateState
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.ValidateState
api_type:
- COM
ms.assetid: c3649daa-cba1-48e3-9ffb-069c1bcf8228
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4fd0dd02c5cf6f6a49b782d06c02e373dcfc3327
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577483"
---
# <a name="ixplogonvalidatestate"></a>IXPLogon::ValidateState

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
检查传输提供程序的外部状态。 
  
```cpp
HRESULT ValidateState(
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]任何对话框的父窗口或该方法显示的窗口句柄。
    
 _ulFlags_
  
> [in]控制如何执行状态检查的标志的位掩码和状态检查的结果。 可以设置以下标志：
    
ABORT_XP_HEADER_OPERATION 
  
> 用户取消操作，通常通过单击对话框中的**取消**按钮。 传输提供程序具有选项后，继续使用上一操作，或者可以中止操作并返回 MAPI_E_USER_CANCELED。 
    
CONFIG_CHANGED 
  
> MAPI 后台处理程序调用其[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法，从而验证当前加载的传输提供程序的状态。 此标志还提供 MAPI 后台处理程序而不强制注销并重新登录的客户端应用程序中更正关键的传输提供程序失败的机会。 
    
FORCE_XP_CONNECT 
  
> 用户选择一个连接操作。 此标志用于 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 标志，连接操作时不进行缓存。
    
FORCE_XP_DISCONNECT 
  
> 用户选择断开连接操作。 与 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 使用此标志，则断开连接操作时不进行缓存。
    
PROCESS_XP_HEADER_CACHE 
  
> 应处理标题缓存表中的条目，应下载标记有 MSGSTATUS_REMOTE_DOWNLOAD 标志的所有邮件，以及应删除与 MSGSTATUS_REMOTE_DELETE 标志标记的所有邮件。 应移动 MSGSTATUS_REMOTE_DOWNLOAD 和 MSGSTATUS_REMOTE_DELETE 设置的消息。
    
REFRESH_XP_HEADER_CACHE 
  
> 应下载邮件头的新列表，并应清除标记标志的所有邮件状态。
    
SUPPRESS_UI 
  
> 防止传输提供程序显示的用户界面。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
MAPI_E_BUSY 
  
> 正在进行; 另一个操作应允许其完成，或尝试此操作之前，应停止它。
    
MAPI_E_NO_SUPPORT 
  
> 所涉及的远程传输提供程序不支持用户界面，并在客户端应用程序自身应显示对话框。
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击对话框中的**取消**按钮。 
    
## <a name="remarks"></a>注解

MAPI 后台处理程序调用**IXPLogon::ValidateState**方法以支持的状态对象调用[IMAPIStatus::ValidateState](imapistatus-validatestate.md)方法。 传输提供程序应当给出答复到**IXPLogon::ValidateState**的呼叫就好像 MAPI 后台处理程序已打开了当前登录会话状态对象，然后在该对象上调用**IMAPIStatus::ValidateState** 。 
  
若要支持**IMAPIStatus::ValidateState**其实现，MAPI 后台处理程序调用**IXPLogon::ValidateState**登录的所有对象上为配置文件会话中运行的所有活动传输提供程序。 
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus::ValidateState](imapistatus-validatestate.md)
  
[IXPLogon::AddressTypes](ixplogon-addresstypes.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

