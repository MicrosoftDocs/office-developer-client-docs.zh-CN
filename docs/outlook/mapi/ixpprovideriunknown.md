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
ms.openlocfilehash: e12f69e3486e5eeb9087b30753735f7f910dc6f4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776149"
---
# <a name="ixpprovider--iunknown"></a><span data-ttu-id="78272-103">IXPProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="78272-103">IXPProvider : IUnknown</span></span>

  
  
<span data-ttu-id="78272-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="78272-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="78272-105">初始化传输提供程序对象，并关闭该对象，当不再需要时。</span><span class="sxs-lookup"><span data-stu-id="78272-105">Initializes a transport provider object and shuts down the object when it is no longer needed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="78272-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="78272-106">Header file:</span></span>  <br/> |<span data-ttu-id="78272-107">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="78272-107">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="78272-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="78272-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="78272-109">传输提供程序对象</span><span class="sxs-lookup"><span data-stu-id="78272-109">Transport provider objects</span></span>  <br/> |
|<span data-ttu-id="78272-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="78272-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="78272-111">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="78272-111">Transport providers</span></span>  <br/> |
|<span data-ttu-id="78272-112">调用：</span><span class="sxs-lookup"><span data-stu-id="78272-112">Called by:</span></span>  <br/> |<span data-ttu-id="78272-113">MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="78272-113">The MAPI spooler</span></span>  <br/> |
|<span data-ttu-id="78272-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="78272-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="78272-115">IID_IXPProvider</span><span class="sxs-lookup"><span data-stu-id="78272-115">IID_IXPProvider</span></span>  <br/> |
|<span data-ttu-id="78272-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="78272-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="78272-117">LPXPROVIDER</span><span class="sxs-lookup"><span data-stu-id="78272-117">LPXPROVIDER</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="78272-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="78272-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="78272-119">关闭</span><span class="sxs-lookup"><span data-stu-id="78272-119">Shutdown</span></span>](ixpprovider-shutdown.md) <br/> |<span data-ttu-id="78272-120">传输提供程序中有序的方式将关闭。</span><span class="sxs-lookup"><span data-stu-id="78272-120">Closes down a transport provider in an orderly fashion.</span></span>  <br/> |
|[<span data-ttu-id="78272-121">TransportLogon</span><span class="sxs-lookup"><span data-stu-id="78272-121">TransportLogon</span></span>](ixpprovider-transportlogon.md) <br/> |<span data-ttu-id="78272-122">建立一个会话中的客户端应用程序登录到传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="78272-122">Establishes a session in which a client application logs on to a transport provider.</span></span>  <br/> |
   

