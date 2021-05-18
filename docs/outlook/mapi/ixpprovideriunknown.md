---
title: IXPProvider IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPProvider
api_type:
- COM
ms.assetid: d5507785-c924-4981-ae80-19709ceb054d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0aa77ced9d0c242dcafb84ca1e1a60d02db9504a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404692"
---
# <a name="ixpprovider--iunknown"></a><span data-ttu-id="239e9-103">IXPProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="239e9-103">IXPProvider : IUnknown</span></span>

  
  
<span data-ttu-id="239e9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="239e9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="239e9-105">初始化传输提供程序对象，并关闭不再需要的对象。</span><span class="sxs-lookup"><span data-stu-id="239e9-105">Initializes a transport provider object and shuts down the object when it is no longer needed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="239e9-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="239e9-106">Header file:</span></span>  <br/> |<span data-ttu-id="239e9-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="239e9-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="239e9-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="239e9-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="239e9-109">传输提供程序对象</span><span class="sxs-lookup"><span data-stu-id="239e9-109">Transport provider objects</span></span>  <br/> |
|<span data-ttu-id="239e9-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="239e9-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="239e9-111">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="239e9-111">Transport providers</span></span>  <br/> |
|<span data-ttu-id="239e9-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="239e9-112">Called by:</span></span>  <br/> |<span data-ttu-id="239e9-113">MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="239e9-113">The MAPI spooler</span></span>  <br/> |
|<span data-ttu-id="239e9-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="239e9-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="239e9-115">IID_IXPProvider</span><span class="sxs-lookup"><span data-stu-id="239e9-115">IID_IXPProvider</span></span>  <br/> |
|<span data-ttu-id="239e9-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="239e9-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="239e9-117">LPXPROVIDER</span><span class="sxs-lookup"><span data-stu-id="239e9-117">LPXPROVIDER</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="239e9-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="239e9-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="239e9-119">关闭</span><span class="sxs-lookup"><span data-stu-id="239e9-119">Shutdown</span></span>](ixpprovider-shutdown.md) <br/> |<span data-ttu-id="239e9-120">以有序方式关闭传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="239e9-120">Closes down a transport provider in an orderly fashion.</span></span>  <br/> |
|[<span data-ttu-id="239e9-121">TransportLogon</span><span class="sxs-lookup"><span data-stu-id="239e9-121">TransportLogon</span></span>](ixpprovider-transportlogon.md) <br/> |<span data-ttu-id="239e9-122">建立客户端应用程序登录到传输提供程序的会话。</span><span class="sxs-lookup"><span data-stu-id="239e9-122">Establishes a session in which a client application logs on to a transport provider.</span></span>  <br/> |
   

