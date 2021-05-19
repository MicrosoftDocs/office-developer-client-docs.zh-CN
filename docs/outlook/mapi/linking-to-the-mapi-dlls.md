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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419301"
---
# <a name="linking-to-the-mapi-dlls"></a><span data-ttu-id="27a5b-103">链接到 MAPI DLL</span><span class="sxs-lookup"><span data-stu-id="27a5b-103">Linking to the MAPI DLLs</span></span>

  
  
<span data-ttu-id="27a5b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="27a5b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="27a5b-105">MAPI 客户端可以隐式或显式链接到 MAPI DLL，或者使用 Windows 函数 **LoadLibrary** 和 **GetProcAddress** 显式链接。</span><span class="sxs-lookup"><span data-stu-id="27a5b-105">MAPI clients can link to the MAPI DLLs implicitly, or explicitly by using the Windows functions **LoadLibrary** and **GetProcAddress**.</span></span> <span data-ttu-id="27a5b-106">有关显式链接 MAPI DLL 的信息，请参阅 [链接到 MAPI 函数](how-to-link-to-mapi-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="27a5b-106">For information on explicitly linking MAPI DLLs, see [Link to MAPI Functions](how-to-link-to-mapi-functions.md).</span></span>
  
<span data-ttu-id="27a5b-107">MAPI 在 MAPIX 中提供类型定义语句。以下每个函数的 H 头文件：</span><span class="sxs-lookup"><span data-stu-id="27a5b-107">MAPI provides type definition statements in the MAPIX.H header file for each of the following functions:</span></span>
  
[<span data-ttu-id="27a5b-108">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="27a5b-108">MAPILogonEx</span></span>](mapilogonex.md)
  
[<span data-ttu-id="27a5b-109">MAPIUninitialize</span><span class="sxs-lookup"><span data-stu-id="27a5b-109">MAPIUninitialize</span></span>](mapiuninitialize.md)
  
[<span data-ttu-id="27a5b-110">MAPIInitialize</span><span class="sxs-lookup"><span data-stu-id="27a5b-110">MAPIInitialize</span></span>](mapiinitialize.md)
  
[<span data-ttu-id="27a5b-111">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="27a5b-111">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="27a5b-112">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="27a5b-112">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="27a5b-113">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="27a5b-113">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="27a5b-114">MAPIAdminProfiles</span><span class="sxs-lookup"><span data-stu-id="27a5b-114">MAPIAdminProfiles</span></span>](mapiadminprofiles.md)
  
<span data-ttu-id="27a5b-115">如果显式链接到 MAPI DLL，请使用这些类型定义正确调用相应的入口点。</span><span class="sxs-lookup"><span data-stu-id="27a5b-115">Use these type definitions to correctly call the corresponding entry points if you link explicitly to the MAPI DLLs.</span></span>
  
<span data-ttu-id="27a5b-116">服务提供程序可以在其 DLL 中包含非 MAPI 功能（与 MAPI 完全无关的功能）。</span><span class="sxs-lookup"><span data-stu-id="27a5b-116">Service providers can contain non-MAPI functionality — features that are completely unrelated to MAPI — in their DLL.</span></span> <span data-ttu-id="27a5b-117">如果你需要使用这些功能，在使用 DLL 和 FreeLibrary 之前调用 **LoadLibrary，** 以在使用 DLL 后从内存中删除该 DLL。 </span><span class="sxs-lookup"><span data-stu-id="27a5b-117">If you need to use these features, call **LoadLibrary** before using the DLL and **FreeLibrary** to remove the DLL from memory after its use.</span></span> <span data-ttu-id="27a5b-118">由于 MAPI 不知道服务提供程序 DLL 的非 MAPI 用法，因此无法保证 DLL 将根据需要可用。</span><span class="sxs-lookup"><span data-stu-id="27a5b-118">Because MAPI is unaware of non-MAPI uses of a service provider DLL, there is no guarantee that the DLL will be available when needed.</span></span> <span data-ttu-id="27a5b-119">当不再有任何具有活动会话的客户端需要其服务时，MAPI 将释放服务提供程序 DLL。</span><span class="sxs-lookup"><span data-stu-id="27a5b-119">MAPI releases a service provider DLL when there are no longer any clients with active sessions that require its services.</span></span> 
  

