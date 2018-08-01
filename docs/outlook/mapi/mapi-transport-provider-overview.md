---
title: MAPI 传输提供程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b193e819-749e-4642-8afc-dbc47b17b617
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 11cd1040bb228d789248a89184572b87cd1688ef
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776351"
---
# <a name="mapi-transport-provider-overview"></a>MAPI 传输提供程序概述

  
  
**适用于**： Outlook 
  
传输提供程序处理邮件传输和接收和必要实现安全性。 他们还负责任何必要预处理和后处理任务。 没有为每个活动的邮件系统通常一个传输提供程序。
  
与传输提供程序通过消息存储提供程序通信客户端应用程序。 
  
传输提供程序注册到 MAPI 处理一个或多个特定类型的收件人的条目。 准备发送一条消息时，MAPI 必须确定哪些传输提供程序应处理传输。 根据收件人的类型，MAPI 甚至可以呼叫在多个传输提供程序。 如果不可用的传输提供程序是唯一可以处理收件人，将会推迟消息传输，直到可重新建立与该提供商的连接。
  
某些消息系统是安全的系统;所有潜在用户需要允许访问之前输入的一组有效的凭据。 MAPI 防止未授权的访问此类安全的消息系统通过传输提供程序在登录时验证凭据。 
  

