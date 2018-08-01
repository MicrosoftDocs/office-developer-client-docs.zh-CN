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
# <a name="manage-messages-in-ost-without-invoking-a-synchronization-in-cached-exchange-mode"></a><span data-ttu-id="9aace-103">管理 OST 中的邮件，而无需调用缓存 Exchange 模式同步</span><span class="sxs-lookup"><span data-stu-id="9aace-103">Manage messages in OST without invoking a synchronization in Cached Exchange mode</span></span>

<span data-ttu-id="9aace-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9aace-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9aace-105">本主题包含演示如何使用 c + + 中的代码示例`IID_IMessageRaw`中**[IMsgStore::OpenEntry](imsgstore-openentry.md)** 不强制下载整体的情况下获取**[IMessage](imessageimapiprop.md)** 接口管理一条消息，脱机文件夹 (OST) 文件中的消息时客户端缓存 Exchange 模式下。</span><span class="sxs-lookup"><span data-stu-id="9aace-105">This topic contains a code sample in C++ that shows how to use `IID_IMessageRaw` in **[IMsgStore::OpenEntry](imsgstore-openentry.md)** to obtain an **[IMessage](imessageimapiprop.md)** interface that manages a message in an offline folders file (OST) without forcing a download of the whole message when the client is in Cached Exchange Mode.</span></span> 
  
<span data-ttu-id="9aace-106">客户端缓存 Exchange 模式时的 OST 文件中的消息可以是两种状态之一：</span><span class="sxs-lookup"><span data-stu-id="9aace-106">When a client is in Cached Exchange Mode, messages in the OST can be in one of two states:</span></span>
  
- <span data-ttu-id="9aace-107">下载包含标题和正文的整个邮件。</span><span class="sxs-lookup"><span data-stu-id="9aace-107">The whole message that contains the header and the body is downloaded.</span></span>
    
- <span data-ttu-id="9aace-108">下载与只有其标头的消息。</span><span class="sxs-lookup"><span data-stu-id="9aace-108">The message with only its header is downloaded.</span></span>
    
<span data-ttu-id="9aace-109">当您请求**IMessage**接口的 OST 一条消息并且客户端缓存 Exchange 模式下时，使用`IID_IMessageRaw`。</span><span class="sxs-lookup"><span data-stu-id="9aace-109">When you request an **IMessage** interface for a message in an OST and the client is in Cached Exchange Mode, use  `IID_IMessageRaw`.</span></span> <span data-ttu-id="9aace-110">如果您使用`IID_IMessage`请求**IMessage**接口，并您如果邮件仅下载的 OST 文件中的标题，调用尝试下载整个邮件的同步。</span><span class="sxs-lookup"><span data-stu-id="9aace-110">If you use  `IID_IMessage` to request an **IMessage** interface, and if the message has only its header downloaded in the OST, you invoke a synchronization that attempts to download the whole message.</span></span> 
  
<span data-ttu-id="9aace-111">如果您使用`IID_IMessageRaw`或`IID_IMessage`请求**IMessage**接口，返回的接口是在使用相同。</span><span class="sxs-lookup"><span data-stu-id="9aace-111">If you use  `IID_IMessageRaw` or  `IID_IMessage` to request an **IMessage** interface, the interfaces that are returned are identical in use.</span></span> <span data-ttu-id="9aace-112">使用请求的**IMessage**接口`IID_IMessageRaw`返回电子邮件，如它存在于 OST，并不强制同步。</span><span class="sxs-lookup"><span data-stu-id="9aace-112">The **IMessage** interface that was requested by using  `IID_IMessageRaw` returns an email message as it exists in the OST, and synchronization is not forced.</span></span> 
  
<span data-ttu-id="9aace-113">下面的示例演示如何调用**OpenEntry**方法，传递`IID_IMessageRaw`而不是`IID_IMessage`。</span><span class="sxs-lookup"><span data-stu-id="9aace-113">The following example shows how to call the **OpenEntry** method, passing  `IID_IMessageRaw` instead of  `IID_IMessage`.</span></span>
  
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

<span data-ttu-id="9aace-114">如果**OpenEntry**方法返回的**MAPI_E_INTERFACE_NOT_SUPPORTED**错误代码，它指示消息存储不支持访问原始模式中的消息。</span><span class="sxs-lookup"><span data-stu-id="9aace-114">If the **OpenEntry** method returns the **MAPI_E_INTERFACE_NOT_SUPPORTED** error code, it indicates that the message store does not support accessing the message in raw mode.</span></span> <span data-ttu-id="9aace-115">在此情况下，重试**OpenEntry**方法传递`IID_IMessage`。</span><span class="sxs-lookup"><span data-stu-id="9aace-115">In this situation, try the **OpenEntry** method again by passing  `IID_IMessage`.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="9aace-116">`IID_IMessageRaw`不可能当前具有可下载标头文件中定义。</span><span class="sxs-lookup"><span data-stu-id="9aace-116">`IID_IMessageRaw` might not be defined in the downloadable header file that you currently have.</span></span> <span data-ttu-id="9aace-117">在这种情况下，您可以将其添加到您的代码通过使用下面的定义。</span><span class="sxs-lookup"><span data-stu-id="9aace-117">In this case, you can add it to your code by using the following definition.</span></span> <span data-ttu-id="9aace-118">使用 Microsoft Windows 软件开发工具包 (SDK) 标头文件 guiddef.h 中定义的 DEFINE_OLEGUID 宏其值与关联的 GUID 的符号名称。</span><span class="sxs-lookup"><span data-stu-id="9aace-118">Use the DEFINE_OLEGUID macro defined in the Microsoft Windows Software Development Kit (SDK) header file guiddef.h to associate the GUID symbolic name with its value.</span></span> >  `#if !defined(INITGUID) || defined(USES_IID_IMessageRaw)`>  `DEFINE_OLEGUID(IID_IMessageRaw,0x0002038A, 0, 0);`>  `#endif`
  
## <a name="see-also"></a><span data-ttu-id="9aace-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9aace-119">See also</span></span>

- [<span data-ttu-id="9aace-120">关于 MAPI 添加件</span><span class="sxs-lookup"><span data-stu-id="9aace-120">About MAPI Additions</span></span>](about-mapi-additions.md) 
- [<span data-ttu-id="9aace-121">当 Outlook 处于缓存 Exchange 模式下时，访问远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="9aace-121">Access a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-access-store-on-remote-server-in-cached-exchange-mode.md)
- [<span data-ttu-id="9aace-122">当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="9aace-122">Open a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)

