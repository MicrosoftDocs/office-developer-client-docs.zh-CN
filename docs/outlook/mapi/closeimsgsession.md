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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334935"
---
# <a name="closeimsgsession"></a><span data-ttu-id="cb54c-103">CloseIMsgSession</span><span class="sxs-lookup"><span data-stu-id="cb54c-103">CloseIMsgSession</span></span>

  
  
<span data-ttu-id="cb54c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cb54c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cb54c-105">关闭邮件会话以及在该会话中创建的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="cb54c-105">Closes a message session and all the messages created within that session.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cb54c-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="cb54c-106">Header file:</span></span>  <br/> |<span data-ttu-id="cb54c-107">Imessage</span><span class="sxs-lookup"><span data-stu-id="cb54c-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="cb54c-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="cb54c-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="cb54c-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="cb54c-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="cb54c-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="cb54c-110">Called by:</span></span>  <br/> |<span data-ttu-id="cb54c-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="cb54c-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
VOID CloseIMsgSession(
  LPMSGSESS lpMsgSess
);
```

## <a name="parameters"></a><span data-ttu-id="cb54c-112">参数</span><span class="sxs-lookup"><span data-stu-id="cb54c-112">Parameters</span></span>

 <span data-ttu-id="cb54c-113">_lpMsgSess_</span><span class="sxs-lookup"><span data-stu-id="cb54c-113">_lpMsgSess_</span></span>
  
> <span data-ttu-id="cb54c-114">实时指向在邮件会话开始时使用[OpenIMsgSession](openimsgsession.md)函数获取的邮件会话对象的指针。</span><span class="sxs-lookup"><span data-stu-id="cb54c-114">[in] Pointer to the message session object obtained using the [OpenIMsgSession](openimsgsession.md) function at the start of the message session.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="cb54c-115">返回值</span><span class="sxs-lookup"><span data-stu-id="cb54c-115">Return value</span></span>

<span data-ttu-id="cb54c-116">无。</span><span class="sxs-lookup"><span data-stu-id="cb54c-116">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="cb54c-117">注解</span><span class="sxs-lookup"><span data-stu-id="cb54c-117">Remarks</span></span>

<span data-ttu-id="cb54c-118">客户端应用程序和服务提供程序使用消息会话, 以处理基于基础 OLE **IStorage**对象之上构建的多个相关 MAPI **IMessage**对象。</span><span class="sxs-lookup"><span data-stu-id="cb54c-118">A message session is used by client applications and service providers that want to deal with several related MAPI **IMessage** objects built on top of underlying OLE **IStorage** objects.</span></span> <span data-ttu-id="cb54c-119">客户端或提供程序使用[OpenIMsgSession](openimsgsession.md)和**CloseIMsgSession**函数来包装邮件会话中的邮件的创建。</span><span class="sxs-lookup"><span data-stu-id="cb54c-119">The client or provider uses the [OpenIMsgSession](openimsgsession.md) and **CloseIMsgSession** functions to wrap the creation of such messages inside a message session.</span></span> <span data-ttu-id="cb54c-120">一旦打开了消息会话, 客户端或提供程序就会在调用[OpenIMsgOnIStg](openimsgonistg.md)中传递指向它的指针, 以创建新的**IMessage** **IStorage**对象。</span><span class="sxs-lookup"><span data-stu-id="cb54c-120">Once the message session is opened, the client or provider passes a pointer to it in a call to [OpenIMsgOnIStg](openimsgonistg.md) to create a new **IMessage**-on- **IStorage** object.</span></span> 
  
<span data-ttu-id="cb54c-121">除了邮件的所有附件和其他属性, 消息会话仍跟踪在会话期间打开的所有**IMessage** **IStorage**对象。</span><span class="sxs-lookup"><span data-stu-id="cb54c-121">A message session keeps track of all **IMessage**-on- **IStorage** objects opened during the duration of the session, in addition to all the attachments and other properties of the messages.</span></span> <span data-ttu-id="cb54c-122">当客户端或提供程序调用**CloseIMsgSession**时, 它将关闭所有这些对象。</span><span class="sxs-lookup"><span data-stu-id="cb54c-122">When a client or provider calls **CloseIMsgSession**, it closes all these objects.</span></span> <span data-ttu-id="cb54c-123">调用**CloseIMsgSession**是关闭**IMessage**的**IStorage**对象的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="cb54c-123">Calling **CloseIMsgSession** is the only way to close **IMessage**-on- **IStorage** objects.</span></span> 
  

