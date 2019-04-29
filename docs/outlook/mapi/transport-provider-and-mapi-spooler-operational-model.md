---
title: 传输提供程序和 MAPI 后台处理程序操作模型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b0f8d8f0-fed7-4a7c-bc40-e935f159591d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5987111844f087801c63989b905992900ff6909c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426623"
---
# <a name="transport-provider-and-mapi-spooler-operational-model"></a>传输提供程序和 MAPI 后台处理程序操作模型

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
传输提供程序初始化、启动、处理、关闭和 deinitialization 都是通过从 MAPI 后台处理程序到传输提供程序的一系列呼叫来完成的。 这些调用的序列化如下所示:
  
1. MAPI 后台处理程序调用[XPProviderInit](xpproviderinit.md)函数, 传递支持对象, 获取 provider 对象, 并检查传输提供程序和 mapi 后台处理程序是否支持 mapi 版本号的兼容范围。 
    
2. MAPI 后台处理程序调用[IXPProvider: IUnknown](ixpprovideriunknown.md)接口的[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)方法。 在 MAPI 后台处理程序和传输提供程序之间, 将在配置文件的当前节中的凭据之间建立会话。 传输提供程序返回一个登录对象。 
    
3. MAPI 后台处理程序调用[IXPLogon:: AddressTypes](ixplogon-addresstypes.md)方法。 传输提供程序将返回它将接受的唯一标识符 (uid) 和电子邮件地址类型的列表。 
    
4. 传输提供程序调用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)方法来创建其在 MAPI 状态表中的行。 
    
5. MAPI 后台处理程序调用[IXPLogon:: TransportNotify](ixplogon-transportnotify.md)方法来启用邮件传输和接收。 
    
6. 如果传输提供程序在其返回的**TransportLogon**呼叫中请求, MAPI 后台处理程序将定期调用[IXPLogon:: Idle](ixplogon-idle.md)方法。 如果传输提供程序需要轮询基础邮件系统中的新邮件或执行其他低优先级任务, 空闲处理将非常有用。 
    
7. MAPI 后台处理程序和传输提供程序发送和接收邮件。 有关详细信息, 请参阅[邮件提交模型](message-submission-model.md)和[邮件接收模型](message-reception-model.md)。 MAPI 后台处理程序服务传输请求和对支持、消息和附件对象的调用。
    
8. MAPI 后台处理程序调用**TransportNotify**方法以禁用邮件传输和接收。 
    
9. MAPI 后台处理程序释放登录和提供程序对象。 有关详细信息, 请参阅[IXPProvider:: Shutdown](ixpprovider-shutdown.md)方法。 
    

