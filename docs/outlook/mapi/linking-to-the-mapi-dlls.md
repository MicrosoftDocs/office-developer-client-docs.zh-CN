---
title: 链接到 MAPI DLL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 19fd4678-21d3-47a6-a439-1d4959cac407
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 394537a60f4cb9603024115ccea67570291d8ac6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270040"
---
# <a name="linking-to-the-mapi-dlls"></a><span data-ttu-id="23fa2-103">链接到 MAPI DLL</span><span class="sxs-lookup"><span data-stu-id="23fa2-103">Linking to the MAPI DLLs</span></span>

  
  
<span data-ttu-id="23fa2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="23fa2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="23fa2-105">mapi 客户端可以隐式链接到 mapi dll, 也可以通过使用 Windows 函数**LoadLibrary**和**GetProcAddress**进行显式链接。</span><span class="sxs-lookup"><span data-stu-id="23fa2-105">MAPI clients can link to the MAPI DLLs implicitly, or explicitly by using the Windows functions **LoadLibrary** and **GetProcAddress**.</span></span> <span data-ttu-id="23fa2-106">有关显式链接 MAPI dll 的信息, 请参阅[链接到 mapi 函数](how-to-link-to-mapi-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="23fa2-106">For information on explicitly linking MAPI DLLs, see [Link to MAPI Functions](how-to-link-to-mapi-functions.md).</span></span>
  
<span data-ttu-id="23fa2-107">MAPI 在 MAPIX 中提供类型定义语句。以下每个函数的 H 头文件:</span><span class="sxs-lookup"><span data-stu-id="23fa2-107">MAPI provides type definition statements in the MAPIX.H header file for each of the following functions:</span></span>
  
[<span data-ttu-id="23fa2-108">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="23fa2-108">MAPILogonEx</span></span>](mapilogonex.md)
  
[<span data-ttu-id="23fa2-109">MAPIUninitialize</span><span class="sxs-lookup"><span data-stu-id="23fa2-109">MAPIUninitialize</span></span>](mapiuninitialize.md)
  
[<span data-ttu-id="23fa2-110">MAPIInitialize</span><span class="sxs-lookup"><span data-stu-id="23fa2-110">MAPIInitialize</span></span>](mapiinitialize.md)
  
[<span data-ttu-id="23fa2-111">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="23fa2-111">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="23fa2-112">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="23fa2-112">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="23fa2-113">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="23fa2-113">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="23fa2-114">MAPIAdminProfiles</span><span class="sxs-lookup"><span data-stu-id="23fa2-114">MAPIAdminProfiles</span></span>](mapiadminprofiles.md)
  
<span data-ttu-id="23fa2-115">如果显式链接到 MAPI dll, 请使用这些类型定义来正确地调用相应的入口点。</span><span class="sxs-lookup"><span data-stu-id="23fa2-115">Use these type definitions to correctly call the corresponding entry points if you link explicitly to the MAPI DLLs.</span></span>
  
<span data-ttu-id="23fa2-116">服务提供程序可以在其 DLL 中包含非 mapi 功能 (与 MAPI 完全无关的功能)。</span><span class="sxs-lookup"><span data-stu-id="23fa2-116">Service providers can contain non-MAPI functionality — features that are completely unrelated to MAPI — in their DLL.</span></span> <span data-ttu-id="23fa2-117">如果需要使用这些功能, 请在使用 dll 和**FreeLibrary**之前调用**LoadLibrary** , 以在使用 dll 后将其从内存中删除。</span><span class="sxs-lookup"><span data-stu-id="23fa2-117">If you need to use these features, call **LoadLibrary** before using the DLL and **FreeLibrary** to remove the DLL from memory after its use.</span></span> <span data-ttu-id="23fa2-118">由于 MAPI 不知道服务提供程序 DLL 的非 MAPI 使用, 因此不能保证 DLL 在需要时可用。</span><span class="sxs-lookup"><span data-stu-id="23fa2-118">Because MAPI is unaware of non-MAPI uses of a service provider DLL, there is no guarantee that the DLL will be available when needed.</span></span> <span data-ttu-id="23fa2-119">当不再有任何具有需要服务的活动会话的客户端时, MAPI 将释放服务提供程序 DLL。</span><span class="sxs-lookup"><span data-stu-id="23fa2-119">MAPI releases a service provider DLL when there are no longer any clients with active sessions that require its services.</span></span> 
  

