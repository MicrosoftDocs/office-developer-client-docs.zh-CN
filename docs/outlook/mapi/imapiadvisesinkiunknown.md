---
title: IMAPIAdviseSink IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIAdviseSink
api_type:
- COM
ms.assetid: f598fc57-75d3-473b-8eb0-9d8a3b92e9f2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d537184f427b2ef240dd2a9a59ab2f624f8f75d0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409564"
---
# <a name="imapiadvisesink--iunknown"></a>IMAPIAdviseSink : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
实现用于处理通知的通知接收器对象。 指向通知接收器对象的指针在对服务提供程序的**advise**方法的调用中传递, 用于注册通知的机制。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|公开者:  <br/> |通知接收器对象  <br/> |
|实现者：  <br/> |客户端应用程序和 MAPI  <br/> |
|调用者：  <br/> |服务提供商和 MAPI  <br/> |
|接口标识符:  <br/> |IID_IMAPIAdviseSink  <br/> |
|指针类型:  <br/> |LPMAPIADVISESINK  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[OnNotify](imapiadvisesink-onnotify.md) <br/> |通过执行一个或多个任务来响应通知。 执行的任务取决于事件的类型和生成通知的对象。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

