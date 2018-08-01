---
title: 管理 OST 中的邮件，而无需调用缓存 Exchange 模式同步
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 3a1f0aa2-813f-222c-f871-0501de5d9dec
description: 包含的代码示例演示如何使用在 IMsgStore::OpenEntry IID_IMessageRaw 获取 IMessage 接口管理一条消息，脱机文件夹 (OST) 文件中的 c + + 中，而不在缓存 Exchange 客户端时强制整个邮件的下载模式。
ms.openlocfilehash: e32bf4f64bfb91979133ee983e45481b3d5b9732
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775117"
---
# <a name="manage-messages-in-ost-without-invoking-a-synchronization-in-cached-exchange-mode"></a>管理 OST 中的邮件，而无需调用缓存 Exchange 模式同步

**适用于**： Outlook 
  
本主题包含演示如何使用 c + + 中的代码示例`IID_IMessageRaw`中**[IMsgStore::OpenEntry](imsgstore-openentry.md)** 不强制下载整体的情况下获取**[IMessage](imessageimapiprop.md)** 接口管理一条消息，脱机文件夹 (OST) 文件中的消息时客户端缓存 Exchange 模式下。 
  
客户端缓存 Exchange 模式时的 OST 文件中的消息可以是两种状态之一：
  
- 下载包含标题和正文的整个邮件。
    
- 下载与只有其标头的消息。
    
当您请求**IMessage**接口的 OST 一条消息并且客户端缓存 Exchange 模式下时，使用`IID_IMessageRaw`。 如果您使用`IID_IMessage`请求**IMessage**接口，并您如果邮件仅下载的 OST 文件中的标题，调用尝试下载整个邮件的同步。 
  
如果您使用`IID_IMessageRaw`或`IID_IMessage`请求**IMessage**接口，返回的接口是在使用相同。 使用请求的**IMessage**接口`IID_IMessageRaw`返回电子邮件，如它存在于 OST，并不强制同步。 
  
下面的示例演示如何调用**OpenEntry**方法，传递`IID_IMessageRaw`而不是`IID_IMessage`。
  
```cpp
HRESULT HrOpenRawMessage ( 
    LPMDB lpMSB,  
    ULONG cbEntryID,  
    LPENTRYID lpEntryID,  
    ULONG ulFlags,  
    LPMESSAGE* lpMessage) 
{ 
    ULONG ulObjType = NULL; 
 
    HRESULT hRes = lpMDB->OpenEntry( 
        cbEntryID, 
        lpEntryID, 
        IID_IMessageRaw, 
        ulFlags, 
        &ulObjType, 
        (LPUNKNOWN*) lpMessage)); 
 
   return hRes; 
} 

```

如果**OpenEntry**方法返回的**MAPI_E_INTERFACE_NOT_SUPPORTED**错误代码，它指示消息存储不支持访问原始模式中的消息。 在此情况下，重试**OpenEntry**方法传递`IID_IMessage`。

> [!IMPORTANT]
>  `IID_IMessageRaw`不可能当前具有可下载标头文件中定义。 在这种情况下，您可以将其添加到您的代码通过使用下面的定义。 使用 Microsoft Windows 软件开发工具包 (SDK) 标头文件 guiddef.h 中定义的 DEFINE_OLEGUID 宏其值与关联的 GUID 的符号名称。 >  `#if !defined(INITGUID) || defined(USES_IID_IMessageRaw)`>  `DEFINE_OLEGUID(IID_IMessageRaw,0x0002038A, 0, 0);`>  `#endif`
  
## <a name="see-also"></a>另请参阅

- [关于 MAPI 添加件](about-mapi-additions.md) 
- [当 Outlook 处于缓存 Exchange 模式下时，访问远程服务器上的存储区](how-to-access-store-on-remote-server-in-cached-exchange-mode.md)
- [当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)

