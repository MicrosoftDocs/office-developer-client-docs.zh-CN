---
title: 可用的事件和其 dispid （Outlook 导出的 Api）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 1fd848c7-038e-4e2f-8997-c8509b31df79
description: 本节介绍 Outlook 使可用的事件的调度标识符。
ms.openlocfilehash: a94787063e0fd5be30de1ef772813979d3cb2f21
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582971"
---
# <a name="available-events-and-their-dispids-outlook-exported-apis"></a>可用的事件和其 dispid （Outlook 导出的 Api）

本节介绍 Outlook 使可用的事件的调度标识符。
  
Outlook 公开以下的调度标识符 (dispid)，以允许 c + + 加载项以收听和处理[idispatch:: Invoke](https://docs.microsoft.com/en-us/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)函数中的相应事件。 
  
|**常量**|**Dispid 事件**|**说明**|**参数**|**说明**|
|:-----|:-----|:-----|:-----|:-----|
|**dispidBeforePrint** <br/> |0xFC8E  <br/> |用于处理来自打印操作之前，会触发的**idispatch:: Invoke**函数的应用程序级事件。  <br/> | 有 2 的未命名的参数：  <br/>  第一个参数为类型 * * VT_BOOL|VT_BREF * *。 此参数来取消事件中返回**variant_true 时**。  <br/>  第二个参数不使用，并且应忽略。  <br/> |此 dispid 位于以来 Outlook 2010。  <br/> |
|**dispidEventReadComplete** <br/> |0xFC8F  <br/> |用于处理来自 Outlook 已完成读取项目的属性时触发的**idispatch:: Invoke**函数的项目级事件。  <br/> |没有只有一个参数_取消_其类型为 * * VT_BOOL|VT_BREF * *。 此参数，以取消读取的操作中返回**variant_true 时**。  <br/> |此 dispid 位于以来 Outlook 2010。  <br/> 此事件对应于 Exchange 客户端扩展 (ECE) 事件**IExchExtMessageEvents::OnReadComplete**，并还**ReadComplete**事件已添加到对象模型以来 Outlook 2013。  <br/> |
   
有关如何使用 dispid 以收听和处理事件的示例，请参阅`CAppEventListener::Invoke` [MFC c + + 2003年.NET 中实现 XP Outlook 2002/事件接收器](http://www.codeproject.com/Articles/4230/Implementing-Outlook-2002-XP-Event-Sinks-in-MFC-C)中所述在 c + + Outlook 解决方案中的函数。
  
## <a name="see-also"></a>另请参阅

- [Outlook 导出的 API](outlook-exported-apis.md)
- [（Outlook 导出的 Api） 的常量](constants-outlook-exported-apis.md)
- [关于 Outlook 导出的 API](about-apis-exported-by-outlook.md)
- [MFC c + + 2003年.NET 中实现 XP Outlook 2002/事件接收器](http://www.codeproject.com/Articles/4230/Implementing-Outlook-2002-XP-Event-Sinks-in-MFC-C)

