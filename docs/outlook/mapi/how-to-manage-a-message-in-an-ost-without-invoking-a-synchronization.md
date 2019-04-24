---
title: 在缓存 Exchange 模式下管理 OST 中的邮件而不调用同步
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 3a1f0aa2-813f-222c-f871-0501de5d9dec
description: '包含 c + + 中的代码示例, 该示例演示如何使用 IMsgStore:: OpenEntry 中的 IID_IMessageRaw 获取管理脱机文件夹文件 (OST) 中的邮件的 IMessage 接口, 而无需在客户端处于缓存 Exchange 中时强制下载整个邮件模式.'
ms.openlocfilehash: e50637b496ff43daedad2df27d027d8a6d0dc743
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316392"
---
# <a name="manage-messages-in-ost-without-invoking-a-synchronization-in-cached-exchange-mode"></a>在缓存 Exchange 模式下管理 OST 中的邮件而不调用同步

**适用于**：Outlook 2013 | Outlook 2016 
  
本主题包含 c + + 中的代码示例, 演示如何`IID_IMessageRaw`在**[IMsgStore:: OpenEntry](imsgstore-openentry.md)** 中使用, 以获取管理脱机文件夹文件 (OST) 中的邮件的**[IMessage](imessageimapiprop.md)** 接口, 而无需在客户端上强制下载整个邮件。处于缓存 Exchange 模式。 
  
当客户端处于缓存 Exchange 模式下时, OST 中的邮件可以处于以下两种状态之一:
  
- 将下载包含页眉和正文的整个邮件。
    
- 仅下载了其邮件头的邮件。
    
当您为 OST 中的邮件请求**IMessage**接口且该客户端处于缓存 Exchange 模式时, 请使用`IID_IMessageRaw`。 如果您使用`IID_IMessage`来请求**IMessage**接口, 并且邮件仅在 OST 中下载了其头, 则会调用尝试下载整个邮件的同步。 
  
如果使用`IID_IMessageRaw`或`IID_IMessage`请求**IMessage**接口, 则返回的接口在使用中相同。 使用**** `IID_IMessageRaw`请求的 IMessage 接口返回的电子邮件在 OST 中存在, 但不强制执行同步。 
  
下面的示例演示如何调用**OpenEntry**方法, 而不是`IID_IMessageRaw`传递`IID_IMessage`。
  
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

如果**OpenEntry**方法返回**MAPI_E_INTERFACE_NOT_SUPPORTED**错误代码, 则表明邮件存储区不支持以 raw 模式访问邮件。 在这种情况下, **** 请通过传递`IID_IMessage`来再次尝试 OpenEntry 方法。

> [!IMPORTANT]
>  `IID_IMessageRaw`可能在您当前拥有的可下载头文件中未定义。 在这种情况下, 可以使用以下定义将其添加到代码中。 使用 Microsoft Windows 软件开发工具包 (SDK) 头文件 guiddef.h 中定义的 DEFINE_OLEGUID 宏将 GUID 符号名称与它的值关联。 >  `#if !defined(INITGUID) || defined(USES_IID_IMessageRaw)`>  `DEFINE_OLEGUID(IID_IMessageRaw,0x0002038A, 0, 0);`>  `#endif`
  
## <a name="see-also"></a>另请参阅

- [关于 MAPI 添加件](about-mapi-additions.md) 
- [当 Outlook 处于缓存 Exchange 模式下时，访问远程服务器上的存储区](how-to-access-store-on-remote-server-in-cached-exchange-mode.md)
- [当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)

