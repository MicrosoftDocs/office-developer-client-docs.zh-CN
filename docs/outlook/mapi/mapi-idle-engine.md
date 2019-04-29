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
  
MAPI 提供了几个统称为空闲引擎的功能。 这些函数允许客户端、通讯簿提供程序和邮件存储提供程序在会话速度较慢或响应速度较慢时执行各种任务。 例如, 客户端和服务提供程序可以推迟运行缓慢的操作, 或关闭在较长时间内仍未使用的文件。 传输提供程序通常不使用空闲引擎, 因为**IXPLogon:: idle**方法会替代它。 有关详细信息, 请参阅[IXPLogon:: Idle](ixplogon-idle.md)。
  
若要使用空闲引擎, 客户端和服务提供程序将创建一个回调函数, 其中包含当 MAPI 子系统处于空闲状态时应发生的任务。 当 MAPI 检测到空闲时间时, 它会调用此回调函数。 回调函数遵循**FNIDLE**原型, 定义如下: 
  
 `BOOL (STDAPICALLTYPE FNIDLE) (LPVOID lpvContext)`
  
有关详细信息, 请参阅[FNIDLE](fnidle.md)。
  
组成空闲引擎的函数包括:
  
[ChangeIdleRoutine](changeidleroutine.md)
  
[DeregisterIdleRoutine](deregisteridleroutine.md)
  
[EnableIdleRoutine](enableidleroutine.md)
  
[FtgRegisterIdleRoutine](ftgregisteridleroutine.md)
  
[MAPIDeInitIdle](mapideinitidle.md)
  
[MAPIInitIdle](mapiinitidle.md)
  
若要注册回调函数, 客户端和服务提供程序将调用**FtgRegisterIdleRoutine**函数。 输入参数包括一个可选的优先级、作为输入传递给回调函数的内存块、用于任何适当的方式的时间量以及一组选项标志。 
  
客户端和服务提供程序可以在_priIdle_参数中指定一个优先级, 该参数控制 idle 函数的运行方式, 或指定零 (如果优先级不是问题)。 由于负数表示的优先级高于正数或零, 因此应为压缩和搜索操作分配负数。 应为只发生一次的任务分配正数。 
  
若要取消注册活动回调函数, 客户端和服务提供程序将调用**DeregisterIdleRoutine**函数。 由于**DeregisterIdleRoutine**以异步方式运行, 因此可以在取消注册的过程中随时调用回调函数, 甚至可能在**DeregisterIdleRoutine**返回后调用。 
  
若要修改回调函数的部分或全部特征, 客户端和服务提供程序将调用**ChangeIdleRoutine**函数。 **ChangeIdleRoutine**根据如何设置 flags 参数_ircIdle_来进行更改;**ChangeIdleRoutine**可以更改函数本身、其优先级、时间设置和输入参数。 
  
当操作系统有定义时, MAPI 将定义与操作系统相同的空闲。 在 Win32 中, MAPI 将创建一个具有空闲类优先级的线程, 以安排空闲任务。 此线程跟踪时间, 并将邮件发送到在其执行到达时执行空闲任务的线程。 Win32 调度线程, 而不是进程。 如果在工作站上发生优先级高于空闲优先级的任务, 则在任务完成之前, 空闲任务不应计划执行。 
  
所有空闲任务都在名为**MAPIInitIdle**的线程上运行。 MAPI 具有单独的调度线程, 但当空闲任务符合条件时, 它会将一条消息发送回初始化线程, 并在其中执行空闲任务。 不同类型的客户端的含义如下所示。
  
|**线程模型**|**含义**|
|:-----|:-----|
|单线程  <br/> |没关系。 Idle 函数在客户端的主线程上执行, 并通过消息循环进行序列化。  <br/> |
|自由线程  <br/> |Idle 函数必须是线程安全的, 但您的客户端已经具有必要的基础结构。 您的客户端可能根本不需要 MAPI 空闲引擎。  <br/> |
|单元线程  <br/> |Idle 函数必须在注册它的同一线程上执行, 如果它要使用 MAPI、OLE 或任何其他 COM 接口。 最简单的方法是使用 MAPI 注册 idle 函数, 以便将邮件发布到右侧线程, 并直接从该线程的邮件循环发送 "真实" 空闲函数。  <br/> |
   

