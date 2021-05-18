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
  
与其他 MAPI 服务提供程序一样，邮件存储是动态链接库 (DLL) ，用于向 MAPI 客户端应用程序和 MAPI 后台处理程序提供基础存储机制的服务。 邮件存储提供程序将基础存储机制呈现为 MAPI 客户端和 MAPI 后台处理程序可以使用的一组分层文件夹和邮件。
  
下图显示了基本 MAPI 邮件存储体系结构。
  
**消息存储体系结构**
  
![邮件存储体系结构](media/storearc.gif "邮件存储体系结构")
  
可以使用您喜欢的任何一种基础存储机制来实现邮件存储提供程序。 但是，您需要了解性能问题。 此外，基础存储机制必须呈现为 MAPI 对象的分层集合。 这些要求意味着邮件存储通常通过使用支持数据库中对象的分层存储且具有编程接口或明确定义的文件结构的现有数据库产品实现。 例如，Microsoft Office Access、SQL 和 Oracle 数据库可以用作基础存储机制。 某些数据库产品具有使 MAPI 功能更易于实现的功能集，因此您的数据库产品选择可能会受邮件存储提供程序需要支持的功能的影响。
  
使用现有数据库作为基础存储机制可节省工作，因为与实现自己的分层存储机制不同，将数据库对象作为 MAPI 对象呈现给 MAPI 客户端通常更容易。 这样做可使你在比实现自己的分层存储机制时更高级别地处理 MAPI 操作。 例如，搜索具有特定主题行的邮件成为构造和提交适当的数据库查询的相当简单的问题，而不是实现复杂的例程来搜索分层存储机制。
  
邮件存储提供程序与 MAPI 客户端和 MAPI 后台处理程序通信，以对文件夹和对象执行操作。 邮件存储提供程序将这些操作转换为基础存储机制上的较低级别的操作。 MAPI 后台处理程序通常在发送和接收邮件时与邮件存储提供程序通信。 MAPI 客户端通常与邮件存储提供程序通信，以操作文件夹层次结构以及读取、编辑、删除和发送邮件。
  
MAPI 后台处理程序和 MAPI 客户端与邮件存储提供程序通信以创建新邮件。 客户端应用程序在用户撰写邮件时执行此操作。 MAPI 后台处理程序在接收传入消息时会这样做。 在任一情况下，新邮件通常会在邮件存储的"收件箱"文件夹中创建（如果有）。
  
邮件存储提供程序大量使用 MAPI 表、文件夹、邮件和属性。 这些对象的实现详细信息记录在 [MAPI Tables](mapi-tables.md)、 [MAPI Folders](mapi-folders.md)、 [MAPI Messages](mapi-messages.md)和 [MAPI Property Overview 中](mapi-property-overview.md)。 在尝试实现邮件存储提供程序之前，您应熟悉该材料。
  
有两种重要的邮件存储提供程序类型：可以充当用户的默认邮件存储的提供程序和无法执行的邮件存储提供程序。 默认邮件存储是客户端应用程序和 MAPI 后台处理程序可以执行任何邮件任务（如接收邮件或创建文件夹）的邮件存储。 默认邮件存储提供程序必须支持比所有邮件存储提供程序所需的最小数量更多的功能。
  
## <a name="see-also"></a>另请参阅

- [MAPI 概念](mapi-concepts.md)

