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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 607105bd58a14a3510f1ae71246069440a4f05cb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326192"
---
# <a name="openimsgsession"></a><span data-ttu-id="fb8bf-103">OpenIMsgSession</span><span class="sxs-lookup"><span data-stu-id="fb8bf-103">OpenIMsgSession</span></span>

  
  
<span data-ttu-id="fb8bf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb8bf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fb8bf-105">创建并打开一个邮件会话，该会话对其中创建的邮件进行分组。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-105">Creates and opens a message session that groups the messages created within it.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fb8bf-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="fb8bf-106">Header file:</span></span>  <br/> |<span data-ttu-id="fb8bf-107">Imessage.h</span><span class="sxs-lookup"><span data-stu-id="fb8bf-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="fb8bf-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="fb8bf-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="fb8bf-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="fb8bf-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="fb8bf-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="fb8bf-110">Called by:</span></span>  <br/> |<span data-ttu-id="fb8bf-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="fb8bf-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE OpenIMsgSession(
  LPMALLOC lpMalloc,
  ULONG ulFlags,
  LPMSGSESS FAR * lppMsgSess
);
```

## <a name="parameters"></a><span data-ttu-id="fb8bf-112">参数</span><span class="sxs-lookup"><span data-stu-id="fb8bf-112">Parameters</span></span>

 <span data-ttu-id="fb8bf-113">_lpMalloc_</span><span class="sxs-lookup"><span data-stu-id="fb8bf-113">_lpMalloc_</span></span>
  
> <span data-ttu-id="fb8bf-114">[in]指向公开 OLE [IMalloc 接口的内存分配器对象的](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-imalloc) 指针。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-114">[in] Pointer to a memory allocator object exposing the OLE [IMalloc](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-imalloc) interface.</span></span> <span data-ttu-id="fb8bf-115">使用 OLE [IStorage](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istorage) 接口时，MAPI 需要使用此分配方法。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-115">MAPI needs to use this allocation method when working with the OLE [IStorage](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istorage) interface.</span></span> 
    
 <span data-ttu-id="fb8bf-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="fb8bf-116">_ulFlags_</span></span>
  
> <span data-ttu-id="fb8bf-117">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-117">[in] Reserved; must be zero.</span></span> 
    
 <span data-ttu-id="fb8bf-118">_lppMsgSess_</span><span class="sxs-lookup"><span data-stu-id="fb8bf-118">_lppMsgSess_</span></span>
  
> <span data-ttu-id="fb8bf-119">[out]指向返回的邮件会话对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-119">[out] Pointer to a pointer to the returned message session object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fb8bf-120">返回值</span><span class="sxs-lookup"><span data-stu-id="fb8bf-120">Return value</span></span>

<span data-ttu-id="fb8bf-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb8bf-121">S_OK</span></span>
  
> <span data-ttu-id="fb8bf-122">会话已打开。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-122">The session was opened.</span></span>
    
<span data-ttu-id="fb8bf-123">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="fb8bf-123">MAPI_E_INVALID_PARAMETER</span></span>
  
>  <span data-ttu-id="fb8bf-124">_lpMalloc_ 或  _lppMsgSess_ 为 NULL。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-124">_lpMalloc_ or  _lppMsgSess_ is NULL.</span></span> 
    
<span data-ttu-id="fb8bf-125">MAPI_E_INVALID_FLAGS</span><span class="sxs-lookup"><span data-stu-id="fb8bf-125">MAPI_E_INVALID_FLAGS</span></span>
  
> <span data-ttu-id="fb8bf-126">传递了无效标志。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-126">Invalid flags were passed.</span></span>
    
<span data-ttu-id="fb8bf-127">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="fb8bf-127">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="fb8bf-128">调用此函数时，客户端或服务提供商设置 MAPI_UNICODE 标志以创建 Unicode .msg 文件。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-128">When calling this function, a client or service provider sets the MAPI_UNICODE flag to create Unicode .msg files.</span></span> <span data-ttu-id="fb8bf-129">生成的 [Imessage](imessageimapiprop.md) 文件在其STORE_UNICODE_OK中显示PR_STORE_SUPPORT_MASK并支持 Unicode 属性。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-129">The resulting [Imessage](imessageimapiprop.md) file shows STORE_UNICODE_OK in its PR_STORE_SUPPORT_MASK and supports Unicode properties.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="fb8bf-130">备注</span><span class="sxs-lookup"><span data-stu-id="fb8bf-130">Remarks</span></span>

<span data-ttu-id="fb8bf-131">消息会话由需要处理多个相关 MAPI [IMessage：IMAPIProp](imessageimapiprop.md) 对象（基于基础 OLE **IStorage** 对象构建）的客户端应用程序和服务提供商使用。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-131">A message session is used by client applications and service providers that want to deal with several related MAPI [IMessage : IMAPIProp](imessageimapiprop.md) objects built on top of underlying OLE **IStorage** objects.</span></span> <span data-ttu-id="fb8bf-132">客户端或提供程序使用 **OpenIMsgSession** 和 [CloseIMsgSession](closeimsgsession.md) 函数将此类消息的创建包装在邮件会话中。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-132">The client or provider uses the **OpenIMsgSession** and [CloseIMsgSession](closeimsgsession.md) functions to wrap the creation of such messages inside a message session.</span></span> <span data-ttu-id="fb8bf-133">打开消息会话后，客户端或提供程序在 [调用 OpenIMsgOnIStg](openimsgonistg.md) 时传递指向该会话的指针，以创建新的 **IMessage**-on- **IStorage** 对象。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-133">Once the message session is opened, the client or provider passes a pointer to it in a call to [OpenIMsgOnIStg](openimsgonistg.md) to create a new **IMessage**-on- **IStorage** object.</span></span> 
  
<span data-ttu-id="fb8bf-134">邮件会话跟踪会话期间创建的所有 **IMessage**-on- **IStorage** 对象，以及邮件的所有附件和其他属性。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-134">A message session keeps track of all **IMessage**-on- **IStorage** objects created during the duration of the session, in addition to all the attachments and other properties of the messages.</span></span> <span data-ttu-id="fb8bf-135">当客户端或提供程序调用 **CloseIMsgSession** 时，它将关闭所有这些对象。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-135">When a client or provider calls **CloseIMsgSession**, it closes all these objects.</span></span> <span data-ttu-id="fb8bf-136">调用 **CloseIMsgSession** 是关闭 **IMessage**-on- **IStorage 对象的唯一** 方法。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-136">Calling **CloseIMsgSession** is the only way to close **IMessage**-on- **IStorage** objects.</span></span> 
  
 <span data-ttu-id="fb8bf-137">需要能够将多个相关消息作为 OLE **IStorage** 对象处理的客户端和提供程序使用 **OpenIMsgSession。**</span><span class="sxs-lookup"><span data-stu-id="fb8bf-137">**OpenIMsgSession** is used by clients and providers that require the ability to handle several related messages as OLE **IStorage** objects.</span></span> <span data-ttu-id="fb8bf-138">如果一次仅打开一条此类邮件，则无需跟踪多个邮件，也无需使用 **OpenIMsgSession** 创建邮件会话。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-138">If only one such message is to be open at a time, there is no need to track multiple messages and no reason to create a message session with **OpenIMsgSession**.</span></span> 
  
<span data-ttu-id="fb8bf-139">因为它处理的是基础 OLE 对象，所以 MAPI 需要使用 OLE 内存分配。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-139">Because it is dealing with an underlying OLE object, MAPI needs to use OLE memory allocation.</span></span> <span data-ttu-id="fb8bf-140">有关 OLE 结构化存储对象和 OLE 内存分配的信息，请参阅 [OLE 和数据传输](https://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fb8bf-140">For more information about OLE structured storage objects and OLE memory allocation, see [OLE and Data Transfer](https://msdn.microsoft.com/library/d4a57956-37ba-44ca-8efc-bf617ad5e77b.aspx).</span></span> 
  

