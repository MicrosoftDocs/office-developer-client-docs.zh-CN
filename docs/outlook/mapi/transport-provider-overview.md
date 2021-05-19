---
title: 传输提供程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a51547e6-8f0e-45f4-a341-3cfa735112c2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 53bdba624ba759debba25bae78fb45b0f9d5247e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433155"
---
# <a name="transport-provider-overview"></a>传输提供程序概述

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
传输提供程序是动态链接库， (DLL) 充当 MAPI 子系统与一个或多个基础邮件系统之间的中介。 邮件系统是一些特定的机制，通过该机制可以收发邮件。 邮件系统的一些示例如下：
  
- 传输提供程序直接将邮件写入的共享网络文件系统。
    
- 传输提供程序用于连接到消息服务器的 TCP/IP 网络接口。
    
- 用户连接到的联机服务。
    
- 基于主机的消息传送或 Office 自动化系统。
    
- 对消息服务器的一组远程过程调用。
    
- 可用于将数据从一台计算机转移到另一台计算机的一切内容。
    
传输提供程序 DLL 必须符合 MAPI 指定的接口。 作为传输提供程序开发人员，您将根据邮件系统中提供的功能实现此接口。
  

