---
title: 可用的事件和其 dispid （Outlook 导出的 Api）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 1fd848c7-038e-4e2f-8997-c8509b31df79
description: 本节介绍 Outlook 提供的事件的调度标识符。
ms.openlocfilehash: 31843a2eb8f91eabdc0dbf54a269270eb172baa7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316875"
---
# <a name="available-events-and-their-dispids-outlook-exported-apis"></a>可用的事件和其 dispid （Outlook 导出的 Api）

本节介绍 Outlook 提供的事件的调度标识符。
  
Outlook 公开以下调度标识符 (dispid), 以允许 c + + 加载项侦听和处理[IDispatch:: Invoke](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)函数中的相应事件。 
  
|**常量**|**Dispid 事件**|**说明**|**参数**|**备注**|
|:-----|:-----|:-----|:-----|:-----|
|**dispidBeforePrint** <br/> |0xFC8E  <br/> |用于处理在打印操作之前触发的**IDispatch:: Invoke**函数中的应用程序级别事件。  <br/> | 有两个未命名参数:  <br/>  第一个参数的类型为 * * VT_BOOL|VT_BREF * *。 在此参数中返回**VARIANT_TRUE**以取消事件。  <br/>  不使用第二个参数, 应忽略它。  <br/> |此 dispid 可从 Outlook 2010 开始。  <br/> |
|**dispidEventReadComplete** <br/> |0xFC8F  <br/> |用于处理在 Outlook 已完成项目属性读取时触发的**IDispatch:: Invoke**函数中的项目级事件。  <br/> |只有一个参数_Cancel_ , 它的类型为 * * VT_BOOL|VT_BREF * *。 在此参数中返回**VARIANT_TRUE**以取消读取操作。  <br/> |此 dispid 可从 Outlook 2010 开始。  <br/> 此事件对应于 Exchange 客户端扩展 (ECE) 事件**IExchExtMessageEvents:: OnReadComplete**, 以及自 Outlook 2013 以来添加到对象模型中的**ReadComplete**事件。  <br/> |
   
有关如何使用 dispid 来侦听和处理事件的示例, 请参阅在`CAppEventListener::Invoke` [MFC c + + 2003 .net 中实现 Outlook 2002/XP 事件接收器](https://www.codeproject.com/Articles/4230/Implementing-Outlook-2002-XP-Event-Sinks-in-MFC-C)中所述的 c + + Outlook 解决方案中的函数。
  
## <a name="see-also"></a>另请参阅

- [Outlook 导出的 API](outlook-exported-apis.md)
- [（Outlook 导出的 Api） 的常量](constants-outlook-exported-apis.md)
- [关于 Outlook 导出的 API](about-apis-exported-by-outlook.md)
- [在 MFC c + + 2003 .net 中实现 Outlook 2002/XP 事件接收器](https://www.codeproject.com/Articles/4230/Implementing-Outlook-2002-XP-Event-Sinks-in-MFC-C)

