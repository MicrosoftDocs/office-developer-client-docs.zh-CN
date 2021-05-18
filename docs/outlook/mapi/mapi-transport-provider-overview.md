---
title: MAPI 传输提供程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b193e819-749e-4642-8afc-dbc47b17b617
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 20b03f7c52ec86d1fb554bf69c53947c3dda4f36
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404573"
---
# <a name="mapi-transport-provider-overview"></a>MAPI 传输提供程序概述

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
传输提供商负责处理邮件传输和接收，并在必要时实现安全性。 它们还负责任何必要的预处理和后处理任务。 每个活动邮件系统通常有一个传输提供程序。
  
客户端应用程序通过邮件存储提供程序与传输提供程序通信。 
  
传输提供程序在 MAPI 中注册以处理一个或多个特定类型的收件人条目。 当准备好发送邮件时，MAPI 必须确定哪个传输提供程序应处理传输。 根据收件人的类型，MAPI 甚至可以调用多个传输提供程序。 如果不可用的传输提供程序是唯一可以处理收件人的传输提供程序，则邮件传输将延迟，直到可以重新建立与该提供商的连接。
  
某些邮件系统是安全系统;所有潜在用户都需要在允许访问之前输入一组有效凭据。 MAPI 通过让传输提供程序在登录时验证凭据来防止对此类安全邮件系统的未经授权的访问。 
  

