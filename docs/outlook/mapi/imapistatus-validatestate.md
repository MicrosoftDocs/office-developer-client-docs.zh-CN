---
title: IMAPIStatusValidateState
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIStatus.ValidateState
api_type:
- COM
ms.assetid: 036b9b15-86e1-4a37-8e4b-e37b2963d8fb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: adcdf04653f8c9fed2ecc6520648abd3acd36134
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438146"
---
# <a name="imapistatusvalidatestate"></a>IMAPIStatus::ValidateState

**适用于**：Outlook 2013 | Outlook 2016 
  
确认 MAPI 资源或服务提供商可用的外部状态信息。 此方法在所有状态对象中都受支持。 
  
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
  
> [in]控制验证的标志的位掩码。 可以设置以下标志：
    
ABORT_XP_HEADER_OPERATION
  
> 用户通常通过单击相应对话框中的"取消"按钮来取消操作。 status 对象有两个选项： 
    
   - 继续操作。
    
   - 停止操作并返回MAPI_E_USER_CANCELED。
    
CONFIG_CHANGED 
  
> 一个或多个状态对象的配置属性已更改。 客户端可以设置此标志以允许 MAPI 后台处理程序动态更正关键传输提供程序故障。 
    
FORCE_XP_CONNECT 
  
> status 对象应执行连接。 当此标志与 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 标志一同使用时，无需缓存即可进行连接。
    
FORCE_XP_DISCONNECT 
  
> 状态对象应执行断开连接操作。 当此标志与 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 一PROCESS_XP_HEADER_CACHE时，断开连接时无需缓存。
    
PROCESS_XP_HEADER_CACHE 
  
> 应处理邮件头缓存表中的条目，应下载标有 MSGSTATUS_REMOTE_DOWNLOAD 标志的所有邮件，并删除标记有 MSGSTATUS_REMOTE_DELETE 标志的所有邮件。 应移动同时MSGSTATUS_REMOTE_DOWNLOAD和MSGSTATUS_REMOTE_DELETE的邮件。
    
REFRESH_XP_HEADER_CACHE 
  
> 对于远程传输提供程序，应下载新的邮件头列表，并清除标记邮件状态的所有标志。
    
SUPPRESS_UI 
  
> 防止 status 对象在操作过程中显示用户界面。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 验证成功。
    
MAPI_E_BUSY 
  
> 正在进行另一个操作;在启动此操作之前，应允许其完成或停止。
    
MAPI_E_NO_SUPPORT 
  
> status 对象不支持验证方法，如 PR_RESOURCE_METHODS ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)属性中缺少 **STATUS_VALIDATE_STATE** 标志) 。
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消" **按钮来取消** 验证操作。 此值仅由远程传输提供程序返回。 
    
## <a name="remarks"></a>备注

**IMAPIStatus：：ValidateState** 方法检查与状态对象关联的资源的状态。 **ValidateState** 是 [IMAPIStatus](imapistatusimapiprop.md) 接口中所有状态对象所需的唯一方法。 此方法的确切行为取决于实现。 下表介绍了每种不同类型的状态对象的实现。 
  
|**Status 对象**|ValidateState** implementation**|
|:-----|:-----|
|MAPI 子系统  <br/> |验证当前活动的服务提供商和子系统本身拥有的所有资源的状态。  <br/> |
|MAPI 后台处理程序  <br/> |执行所有传输提供程序的登录，而不考虑是否已登录。  <br/> |
|MAPI 通讯簿  <br/> |检查其配置文件节中的条目。  <br/> |
|服务提供程序  <br/> |实现取决于提供程序的类型和  _ulFlags 参数中设置_ 的标志。  <br/> |
   
## <a name="notes-to-implementers"></a>针对实现者的说明

远程客户端应用程序调用 **ValidateState** 方法以针对各种操作启动远程处理。 此方法主要用于设置状态位以与 MAPI 后台处理程序通信，而不是实际执行任何工作。 通常，传输提供程序在其状态行中设置标志，向 MAPI 后台处理程序指示完成客户端请求需要启动哪些操作。 

