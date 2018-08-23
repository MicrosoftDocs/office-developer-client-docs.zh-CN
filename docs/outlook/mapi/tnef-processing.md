---
title: TNEF 处理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d324fb3-d917-4502-b3a4-179c479deb79
description: 上次修改时间： 2012 年 7 月 5 日
ms.openlocfilehash: e6b3ef7c7eb469a5de909d440e22e522218a41f8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569489"
---
# <a name="tnef-processing"></a>TNEF 处理

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
以下一系列操作描述传输如何使用 TNEF 方法处理传出和传入邮件。
  
 **发送一条消息，包括 TNEF 流**
  
1. 处理的消息系统支持的邮件属性。
    
2. 将邮件标记中实现特定方式，以便接收传输提供程序可以确定邮件需要 TNEF 处理。 例如，TNEF 传输提供程序将发送到 SMTP 邮件系统可能会添加一个自定义标头字段，如"X-包含-TNEF"以指示邮件包含 TNEF 数据。
    
3. 获取一个 TNEF 对象并使用它来封装到 TNEF 流不支持在邮件系统的邮件属性。
    
4. 对使用消息系统的附件模型 TNEF 流进行编码。 例如，如果基础附件模型到 uuencode 附件，并将其追加到的消息文本，然后传输提供程序必须 uuencode TNEF 流到另一个附件。 传输提供程序还必须实现识别哪些附件包含已编码的 TNEF 流时收到消息的方法。 标记此附件标准方式是要为其提供"WINMAIL 附件文件名。揭示数据"。 如果您传输提供程序执行此操作，遵循此约定任何其他 TNEF 启用传输提供程序都将能够与之进行互操作。
    
5. 使用[ITnef: IUnknown](itnefiunknown.md)接口方法插入标记描述消息文本中的邮件附件的位置。 
    
6. 通过[IStream](http://msdn.microsoft.com/en-us/library/aa380034%28VS.85%29.aspx)方法访问已标记的邮件文本，并将其发送给邮件系统。 
    
 **若要检索封装的属性**
  
1. 写入到新邮件，包括已标记的邮件文本，其中包含封装的属性支持邮件系统的属性。
    
2. 解码 TNEF stream 从适当的附件。
    
3. 解码任何其他附件，并将它们写入新 MAPI 附件上一条消息。
    
4. 打开 TNEF 流解码使用[OpenTnefStreamEx](opentnefstreamex.md)函数。 
    
5. 使用[ITnef::ExtractProps](itnef-extractprops.md)方法进行解码 TNEF 流，并编写封装的属性到新邮件。 重复 nonencoded 任何的属性编码的属性将覆盖 nonencoded 的属性时进行解码的编码的属性。 
    
6. 使用[ITnef::OpenTaggedBody](itnef-opentaggedbody.md)方法解析的消息文本从消息文本中的标记中恢复附件的位置。 
    

