---
title: TNEF 处理
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d324fb3-d917-4502-b3a4-179c479deb79
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: 066ad3dfb64161e326b92fef7774d5b3b9461d8a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339597"
---
# <a name="tnef-processing"></a>TNEF 处理

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
以下一系列操作介绍了传输如何使用 TNEF 方法来处理传出和传入的邮件。
  
 **发送包含 TNEF 流的消息**
  
1. 处理邮件系统支持的邮件属性。
    
2. 以特定实现方式标记邮件，以便接收传输提供程序可以确定邮件需要 TNEF 处理。 例如，发送到 SMTP 邮件系统的 TNEF 传输提供程序可能会添加自定义头字段（如"X-CONTAINS-TNEF"）以指示邮件包含 TNEF 数据。
    
3. 获取一个 TNEF 对象，并使用它将邮件系统不支持的邮件属性封装到 TNEF 流中。
    
4. 使用邮件系统的附件模型对 TNEF 流进行编码。 例如，如果基础附件模型是 uuencode 附件并将其附加到邮件文本，则传输提供程序必须将 TNEF 流编码为其他附件。 传输提供程序还必须实现一种方法，用于识别在接收邮件时包含编码 TNEF 流的附件。 标记此附件的标准方法为，为附件提供"WINMAIL"文件名。DAT"。 如果传输提供程序这样做，则遵循此约定的其他任何启用 TNEF 的传输提供程序将能够与它进行互操作。
    
5. 使用 [ITnef ： IUnknown](itnefiunknown.md) 接口方法插入描述邮件文本中邮件附件位置的标记。 
    
6. 通过 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 方法访问带标记的邮件文本，并将其发送到邮件系统。 
    
 **检索封装的属性**
  
1. 将邮件系统支持的属性写入新邮件，包括包含封装属性的带标记的邮件文本。
    
2. 从正确的附件解码 TNEF 流。
    
3. 解码任何其他附件，并写入邮件上的新 MAPI 附件。
    
4. 使用 [OpenTnefStreamEx](opentnefstreamex.md) 函数打开 TNEF 流进行解码。 
    
5. 使用 [ITnef：：ExtractProps](itnef-extractprops.md) 方法可解码 TNEF 流，将封装的属性写入新消息中。 解码编码属性时，任何为非编码属性重复的编码属性都将覆盖非编码属性。 
    
6. 使用 [ITnef：：OpenTaggedBody](itnef-opentaggedbody.md) 方法分析邮件文本，以从邮件文本中的标记恢复附件位置。 
    

