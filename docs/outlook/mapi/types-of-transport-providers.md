---
title: 传输提供程序的类型
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 772ecab1-7e91-415b-bae8-af8ffb7b7ed9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ca224658552af105d95794b4dd01d2ac76fe084f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406162"
---
# <a name="types-of-transport-providers"></a>传输提供程序的类型

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
所有传输提供程序都支持一系列标准功能，例如：
  
- 为基础邮件系统提供适当的安全性。
    
- 从基础邮件系统发送和接收邮件。
    
- 公开传输提供程序支持的地址类型，以便 MAPI 后台处理程序和客户端应用程序可以正确使用它们。
    
- 接受特定收件人的传递。
    
此外，MAPI 还支持两种特定邮件系统的专用类型的提供程序。
  
|**传输类型**|**添加了功能**|
|:-----|:-----|
|远程传输  <br/> |启用与远程连接的客户端的互操作性。  <br/> |
|TNEF 传输  <br/> |允许在不支持 MAPI 属性的邮件系统上保留这些属性。  <br/> |
   
TNEF 传输用于在支持不同 MAPI 属性集的邮件系统之间转换邮件。 TNEF 传输使用 MAPI [ITnef ： IUnknown](itnefiunknown.md) 接口将目标系统无法直接表示的任何属性转换为可附加到邮件的二进制数据流。 稍后，另一个 TNEF 传输可以使用 **ITnef** 解码数据流，使原始 MAPI 属性对客户端应用程序可用。 此外，如果您的传输需要支持自定义邮件类，则 TNEF 支持是必需的。 有关实现 TNEF 传输的信息，请参阅 Developing [a TNEF-Enabled Transport Provider](developing-a-tnef-enabled-transport-provider.md)。
  
如果您的传输提供程序不是这些类型之一，您必须使用目标平台上提供的基本 MAPI 函数和网络功能来实现它。
  

