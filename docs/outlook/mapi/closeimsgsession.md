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
ms.openlocfilehash: f358467d72f2a9f395762f529244041a5d9d8d6a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575978"
---
# <a name="closeimsgsession"></a><span data-ttu-id="00bfc-103">CloseIMsgSession</span><span class="sxs-lookup"><span data-stu-id="00bfc-103">CloseIMsgSession</span></span>

  
  
<span data-ttu-id="00bfc-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="00bfc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="00bfc-105">关闭消息会话并在该会话中创建的所有消息。</span><span class="sxs-lookup"><span data-stu-id="00bfc-105">Closes a message session and all the messages created within that session.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="00bfc-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="00bfc-106">Header file:</span></span>  <br/> |<span data-ttu-id="00bfc-107">Imessage.h</span><span class="sxs-lookup"><span data-stu-id="00bfc-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="00bfc-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="00bfc-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="00bfc-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="00bfc-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="00bfc-110">调用：</span><span class="sxs-lookup"><span data-stu-id="00bfc-110">Called by:</span></span>  <br/> |<span data-ttu-id="00bfc-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="00bfc-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
VOID CloseIMsgSession(
  LPMSGSESS lpMsgSess
);
```

## <a name="parameters"></a><span data-ttu-id="00bfc-112">参数</span><span class="sxs-lookup"><span data-stu-id="00bfc-112">Parameters</span></span>

 <span data-ttu-id="00bfc-113">_lpMsgSess_</span><span class="sxs-lookup"><span data-stu-id="00bfc-113">_lpMsgSess_</span></span>
  
> <span data-ttu-id="00bfc-114">[in]对消息会话的开头使用[OpenIMsgSession](openimsgsession.md)函数获取邮件会话对象的指针。</span><span class="sxs-lookup"><span data-stu-id="00bfc-114">[in] Pointer to the message session object obtained using the [OpenIMsgSession](openimsgsession.md) function at the start of the message session.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="00bfc-115">返回值</span><span class="sxs-lookup"><span data-stu-id="00bfc-115">Return value</span></span>

<span data-ttu-id="00bfc-116">无。</span><span class="sxs-lookup"><span data-stu-id="00bfc-116">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="00bfc-117">注解</span><span class="sxs-lookup"><span data-stu-id="00bfc-117">Remarks</span></span>

<span data-ttu-id="00bfc-118">客户端应用程序和服务提供商想要处理基于基础 OLE **IStorage**对象的多个相关 MAPI **IMessage**对象使用的邮件会话。</span><span class="sxs-lookup"><span data-stu-id="00bfc-118">A message session is used by client applications and service providers that want to deal with several related MAPI **IMessage** objects built on top of underlying OLE **IStorage** objects.</span></span> <span data-ttu-id="00bfc-119">在客户端或提供程序使用的[OpenIMsgSession](openimsgsession.md)和**CloseIMsgSession**函数来包装创建的此类邮件内的邮件会话。</span><span class="sxs-lookup"><span data-stu-id="00bfc-119">The client or provider uses the [OpenIMsgSession](openimsgsession.md) and **CloseIMsgSession** functions to wrap the creation of such messages inside a message session.</span></span> <span data-ttu-id="00bfc-120">后打开消息会话时，在客户端或提供程序将指针传递给它-上- **IStorage**对象创建新**IMessage** [OpenIMsgOnIStg](openimsgonistg.md)将调用。</span><span class="sxs-lookup"><span data-stu-id="00bfc-120">Once the message session is opened, the client or provider passes a pointer to it in a call to [OpenIMsgOnIStg](openimsgonistg.md) to create a new **IMessage**-on- **IStorage** object.</span></span> 
  
<span data-ttu-id="00bfc-121">打开会话，除了的所有附件和邮件的其他属性的持续时间内的所有**IMessage**-亮- **IStorage**对象跟踪都的邮件会话。</span><span class="sxs-lookup"><span data-stu-id="00bfc-121">A message session keeps track of all **IMessage**-on- **IStorage** objects opened during the duration of the session, in addition to all the attachments and other properties of the messages.</span></span> <span data-ttu-id="00bfc-122">当客户端或提供程序调用**CloseIMsgSession**时，它将关闭所有这些对象。</span><span class="sxs-lookup"><span data-stu-id="00bfc-122">When a client or provider calls **CloseIMsgSession**, it closes all these objects.</span></span> <span data-ttu-id="00bfc-123">调用**CloseIMsgSession**是关闭**IMessage**-上- **IStorage**对象的唯一方式。</span><span class="sxs-lookup"><span data-stu-id="00bfc-123">Calling **CloseIMsgSession** is the only way to close **IMessage**-on- **IStorage** objects.</span></span> 
  

