---
title: 启动 MAPI 会话
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7935ebed-f252-482c-ad8c-757aa2d8501d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d683d5fc959b219569417c74494cb47d7c2c059e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778869"
---
# <a name="starting-a-mapi-session"></a><span data-ttu-id="a97c7-103">启动 MAPI 会话</span><span class="sxs-lookup"><span data-stu-id="a97c7-103">Starting a MAPI Session</span></span>

  
  
<span data-ttu-id="a97c7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a97c7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a97c7-105">虽然大量会话开始备份过程中执行，但需要执行的任务是操作的最少。</span><span class="sxs-lookup"><span data-stu-id="a97c7-105">Although there is a significant amount of work performed during session start up, the required tasks are minimal.</span></span> <span data-ttu-id="a97c7-106">MAPI 中完成的此工作的大部分[MAPIInitialize](mapiinitialize.md)和[MAPILogonEx](mapilogonex.md)呼叫处理。</span><span class="sxs-lookup"><span data-stu-id="a97c7-106">Much of this work is done in the MAPI processing of the [MAPIInitialize](mapiinitialize.md) and [MAPILogonEx](mapilogonex.md) calls.</span></span> <span data-ttu-id="a97c7-107">这两个这些函数接受作为输入参数的控制的会话的用户界面通知处理等方面的标志。</span><span class="sxs-lookup"><span data-stu-id="a97c7-107">Both of these functions accept flags as input parameters for controlling aspects of the session such as notification handling and the user interface.</span></span> <span data-ttu-id="a97c7-108">若要了解调用**MAPIInitialize**初始化 MAPI 库和**MAPILogonEx**用于登录到 MAPI 子系统时设置每个这些标志的后果至关重要。</span><span class="sxs-lookup"><span data-stu-id="a97c7-108">It is important to understand the consequences of setting each of these flags when calling **MAPIInitialize** to initialize the MAPI libraries and **MAPILogonEx** to log on to the MAPI subsystem.</span></span> 
  
 <span data-ttu-id="a97c7-109">**若要启动的 MAPI 会话**</span><span class="sxs-lookup"><span data-stu-id="a97c7-109">**To start a MAPI session**</span></span>
  
1. <span data-ttu-id="a97c7-110">调用**MAPIInitialize**初始化一组标准的 MAPI 库。</span><span class="sxs-lookup"><span data-stu-id="a97c7-110">Call **MAPIInitialize** to initialize the standard set of MAPI libraries.</span></span> 
    
2. <span data-ttu-id="a97c7-111">如果您需要使用 OLE 库，请调用 OLE 函数[OleInitialize](http://msdn.microsoft.com/library/9a13e7a0-f2e2-466b-98f5-38d5972fa391%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a97c7-111">If you need to use the OLE libraries, call the OLE function [OleInitialize](http://msdn.microsoft.com/library/9a13e7a0-f2e2-466b-98f5-38d5972fa391%28Office.15%29.aspx).</span></span>
    
3. <span data-ttu-id="a97c7-112">如果您需要使用 MAPI 实用程序库，请调用[ScInitMapiUtil](scinitmapiutil.md)。</span><span class="sxs-lookup"><span data-stu-id="a97c7-112">If you need to use the MAPI utility library, call [ScInitMapiUtil](scinitmapiutil.md).</span></span>
    
4. <span data-ttu-id="a97c7-113">一个有效的配置文件，用于登录到 MAPI 子系统调用**MAPILogonEx** 。</span><span class="sxs-lookup"><span data-stu-id="a97c7-113">Call **MAPILogonEx** with a valid profile to log on to the MAPI subsystem.</span></span> <span data-ttu-id="a97c7-114">**MAPILogonEx**验证每个提示用户提供其他信息，如果必要，并且可能在配置文件中包含的邮件服务中的服务提供程序的配置。</span><span class="sxs-lookup"><span data-stu-id="a97c7-114">**MAPILogonEx** verifies the configuration of each of the service providers in the message services included in the profile, prompting the user for additional information if necessary and possible.</span></span> <span data-ttu-id="a97c7-115">**MAPILogonEx**完成后，配置的服务提供商可供服务。</span><span class="sxs-lookup"><span data-stu-id="a97c7-115">When **MAPILogonEx** completes, the configured service providers are ready for service.</span></span> 
    
## <a name="in-this-section"></a><span data-ttu-id="a97c7-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="a97c7-116">In this section</span></span>

[<span data-ttu-id="a97c7-117">初始化 MAPI</span><span class="sxs-lookup"><span data-stu-id="a97c7-117">Initializing MAPI</span></span>](initializing-mapi.md)
  
> <span data-ttu-id="a97c7-118">介绍如何为会话初始化 MAPI。</span><span class="sxs-lookup"><span data-stu-id="a97c7-118">Describes how to initialize MAPI for a session.</span></span>
    
[<span data-ttu-id="a97c7-119">初始化 MAPI 的 OLE</span><span class="sxs-lookup"><span data-stu-id="a97c7-119">Initializing OLE for MAPI</span></span>](initializing-ole-for-mapi.md)
  
> <span data-ttu-id="a97c7-120">介绍呼叫发出 MAPI 用于初始化 OLE。</span><span class="sxs-lookup"><span data-stu-id="a97c7-120">Describes the calls to make to initialize OLE for use with MAPI.</span></span>
    
[<span data-ttu-id="a97c7-121">初始化 MAPI 实用工具</span><span class="sxs-lookup"><span data-stu-id="a97c7-121">Initializing the MAPI Utilities</span></span>](initializing-the-mapi-utilities.md)
  
> <span data-ttu-id="a97c7-122">介绍如何初始化 MAPI 实用程序。</span><span class="sxs-lookup"><span data-stu-id="a97c7-122">Describes how to initialize MAPI utilities.</span></span>
    
[<span data-ttu-id="a97c7-123">登录到 MAPI</span><span class="sxs-lookup"><span data-stu-id="a97c7-123">Logging on to MAPI</span></span>](logging-on-to-mapi.md)
  
> <span data-ttu-id="a97c7-124">介绍如何客户端应用程序登录到 MAPI sub 系统。</span><span class="sxs-lookup"><span data-stu-id="a97c7-124">Describes how client applications log on to the MAPI sub system.</span></span>
    

