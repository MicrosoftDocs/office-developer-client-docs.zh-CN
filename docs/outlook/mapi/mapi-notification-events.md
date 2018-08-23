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
ms.openlocfilehash: 8acf197f305373c082ef411732d631535201d488
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567249"
---
# <a name="mapi-notification-events"></a>MAPI 通知事件

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
当客户端应用程序注册事件通知时，它们必须指定一个或多个事件。 他们可以指定的事件取决于预期的 advise 源支持的事件的设置。 有 10 个类型的客户端和服务提供商可以注册，每个由常量的通知。 状态对象通知是一个例外。 状态对象通知是内部的 MAPI 通知;客户端无法为其注册和服务提供程序无法生成它。 下表介绍的事件和能够支持它们的 advise 源对象的类型。 事件常量是附带的事件类型。
  
|**事件类型**|**说明**|**建议源对象**|
|:-----|:-----|:-----|
|严重错误 ( _fnevCriticalError_)  <br/> |全局错误或事件发生，例如会话关闭正在进行。  <br/> |会话，所有类型的消息存储和地址簿对象、 表、 状态  <br/> |
|对象修改 ( _fnevObjectModified_)  <br/> |MAPI 对象已更改。  <br/> |文件夹、 邮件、 所有类型的地址簿对象  <br/> |
|创建的对象 ( _fnevObjectCreated_)  <br/> |已创建一个 MAPI 对象。  <br/> |文件夹、 邮件、 所有类型的地址簿对象  <br/> |
|移动对象 ( _fnevObjectMoved_)  <br/> |MAPI 对象已移动。  <br/> |文件夹、 邮件、 所有类型的地址簿对象  <br/> |
|对象已删除 ( _fnevObjectDeleted_)  <br/> |MAPI 对象已被删除。  <br/> |文件夹、 邮件、 所有类型的地址簿对象  <br/> |
|复制的对象 ( _fnevObjectCopied_)  <br/> |已复制的 MAPI 对象。  <br/> |文件夹、 邮件、 所有类型的地址簿对象  <br/> |
|扩展的事件 ( _fnevExtended_)  <br/> |特定服务提供程序定义的内部事件发生。  <br/> |任何 advise 源对象  <br/> |
|搜索完成 ( _fnevSearchComplete_)  <br/> |完成搜索操作并且可搜索的结果。  <br/> |Folders  <br/> |
|表修改 ( _fnevTableModified_)  <br/> |已更改 MAPI table 对象中的信息。  <br/> |表  <br/> |
|新邮件 ( _fnevNewMail_)  <br/> |邮件已送达并等待处理。  <br/> |消息存储库文件夹  <br/> |
   
由表示不能由任何其他的预定义的事件的事件的服务提供程序定义扩展的事件。 只有知道他们注册服务提供商支持扩展的事件之前的客户端可以注册的事件。 不能为客户端确定高级不知情的情况下，如果服务提供商支持扩展的事件和如果是，如何处理接收时的事件。
  

