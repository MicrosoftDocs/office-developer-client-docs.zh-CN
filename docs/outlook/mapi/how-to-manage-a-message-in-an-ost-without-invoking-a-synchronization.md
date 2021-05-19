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
# <a name="manage-messages-in-ost-without-invoking-a-synchronization-in-cached-exchange-mode"></a><span data-ttu-id="a4083-103">在 OST 中管理邮件，而无需在缓存缓存模式下Exchange同步</span><span class="sxs-lookup"><span data-stu-id="a4083-103">Manage messages in OST without invoking a synchronization in Cached Exchange mode</span></span>

<span data-ttu-id="a4083-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a4083-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a4083-105">本主题包含一个 C++ 代码示例，演示如何在 `IID_IMessageRaw` **[IMsgStore：：OpenEntry](imsgstore-openentry.md)** 中用于获取管理脱机文件夹文件 (OST) 中的邮件的 **[IMessage](imessageimapiprop.md)** 接口，而无需强制在客户端处于缓存 Exchange 模式时下载整个邮件。</span><span class="sxs-lookup"><span data-stu-id="a4083-105">This topic contains a code sample in C++ that shows how to use `IID_IMessageRaw` in **[IMsgStore::OpenEntry](imsgstore-openentry.md)** to obtain an **[IMessage](imessageimapiprop.md)** interface that manages a message in an offline folders file (OST) without forcing a download of the whole message when the client is in Cached Exchange Mode.</span></span> 
  
<span data-ttu-id="a4083-106">当客户端在缓存Exchange模式时，OST 中的邮件可能为以下两种状态之一：</span><span class="sxs-lookup"><span data-stu-id="a4083-106">When a client is in Cached Exchange Mode, messages in the OST can be in one of two states:</span></span>
  
- <span data-ttu-id="a4083-107">下载包含标头和正文的整个邮件。</span><span class="sxs-lookup"><span data-stu-id="a4083-107">The whole message that contains the header and the body is downloaded.</span></span>
    
- <span data-ttu-id="a4083-108">仅下载其头的邮件。</span><span class="sxs-lookup"><span data-stu-id="a4083-108">The message with only its header is downloaded.</span></span>
    
<span data-ttu-id="a4083-109">当您为 OST 中的邮件请求 **IMessage** 接口并且客户端位于缓存Exchange模式时，请使用 `IID_IMessageRaw` 。</span><span class="sxs-lookup"><span data-stu-id="a4083-109">When you request an **IMessage** interface for a message in an OST and the client is in Cached Exchange Mode, use  `IID_IMessageRaw`.</span></span> <span data-ttu-id="a4083-110">如果使用 请求  `IID_IMessage` **IMessage** 接口，并且邮件在 OST 中仅下载其头，则调用尝试下载整个邮件的同步。</span><span class="sxs-lookup"><span data-stu-id="a4083-110">If you use  `IID_IMessage` to request an **IMessage** interface, and if the message has only its header downloaded in the OST, you invoke a synchronization that attempts to download the whole message.</span></span> 
  
<span data-ttu-id="a4083-111">如果使用 或  `IID_IMessageRaw`  `IID_IMessage` 请求 **IMessage** 接口，则返回的接口使用相同。</span><span class="sxs-lookup"><span data-stu-id="a4083-111">If you use  `IID_IMessageRaw` or  `IID_IMessage` to request an **IMessage** interface, the interfaces that are returned are identical in use.</span></span> <span data-ttu-id="a4083-112">使用 请求的 **IMessage** 接口返回 OST 中存在的电子邮件，  `IID_IMessageRaw` 并且不会强制同步。</span><span class="sxs-lookup"><span data-stu-id="a4083-112">The **IMessage** interface that was requested by using  `IID_IMessageRaw` returns an email message as it exists in the OST, and synchronization is not forced.</span></span> 
  
<span data-ttu-id="a4083-113">下面的示例演示如何调用 **OpenEntry** 方法，而不是  `IID_IMessageRaw` 传递  `IID_IMessage` 。</span><span class="sxs-lookup"><span data-stu-id="a4083-113">The following example shows how to call the **OpenEntry** method, passing  `IID_IMessageRaw` instead of  `IID_IMessage`.</span></span>
  
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

<span data-ttu-id="a4083-114">如果 **OpenEntry** 方法返回MAPI_E_INTERFACE_NOT_SUPPORTED错误代码，则表明邮件存储不支持在原始模式下访问邮件。</span><span class="sxs-lookup"><span data-stu-id="a4083-114">If the **OpenEntry** method returns the **MAPI_E_INTERFACE_NOT_SUPPORTED** error code, it indicates that the message store does not support accessing the message in raw mode.</span></span> <span data-ttu-id="a4083-115">在这种情况下，请再次尝试通过传递 的 **OpenEntry** 方法  `IID_IMessage` 。</span><span class="sxs-lookup"><span data-stu-id="a4083-115">In this situation, try the **OpenEntry** method again by passing  `IID_IMessage`.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="a4083-116">`IID_IMessageRaw` 可能未在当前具有的可下载头文件中定义。</span><span class="sxs-lookup"><span data-stu-id="a4083-116">`IID_IMessageRaw` might not be defined in the downloadable header file that you currently have.</span></span> <span data-ttu-id="a4083-117">在这种情况下，可以使用以下定义将其添加到代码中。</span><span class="sxs-lookup"><span data-stu-id="a4083-117">In this case, you can add it to your code by using the following definition.</span></span> <span data-ttu-id="a4083-118">使用 Microsoft Windows DEFINE_OLEGUID 软件开发工具包 (SDK) 头文件 guiddef.h 中定义的 DEFINE_OLEGUID 宏将 GUID 符号名称与它的值关联。</span><span class="sxs-lookup"><span data-stu-id="a4083-118">Use the DEFINE_OLEGUID macro defined in the Microsoft Windows Software Development Kit (SDK) header file guiddef.h to associate the GUID symbolic name with its value.</span></span> >  `#if !defined(INITGUID) || defined(USES_IID_IMessageRaw)`>  `DEFINE_OLEGUID(IID_IMessageRaw,0x0002038A, 0, 0);`>  `#endif`
  
## <a name="see-also"></a><span data-ttu-id="a4083-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4083-119">See also</span></span>

- [<span data-ttu-id="a4083-120">关于 MAPI 添加件</span><span class="sxs-lookup"><span data-stu-id="a4083-120">About MAPI Additions</span></span>](about-mapi-additions.md) 
- [<span data-ttu-id="a4083-121">当 Outlook 处于缓存 Exchange 模式下时，访问远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="a4083-121">Access a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-access-store-on-remote-server-in-cached-exchange-mode.md)
- [<span data-ttu-id="a4083-122">当 Outlook 处于缓存 Exchange 模式下时，打开远程服务器上的存储区</span><span class="sxs-lookup"><span data-stu-id="a4083-122">Open a Store on the Remote Server When Outlook is in Cached Exchange Mode</span></span>](how-to-open-store-on-remote-server-in-cached-exchange-mode.md)

