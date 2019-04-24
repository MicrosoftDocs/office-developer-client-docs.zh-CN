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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351567"
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
  
> 实时此方法显示的任何对话框或窗口的父窗口的句柄。
    
 _ulFlags_
  
> 实时用于控制如何执行状态检查和状态检查结果的标志的位掩码。 可以设置以下标志:
    
ABORT_XP_HEADER_OPERATION 
  
> 用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。 传输提供程序可以选择继续处理此操作, 也可以中止操作并返回 MAPI_E_USER_CANCELED。 
    
CONFIG_CHANGED 
  
> 通过使 MAPI 后台处理程序调用[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法来验证当前加载的传输提供程序的状态。 此标志还为 MAPI 后台处理程序提供了在不强制客户端应用程序注销和重新登录的情况下纠正关键传输提供程序故障的机会。 
    
FORCE_XP_CONNECT 
  
> 用户选择了一个连接操作。 将此标志与 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 标志一起使用时, 将发生 connect 操作, 而不进行缓存。
    
FORCE_XP_DISCONNECT 
  
> 用户选择了一个断开连接操作。 将此标志与 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 一起使用时, 不进行缓存就会发生断开连接操作。
    
PROCESS_XP_HEADER_CACHE 
  
> 应处理标头缓存表中的条目, 应下载所有标记为 MSGSTATUS_REMOTE_DOWNLOAD 标志的邮件, 并且应删除所有使用 MSGSTATUS_REMOTE_DELETE 标志标记的邮件。 应移动同时包含 MSGSTATUS_REMOTE_DOWNLOAD 和 MSGSTATUS_REMOTE_DELETE 集的邮件。
    
REFRESH_XP_HEADER_CACHE 
  
> 应下载邮件头的新列表, 并且应清除所有邮件状态标记标志。
    
SUPPRESS_UI 
  
> 阻止传输提供程序显示用户界面。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作;应允许完成此操作, 否则应在尝试执行此操作之前将其停止。
    
MAPI_E_NO_SUPPORT 
  
> 涉及的远程传输提供程序不支持用户界面, 并且客户端应用程序本身应显示对话框。
    
MAPI_E_USER_CANCEL 
  
> 用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。 
    
## <a name="remarks"></a>注解

MAPI 后台处理程序调用**IXPLogon:: ValidateState**方法, 以支持对 status 对象的[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)方法的调用。 传输提供程序应将**IXPLogon:: ValidateState**调用完全按照 MAPI 后台处理程序打开当前登录会话的状态对象, 然后对该对象调用**IMAPIStatus:: ValidateState** 。 
  
若要支持**IMAPIStatus:: ValidateState**的实现, MAPI 后台处理程序将对在配置文件会话中运行的所有活动传输提供程序的所有登录对象调用**IXPLogon:: ValidateState** 。 
  
## <a name="see-also"></a>另请参阅



[IMAPIStatus::ValidateState](imapistatus-validatestate.md)
  
[IXPLogon::AddressTypes](ixplogon-addresstypes.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

