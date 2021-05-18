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
  
关闭邮件会话以及该会话中创建的所有邮件。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
VOID CloseIMsgSession(
  LPMSGSESS lpMsgSess
);
```

## <a name="parameters"></a>参数

 _lpMsgSess_
  
> [in]指向在邮件会话开始时使用 [OpenIMsgSession](openimsgsession.md) 函数获取的消息会话对象的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>说明

邮件会话由需要处理基于基础 OLE **IStorage** 对象构建的几个相关 MAPI **IMessage** 对象的客户端应用程序和服务提供商使用。 客户端或提供程序使用 [OpenIMsgSession](openimsgsession.md) 和 **CloseIMsgSession** 函数将此类消息的创建包装在邮件会话中。 打开消息会话后，客户端或提供程序在 [调用 OpenIMsgOnIStg](openimsgonistg.md) 时传递指向该会话的指针，以创建新的 **IMessage**-on- **IStorage** 对象。 
  
邮件会话跟踪会话期间打开的所有 **IMessage**-on- **IStorage** 对象，以及邮件的所有附件和其他属性。 当客户端或提供程序调用 **CloseIMsgSession** 时，它将关闭所有这些对象。 调用 **CloseIMsgSession** 是关闭 **IMessage**-on- **IStorage 对象的唯一** 方法。 
  

