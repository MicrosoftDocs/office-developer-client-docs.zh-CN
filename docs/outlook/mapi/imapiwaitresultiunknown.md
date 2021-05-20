---
title: 'IMAPIWaitResult : IUnknown'
manager: lindalu
ms.date: 04/26/2021
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIWAITRESULT
api_type:
- COM
ms.assetid: d7157f57-709d-4e53-973b-176954e2bb73
description: IMAPIWaitResult
Last modified: April 26, 2021
ms.openlocfilehash: 67a0fffdd0ab6d4989c12568f4d89808ba5adc7a
ms.sourcegitcommit: 289cececd9fa38a3f4b8a0d7fd1f86adb6be9689
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52062037"
---
# <a name="imapiwaitresult--iunknown"></a>IMAPIWaitResult : IUnknown
  
**适用于：** Outlook 2013 |Outlook 2016 |Outlook 2019 年

IMAPIInitMonitor 的使用者使用此接口来控制等待发生位置。 它允许他们在一个线程上创建对象，并移动另一个线程来执行实际等待。

## <a name="vtable-order"></a>Vtable 顺序

| function | 说明 |
|:-----|:-----|
|[HRESULT IMAPIWaitResult：：End () ](imapiwaitresult-end.md)|调用 以在调用它的线程上启动阻止等待，该线程不需要与调用 *IMAPIInitMonitor：：BeginWait 的线程相同*。|

| 快速信息 | result |
|:-----|:-----|
|继承自：  <br/> |IUnknown  <br/> |
|实现者：  <br/> |  OLMAPI32.DLL<br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IMAPIWaitResult  <br/> |

## <a name="see-also"></a>另请参阅

[IMAPIInitMonitor](imapiinitmonitoriunknown.md)

[IMAPIInitMonitor::BeginWait](imapiinitmonitor-beginwait.md)

[IMAPIInitMonitor : IUnknown](imapiinitmonitoriunknown.md)

[CreateMAPIInitializationMonitor](createmapiinitializationmonitor.md)
