---
title: MAPI 通知事件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ef082d7b-9b2d-4267-beb5-d3ed1d9c7bbf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0d05672a0b136520216357cc85a6b7a125415759
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427953"
---
# <a name="mapi-notification-events"></a>MAPI 通知事件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端应用程序注册事件通知时, 它们必须指定一个或多个事件。 他们可以指定的事件取决于预期的建议源支持的事件集。 客户端和服务提供程序可以为其注册10种类型的通知, 每种类型均由一个常量表示。 状态对象通知是一个例外。 Status 对象通知是一个内部 MAPI 通知;客户端无法注册它, 服务提供商无法生成它。 下表介绍了可支持的事件类型和建议源对象。 事件常量包含在事件类型中。
  
|**事件类型**|**说明**|**通知源对象**|
|:-----|:-----|:-----|
|严重错误 ( _fnevCriticalError_)  <br/> |发生全局错误或事件, 例如正在进行会话关闭。  <br/> |会话, 所有类型的邮件存储和通讯簿对象, 表, 状态  <br/> |
|修改的对象 ( _fnevObjectModified_)  <br/> |MAPI 对象已更改。  <br/> |文件夹、邮件、所有类型的通讯簿对象  <br/> |
|创建的对象 ( _fnevObjectCreated_)  <br/> |已创建 MAPI 对象。  <br/> |文件夹、邮件、所有类型的通讯簿对象  <br/> |
|移动的对象 ( _fnevObjectMoved_)  <br/> |MAPI 对象已移动。  <br/> |文件夹、邮件、所有类型的通讯簿对象  <br/> |
|删除的对象 ( _fnevObjectDeleted_)  <br/> |MAPI 对象已被删除。  <br/> |文件夹、邮件、所有类型的通讯簿对象  <br/> |
|复制的对象 ( _fnevObjectCopied_)  <br/> |MAPI 对象已复制。  <br/> |文件夹、邮件、所有类型的通讯簿对象  <br/> |
|扩展事件 ( _fnevExtended_)  <br/> |特定服务提供程序定义的内部事件已发生。  <br/> |任何建议源对象  <br/> |
|搜索完成 ( _fnevSearchComplete_)  <br/> |已完成搜索操作, 并且搜索结果可用。  <br/> |Folders  <br/> |
|修改的表 ( _fnevTableModified_)  <br/> |MAPI 表对象中的信息已更改。  <br/> |表  <br/> |
|新邮件 ( _fnevNewMail_)  <br/> |邮件已传递, 正在等待处理。  <br/> |邮件存储、文件夹  <br/> |
   
扩展事件由服务提供程序定义, 以表示不能由任何其他预定义事件覆盖的事件。 只有在注册服务提供程序之前知道的客户端支持扩展事件才能为该事件注册。 如果服务提供程序支持一个扩展事件, 且在收到此事件时, 如何处理此类事件, 则客户端无法在不事先知道的情况下确定是否有任何帮助。
  

