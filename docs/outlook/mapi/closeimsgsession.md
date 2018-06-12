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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: c190691c8cfcb9b049bcf9ee4f21436e20955def
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774659"
---
# <a name="closeimsgsession"></a>CloseIMsgSession

  
  
**适用于**： Outlook 
  
关闭消息会话并在该会话中创建的所有消息。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Imessage.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
VOID CloseIMsgSession(
  LPMSGSESS lpMsgSess
);
```

## <a name="parameters"></a>参数

 _lpMsgSess_
  
> [in]对消息会话的开头使用[OpenIMsgSession](openimsgsession.md)函数获取邮件会话对象的指针。 
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>备注

客户端应用程序和服务提供商想要处理基于基础 OLE **IStorage**对象的多个相关 MAPI **IMessage**对象使用的邮件会话。 在客户端或提供程序使用的[OpenIMsgSession](openimsgsession.md)和**CloseIMsgSession**函数来包装创建的此类邮件内的邮件会话。 后打开消息会话时，在客户端或提供程序将指针传递给它-上- **IStorage**对象创建新**IMessage** [OpenIMsgOnIStg](openimsgonistg.md)将调用。 
  
打开会话，除了的所有附件和邮件的其他属性的持续时间内的所有**IMessage**-亮- **IStorage**对象跟踪都的邮件会话。 当客户端或提供程序调用**CloseIMsgSession**时，它将关闭所有这些对象。 调用**CloseIMsgSession**是关闭**IMessage**-上- **IStorage**对象的唯一方式。 
  

