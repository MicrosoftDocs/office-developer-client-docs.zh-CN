---
title: MAPI 空闲引擎
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 755d096a-2a61-44d2-a765-5d464a857756
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d8d591c02bb621c16a1d1b46272b19573ea79785
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428450"
---
# <a name="mapi-idle-engine"></a>MAPI 空闲引擎

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 提供了多个统称为空闲引擎的函数。 这些函数允许客户端、通讯簿提供程序和邮件存储提供程序在会话的较慢时间或为响应较慢的时间执行各种任务。 例如，客户端和服务提供商可以延迟较慢的操作或关闭长时间未使用的文件。 传输提供程序通常不使用空闲引擎，因为 **IXPLogon：：Idle** 方法将处于其位置。 有关详细信息，请参阅 [IXPLogon：：Idle](ixplogon-idle.md)。
  
若要使用空闲引擎，客户端和服务提供商会创建一个回调函数，其中包含 MAPI 子系统处于空闲状态时应执行的任务。 当 MAPI 检测到空闲时间时，它将调用此回调函数。 回调函数遵循 **FNIDLE** 原型，定义如下： 
  
 `BOOL (STDAPICALLTYPE FNIDLE) (LPVOID lpvContext)`
  
有关详细信息，请参阅 [FNIDLE](fnidle.md)。
  
作为空闲引擎的一些功能包括：
  
[ChangeIdleRoutine](changeidleroutine.md)
  
[DeregisterIdleRoutine](deregisteridleroutine.md)
  
[EnableIdleRoutine](enableidleroutine.md)
  
[FtgRegisterIdleRoutine](ftgregisteridleroutine.md)
  
[MAPIDeInitIdle](mapideinitidle.md)
  
[MAPIInitIdle](mapiinitidle.md)
  
为了注册回调函数，客户端和服务提供商调用 **FtgRegisterIdleRoutine** 函数。 输入参数包括可选优先级、作为输入传递给回调函数的内存块、以任何适当方式使用的时间量以及一组选项标志。 
  
客户端和服务提供商可以在  _priIdle_ 参数中指定一个优先级，该优先级控制空闲函数的运行方式;如果优先级不是问题，则指定零。 由于负数表示的优先级高于正数或零，因此压缩和搜索操作应分配负数。 应为一次发生的任务分配正数。 
  
若要取消注册活动回调函数，客户端和服务提供商将调用 **DeregisterIdleRoutine** 函数。 由于 **DeregisterIdleRoutine** 以异步方式运行，因此在取消注册调用期间，或者即使在 **DeregisterIdleRoutine** 返回后，也随时可能调用回调函数。 
  
为了修改回调函数的一些或所有特征，客户端和服务提供商调用 **ChangeIdleRoutine** 函数。 **ChangeIdleRoutine** 根据 flags 参数  _ircIdle_ 的设置方法进行更改; **ChangeIdleRoutine** 可以更改函数本身、其优先级、时间设置和输入参数。 
  
当操作系统具有定义时，MAPI 定义与操作系统相同的空闲。 在 Win32 上，MAPI 创建具有空闲类优先级的线程来计划空闲任务。 此线程跟踪时间，并在其执行时间到达时向线程发布消息以执行空闲任务。 Win32 计划线程，而不是进程。 如果工作站上发生优先级高于空闲优先级的任务，则空闲任务不应在任务完成之前计划执行。 
  
所有空闲任务在名为 **MAPIInitIdle 的线程上运行**。 MAPI 具有单独的计划线程，但当空闲任务符合条件时，它会将消息发回到初始化线程，并在那里执行空闲任务。 不同类型的客户端的含义如下所示。
  
|**线程模型**|**含义**|
|:-----|:-----|
|单线程  <br/> |没问题。 空闲函数在客户端的主线程上执行，并通过消息循环进行序列化。  <br/> |
|自由线程  <br/> |空闲函数必须是线程安全的，但客户端已具有必要的基础结构。 客户端可能完全不需要 MAPI 空闲引擎。  <br/> |
|单元线程  <br/> |如果空闲函数想要使用 MAPI、OLE 或其他任何 COM 接口，必须在同一个注册该函数的线程上执行。 最简单的方式是使用 MAPI 注册空闲函数，该函数将消息发送到正确的线程，并直接从该线程的消息循环调度"真实"空闲函数。  <br/> |
   

