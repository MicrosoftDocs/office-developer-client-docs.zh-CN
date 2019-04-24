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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315377"
---
# <a name="types-of-transport-providers"></a>传输提供程序的类型

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
所有传输提供程序都支持一系列标准功能, 如:
  
- 为基础邮件系统提供正确的安全性。
    
- 从基础邮件系统发送和接收邮件。
    
- 公开传输提供程序支持的地址类型, 以便 MAPI 后台处理程序和客户端应用程序可以适当地使用它们。
    
- 接受特定收件人的传递。
    
此外, MAPI 还支持针对特定邮件系统的两种专用类型的提供程序。
  
|**传输类型**|**新增功能**|
|:-----|:-----|
|远程传输  <br/> |启用与远程连接的客户端的互操作性。  <br/> |
|TNEF 传输  <br/> |允许将 MAPI 属性保留在不支持它们的邮件系统上。  <br/> |
   
TNEF 传输用于在支持不同的 MAPI 属性集的邮件系统之间转换邮件。 TNEF 传输使用 MAPI [ITnef: IUnknown](itnefiunknown.md)接口将目标系统不能直接代表的任何属性转换为可以附加到邮件的二进制数据流。 稍后, 另一个 TNEF 传输可以使用**ITnef**对数据流进行解码, 并使原始 MAPI 属性对客户端应用程序可用。 此外, 如果传输需要支持自定义邮件类别, 则需要 TNEF 支持。 有关实现 tnef 传输的信息, 请参阅[开发启用 tnef 的传输提供程序](developing-a-tnef-enabled-transport-provider.md)。
  
如果你的传输提供程序不是这些类型之一, 则必须使用目标平台上可用的基本 MAPI 函数和网络功能来实现它。
  

