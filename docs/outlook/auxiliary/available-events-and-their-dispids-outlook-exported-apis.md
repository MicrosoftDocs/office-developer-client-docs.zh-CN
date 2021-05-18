---
title: 可用的事件和其 dispid （Outlook 导出的 Api）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 1fd848c7-038e-4e2f-8997-c8509b31df79
description: 本节介绍可用事件的调度标识符Outlook事件。
ms.openlocfilehash: 31843a2eb8f91eabdc0dbf54a269270eb172baa7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316875"
---
# <a name="available-events-and-their-dispids-outlook-exported-apis"></a>可用的事件和其 dispid （Outlook 导出的 Api）

本节介绍可用事件的调度标识符Outlook事件。
  
Outlook公开以下调度标识符 (dispids) 以允许 C++ 加载项侦听和处理[IDispatch：：Invoke](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)函数中的相应事件。 
  
|**常量**|**事件的 Dispid**|**说明**|**参数**|**备注**|
|:-----|:-----|:-----|:-----|:-----|
|**dispidBeforePrint** <br/> |0xFC8E  <br/> |用于处理在打印操作之前触发 **的 IDispatch：：Invoke** 函数中的应用程序级事件。  <br/> | 有 2 个未命名的参数：  <br/>  第一个参数的类型为 **VT_BOOL|VT_BREF**。 返回 **VARIANT_TRUE** 参数中的值以取消事件。  <br/>  第二个参数未使用，应忽略。  <br/> |此 dispid 自 2010 Outlook可用。  <br/> |
|**dispidEventReadComplete** <br/> |0xFC8F  <br/> |用于处理 **IDispatch：：Invoke** 函数中的项目级事件，该事件在项目Outlook读取完项目属性后触发。  <br/> |只有一个参数  _Cancel，_ 其类型为 **VT_BOOL|VT_BREF**。 返回 **VARIANT_TRUE** 参数中的值以取消读取操作。  <br/> |此 dispid 自 2010 Outlook可用。  <br/> 此事件对应于 Exchange 客户端扩展 (ECE) 事件 **IExchExtMessageEvents：：OnReadComplete，** 以及自 Outlook 2013 以来已添加到对象模型中的 **ReadComplete** 事件。  <br/> |
   
有关如何使用 dispid 侦听和处理事件的示例，请参阅在 `CAppEventListener::Invoke` [MFC C++ 2003 .NET 中实现 Outlook 2002/XP 事件](https://www.codeproject.com/Articles/4230/Implementing-Outlook-2002-XP-Event-Sinks-in-MFC-C)接收器中所述的 C++ Outlook 解决方案中的 函数。
  
## <a name="see-also"></a>另请参阅

- [Outlook 导出的 API](outlook-exported-apis.md)
- [（Outlook 导出的 Api） 的常量](constants-outlook-exported-apis.md)
- [关于 Outlook 导出的 API](about-apis-exported-by-outlook.md)
- [在 MFC C++ 2003 .NET 中实现 Outlook 2002/XP 事件接收器](https://www.codeproject.com/Articles/4230/Implementing-Outlook-2002-XP-Event-Sinks-in-MFC-C)

