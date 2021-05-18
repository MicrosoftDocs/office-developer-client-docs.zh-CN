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
  
创建并打开一个邮件会话，该会话对其中创建的邮件进行分组。 
  
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
  
> [in]指向公开 OLE [IMalloc 接口的内存分配器对象的](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-imalloc) 指针。 使用 OLE [IStorage](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istorage) 接口时，MAPI 需要使用此分配方法。 
    
 _ulFlags_
  
> [in]保留;必须为零。 
    
 _lppMsgSess_
  
> [out]指向返回的邮件会话对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK
  
> 会话已打开。
    
MAPI_E_INVALID_PARAMETER
  
>  _lpMalloc_ 或  _lppMsgSess_ 为 NULL。 
    
MAPI_E_INVALID_FLAGS
  
> 传递了无效标志。
    
MAPI_UNICODE
  
> 调用此函数时，客户端或服务提供商设置 MAPI_UNICODE 标志以创建 Unicode .msg 文件。 生成的 [Imessage](imessageimapiprop.md) 文件在其STORE_UNICODE_OK中显示PR_STORE_SUPPORT_MASK并支持 Unicode 属性。 
    
## <a name="remarks"></a>备注

消息会话由需要处理多个相关 MAPI [IMessage：IMAPIProp](imessageimapiprop.md) 对象（基于基础 OLE **IStorage** 对象构建）的客户端应用程序和服务提供商使用。 客户端或提供程序使用 **OpenIMsgSession** 和 [CloseIMsgSession](closeimsgsession.md) 函数将此类消息的创建包装在邮件会话中。 打开消息会话后，客户端或提供程序在 [调用 OpenIMsgOnIStg](openimsgonistg.md) 时传递指向该会话的指针，以创建新的 **IMessage**-on- **IStorage** 对象。 
  
邮件会话跟踪会话期间创建的所有 **IMessage**-on- **IStorage** 对象，以及邮件的所有附件和其他属性。 当客户端或提供程序调用 **CloseIMsgSession** 时，它将关闭所有这些对象。 调用 **CloseIMsgSession** 是关闭 **IMessage**-on- **IStorage 对象的唯一** 方法。 
  
 需要能够将多个相关消息作为 OLE **IStorage** 对象处理的客户端和提供程序使用 **OpenIMsgSession。** 如果一次仅打开一条此类邮件，则无需跟踪多个邮件，也无需使用 **OpenIMsgSession** 创建邮件会话。 
  
因为它处理的是基础 OLE 对象，所以 MAPI 需要使用 OLE 内存分配。 有关 OLE 结构化存储对象和 OLE 内存分配的信息，请参阅 [OLE 和数据传输](https://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx)。 
  