在此客户端传输后台处理程序交互模型中，客户端请求的操作是异步的，其中 **ValidateState** 在请求的操作完成之前返回。 但是，不一定涉及基础邮件系统的操作或涉及特定于传输的接口的操作可以是同步的。 客户端应用程序将传递以下标志的位掩码，以指定远程传输提供程序应执行哪些操作。 
  
ABORT_XP_HEADER_OPERATION 
  
> 如果可能，远程传输提供程序应取消任何涉及下载邮件头的操作。 为此，传输提供程序必须在登录对象的状态行中设置以下属性值：
    
   - 清除 PR_STATUS_CODE ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性中的 STATUS_INBOUND_ENABLED 和 **STATUS_INBOUND_ACTIVE** 位，以告诉 MAPI 后台处理程序停止此传输提供程序的传入刷新过程。
    
   - 在 STATUS_OFFLINE 属性中设置 **PR_STATUS_CODE** 位。 
    
   - 将 **PR_REMOTE_VALIDATE_OK (** [PidTagRemoteValidateOk](pidtagremotevalidateok-canonical-property.md)) 设置为 TRUE。
    
   - 将 **PR_STATUS_STRING (** [PidTagStatusString](pidtagstatusstring-canonical-property.md)) 属性设置为向用户指示传输提供程序状态的字符串。
    
   - 返回S_OK。 但是，如果无法取消进行中的操作， **则 ValidateState** 应返回MAPI_E_BUSY。 
    
FORCE_XP_CONNECT 
  
> 远程传输提供程序永远不应与共享资源 (例如，在 [IXPLogon：：FlushQueues](ixplogon-flushqueues.md) 方法所涉及的 MAPI 后台处理程序传输交互上下文之外建立调制解调器或 COM 端口) 。 如果通过此标志调用 **ValidateState，** 则传输提供程序应执行以下操作： 
    
   - 设置内部状态标志，以指示在调用 **IXPLogon：：FlushQueues** 方法时必须建立远程连接。 
    
   - 在状态表中设置正确的值，使 MAPI 后台处理程序启动队列刷新过程。
    
   - 刷新队列完成后，释放共享资源。
    
   - 清除 STATUS_OFFLINE 属性 **中的PR_STATUS_CODE位** 。 
    
   - 返回S_OK。
    
FORCE_XP_DISCONNECT 
  
> 远程传输提供程序应释放与邮件系统资源的连接。 执行此操作后，它应在 STATUS_OFFLINE 属性中设置 PR_STATUS_CODE **位并** 返回S_OK。 
    
PROCESS_XP_HEADER_CACHE 
  
> 远程传输提供程序应处理远程邮件并上载已延迟的任何邮件。 为此，传输提供程序必须在登录对象的状态行中设置以下属性值：
    
   - 将 **PR_STATUS_STRING** 属性设置为向用户指示传输提供程序状态的字符串。 
    
   - 设置 STATUS_OUTBOUND_ENABLED STATUS_OUTBOUND_ACTIVE 属性中的 PR_STATUS_CODE **位。** 
    
   - 将 **PR_REMOTE_VALIDATE_OK** 提供程序的状态行中的属性设置为 FALSE。 
    
   - 如果正在进行其他操作， (**调用 ValidateState** 时下载 **) ，ValidateState** 应返回 MAPI_E_BUSY。 
    
   - 执行用于处理 REFRESH_XP_HEADER_CACHE 标志的代码，以满足 Microsoft Exchange 客户端的要求。
    
REFRESH_XP_HEADER_CACHE 
  
