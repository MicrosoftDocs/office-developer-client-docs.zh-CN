---
title: 在 OST 中管理邮件，而无需在缓存缓存模式下Exchange同步
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 3a1f0aa2-813f-222c-f871-0501de5d9dec
description: 包含一个 C++ 代码示例，演示如何使用 IMsgStore：：OpenEntry 中的 IID_IMessageRaw 来获取 IMessage 接口，该接口管理脱机文件夹文件 (OST) 中的邮件，而无需强制在客户端处于缓存 Exchange 模式时下载整个邮件。
ms.openlocfilehash: e50637b496ff43daedad2df27d027d8a6d0dc743
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418755"
---
# <a name="manage-messages-in-ost-without-invoking-a-synchronization-in-cached-exchange-mode"></a>在 OST 中管理邮件，而无需在缓存缓存模式下Exchange同步

**适用于**：Outlook 2013 | Outlook 2016 
  
本主题包含一个 C++ 代码示例，演示如何在 `IID_IMessageRaw` **[IMsgStore：：OpenEntry](imsgstore-openentry.md)** 中用于获取管理脱机文件夹文件 (OST) 中的邮件的 **[IMessage](imessageimapiprop.md)** 接口，而无需强制在客户端处于缓存 Exchange 模式时下载整个邮件。 
  
当客户端在缓存Exchange模式时，OST 中的邮件可能为以下两种状态之一：
  
- 下载包含标头和正文的整个邮件。
    
- 仅下载其头的邮件。
    
当您为 OST 中的邮件请求 **IMessage** 接口并且客户端位于缓存Exchange模式时，请使用 `IID_IMessageRaw` 。 如果使用 请求  `IID_IMessage` **IMessage** 接口，并且邮件在 OST 中仅下载其头，则调用尝试下载整个邮件的同步。 
  
如果使用 或  `IID_IMessageRaw`  `IID_IMessage` 请求 **IMessage** 接口，则返回的接口使用相同。 使用 请求的 **IMessage** 接口返回 OST 中存在的电子邮件，  `IID_IMessageRaw` 并且不会强制同步。 
  
下面的示例演示如何调用 **OpenEntry** 方法，而不是  `IID_IMessageRaw` 传递  `IID_IMessage` 。
  
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

如果 **OpenEntry** 方法返回MAPI_E_INTERFACE_NOT_SUPPORTED错误代码，则表明邮件存储不支持在原始模式下访问邮件。 在这种情况下，请再次尝试通过传递 的 **OpenEntry** 方法  `IID_IMessage` 。

> [!IMPORTANT]
>  `IID_IMessageRaw` 可能未在当前具有的可下载头文件中定义。 在这种情况下，可以使用以下定义将其添加到代码中。 使用 Microsoft Windows DEFINE_OLEGUID 软件开发工具包 (SDK) 头文件 guiddef.h 中定义的 DEFINE_OLEGUID 宏将 GUID 符号名称与它的值关联。 >  `#if !defined(INITGUID) || defined(USES_IID_IMessageRaw)`>  `DEFINE_OLEGUID(IID_IMessageRaw,0x0002038A, 0, 0);`>  `#endif`
  
## <a name="see-also"></a>另请参阅

- [关于 MAPI 添加件](about-mapi-additions.md) 
- [当 Outlook 处于缓存 Exchange 模式下时，访问远程服务器上的存储区](how-to-access-store-on-remote-server-in-cached-exchange-mode.md)
- [当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)

