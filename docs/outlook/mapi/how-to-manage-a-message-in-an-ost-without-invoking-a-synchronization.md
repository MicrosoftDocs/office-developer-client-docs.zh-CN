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
# <a name="manage-messages-in-ost-without-invoking-a-synchronization-in-cached-exchange-mode"></a><span data-ttu-id="c974d-103">在缓存 Exchange 模式下管理 OST 中的邮件而不调用同步</span><span class="sxs-lookup"><span data-stu-id="c974d-103">Manage messages in OST without invoking a synchronization in Cached Exchange mode</span></span>

<span data-ttu-id="c974d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c974d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c974d-105">本主题包含 c + + 中的代码示例, 演示如何`IID_IMessageRaw`在**[IMsgStore:: OpenEntry](imsgstore-openentry.md)** 中使用, 以获取管理脱机文件夹文件 (OST) 中的邮件的**[IMessage](imessageimapiprop.md)** 接口, 而无需在客户端上强制下载整个邮件。处于缓存 Exchange 模式。</span><span class="sxs-lookup"><span data-stu-id="c974d-105">This topic contains a code sample in C++ that shows how to use `IID_IMessageRaw` in **[IMsgStore::OpenEntry](imsgstore-openentry.md)** to obtain an **[IMessage](imessageimapiprop.md)** interface that manages a message in an offline folders file (OST) without forcing a download of the whole message when the client is in Cached Exchange Mode.</span></span> 
  
<span data-ttu-id="c974d-106">当客户端处于缓存 Exchange 模式下时, OST 中的邮件可以处于以下两种状态之一:</span><span class="sxs-lookup"><span data-stu-id="c974d-106">When a client is in Cached Exchange Mode, messages in the OST can be in one of two states:</span></span>
  
- <span data-ttu-id="c974d-107">将下载包含页眉和正文的整个邮件。</span><span class="sxs-lookup"><span data-stu-id="c974d-107">The whole message that contains the header and the body is downloaded.</span></span>
    
- <span data-ttu-id="c974d-108">仅下载了其邮件头的邮件。</span><span class="sxs-lookup"><span data-stu-id="c974d-108">The message with only its header is downloaded.</span></span>
    
<span data-ttu-id="c974d-109">当您为 OST 中的邮件请求**IMessage**接口且该客户端处于缓存 Exchange 模式时, 请使用`IID_IMessageRaw`。</span><span class="sxs-lookup"><span data-stu-id="c974d-109">When you request an **IMessage** interface for a message in an OST and the client is in Cached Exchange Mode, use  `IID_IMessageRaw`.</span></span> <span data-ttu-id="c974d-110">如果您使用`IID_IMessage`来请求**IMessage**接口, 并且邮件仅在 OST 中下载了其头, 则会调用尝试下载整个邮件的同步。</span><span class="sxs-lookup"><span data-stu-id="c974d-110">If you use  `IID_IMessage` to request an **IMessage** interface, and if the message has only its header downloaded in the OST, you invoke a synchronization that attempts to download the whole message.</span></span> 
  
<span data-ttu-id="c974d-111">如果使用`IID_IMessageRaw`或`IID_IMessage`请求**IMessage**接口, 则返回的接口在使用中相同。</span><span class="sxs-lookup"><span data-stu-id="c974d-111">If you use  `IID_IMessageRaw` or  `IID_IMessage` to request an **IMessage** interface, the interfaces that are returned are identical in use.</span></span> <span data-ttu-id="c974d-112">使用\*\*\*\* `IID_IMessageRaw`请求的 IMessage 接口返回的电子邮件在 OST 中存在, 但不强制执行同步。</span><span class="sxs-lookup"><span data-stu-id="c974d-112">The **IMessage** interface that was requested by using  `IID_IMessageRaw` returns an email message as it exists in the OST, and synchronization is not forced.</span></span> 
  
<span data-ttu-id="c974d-113">下面的示例演示如何调用**OpenEntry**方法, 而不是`IID_IMessageRaw`传递`IID_IMessage`。</span><span class="sxs-lookup"><span data-stu-id="c974d-113">The following example shows how to call the **OpenEntry** method, passing  `IID_IMessageRaw` instead of  `IID_IMessage`.</span></span>
  
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

<span data-ttu-id="c974d-114">如果**OpenEntry**方法返回**MAPI_E_INTERFACE_NOT_SUPPORTED**错误代码, 则表明邮件存储区不支持以 raw 模式访问邮件。</span><span class="sxs-lookup"><span data-stu-id="c974d-114">If the **OpenEntry** method returns the **MAPI_E_INTERFACE_NOT_SUPPORTED** error code, it indicates that the message store does not support accessing the message in raw mode.</span></span> <span data-ttu-id="c974d-115">在这种情况下, \*\*\*\* 请通过传递`IID_IMessage`来再次尝试 OpenEntry 方法。</span><span class="sxs-lookup"><span data-stu-id="c974d-115">In this situation, try the **OpenEntry** method again by passing  `IID_IMessage`.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="c974d-116">`IID_IMessageRaw`可能在您当前拥有的可下载头文件中未定义。</span><span class="sxs-lookup"><span data-stu-id="c974d-116">`IID_IMessageRaw` might not be defined in the downloadable header file that you currently have.</span></span> <span data-ttu-id="c974d-117">在这种情况下, 可以使用以下定义将其添加到代码中。</span><span class="sxs-lookup"><span data-stu-id="c974d-117">In this case, you can add it to your code by using the following definition.</span></span> <span data-ttu-id="c974d-118">使用 Microsoft Windows 软件开发工具包 (SDK) 头文件 guiddef.h 中定义的 DEFINE_OLEGUID 宏将 GUID 符号名称与它的值关联。</span><span class="sxs-lookup"><span data-stu-id="c974d-118">Use the DEFINE_OLEGUID macro defined in the Microsoft Windows Software Development Kit (SDK) header file guiddef.h to associate the GUID symbolic name with its value.</span></span> >  `#if !defined(INITGUID) || defined(USES_IID_IMessageRaw)`>  `DEFINE_OLEGUID(IID_IMessageRaw,0x0002038A, 0, 0);`>  `#endif`
  
## <a name="see-also"></a><span data-ttu-id="c974d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c974d-119">See also</span></span>

- [<span data-ttu-id="c974d-120">关于 MAPI 添加件</span><span class="sxs-lookup"><span data-stu-id="c974d-120">About MAPI Additions</span></span>](about-mapi-additions.md) 
- [<span data-ttu-id="c974d-121">当 Outlook 处于缓存 Exchange 模式下时，访问远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="c974d-121">Access a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-access-store-on-remote-server-in-cached-exchange-mode.md)
- [<span data-ttu-id="c974d-122">当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="c974d-122">Open a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)

