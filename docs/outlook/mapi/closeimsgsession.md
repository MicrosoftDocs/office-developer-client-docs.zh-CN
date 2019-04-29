---
title: CloseIMsgSession
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.CloseIMsgSession
api_type:
- COM
ms.assetid: a0a17309-fc59-4822-be9b-b6f623b68bb1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 877bebf0a156c99907505d815ca8d36a4b398678
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412035"
---
# <a name="closeimsgsession"></a>CloseIMsgSession

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
关闭邮件会话以及在该会话中创建的所有邮件。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
VOID CloseIMsgSession(
  LPMSGSESS lpMsgSess
);
```

## <a name="parameters"></a>参数

 _lpMsgSess_
  
> 实时指向在邮件会话开始时使用[OpenIMsgSession](openimsgsession.md)函数获取的邮件会话对象的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

客户端应用程序和服务提供程序使用消息会话, 以处理基于基础 OLE **IStorage**对象之上构建的多个相关 MAPI **IMessage**对象。 客户端或提供程序使用[OpenIMsgSession](openimsgsession.md)和**CloseIMsgSession**函数来包装邮件会话中的邮件的创建。 一旦打开了消息会话, 客户端或提供程序就会在调用[OpenIMsgOnIStg](openimsgonistg.md)中传递指向它的指针, 以创建新的**IMessage** **IStorage**对象。 
  
除了邮件的所有附件和其他属性, 消息会话仍跟踪在会话期间打开的所有**IMessage** **IStorage**对象。 当客户端或提供程序调用**CloseIMsgSession**时, 它将关闭所有这些对象。 调用**CloseIMsgSession**是关闭**IMessage**的**IStorage**对象的唯一方法。 
  

