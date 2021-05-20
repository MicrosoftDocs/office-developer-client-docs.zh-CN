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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a3469e6baacb52938b870ca87d824bf640a8a88f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439483"
---
# <a name="ixplogonvalidatestate"></a>IXPLogon::ValidateState

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检查传输提供程序的外部状态。 
  
```cpp
HRESULT ValidateState(
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。
    
 _ulFlags_
  
> [in]控制状态检查执行方式和状态检查结果的标志的位掩码。 可以设置以下标志：
    
ABORT_XP_HEADER_OPERATION 
  
> 用户通常通过单击对话框中的"取消" **按钮来取消** 操作。 传输提供程序可以选择继续操作，也可以中止操作并返回MAPI_E_USER_CANCELED。 
    
CONFIG_CHANGED 
  
> 通过使 MAPI 后台处理程序调用其 [IXPLogon：：AddressTypes](ixplogon-addresstypes.md) 方法，验证当前加载的传输提供程序的状态。 此标志还为 MAPI 后台处理程序提供了更正关键传输提供程序故障的机会，而无需强制客户端应用程序注销然后重新登录。 
    
FORCE_XP_CONNECT 
  
> 用户选择了连接操作。 当此标志与 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 标志一起使用时，将执行连接操作而不进行缓存。
    
FORCE_XP_DISCONNECT 
  
> 用户选择了断开连接操作。 当此标志与 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 一PROCESS_XP_HEADER_CACHE时，将执行断开连接操作，而不进行缓存。
    
PROCESS_XP_HEADER_CACHE 
  
> 应处理邮件头缓存表中的条目，应下载标有 MSGSTATUS_REMOTE_DOWNLOAD 标志的所有邮件，并删除标记有 MSGSTATUS_REMOTE_DELETE 标志的所有邮件。 应移动同时MSGSTATUS_REMOTE_DOWNLOAD和MSGSTATUS_REMOTE_DELETE的邮件。
    
REFRESH_XP_HEADER_CACHE 
  
> 应下载新的邮件头列表，并清除所有邮件状态标记标志。
    
SUPPRESS_UI 
  
> 阻止传输提供程序显示用户界面。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作;应允许其完成，或者应在尝试此操作之前停止。
    
MAPI_E_NO_SUPPORT 
  
> 涉及的远程传输提供程序不支持用户界面，客户端应用程序本身应显示对话框。
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消" **按钮来取消** 操作。 
    
## <a name="remarks"></a>备注

MAPI 后台处理程序调用 **IXPLogon：：ValidateState** 方法以支持对状态对象的 [IMAPIStatus：：ValidateState](imapistatus-validatestate.md) 方法的调用。 传输提供程序应完全响应 **IXPLogon：：ValidateState** 调用，就像 MAPI 后台处理程序打开了当前登录会话的状态对象，然后对该对象调用 **IMAPIStatus：：ValidateState** 一样。 
  
为了支持 **IMAPIStatus：：ValidateState** 的实现，MAPI 后台处理程序对在配置文件会话中运行的所有活动传输提供程序的所有登录对象调用 **IXPLogon：：ValidateState。** 
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus::ValidateState](imapistatus-validatestate.md)
  
[IXPLogon::AddressTypes](ixplogon-addresstypes.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

