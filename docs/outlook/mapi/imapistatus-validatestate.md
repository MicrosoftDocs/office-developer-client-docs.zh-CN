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
ms.openlocfilehash: 3ff29ac7e7f9b7876bb678930390ca556351ecf6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775610"
---
# <a name="imapistatusvalidatestate"></a>IMAPIStatus::ValidateState

**适用于**： Outlook 
  
确认可供 MAPI 资源或服务提供商的外部状态信息。 此方法支持所有状态对象。 
  
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
  
> [in]位掩码的标志来控制验证。 可以设置以下标志：
    
ABORT_XP_HEADER_OPERATION
  
> 用户取消操作，通常通过单击相应的对话框中的**取消**按钮。 状态对象有两个选项： 
    
   - 继续操作。
    
   - 停止操作并返回 MAPI_E_USER_CANCELED。
    
CONFIG_CHANGED 
  
> 更改一个或多个状态对象的配置属性。 客户端可以设置此标志以允许 MAPI 后台处理程序动态更正关键传输提供程序失败。 
    
FORCE_XP_CONNECT 
  
> 状态对象应执行连接。 此标志用于 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 标志，连接时不进行缓存。
    
FORCE_XP_DISCONNECT 
  
> 状态对象应执行断开连接操作。 此标志用于 REFRESH_XP_HEADER_CACHE 或 PROCESS_XP_HEADER_CACHE 标志，断开连接时不进行缓存。
    
PROCESS_XP_HEADER_CACHE 
  
> 应处理标题缓存表中的条目，应下载标记有 MSGSTATUS_REMOTE_DOWNLOAD 标志的所有邮件，以及应删除与 MSGSTATUS_REMOTE_DELETE 标志标记的所有邮件。 应移动 MSGSTATUS_REMOTE_DOWNLOAD 和 MSGSTATUS_REMOTE_DELETE 设置的消息。
    
REFRESH_XP_HEADER_CACHE 
  
> 为远程传输提供程序应下载邮件头的新列表，并应清除标记邮件状态的所有标志。
    
SUPPRESS_UI 
  
> 阻止操作的一部分显示用户界面的状态对象。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 验证成功。
    
MAPI_E_BUSY 
  
> 正在进行; 另一个操作应允许其完成，或者它应停止，开始此操作之前。
    
MAPI_E_NO_SUPPORT 
  
> 状态对象不支持的验证方法，由 STATUS_VALIDATE_STATE 标志**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中不存在。
    
MAPI_E_USER_CANCEL 
  
> 用户取消验证操作，通常通过单击对话框中的**取消**按钮。 只能通过远程传输提供程序，则返回此值。 
    
## <a name="remarks"></a>说明

**IMAPIStatus::ValidateState**方法检查与状态对象相关联的资源的状态。 **ValidateState**是[IMAPIStatus](imapistatusimapiprop.md)界面所需的所有状态对象中的唯一方法。 完全本方法的行为取决于实现。 下表介绍了每种状态对象的不同类型的实现。 
  
|**状态对象**|ValidateState * * 实现 * *|
|:-----|:-----|
|MAPI 子系统  <br/> |验证的当前处于活动状态的服务提供商和子系统本身拥有的所有资源的状态。  <br/> |
|MAPI 后台处理程序  <br/> |执行所有传输提供程序，无论他们是否已记录在上一个登录的名。  <br/> |
|MAPI 通讯簿  <br/> |检查其配置文件节中的项。  <br/> |
|服务提供商  <br/> |实现取决于类型提供程序和设置_ulFlags_参数中的标志。  <br/> |
   
## <a name="notes-to-implementers"></a>针对实施者的注释

远程客户端应用程序调用**ValidateState**方法以启动远程处理的各种操作。 此方法存在主要是为了设置状态位要与之通信 MAPI 后台处理程序，而不是实际执行任何操作。 通常，传输提供程序设置其 MAPI 后台处理程序向指示需要启动以完成客户端的请求的操作的状态行中的标志。 

