---
title: 发送邮件送达报告
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: abb12ec5-f0b7-488a-a75d-446f4be53e96
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2a31e7d088d5c1f94b272cb4d307f3aff99f32ee
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433078"
---
# <a name="sending-message-delivery-reports"></a>发送邮件送达报告

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
一些基础邮件系统支持送达报告，而有些不支持。 传输提供程序如何确定是否可以将邮件传递或未送达报告发送到客户端应用程序是特定于各个传输提供程序的实现详细信息。 如果送达报告可以发送到客户端应用程序，传输提供程序将使用 [IMAPISupport：：StatusRecips](imapisupport-statusrecips.md) 方法通知 MAPI 一个或多个收件人的传递成功或失败。 然后，MAPI 会生成与这些收件人对应的送达或未送达报告。 传输提供程序还可以通过 **StatusRecips** 将邮件系统本机的传入传递和未送达报告转换为 MAPI 传递报告和未送达报告。
  

