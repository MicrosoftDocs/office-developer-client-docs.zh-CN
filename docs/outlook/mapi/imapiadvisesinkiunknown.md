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
ms.openlocfilehash: b9244e28337c74487562ec235f246559a49a390d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573801"
---
# <a name="imapiadvisesink--iunknown"></a>IMAPIAdviseSink : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
实现用于处理通知 advise 接收器对象。 指向 advise 接收器对象的指针传递给服务提供商的**Advise**方法，用于注册通知的机制呼叫中。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |建议接收器对象  <br/> |
|通过实现：  <br/> |客户端应用程序和 MAPI  <br/> |
|调用：  <br/> |服务提供商和 MAPI  <br/> |
|接口标识符：  <br/> |IID_IMAPIAdviseSink  <br/> |
|指针类型：  <br/> |LPMAPIADVISESINK  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[OnNotify](imapiadvisesink-onnotify.md) <br/> |通过执行一个或多个任务响应通知。 执行的任务取决于事件以及生成通知的对象类型。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

