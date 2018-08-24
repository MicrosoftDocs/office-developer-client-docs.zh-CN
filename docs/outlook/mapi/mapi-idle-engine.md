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
ms.openlocfilehash: 9fdc254053c2d35c83866bd8a076279fd383db02
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583034"
---
# <a name="mapi-idle-engine"></a>MAPI 空闲引擎

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 提供了几个统称为空闲引擎的功能。 这些功能允许客户端、 通讯簿提供程序和消息存储提供程序在慢速时间内或响应慢时间会话中执行各种任务。 例如，客户端和服务提供商可以推迟速度慢的操作或关闭一长段仍保留未使用的文件。 通常传输提供程序不使用空闲引擎，因为该**IXPLogon::Idle**方法采用其位置。 有关详细信息，请参阅[IXPLogon::Idle](ixplogon-idle.md)。
  
若要使用空闲引擎，客户端和服务提供商创建一个包含应 MAPI 子系统空闲时进行的任务的回调函数。 MAPI 检测到空闲时间后，它会调用此回调函数。 回调函数遵循**FNIDLE**原型，定义如下： 
  
 `BOOL (STDAPICALLTYPE FNIDLE) (LPVOID lpvContext)`
  
有关详细信息，请参阅[FNIDLE](fnidle.md)。
  
构成空闲引擎的功能是：
  
[ChangeIdleRoutine](changeidleroutine.md)
  
[DeregisterIdleRoutine](deregisteridleroutine.md)
  
[EnableIdleRoutine](enableidleroutine.md)
  
[FtgRegisterIdleRoutine](ftgregisteridleroutine.md)
  
[MAPIDeInitIdle](mapideinitidle.md)
  
[MAPIInitIdle](mapiinitidle.md)
  
若要注册回调函数，客户端和服务提供商，请调用**FtgRegisterIdleRoutine**函数。 输入的参数包含可选的优先级，传递给回调函数中作为输入，一段时间以任何方式相应，要使用的内存块和一选项的标志。 
  
客户端和服务提供商可以控制空闲函数的运行方式_priIdle_参数中指定的优先级，或指定零，如果优先级不是问题。 由于负数表示比正数或 0 更高的优先级，压缩和搜索操作应分配给负数。 应将出现一次的任务分配正数。 
  
若要取消注册的活动的回调函数，客户端和服务提供商，请调用**DeregisterIdleRoutine**函数。 因为**DeregisterIdleRoutine**异步操作，很可能随时取消注册呼叫过程中调用的回调函数和甚至可能返回了**DeregisterIdleRoutine**之后。 
  
若要修改的特征的回调函数的部分或全部，客户端和服务提供商，请调用**ChangeIdleRoutine**函数。 **ChangeIdleRoutine**进行根据如何设置 flags 参数_ircIdle_ ; 更改**ChangeIdleRoutine**可以更改函数本身、 其优先级、 时间设置和输入的参数。 
  
MAPI 定义空闲时操作系统都有一个定义操作系统相同。 在 Win32，MAPI 空闲类优先级来安排空闲任务创建一个线程。 此线程跟踪时间并发布到线程的执行空闲任务时执行的时间到达一条消息。 Win32 安排线程，不处理。 如果在工作站上出现高于空闲优先级的优先级的任务，空闲任务应不获取之前计划执行任务已完成。 
  
在调用**MAPIInitIdle**线程上运行所有空闲的任务。 MAPI 有单独的线程对于安排，但合格空闲任务时，发布一条消息后通过初始化线程并那里执行空闲的任务。 不同类型的客户端的含义如下所示。
  
|**线程模型**|**暗示**|
|:-----|:-----|
|单线程  <br/> |没关系。 空闲函数在客户端的主线程上执行，并通过消息循环序列。  <br/> |
|自由线程  <br/> |空闲函数必须线程安全的但您的客户端已具有必需的基础结构。 您的客户端不可能根本需要 MAPI 空闲引擎。  <br/> |
|单元线程  <br/> |空闲函数具有相同注册它，如果要使用 MAPI、 OLE 或任何其他 COM 接口的线程上执行。 最简单的方法是使用发布到右的线程一条消息的 MAPI 注册的空闲函数并调度直接从该线程消息循环"实际"空闲函数。  <br/> |
   

