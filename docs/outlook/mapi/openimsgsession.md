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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: e7f652e7426792d8b4c878b7f6738439aec65348
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776550"
---
# <a name="openimsgsession"></a><span data-ttu-id="08dae-103">OpenIMsgSession</span><span class="sxs-lookup"><span data-stu-id="08dae-103">OpenIMsgSession</span></span>

  
  
<span data-ttu-id="08dae-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="08dae-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="08dae-105">创建并打开在其中创建邮件分组的邮件会话。</span><span class="sxs-lookup"><span data-stu-id="08dae-105">Creates and opens a message session that groups the messages created within it.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="08dae-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="08dae-106">Header file:</span></span>  <br/> |<span data-ttu-id="08dae-107">Imessage.h</span><span class="sxs-lookup"><span data-stu-id="08dae-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="08dae-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="08dae-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="08dae-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="08dae-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="08dae-110">调用：</span><span class="sxs-lookup"><span data-stu-id="08dae-110">Called by:</span></span>  <br/> |<span data-ttu-id="08dae-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="08dae-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE OpenIMsgSession(
  LPMALLOC lpMalloc,
  ULONG ulFlags,
  LPMSGSESS FAR * lppMsgSess
);
```

## <a name="parameters"></a><span data-ttu-id="08dae-112">参数</span><span class="sxs-lookup"><span data-stu-id="08dae-112">Parameters</span></span>

 <span data-ttu-id="08dae-113">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="08dae-113">_lpMalloc_</span></span>
  
> <span data-ttu-id="08dae-114">[in]对内存分配器对象公开的 OLE [IMalloc](http://msdn.microsoft.com/library/047f281e-2665-4d6d-9a0b-918cd3339447%28Office.15%29.aspx)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="08dae-114">[in] Pointer to a memory allocator object exposing the OLE [IMalloc](http://msdn.microsoft.com/library/047f281e-2665-4d6d-9a0b-918cd3339447%28Office.15%29.aspx) interface.</span></span> <span data-ttu-id="08dae-115">MAPI 需要时使用的 OLE [IStorage](http://msdn.microsoft.com/library/stg.istorage%28Office.15%29.aspx)界面使用此分配方法。</span><span class="sxs-lookup"><span data-stu-id="08dae-115">MAPI needs to use this allocation method when working with the OLE [IStorage](http://msdn.microsoft.com/library/stg.istorage%28Office.15%29.aspx) interface.</span></span> 
    
 <span data-ttu-id="08dae-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="08dae-116">_ulFlags_</span></span>
  
> <span data-ttu-id="08dae-117">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="08dae-117">[in] Reserved; must be zero.</span></span> 
    
 <span data-ttu-id="08dae-118">_lppMsgSess_</span><span class="sxs-lookup"><span data-stu-id="08dae-118">_lppMsgSess_</span></span>
  
> <span data-ttu-id="08dae-119">[输出]指向到返回的消息的会话对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="08dae-119">[out] Pointer to a pointer to the returned message session object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="08dae-120">返回值</span><span class="sxs-lookup"><span data-stu-id="08dae-120">Return value</span></span>

<span data-ttu-id="08dae-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="08dae-121">S_OK</span></span>
  
> <span data-ttu-id="08dae-122">打开会话。</span><span class="sxs-lookup"><span data-stu-id="08dae-122">The session was opened.</span></span>
    
<span data-ttu-id="08dae-123">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="08dae-123">MAPI_E_INVALID_PARAMETER</span></span>
  
>  <span data-ttu-id="08dae-124">_lpMalloc_或_lppMsgSess_为 NULL。</span><span class="sxs-lookup"><span data-stu-id="08dae-124">_lpMalloc_ or  _lppMsgSess_ is NULL.</span></span> 
    
<span data-ttu-id="08dae-125">MAPI_E_INVALID_FLAGS</span><span class="sxs-lookup"><span data-stu-id="08dae-125">MAPI_E_INVALID_FLAGS</span></span>
  
> <span data-ttu-id="08dae-126">传递了无效的标志。</span><span class="sxs-lookup"><span data-stu-id="08dae-126">Invalid flags were passed.</span></span>
    
<span data-ttu-id="08dae-127">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="08dae-127">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="08dae-128">时调用此函数，客户端或服务提供程序设置 MAPI_UNICODE 标志创建 Unicode.msg 文件。</span><span class="sxs-lookup"><span data-stu-id="08dae-128">When calling this function, a client or service provider sets the MAPI_UNICODE flag to create Unicode .msg files.</span></span> <span data-ttu-id="08dae-129">生成的[Imessage](imessageimapiprop.md)文件显示在其 PR_STORE_SUPPORT_MASK STORE_UNICODE_OK，并支持 Unicode 属性。</span><span class="sxs-lookup"><span data-stu-id="08dae-129">The resulting [Imessage](imessageimapiprop.md) file shows STORE_UNICODE_OK in its PR_STORE_SUPPORT_MASK and supports Unicode properties.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="08dae-130">备注</span><span class="sxs-lookup"><span data-stu-id="08dae-130">Remarks</span></span>

<span data-ttu-id="08dae-131">消息会话由客户端应用程序和服务提供商想要处理多个相关 MAPI [IMessage: IMAPIProp](imessageimapiprop.md)基于基础 OLE **IStorage**对象的对象。</span><span class="sxs-lookup"><span data-stu-id="08dae-131">A message session is used by client applications and service providers that want to deal with several related MAPI [IMessage : IMAPIProp](imessageimapiprop.md) objects built on top of underlying OLE **IStorage** objects.</span></span> <span data-ttu-id="08dae-132">在客户端或提供程序使用的**OpenIMsgSession**和[CloseIMsgSession](closeimsgsession.md)函数来包装创建的此类邮件内的邮件会话。</span><span class="sxs-lookup"><span data-stu-id="08dae-132">The client or provider uses the **OpenIMsgSession** and [CloseIMsgSession](closeimsgsession.md) functions to wrap the creation of such messages inside a message session.</span></span> <span data-ttu-id="08dae-133">后打开消息会话时，在客户端或提供程序将指针传递给它-上- **IStorage**对象创建新**IMessage** [OpenIMsgOnIStg](openimsgonistg.md)将调用。</span><span class="sxs-lookup"><span data-stu-id="08dae-133">Once the message session is opened, the client or provider passes a pointer to it in a call to [OpenIMsgOnIStg](openimsgonistg.md) to create a new **IMessage**-on- **IStorage** object.</span></span> 
  
<span data-ttu-id="08dae-134">在创建会话，除了的所有附件和邮件的其他属性期间**IStorage**对象的所有**IMessage**跟踪都的邮件会话。</span><span class="sxs-lookup"><span data-stu-id="08dae-134">A message session keeps track of all **IMessage**-on- **IStorage** objects created during the duration of the session, in addition to all the attachments and other properties of the messages.</span></span> <span data-ttu-id="08dae-135">当客户端或提供程序调用**CloseIMsgSession**时，它将关闭所有这些对象。</span><span class="sxs-lookup"><span data-stu-id="08dae-135">When a client or provider calls **CloseIMsgSession**, it closes all these objects.</span></span> <span data-ttu-id="08dae-136">调用**CloseIMsgSession**是关闭**IMessage**-上- **IStorage**对象的唯一方式。</span><span class="sxs-lookup"><span data-stu-id="08dae-136">Calling **CloseIMsgSession** is the only way to close **IMessage**-on- **IStorage** objects.</span></span> 
  
 <span data-ttu-id="08dae-137">**OpenIMsgSession**使用客户端和需要能够处理多个相关的消息作为 OLE **IStorage**对象的提供程序。</span><span class="sxs-lookup"><span data-stu-id="08dae-137">**OpenIMsgSession** is used by clients and providers that require the ability to handle several related messages as OLE **IStorage** objects.</span></span> <span data-ttu-id="08dae-138">如果只有一个此类邮件是在每次打开，跟踪多个邮件和创建与**OpenIMsgSession**的邮件会话没有理由需要。</span><span class="sxs-lookup"><span data-stu-id="08dae-138">If only one such message is to be open at a time, there is no need to track multiple messages and no reason to create a message session with **OpenIMsgSession**.</span></span> 
  
<span data-ttu-id="08dae-139">因为它处理基础 OLE 对象，MAPI 需要使用 OLE 内存分配。</span><span class="sxs-lookup"><span data-stu-id="08dae-139">Because it is dealing with an underlying OLE object, MAPI needs to use OLE memory allocation.</span></span> <span data-ttu-id="08dae-140">有关存储的结构化的 OLE 对象和 OLE 内存分配的详细信息，请参阅[OLE 和数据传输](http://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="08dae-140">For more information about OLE structured storage objects and OLE memory allocation, see [OLE and Data Transfer](http://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx).</span></span> 
  

