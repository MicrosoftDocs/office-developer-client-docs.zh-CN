---
title: 链接到 MAPI DLL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 19fd4678-21d3-47a6-a439-1d4959cac407
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0bce1d682057b81135d1684c40bc79e6710d4e2a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776134"
---
# <a name="linking-to-the-mapi-dlls"></a><span data-ttu-id="23c78-103">链接到 MAPI DLL</span><span class="sxs-lookup"><span data-stu-id="23c78-103">Linking to the MAPI DLLs</span></span>

  
  
<span data-ttu-id="23c78-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="23c78-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="23c78-105">MAPI 客户端可以链接到 MAPI Dll 隐式或显式使用**LoadLibrary**和**GetProcAddress**的 Windows 功能。</span><span class="sxs-lookup"><span data-stu-id="23c78-105">MAPI clients can link to the MAPI DLLs implicitly, or explicitly by using the Windows functions **LoadLibrary** and **GetProcAddress**.</span></span> <span data-ttu-id="23c78-106">显式链接 MAPI Dll 的信息，请参阅[MAPI 函数的链接](how-to-link-to-mapi-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="23c78-106">For information on explicitly linking MAPI DLLs, see [Link to MAPI Functions](how-to-link-to-mapi-functions.md).</span></span>
  
<span data-ttu-id="23c78-107">MAPI 提供了在 MAPIX 类型定义语句。H 头文件中的每个以下功能：</span><span class="sxs-lookup"><span data-stu-id="23c78-107">MAPI provides type definition statements in the MAPIX.H header file for each of the following functions:</span></span>
  
[<span data-ttu-id="23c78-108">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="23c78-108">MAPILogonEx</span></span>](mapilogonex.md)
  
[<span data-ttu-id="23c78-109">MAPIUninitialize</span><span class="sxs-lookup"><span data-stu-id="23c78-109">MAPIUninitialize</span></span>](mapiuninitialize.md)
  
[<span data-ttu-id="23c78-110">MAPIInitialize</span><span class="sxs-lookup"><span data-stu-id="23c78-110">MAPIInitialize</span></span>](mapiinitialize.md)
  
[<span data-ttu-id="23c78-111">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="23c78-111">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="23c78-112">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="23c78-112">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="23c78-113">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="23c78-113">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="23c78-114">MAPIAdminProfiles</span><span class="sxs-lookup"><span data-stu-id="23c78-114">MAPIAdminProfiles</span></span>](mapiadminprofiles.md)
  
<span data-ttu-id="23c78-115">使用这些类型定义正确如果显式链接到 MAPI Dll 调用相应的入口点。</span><span class="sxs-lookup"><span data-stu-id="23c78-115">Use these type definitions to correctly call the corresponding entry points if you link explicitly to the MAPI DLLs.</span></span>
  
<span data-ttu-id="23c78-116">服务提供商可以包含非 MAPI 功能 — 与 MAPI 完全无关的功能 — 在其 DLL 中。</span><span class="sxs-lookup"><span data-stu-id="23c78-116">Service providers can contain non-MAPI functionality — features that are completely unrelated to MAPI — in their DLL.</span></span> <span data-ttu-id="23c78-117">如果您需要使用这些功能，请使用的 DLL 和**句**后其使用从内存中删除 DLL 之前调用**LoadLibrary** 。</span><span class="sxs-lookup"><span data-stu-id="23c78-117">If you need to use these features, call **LoadLibrary** before using the DLL and **FreeLibrary** to remove the DLL from memory after its use.</span></span> <span data-ttu-id="23c78-118">因为 MAPI 不知道服务提供商 DLL 的非 MAPI 使用，则将需要时可用 DLL 无法保证。</span><span class="sxs-lookup"><span data-stu-id="23c78-118">Because MAPI is unaware of non-MAPI uses of a service provider DLL, there is no guarantee that the DLL will be available when needed.</span></span> <span data-ttu-id="23c78-119">当不再需要其服务的活动会话任何客户端，MAPI 释放服务提供商 DLL。</span><span class="sxs-lookup"><span data-stu-id="23c78-119">MAPI releases a service provider DLL when there are no longer any clients with active sessions that require its services.</span></span> 
  