该模型中的后台处理传输客户端程序交互，客户端请求的操作是异步的，之前在完成请求的操作,，将返回**ValidateState** 。 但是，操作时，并不一定涉及基础的消息系统，或者所涉及的特定于传输的界面，可以是同步。 客户端应用程序中的指定远程传输提供程序应采取的操作的以下标志位掩码传递。 
  
ABORT_XP_HEADER_OPERATION 
  
> 如果可能，远程传输提供程序应取消的涉及下载邮件头的任何操作。 若要执行此操作，传输提供程序必须登录对象的状态行中设置以下属性值：
    
   - 清除**PR_STATUS_CODE** ([PidTagStatusCode](pidtagstatuscode-canonical-property.md)) 属性以告知 MAPI 后台处理程序停止此传输提供程序的传入刷新进程中的 STATUS_INBOUND_ENABLED 和 STATUS_INBOUND_ACTIVE 位。
    
   - 设置 STATUS_OFFLINE 位**PR_STATUS_CODE**属性中。 
    
   - **PR_REMOTE_VALIDATE_OK** ([PidTagRemoteValidateOk](pidtagremotevalidateok-canonical-property.md)) 属性设置为 TRUE。
    
   - **PR_STATUS_STRING** ([PidTagStatusString](pidtagstatusstring-canonical-property.md)) 属性设置为 string 类型的值，该值指示的传输提供程序向用户的状态。
    
   - 返回 S_OK。 但是，如果不能取消正在进行的操作， **ValidateState**应返回 MAPI_E_BUSY。 
    
FORCE_XP_CONNECT 
  
> 远程传输提供程序应永远不会建立[IXPLogon::FlushQueues](ixplogon-flushqueues.md)方法所涉及的 MAPI 后台处理程序传输交互的与上下文之外的共享资源 （例如，调制解调器或 COM 端口） 的连接。 如果使用此标志调用**ValidateState** ，则您传输提供程序应执行以下操作： 
    
   - 设置内部状态标志，指示调用**IXPLogon::FlushQueues**方法时，必须建立远程连接。 
    
   - 在状态表，以使 MAPI 后台处理程序启动队列刷新过程中设置正确的值。
    
   - 刷新队列的完成后，版本的共享的资源。
    
   - 清除 STATUS_OFFLINE 位**PR_STATUS_CODE**属性中。 
    
   - 返回 S_OK。
    
FORCE_XP_DISCONNECT 
  
> 远程传输提供程序应释放其连接到的消息的系统资源。 此操作后，它应**PR_STATUS_CODE**属性中设置 STATUS_OFFLINE 位，并返回 S_OK。 
    
PROCESS_XP_HEADER_CACHE 
  
> 远程传输提供程序应处理远程邮件，并上载已延迟任何消息。 若要执行此操作，传输提供程序必须登录对象的状态行中设置以下属性值：
    
   - **PR_STATUS_STRING**属性设置为 string 类型的值，该值指示的传输提供程序向用户的状态。 
    
   - **PR_STATUS_CODE**属性中设置的 STATUS_OUTBOUND_ENABLED 和 STATUS_OUTBOUND_ACTIVE 位。 
    
   - 将**PR_REMOTE_VALIDATE_OK**属性设置为 FALSE 的传输提供程序的状态行中。 
    
   - 如果 （如下载邮件头） 正在执行其他操作**ValidateState**调用**ValidateState**时，应返回 MAPI_E_BUSY。 
    
   - 执行用于处理 REFRESH_XP_HEADER_CACHE 标志，同样，以满足要求的 Microsoft Exchange 客户端代码。
    
REFRESH_XP_HEADER_CACHE 
  
