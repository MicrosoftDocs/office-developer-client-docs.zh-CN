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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389622"
---
# <a name="openimsgsession"></a>OpenIMsgSession

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建并打开在其中创建邮件分组的邮件会话。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE OpenIMsgSession(
  LPMALLOC lpMalloc,
  ULONG ulFlags,
  LPMSGSESS FAR * lppMsgSess
);
```

## <a name="parameters"></a>参数

 _lpMalloc_
  
> [in]对内存分配器对象公开的 OLE [IMalloc](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-imalloc)接口的指针。 MAPI 需要时使用的 OLE [IStorage](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istorage)界面使用此分配方法。 
    
 _ulFlags_
  
> [in]保留;必须为零。 
    
 _lppMsgSess_
  
> [输出]指向到返回的消息的会话对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK
  
> 打开会话。
    
MAPI_E_INVALID_PARAMETER
  
>  _lpMalloc_或_lppMsgSess_为 NULL。 
    
MAPI_E_INVALID_FLAGS
  
> 传递了无效的标志。
    
MAPI_UNICODE
  
> 时调用此函数，客户端或服务提供程序设置 MAPI_UNICODE 标志创建 Unicode.msg 文件。 生成的[Imessage](imessageimapiprop.md)文件显示在其 PR_STORE_SUPPORT_MASK STORE_UNICODE_OK，并支持 Unicode 属性。 
    
## <a name="remarks"></a>说明

消息会话由客户端应用程序和服务提供商想要处理多个相关 MAPI [IMessage: IMAPIProp](imessageimapiprop.md)基于基础 OLE **IStorage**对象的对象。 在客户端或提供程序使用的**OpenIMsgSession**和[CloseIMsgSession](closeimsgsession.md)函数来包装创建的此类邮件内的邮件会话。 后打开消息会话时，在客户端或提供程序将指针传递给它-上- **IStorage**对象创建新**IMessage** [OpenIMsgOnIStg](openimsgonistg.md)将调用。 
  
在创建会话，除了的所有附件和邮件的其他属性期间**IStorage**对象的所有**IMessage**跟踪都的邮件会话。 当客户端或提供程序调用**CloseIMsgSession**时，它将关闭所有这些对象。 调用**CloseIMsgSession**是关闭**IMessage**-上- **IStorage**对象的唯一方式。 
  
 **OpenIMsgSession**使用客户端和需要能够处理多个相关的消息作为 OLE **IStorage**对象的提供程序。 如果只有一个此类邮件是在每次打开，跟踪多个邮件和创建与**OpenIMsgSession**的邮件会话没有理由需要。 
  
因为它处理基础 OLE 对象，MAPI 需要使用 OLE 内存分配。 有关存储的结构化的 OLE 对象和 OLE 内存分配的详细信息，请参阅[OLE 和数据传输](https://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx)。 
  

