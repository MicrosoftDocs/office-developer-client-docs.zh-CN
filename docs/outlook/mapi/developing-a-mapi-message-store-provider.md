---
title: 开发 MAPI 邮件存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 83692674-0b5a-468d-9cd7-a2ac3d140bda
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 76332b57b2957b5682efb415121ea6db42409c30
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412609"
---
# <a name="developing-a-mapi-message-store-provider"></a>开发 MAPI 邮件存储提供程序
  
**适用于**：Outlook 2013 | Outlook 2016 
  
与其他 MAPI 服务提供程序一样, 邮件存储是向 mapi 客户端应用程序和 mapi 后台处理程序提供基础存储机制的服务的动态链接库 (dll)。 邮件存储区提供程序将基础存储机制显示为 mapi 客户端和 mapi 后台处理程序可以使用的一组分层文件夹和邮件。
  
下图显示了基本 MAPI 邮件存储库体系结构。
  
**消息存储体系结构**
  
![邮件存储区体系结构](media/storearc.gif "邮件存储区体系结构")
  
您可以使用所需的任何种类的基础存储机制来实现邮件存储区提供程序。 但是, 您需要注意性能方面的问题。 此外, 基础存储机制必须显示为 MAPI 对象的分层集合。 这些要求意味着邮件存储通常是使用现有的数据库产品实现的, 该产品支持数据库中的对象的分层存储, 并且具有编程接口或定义完善的文件结构。 例如, Microsoft Office Access、SQL 和 Oracle 数据库可用作基础存储机制。 某些数据库产品的功能集更易于实现 MAPI 功能, 因此您的数据库产品选择可能会受到您的邮件存储提供程序所需支持的功能的影响。
  
使用现有数据库作为基础存储机制可节省您的工作, 因为将数据库对象作为 mapi 对象提供给 mapi 对象通常要比实施自己的分层存储机制更容易。 这样一来, 可以将 MAPI 操作视为比实施自己的分层存储机制更高的级别。 例如, 搜索带有特定主题行的邮件会非常简单, 那就是构建和提交适当的数据库查询, 而不是实施复杂的例程来搜索分层存储机制。
  
邮件存储提供程序与 mapi 客户端和 mapi 后台处理程序通信, 以对文件夹和对象执行操作。 邮件存储提供程序将这些操作转换为对基础存储机制的较低级别操作。 MAPI 后台处理程序通常会在发送和接收邮件时与邮件存储提供程序进行通信。 MAPI 客户端通常与邮件存储提供程序通信, 以处理文件夹层次结构以及读取、编辑、删除和发送邮件。
  
mapi 后台处理程序和 mapi 客户端都与邮件存储提供程序通信, 以创建新邮件。 当用户撰写邮件时, 客户端应用程序将执行此操作。 MAPI 后台处理程序在收到传入邮件时执行此工作。 无论是哪种情况, 通常都会在邮件存储区 (如果有) 的 "收件箱" 文件夹中创建新邮件。
  
邮件存储提供程序大量使用 MAPI 表、文件夹、邮件和属性。 这些对象的实现详细信息记录在[mapi 表](mapi-tables.md)、 [mapi 文件夹](mapi-folders.md)、 [mapi 邮件](mapi-messages.md)和[mapi 属性概述](mapi-property-overview.md)中。 在尝试实现邮件存储提供程序之前, 您应熟悉该资料。
  
有两种重要的邮件存储提供程序: 它们可以充当用户的默认邮件存储, 不能作为用户的默认邮件存储。 默认邮件存储是指客户端应用程序和 MAPI 后台处理程序可以执行任何邮件任务 (如接收邮件或创建文件夹) 的邮件存储。 默认邮件存储提供程序必须支持的功能数多于所有邮件存储提供程序所需的最小数量。
  
## <a name="see-also"></a>另请参阅

- [MAPI 概念](mapi-concepts.md)

