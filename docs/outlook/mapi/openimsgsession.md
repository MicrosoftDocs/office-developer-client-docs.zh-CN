---
title: OpenIMsgSession
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.OpenIMsgSession
api_type:
- COM
ms.assetid: f75229e3-5f44-4298-8706-9eddf0ef124c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 607105bd58a14a3510f1ae71246069440a4f05cb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326192"
---
# <a name="openimsgsession"></a>OpenIMsgSession

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建并打开一个邮件会话, 其中对在其中创建的邮件进行分组。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
SCODE OpenIMsgSession(
  LPMALLOC lpMalloc,
  ULONG ulFlags,
  LPMSGSESS FAR * lppMsgSess
);
```

## <a name="parameters"></a>参数

 _lpMalloc_
  
> 实时指向用于公开 OLE [IMalloc](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-imalloc)接口的内存分配器对象的指针。 使用 OLE [IStorage](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istorage)接口时, MAPI 需要使用此分配方法。 
    
 _ulFlags_
  
> 实时保留必须为零。 
    
 _lppMsgSess_
  
> 排除指向返回的邮件会话对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK
  
> 会话已打开。
    
MAPI_E_INVALID_PARAMETER
  
>  _lpMalloc_或_lppMsgSess_为 NULL。 
    
MAPI_E_INVALID_FLAGS
  
> 传递了无效的标志。
    
MAPI_UNICODE
  
> 调用此函数时, 客户端或服务提供程序将 MAPI_UNICODE 标志设置为创建 UNICODE .msg 文件。 生成的[Imessage](imessageimapiprop.md)文件在其 PR_STORE_SUPPORT_MASK 中显示 STORE_UNICODE_OK, 并支持 UNICODE 属性。 
    
## <a name="remarks"></a>注解

要处理多个相关 MAPI IMessage 的客户端应用程序和服务提供程序使用消息会话, 这些对象是基于基础 OLE **IStorage**对象的基础构建的[IMAPIProp](imessageimapiprop.md)对象。 客户端或提供程序使用**OpenIMsgSession**和[CloseIMsgSession](closeimsgsession.md)函数来包装邮件会话中的邮件的创建。 一旦打开了消息会话, 客户端或提供程序就会在调用[OpenIMsgOnIStg](openimsgonistg.md)中传递指向它的指针, 以创建新的**IMessage** **IStorage**对象。 
  
除了邮件的所有附件和其他属性, 消息会话仍跟踪在会话期间创建的所有**IMessage** **IStorage**对象。 当客户端或提供程序调用**CloseIMsgSession**时, 它将关闭所有这些对象。 调用**CloseIMsgSession**是关闭**IMessage**的**IStorage**对象的唯一方法。 
  
 **OpenIMsgSession**由需要能够将几个相关邮件作为 OLE **IStorage**对象处理的客户端和提供程序使用。 如果一次只能打开一个这样的邮件, 则无需跟踪多个邮件, 也无需创建与**OpenIMsgSession**的邮件会话。 
  
因为它处理的是基础 ole 对象, 所以 MAPI 需要使用 OLE 内存分配。 有关 ole 结构化存储对象和 ole 内存分配的详细信息, 请参阅[OLE and Data Transfer](https://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx)。 
  

