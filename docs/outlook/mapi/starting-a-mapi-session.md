---
title: 启动 MAPI 会话
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7935ebed-f252-482c-ad8c-757aa2d8501d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d88ce382b6a6b5f98ec5f88c4deb1565d3b60151
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336342"
---
# <a name="starting-a-mapi-session"></a><span data-ttu-id="cb658-103">启动 MAPI 会话</span><span class="sxs-lookup"><span data-stu-id="cb658-103">Starting a MAPI Session</span></span>

  
  
<span data-ttu-id="cb658-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cb658-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cb658-105">尽管会话启动期间执行大量工作，但所需任务最少。</span><span class="sxs-lookup"><span data-stu-id="cb658-105">Although there is a significant amount of work performed during session start up, the required tasks are minimal.</span></span> <span data-ttu-id="cb658-106">大部分工作是在 [MAPIInitialize](mapiinitialize.md) 和 [MAPILogonEx 调用的 MAPI](mapilogonex.md) 处理中完成。</span><span class="sxs-lookup"><span data-stu-id="cb658-106">Much of this work is done in the MAPI processing of the [MAPIInitialize](mapiinitialize.md) and [MAPILogonEx](mapilogonex.md) calls.</span></span> <span data-ttu-id="cb658-107">这两个函数均接受标志作为输入参数，用于控制会话的各个方面，如通知处理和用户界面。</span><span class="sxs-lookup"><span data-stu-id="cb658-107">Both of these functions accept flags as input parameters for controlling aspects of the session such as notification handling and the user interface.</span></span> <span data-ttu-id="cb658-108">在调用 **MAPIInitialize** 以初始化 MAPI 库和 **MAPILogonEx** 以登录到 MAPI 子系统时，了解设置每个标志的后果非常重要。</span><span class="sxs-lookup"><span data-stu-id="cb658-108">It is important to understand the consequences of setting each of these flags when calling **MAPIInitialize** to initialize the MAPI libraries and **MAPILogonEx** to log on to the MAPI subsystem.</span></span> 
  
 <span data-ttu-id="cb658-109">**启动 MAPI 会话**</span><span class="sxs-lookup"><span data-stu-id="cb658-109">**To start a MAPI session**</span></span>
  
1. <span data-ttu-id="cb658-110">调用 **MAPIInitialize** 以初始化标准 MAPI 库集。</span><span class="sxs-lookup"><span data-stu-id="cb658-110">Call **MAPIInitialize** to initialize the standard set of MAPI libraries.</span></span> 
    
2. <span data-ttu-id="cb658-111">如果需要使用 OLE 库，请调用 OLE 函数 [OleInitialize](https://msdn.microsoft.com/library/9a13e7a0-f2e2-466b-98f5-38d5972fa391%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cb658-111">If you need to use the OLE libraries, call the OLE function [OleInitialize](https://msdn.microsoft.com/library/9a13e7a0-f2e2-466b-98f5-38d5972fa391%28Office.15%29.aspx).</span></span>
    
3. <span data-ttu-id="cb658-112">如果需要使用 MAPI 实用工具库，请调用 [ScInitMapiUtil](scinitmapiutil.md)。</span><span class="sxs-lookup"><span data-stu-id="cb658-112">If you need to use the MAPI utility library, call [ScInitMapiUtil](scinitmapiutil.md).</span></span>
    
4. <span data-ttu-id="cb658-113">使用有效的配置文件调用 **MAPILogonEx** 以登录到 MAPI 子系统。</span><span class="sxs-lookup"><span data-stu-id="cb658-113">Call **MAPILogonEx** with a valid profile to log on to the MAPI subsystem.</span></span> <span data-ttu-id="cb658-114">**MAPILogonEx** 验证配置文件中包含的邮件服务中每个服务提供程序的配置，并在必要时并可能提示用户输入其他信息。</span><span class="sxs-lookup"><span data-stu-id="cb658-114">**MAPILogonEx** verifies the configuration of each of the service providers in the message services included in the profile, prompting the user for additional information if necessary and possible.</span></span> <span data-ttu-id="cb658-115">**MAPILogonEx** 完成后，配置的服务提供程序即可供服务使用。</span><span class="sxs-lookup"><span data-stu-id="cb658-115">When **MAPILogonEx** completes, the configured service providers are ready for service.</span></span> 
    
## <a name="in-this-section"></a><span data-ttu-id="cb658-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="cb658-116">In this section</span></span>

[<span data-ttu-id="cb658-117">初始化 MAPI</span><span class="sxs-lookup"><span data-stu-id="cb658-117">Initializing MAPI</span></span>](initializing-mapi.md)
  
> <span data-ttu-id="cb658-118">介绍如何初始化会话的 MAPI。</span><span class="sxs-lookup"><span data-stu-id="cb658-118">Describes how to initialize MAPI for a session.</span></span>
    
[<span data-ttu-id="cb658-119">为 MAPI 初始化 OLE</span><span class="sxs-lookup"><span data-stu-id="cb658-119">Initializing OLE for MAPI</span></span>](initializing-ole-for-mapi.md)
  
> <span data-ttu-id="cb658-120">描述初始化 OLE 以与 MAPI 一同使用的调用。</span><span class="sxs-lookup"><span data-stu-id="cb658-120">Describes the calls to make to initialize OLE for use with MAPI.</span></span>
    
[<span data-ttu-id="cb658-121">初始化 MAPI 实用工具</span><span class="sxs-lookup"><span data-stu-id="cb658-121">Initializing the MAPI Utilities</span></span>](initializing-the-mapi-utilities.md)
  
> <span data-ttu-id="cb658-122">介绍如何初始化 MAPI 实用工具。</span><span class="sxs-lookup"><span data-stu-id="cb658-122">Describes how to initialize MAPI utilities.</span></span>
    
[<span data-ttu-id="cb658-123">登录 MAPI</span><span class="sxs-lookup"><span data-stu-id="cb658-123">Logging on to MAPI</span></span>](logging-on-to-mapi.md)
  
> <span data-ttu-id="cb658-124">描述客户端应用程序如何登录到 MAPI 子系统。</span><span class="sxs-lookup"><span data-stu-id="cb658-124">Describes how client applications log on to the MAPI sub system.</span></span>
    

