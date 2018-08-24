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
ms.openlocfilehash: a9bba55b585b09d6a5779ba41a283b20c645656f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576230"
---
# <a name="types-of-transport-providers"></a>传输提供程序的类型

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
所有传输提供程序都支持各种标准版功能，如：
  
- 为基础的消息系统提供适当的安全。
    
- 发送和接收来自基础消息系统消息。
    
- 公开地址类型，以便的 MAPI 后台处理程序和客户端应用程序可以相应地使用它们支持传输提供程序。
    
- 对特定收件人的接受传递。
    
此外，MAPI 支持提供程序的两个专用的的类型的特定邮件系统。
  
|**传输类型**|**新增的功能**|
|:-----|:-----|
|远程传输  <br/> |与远程连接的客户端实现互操作性。  <br/> |
|TNEF 传输  <br/> |允许消息不支持它们的系统上保留的 MAPI 属性。  <br/> |
   
TNEF 传输用于翻译支持不同的 MAPI 属性集的邮件系统之间的邮件。 TNEF 传输使用 MAPI [ITnef: IUnknown](itnefiunknown.md)接口将直接转换可以附加到邮件二进制数据流的目标系统不能代表其任何属性。 更高版本，另一个 TNEF 传输可以使用**ITnef**解码数据流并使其原始的 MAPI 属性供客户端应用程序。 此外，TNEF 支持时需要您传输需要支持自定义邮件类别。 有关实现 TNEF 传输的信息，请参阅[开发 TNEF-Enabled 传输提供程序](developing-a-tnef-enabled-transport-provider.md)。
  
如果您传输提供程序不是其中一种类型，必须将实现它的基本 MAPI 函数和网络功能在您的目标平台上可用。
  

