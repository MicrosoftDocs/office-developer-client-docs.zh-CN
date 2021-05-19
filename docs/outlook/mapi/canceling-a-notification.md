---
title: 取消通知
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: decd5d7d-1f47-47c2-b9c4-be0e652c99dd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fb0972638fdd062c99040694222724566281024f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409760"
---
# <a name="canceling-a-notification"></a>取消通知

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要取消通知，客户端调用通知源 **的 Unadvise** 方法。 调用 **Unadvise** 非常重要，因为它会导致服务提供商发布对建议接收器的引用。 只要服务提供商维护对建议接收器的引用，建议接收器就可以继续接收 [IMAPIAdviseSink：：OnNotify](imapiadvisesink-onnotify.md) 调用。 事实上，由于事件通知的异步特性，即使在成功调用 **Unadvise** 之后，也可以通知客户端。 客户端必须能够随时处理通知的接收。 
  
由于服务提供商实现不同，因此无法调用 **Unadvise** 取消通知的客户端无法假定提供程序何时将释放对通知接收器的引用。 一些服务提供商在发布其建议源时发布对接收器的建议引用。 某些服务提供商不会这样做。 只要服务提供商维护对通知接收器的引用，该通知接收器就可以继续接收通知。 
  

