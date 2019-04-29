---
title: MAPI 中的客户端关闭
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 04ec21b8-8cd8-4d2d-92e7-aa73f4315e1e
description: 上次修改时间：2012 年 6 月 26 日
ms.openlocfilehash: f2d41ad36472f39e434e3f17757559ada5e08fbd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405133"
---
# <a name="client-shutdown-in-mapi"></a><span data-ttu-id="07d45-103">MAPI 中的客户端关闭</span><span class="sxs-lookup"><span data-stu-id="07d45-103">Client Shutdown in MAPI</span></span> 
  
<span data-ttu-id="07d45-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="07d45-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="07d45-105">从 microsoft outlook 2010 开始, 现在包括 microsoft outlook 2013, MAPI 客户端可以像以前那样关闭, 也可以使用 fast shutdown。</span><span class="sxs-lookup"><span data-stu-id="07d45-105">Beginning in Microsoft Outlook 2010 and now including Microsoft Outlook 2013, MAPI clients can shut down the same way as before, or they can use fast shutdown.</span></span> <span data-ttu-id="07d45-106">若要快速关闭以成功进行, 客户端计算机的 mapi 客户端、mapi 提供程序和管理员必须支持快速关闭。</span><span class="sxs-lookup"><span data-stu-id="07d45-106">For fast shutdown to occur successfully, the MAPI client, MAPI provider, and administrator of the client computer have to support fast shutdown.</span></span> 
  
<span data-ttu-id="07d45-107">本节中的主题介绍了对客户端执行快速关机的 MAPI 支持。</span><span class="sxs-lookup"><span data-stu-id="07d45-107">The topics in this section describe MAPI support for a client to perform fast shutdown.</span></span>
  
[<span data-ttu-id="07d45-108">快速关闭概述</span><span class="sxs-lookup"><span data-stu-id="07d45-108">Fast Shutdown Overview</span></span>](fast-shutdown-overview.md)
  
> <span data-ttu-id="07d45-109">本主题介绍快速关闭的基本机制。</span><span class="sxs-lookup"><span data-stu-id="07d45-109">This topic introduces the basic mechanism of fast shutdown.</span></span>
    
[<span data-ttu-id="07d45-110">快速关闭用户选项</span><span class="sxs-lookup"><span data-stu-id="07d45-110">Fast Shutdown User Options</span></span>](fast-shutdown-user-options.md)
  
> <span data-ttu-id="07d45-111">本主题介绍可供管理员在用户级别为用户的 MAPI 客户端采用快速关闭的选项。</span><span class="sxs-lookup"><span data-stu-id="07d45-111">This topic describes the choices available for administrators to adopt fast shutdown at the user level for the user's MAPI clients.</span></span>
    
[<span data-ttu-id="07d45-112">快速关闭最佳做法</span><span class="sxs-lookup"><span data-stu-id="07d45-112">Best Practices for Fast Shutdown</span></span>](best-practices-for-fast-shutdown.md)
  
> <span data-ttu-id="07d45-113">本主题建议使用 fast shutdown 接口以帮助防止在 MAPI 客户端关闭期间丢失数据的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="07d45-113">This topic recommends best practices to use the fast shutdown interfaces to help prevent data loss during a MAPI client shutdown.</span></span>
    

