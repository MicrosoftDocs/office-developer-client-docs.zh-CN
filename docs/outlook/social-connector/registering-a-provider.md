---
title: 注册提供程序
manager: soliver
ms.date: 03/05/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: b60b3634-4c8b-4273-97a0-0a8a5a8a5342
description: 本主题介绍Windows OSC) 提供程序安装 Outlook Social Connector 时所使用的 (位置。
ms.openlocfilehash: a5f76850f9bebcba3c2bff31e799a3b012d6b91a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421758"
---
# <a name="registering-a-provider"></a><span data-ttu-id="2832a-103">注册提供程序</span><span class="sxs-lookup"><span data-stu-id="2832a-103">Registering a provider</span></span>

<span data-ttu-id="2832a-104">本主题介绍Windows OSC) 提供程序安装 Outlook Social Connector 时所使用的 (位置。</span><span class="sxs-lookup"><span data-stu-id="2832a-104">This topic describes the Windows registry locations that are used when you install an Outlook Social Connector (OSC) provider.</span></span>
  
## <a name="com-registration"></a><span data-ttu-id="2832a-105">COM 注册</span><span class="sxs-lookup"><span data-stu-id="2832a-105">COM registration</span></span>

<span data-ttu-id="2832a-106">您必须配置 OSC 提供程序 DLL 以在安装过程中使用 COM 自注册或 regsvr32 进行注册。</span><span class="sxs-lookup"><span data-stu-id="2832a-106">You must configure the OSC provider DLL to register using COM self-registration or regsvr32 during installation.</span></span> <span data-ttu-id="2832a-107">提供程序 DLL 的 COM 注册将 OSC 提供程序注册到 `HKEY_CLASSES_ROOT` 注册表配置单元下。</span><span class="sxs-lookup"><span data-stu-id="2832a-107">COM registration of the provider DLL registers the OSC provider under the `HKEY_CLASSES_ROOT` registry hive.</span></span> 
  
<span data-ttu-id="2832a-108">在托管代码中开发的 OSC 提供程序具有 COM 可见的提供程序程序集。</span><span class="sxs-lookup"><span data-stu-id="2832a-108">An OSC provider developed in managed code has a COM-visible provider assembly.</span></span> <span data-ttu-id="2832a-109">您应该对提供程序组件使用单独的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="2832a-109">You should use a separate application domain for the provider component.</span></span> <span data-ttu-id="2832a-110">否则，OSC 提供程序将使用其他组件使用的默认共享应用程序域，并且该提供程序可能无法按预期运行。</span><span class="sxs-lookup"><span data-stu-id="2832a-110">Otherwise, the OSC provider uses the default shared application domain that is used by other components, and the provider may not operate as expected.</span></span>
  
## <a name="registering-provider-progid"></a><span data-ttu-id="2832a-111">注册提供程序 ProgID</span><span class="sxs-lookup"><span data-stu-id="2832a-111">Registering provider ProgID</span></span>

<span data-ttu-id="2832a-112">每个 OSC 提供程序必须注册一个编程标识符 `ProgID` () 。</span><span class="sxs-lookup"><span data-stu-id="2832a-112">Each OSC provider must register a programmatic identifier (`ProgID`).</span></span> <span data-ttu-id="2832a-113">提供程序安装程序可以选择以下位置之一来添加或删除 `ProgID` ：</span><span class="sxs-lookup"><span data-stu-id="2832a-113">The provider installer can choose one of the following locations to add or remove the `ProgID`:</span></span>
  
- <span data-ttu-id="2832a-114">`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`&ndash;如果仅为当前登录的用户安装了提供程序，则提供程序安装程序应使用此位置。</span><span class="sxs-lookup"><span data-stu-id="2832a-114">`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders` &ndash; Your provider installer should use this location if the provider is installed for only the currently logged-on user.</span></span>
    
- <span data-ttu-id="2832a-115">`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`&ndash;如果为计算机上所有用户安装提供程序，则提供程序安装程序应使用此位置。</span><span class="sxs-lookup"><span data-stu-id="2832a-115">`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders` &ndash; Your provider installer should use this location if the provider is installed for all users on the computer.</span></span>
    
<span data-ttu-id="2832a-116">除非客户端计算机在 64 位操作系统上运行 32 位 Outlook，否则 OSC 将查找Windows `ProgID` 提供程序。</span><span class="sxs-lookup"><span data-stu-id="2832a-116">The OSC looks for the provider  `ProgID` in the above locations, unless the client computer has 32-bit Outlook running on a 64-bit Windows operating system.</span></span> <span data-ttu-id="2832a-117">在这种情况下，提供程序安装程序应在 或 配置单元中选择以下位置  `HKEY_CURRENT_USER` 之  `HKEY_LOCAL_MACHINE` 一：</span><span class="sxs-lookup"><span data-stu-id="2832a-117">In such a case, your provider installer should choose one of the following locations in the  `HKEY_CURRENT_USER` or  `HKEY_LOCAL_MACHINE` hive:</span></span> 
  
- `HKEY_CURRENT_USER\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
- `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
<span data-ttu-id="2832a-118">对于该版本的 Office，提供程序安装程序应在 HKEY_CURRENT_USER 或 HKEY_LOCAL_MACHINE 配置单元中选择以下位置之一：</span><span class="sxs-lookup"><span data-stu-id="2832a-118">For a Click-to-Run version of Office, your provider installer should choose one of the following locations in the HKEY_CURRENT_USER or HKEY_LOCAL_MACHINE hive:</span></span>
  
- `HKEY_CURRENT_USER\Software\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
- `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Microsoft\Outlook\SocialConnector\SocialProviders`
    
## <a name="see-also"></a><span data-ttu-id="2832a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2832a-119">See also</span></span>

- [<span data-ttu-id="2832a-120">安装清单</span><span class="sxs-lookup"><span data-stu-id="2832a-120">Installation Checklist</span></span>](installation-checklist.md)
- [<span data-ttu-id="2832a-121">学习开发提供程序的快速步骤</span><span class="sxs-lookup"><span data-stu-id="2832a-121">Quick Steps for Learning to Develop a Provider</span></span>](quick-steps-for-learning-to-develop-a-provider.md)
- [<span data-ttu-id="2832a-122">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="2832a-122">Deploying a Provider</span></span>](deploying-a-provider.md)

