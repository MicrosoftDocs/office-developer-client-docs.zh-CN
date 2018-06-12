---
title: 传输提供程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a51547e6-8f0e-45f4-a341-3cfa735112c2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 22b9da0cfe70cf499cc6f3a699eabe4aaee25b0f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779012"
---
# <a name="transport-provider-overview"></a>传输提供程序概述

  
  
**适用于**： Outlook 
  
传输提供程序是作为中介的 MAPI 子系统和一个或多个基础的消息系统的动态链接库 (DLL)。 邮件系统是一些特定机制所发送和接收邮件。 邮件系统的一些示例包括：
  
- 共享的网络文件系统传输提供程序直接写入到的邮件。
    
- 传输提供程序用来连接到消息服务器 TCP/IP 网络接口。
    
- 用户连接到联机服务。
    
- 基于主机的消息或 office 自动化系统。
    
- 远程过程调用的消息的服务器的一组。
    
- 任何可用于将数据从一台计算机传输到另一个。
    
传输提供程序 DLL 必须符合指定 MAPI 的接口。 作为传输提供程序开发人员，您将实现此接口方面存在邮件系统中的功能。
  