> 远程传输提供程序应检索邮件系统的任何新邮件头。 为此，传输提供程序必须执行以下操作：
    
   - 将 **PR_STATUS_STRING** 属性设置为向用户指示传输提供程序状态的字符串。 
    
   - 设置 STATUS_INBOUND_ENABLED STATUS_INBOUND_ACTIVE 属性中的 **PR_STATUS_CODE** 位。 
    
   - 清除 STATUS_OFFLINE 属性 **中的PR_STATUS_CODE位** 。 
    
   - 在 STATUS_ONLINE 属性 **中设置PR_STATUS_CODE** 位。 
    
   - 将 **PR_REMOTE_VALIDATE_OK** 提供程序的状态行中的属性设置为 FALSE。 
    
SHOW_XP_SESSION_UI 
  
> 如果您的传输提供程序具有任何用于处理邮件头的用户界面 (例如确认下载邮件的对话框) ，应显示该对话框。 否则 **，ValidateState** 可以返回MAPI_E_NO_SUPPORT。 
    
如果传入除这些标志外的任何标志， **则 ValidateState** 应返回MAPI_E_UNKNOWN_FLAGS。 
  
客户端对传输提供程序的调用通常是对 **IMAPIStatus：：ValidateState** 方法的调用。 在处理 **ValidateState** 期间，传输提供程序不应执行分配系统资源的任何操作，例如调制解调器或 COM 端口。 这是因为 MAPI 后台处理程序有时需要刷新多个传输提供程序上的队列。 但是，客户端随时都可以调用任何传输提供程序的 **ValidateState** 方法。 如果传输提供程序在处理 **ValidateState** 期间尝试分配资源，则由于与 MAPI 后台处理程序已指示刷新其队列的另一个传输提供程序冲突，可能会导致错误。 如果允许所有资源分配在 MAPI 后台处理程序的方向上进行，可以避免此类冲突。 传输提供程序应支持 **PR_REMOTE_VALIDATE_OK** 属性，以便客户端应用程序可以检测传输提供程序何时繁忙或等待 MAPI 后台处理程序启动操作。 
  
## <a name="notes-to-callers"></a>给调用方的说明

由于此方法可能会导致进行其他可能过长的调用， **因此 ValidateState** 可以返回MAPI_E_BUSY，以通知您此方法正在等待另一个操作完成。 在尝试其他任务之前，应等到挂起的操作完成。 
  
您最能够控制对传输提供程序状态对象的调用。 可以将影响传输提供程序的操作的一个或多个标志传递给 **ValidateState。** 例如，ABORT_XP_HEADER_OPERATION标志指示用户已取消验证。 传输提供程序可以决定中止、返回MAPI_E_USER_CANCELED，也可以继续。 
  
可以在对CONFIG_CHANGED状态对象或 MAPI 后台处理程序的调用中设置 CONFIG_CHANGED 标志，以指示配置选项已更改。 可以使用 CONFIG_CHANGED动态重新配置传输提供程序。 当您在CONFIG_CHANGED状态对象的调用上设置此限制时，提供程序将响应 [对 IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 的调用，以提醒 MAPI 后台处理程序更改。 当您在CONFIG_CHANGED MAPI 后台处理程序的状态对象时设置值时，后台处理程序将调用每个活动传输提供程序的[IXPLogon：：AddressTypes。](ixplogon-addresstypes.md) **AddressTypes** 通知 MAPI 后台处理程序传输支持的地址类型。 如果验证需要很长时间，某些服务提供商还会显示进度指示器。 显示进度指示器非常有用，但不是必需的。 
  
设置SUPPRESS_UI时，不能显示任何配置属性表或进度对话框。 
  
## <a name="see-also"></a>另请参阅

- [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)
- [IXPLogon::AddressTypes](ixplogon-addresstypes.md)
- [IXPLogon::FlushQueues](ixplogon-flushqueues.md)
- [PidTagRemoteValidateOk 规范属性](pidtagremotevalidateok-canonical-property.md)
- [PidTagResourceMethods 规范属性](pidtagresourcemethods-canonical-property.md)
- [PidTagStatusCode 规范属性](pidtagstatuscode-canonical-property.md)
- [PidTagStatusString 规范属性](pidtagstatusstring-canonical-property.md)
- [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)

