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
  
当客户端应用程序注册事件通知时，它们必须指定一个或多个事件。 他们可以指定的事件取决于预期建议源支持的事件集。 客户端和服务提供商可以注册十种类型的通知，每种类型的通知由一个常量表示。 Status 对象通知是一个例外。 状态对象通知是一个内部 MAPI 通知;客户端无法注册它，服务提供商无法生成它。 下表介绍了事件类型以及可支持这些事件的建议源对象。 事件常量包含在事件类型中。
  
|**事件类型**|**说明**|**建议源对象**|
|:-----|:-----|:-----|
|_fnevCriticalError (错误)_  <br/> |发生全局错误或事件，例如会话关闭正在进行中。  <br/> |会话、所有类型的邮件存储和通讯簿对象、表、状态  <br/> |
|修改对象 ( _fnevObjectModified_)   <br/> |MAPI 对象已更改。  <br/> |文件夹、邮件、所有类型的通讯簿对象  <br/> |
|使用 _fnevObjectCreated (创建的对象)_  <br/> |已创建 MAPI 对象。  <br/> |文件夹、邮件、所有类型的通讯簿对象  <br/> |
|对象已 ( _fnevObjectMoved)_  <br/> |已移动 MAPI 对象。  <br/> |文件夹、邮件、所有类型的通讯簿对象  <br/> |
|对象已删除 ( _fnevObjectDeleted)_  <br/> |已删除 MAPI 对象。  <br/> |文件夹、邮件、所有类型的通讯簿对象  <br/> |
|复制的对象 ( _fnevObjectCopied)_  <br/> |已复制 MAPI 对象。  <br/> |文件夹、邮件、所有类型的通讯簿对象  <br/> |
|扩展事件 ( _fnevExtended_)   <br/> |发生了由特定服务提供商定义的内部事件。  <br/> |任何建议源对象  <br/> |
|搜索完成 ( _fnevSearchComplete)_  <br/> |搜索操作已完成，搜索结果可用。  <br/> |Folders  <br/> |
|已修改表 ( _fnevTableModified_)   <br/> |MAPI 表对象中的信息已更改。  <br/> |表格  <br/> |
|新邮件 ( _fnevNewMail_)   <br/> |邮件已传递，正在等待处理。  <br/> |邮件存储，文件夹  <br/> |
   
扩展事件由服务提供商定义，以表示任何其他预定义事件无法覆盖的事件。 只有先知道服务提供程序支持扩展事件的客户端才能注册该事件。 客户端无法事先了解服务提供商是否支持扩展事件，如果支持扩展事件，则确定在接收事件时如何处理此类事件。
  