> 远程传输提供程序应从邮件系统中检索任何新的邮件头。 若要执行此操作，传输提供程序必须执行以下操作：
    
   - **PR_STATUS_STRING**属性设置为 string 类型的值，该值指示的传输提供程序向用户的状态。 
    
   - **PR_STATUS_CODE**属性中设置的 STATUS_INBOUND_ENABLED 和 STATUS_INBOUND_ACTIVE 位。 
    
   - 清除 STATUS_OFFLINE 位**PR_STATUS_CODE**属性中。 
    
   - 设置 STATUS_ONLINE 位**PR_STATUS_CODE**属性中。 
    
   - 将**PR_REMOTE_VALIDATE_OK**属性设置为 FALSE 的传输提供程序的状态行中。 
    
SHOW_XP_SESSION_UI 
  
> 如果您传输提供程序具有用于处理邮件头 （如确认消息的下载对话框） 的用户界面的任何部分，应显示的对话框。 否则， **ValidateState**可以返回 MAPI_E_NO_SUPPORT。 
    
如果这些之外的任何标志以传递， **ValidateState**应返回 MAPI_E_UNKNOWN_FLAGS。 
  
到传输提供程序的客户端的呼叫通常会**IMAPIStatus::ValidateState**方法。 处理期间**ValidateState**，传输提供程序不应执行任何操作，分配紧缺系统资源，如调制解调器或 COM 端口。 这是因为 MAPI 后台处理程序将有时需要刷新多个传输提供程序上的队列。 但是，客户端可以随时调用任何传输提供程序**ValidateState**方法。 如果您传输提供程序尝试**ValidateState**处理过程中分配紧缺资源，可以由于与 MAPI 后台处理程序指导刷新其队列的另一个传输提供程序冲突而导致错误。 如果允许 MAPI 后台处理程序的指导下发生的所有紧缺资源分配，则可以避免这样的冲突。 传输提供程序应支持**PR_REMOTE_VALIDATE_OK**属性，因此客户端应用程序可以检测到传输提供程序时正忙或等待 MAPI 后台处理程序启动操作。 
  
## <a name="notes-to-callers"></a>给调用方的说明

由于此方法可能导致其他可能较长的调用进行， **ValidateState**可以返回 MAPI_E_BUSY 来通知您此方法正在等待完成其他操作。 您应等待，直到在挂起的操作尝试另一个任务之前已完成。 
  
您必须对您的呼叫传输提供程序状态对象的大多数控制。 您可以将一个或多个标志传递到**ValidateState**影响传输提供程序的操作。 例如，ABORT_XP_HEADER_OPERATION 标志指示用户已取消验证。 传输提供程序可以决定要放弃，返回 MAPI_E_USER_CANCELED，也可以继续。 
  
您可以对服务提供商的状态对象或 MAPI 后台处理程序的调用，以指示已更改的配置选项设置 CONFIG_CHANGED 标志。 您可以使用 CONFIG_CHANGED 动态重新配置的传输提供程序。 当在服务提供商的状态对象调用设置 CONFIG_CHANGED 时，提供程序返回[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)调用警告更改 MAPI 后台处理程序作为响应。 当在 MAPI 后台处理程序的状态对象调用设置 CONFIG_CHANGED 时，后台处理程序将为每个活动传输提供程序调用[IXPLogon::AddressTypes](ixplogon-addresstypes.md) 。 **AddressTypes**通知传输的受支持的地址类型 MAPI 后台处理程序。 如果预计验证需要很长时间，某些服务提供商还显示进度指示器。 显示进度指示器很有用，但不是需要。 
  
当设置 SUPPRESS_UI 标志时，可以显示的任何配置属性表或进度对话框。 
  
## <a name="see-also"></a>另请参阅

- [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)
- [IXPLogon::AddressTypes](ixplogon-addresstypes.md)
- [IXPLogon::FlushQueues](ixplogon-flushqueues.md)
- [PidTagRemoteValidateOk 规范属性](pidtagremotevalidateok-canonical-property.md)
- [PidTagResourceMethods 规范属性](pidtagresourcemethods-canonical-property.md)
- [PidTagStatusCode 规范属性](pidtagstatuscode-canonical-property.md)
- [PidTagStatusString 规范属性](pidtagstatusstring-canonical-property.md)
- [IMAPIStatus : IMAPIProp](imapistatusimapiprop.md)

