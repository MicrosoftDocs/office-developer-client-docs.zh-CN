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
  
下面的一系列操作描述了传输如何使用 TNEF 方法处理传出和传入的邮件。
  
 **发送包含 TNEF 流的邮件**
  
1. 处理邮件系统支持的邮件属性。
    
2. 以特定于实现的方式标记邮件, 以便接收传输提供程序可以确定邮件需要 TNEF 处理。 例如, 发送到 SMTP 邮件系统的 TNEF 传输提供程序可能会添加一个自定义头字段 (如 "X-包含-TNEF"), 以指示邮件包含 TNEF 数据。
    
3. 获取 tnef 对象, 并使用它将邮件系统不支持的邮件属性封装到 TNEF 流中。
    
4. 使用邮件系统的附件模型对 TNEF 流进行编码。 例如, 如果基础附件模型是用于 uuencode 附件并将其附加到邮件文本, 则传输提供程序必须将 TNEF 流发送到另一个附件中。 传输提供程序还必须实现一种方法, 用于识别在收到邮件时哪个附件包含编码的 TNEF 流。 标记此附件的标准方法是为其提供附件文件名 "winmail.dat"。DAT "。 如果你的传输提供程序执行此操作, 则遵循此约定的任何其他启用 TNEF 的传输提供程序都将能够与之交互。
    
5. 使用[ITnef: IUnknown](itnefiunknown.md)接口方法插入描述邮件文本中邮件附件位置的标记。 
    
6. 通过[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)方法访问带标记的邮件文本, 并将其发送到邮件系统。 
    
 **检索封装的属性**
  
1. 将邮件系统支持的属性写入新邮件中, 包括已标记的邮件文本, 其中包含封装的属性。
    
2. 从正确的附件解码 TNEF 流。
    
3. 对任何其他附件进行解码, 并将其写入邮件中的新 MAPI 附件。
    
4. 使用[OpenTnefStreamEx](opentnefstreamex.md)函数打开 TNEF 流以进行解码。 
    
5. 使用[ITnef:: ExtractProps](itnef-extractprops.md)方法对 TNEF 流进行解码, 并将封装的属性写入新邮件中。 当对编码属性进行解码时, 作为 nonencoded 属性的重复的任何已编码属性将覆盖 nonencoded 属性。 
    
6. 使用[ITnef:: OpenTaggedBody](itnef-opentaggedbody.md)方法分析邮件文本, 以便从邮件文本中的标记中恢复附件位置。 
    

