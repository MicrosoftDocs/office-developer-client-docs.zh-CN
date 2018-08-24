---
title: 传输提供程序和 MAPI 后台处理程序操作模型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b0f8d8f0-fed7-4a7c-bc40-e935f159591d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 26d9982248fde015a584eb79cc248bafc5afc6bb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594031"
---
# <a name="transport-provider-and-mapi-spooler-operational-model"></a>传输提供程序和 MAPI 后台处理程序操作模型

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
传输提供程序初始化、 启动、 处理、 关机和取消初始化通过一系列调用从 MAPI 后台打印到传输提供程序。 呼叫顺序编排会出现，如下所示：
  
1. MAPI 后台处理程序调用[XPProviderInit](xpproviderinit.md)函数，将支持对象传递，获取提供商对象，并检查传输提供程序和 MAPI 后台处理程序支持兼容的 MAPI 版本号。 
    
2. MAPI 后台处理程序调用的[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)方法[IXPProvider: IUnknown](ixpprovideriunknown.md)接口。 MAPI 后台处理程序和配置文件的当前节中的凭据与传输提供程序之间建立会话。 传输提供程序返回登录对象。 
    
3. MAPI 后台处理程序调用[IXPLogon::AddressTypes](ixplogon-addresstypes.md)方法。 传输提供程序返回唯一标识符 (Uid) 及其将接受的电子邮件地址类型的列表。 
    
4. 传输提供程序调用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)方法来创建 MAPI 状态表中其所在行。 
    
5. MAPI 后台处理程序调用[IXPLogon::TransportNotify](ixplogon-transportnotify.md)方法来启用邮件的传输和接收。 
    
6. 如果请求**TransportLogon**呼叫其返回传输提供程序，MAPI 后台处理程序定期调用[IXPLogon::Idle](ixplogon-idle.md)方法。 如果传输提供程序需要轮询新邮件基础邮件系统或执行其他低优先级任务有用空闲时间处理。 
    
7. MAPI 后台处理程序和传输提供程序发送和接收消息。 有关详细信息，请参阅[消息提交模型](message-submission-model.md)和[消息接收模型](message-reception-model.md)。 MAPI 后台处理程序传输请求提供服务，并支持、 消息和附件对象上调用。
    
8. MAPI 后台处理程序调用**TransportNotify**方法来禁用邮件传输和接收。 
    
9. MAPI 后台处理程序释放的登录和提供程序的对象。 有关详细信息，请参阅[IXPProvider::Shutdown](ixpprovider-shutdown.md)方法。 
    

