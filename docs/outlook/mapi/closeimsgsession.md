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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 877bebf0a156c99907505d815ca8d36a4b398678
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412035"
---
# <a name="closeimsgsession"></a><span data-ttu-id="981a8-103">CloseIMsgSession</span><span class="sxs-lookup"><span data-stu-id="981a8-103">CloseIMsgSession</span></span>

  
  
<span data-ttu-id="981a8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="981a8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="981a8-105">关闭邮件会话以及在该会话中创建的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="981a8-105">Closes a message session and all the messages created within that session.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="981a8-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="981a8-106">Header file:</span></span>  <br/> |<span data-ttu-id="981a8-107">Imessage</span><span class="sxs-lookup"><span data-stu-id="981a8-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="981a8-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="981a8-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="981a8-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="981a8-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="981a8-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="981a8-110">Called by:</span></span>  <br/> |<span data-ttu-id="981a8-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="981a8-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
VOID CloseIMsgSession(
  LPMSGSESS lpMsgSess
);
```

## <a name="parameters"></a><span data-ttu-id="981a8-112">参数</span><span class="sxs-lookup"><span data-stu-id="981a8-112">Parameters</span></span>

 <span data-ttu-id="981a8-113">_lpMsgSess_</span><span class="sxs-lookup"><span data-stu-id="981a8-113">_lpMsgSess_</span></span>
  
> <span data-ttu-id="981a8-114">实时指向在邮件会话开始时使用[OpenIMsgSession](openimsgsession.md)函数获取的邮件会话对象的指针。</span><span class="sxs-lookup"><span data-stu-id="981a8-114">[in] Pointer to the message session object obtained using the [OpenIMsgSession](openimsgsession.md) function at the start of the message session.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="981a8-115">返回值</span><span class="sxs-lookup"><span data-stu-id="981a8-115">Return value</span></span>

<span data-ttu-id="981a8-116">无。</span><span class="sxs-lookup"><span data-stu-id="981a8-116">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="981a8-117">说明</span><span class="sxs-lookup"><span data-stu-id="981a8-117">Remarks</span></span>

<span data-ttu-id="981a8-118">客户端应用程序和服务提供程序使用消息会话, 以处理基于基础 OLE **IStorage**对象之上构建的多个相关 MAPI **IMessage**对象。</span><span class="sxs-lookup"><span data-stu-id="981a8-118">A message session is used by client applications and service providers that want to deal with several related MAPI **IMessage** objects built on top of underlying OLE **IStorage** objects.</span></span> <span data-ttu-id="981a8-119">客户端或提供程序使用[OpenIMsgSession](openimsgsession.md)和**CloseIMsgSession**函数来包装邮件会话中的邮件的创建。</span><span class="sxs-lookup"><span data-stu-id="981a8-119">The client or provider uses the [OpenIMsgSession](openimsgsession.md) and **CloseIMsgSession** functions to wrap the creation of such messages inside a message session.</span></span> <span data-ttu-id="981a8-120">一旦打开了消息会话, 客户端或提供程序就会在调用[OpenIMsgOnIStg](openimsgonistg.md)中传递指向它的指针, 以创建新的**IMessage** **IStorage**对象。</span><span class="sxs-lookup"><span data-stu-id="981a8-120">Once the message session is opened, the client or provider passes a pointer to it in a call to [OpenIMsgOnIStg](openimsgonistg.md) to create a new **IMessage**-on- **IStorage** object.</span></span> 
  
<span data-ttu-id="981a8-121">除了邮件的所有附件和其他属性, 消息会话仍跟踪在会话期间打开的所有**IMessage** **IStorage**对象。</span><span class="sxs-lookup"><span data-stu-id="981a8-121">A message session keeps track of all **IMessage**-on- **IStorage** objects opened during the duration of the session, in addition to all the attachments and other properties of the messages.</span></span> <span data-ttu-id="981a8-122">当客户端或提供程序调用**CloseIMsgSession**时, 它将关闭所有这些对象。</span><span class="sxs-lookup"><span data-stu-id="981a8-122">When a client or provider calls **CloseIMsgSession**, it closes all these objects.</span></span> <span data-ttu-id="981a8-123">调用**CloseIMsgSession**是关闭**IMessage**的**IStorage**对象的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="981a8-123">Calling **CloseIMsgSession** is the only way to close **IMessage**-on- **IStorage** objects.</span></span> 
  

