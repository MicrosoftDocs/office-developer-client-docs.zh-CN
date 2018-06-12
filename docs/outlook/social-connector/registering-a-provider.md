---
title: 注册提供程序
manager: soliver
ms.date: 03/05/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: b60b3634-4c8b-4273-97a0-0a8a5a8a5342
description: 本主题介绍安装 Outlook Social Connector (OSC) 提供程序时所使用的 Windows 注册表位置。
ms.openlocfilehash: 3ec594ec94b045d2ceb583144781a5746b945b5c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779321"
---
# <a name="registering-a-provider"></a><span data-ttu-id="fe5fe-103">注册提供程序</span><span class="sxs-lookup"><span data-stu-id="fe5fe-103">Registering a provider</span></span>

<span data-ttu-id="fe5fe-104">本主题介绍安装 Outlook Social Connector (OSC) 提供程序时所使用的 Windows 注册表位置。</span><span class="sxs-lookup"><span data-stu-id="fe5fe-104">This topic describes the Windows registry locations that are used when you install an Outlook Social Connector (OSC) provider.</span></span>
  
## <a name="com-registration"></a><span data-ttu-id="fe5fe-105">COM 注册</span><span class="sxs-lookup"><span data-stu-id="fe5fe-105">COM registration</span></span>

<span data-ttu-id="fe5fe-106">您必须配置 OSC 提供程序注册安装过程中使用 COM 注册或 regsvr32 的 DLL。</span><span class="sxs-lookup"><span data-stu-id="fe5fe-106">You must configure the OSC provider DLL to register using COM self-registration or regsvr32 during installation.</span></span> <span data-ttu-id="fe5fe-107">COM 注册提供程序 DLL 的注册下的 OSC 提供程序`HKEY_CLASSES_ROOT`注册表配置单元。</span><span class="sxs-lookup"><span data-stu-id="fe5fe-107">COM registration of the provider DLL registers the OSC provider under the `HKEY_CLASSES_ROOT` registry hive.</span></span> 
  
<span data-ttu-id="fe5fe-108">在托管代码开发 OSC 提供程序具有 COM 可见的提供程序程序集。</span><span class="sxs-lookup"><span data-stu-id="fe5fe-108">An OSC provider developed in managed code has a COM-visible provider assembly.</span></span> <span data-ttu-id="fe5fe-109">提供程序组件，您应使用单独的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="fe5fe-109">You should use a separate application domain for the provider component.</span></span> <span data-ttu-id="fe5fe-110">否则为 OSC 提供程序使用的默认共享应用程序域由其他组件，并提供程序可能不会按预期。</span><span class="sxs-lookup"><span data-stu-id="fe5fe-110">Otherwise, the OSC provider uses the default shared application domain that is used by other components, and the provider may not operate as expected.</span></span>
  
## <a name="registering-provider-progid"></a><span data-ttu-id="fe5fe-111">注册提供程序 ProgID</span><span class="sxs-lookup"><span data-stu-id="fe5fe-111">Registering provider ProgID</span></span>

<span data-ttu-id="fe5fe-112">每个 OSC 提供程序必须注册的编程标识符 (`ProgID`)。</span><span class="sxs-lookup"><span data-stu-id="fe5fe-112">Each OSC provider must register a programmatic identifier (`ProgID`).</span></span> <span data-ttu-id="fe5fe-113">提供程序安装程序可以选择要添加或删除的以下位置之一`ProgID`:</span><span class="sxs-lookup"><span data-stu-id="fe5fe-113">The provider installer can choose one of the following locations to add or remove the `ProgID`:</span></span>
  
- <span data-ttu-id="fe5fe-114">`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`&ndash;如果提供程序安装仅为当前登录的用户提供程序安装程序应使用此位置。</span><span class="sxs-lookup"><span data-stu-id="fe5fe-114">`HKEY_CURRENT_USER\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders` &ndash; Your provider installer should use this location if the provider is installed for only the currently logged-on user.</span></span>
    
- <span data-ttu-id="fe5fe-115">`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`&ndash;如果提供程序为所有用户的计算机上安装的提供程序安装程序应使用此位置。</span><span class="sxs-lookup"><span data-stu-id="fe5fe-115">`HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders` &ndash; Your provider installer should use this location if the provider is installed for all users on the computer.</span></span>
    
<span data-ttu-id="fe5fe-116">OSC 提供程序查找`ProgID`在上面的位置，除非客户端计算机具有 32 位 Outlook 在 64 位 Windows 操作系统上运行。</span><span class="sxs-lookup"><span data-stu-id="fe5fe-116">The OSC looks for the provider  `ProgID` in the above locations, unless the client computer has 32-bit Outlook running on a 64-bit Windows operating system.</span></span> <span data-ttu-id="fe5fe-117">在这种情况下，提供程序安装程序应选择中的以下位置之一`HKEY_CURRENT_USER`或`HKEY_LOCAL_MACHINE`配置单元：</span><span class="sxs-lookup"><span data-stu-id="fe5fe-117">In such a case, your provider installer should choose one of the following locations in the  `HKEY_CURRENT_USER` or  `HKEY_LOCAL_MACHINE` hive:</span></span> 
  
- `HKEY_CURRENT_USER\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
- `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
<span data-ttu-id="fe5fe-118">单击即点即用版本的 Office，提供程序安装程序应选择在以下位置之一在 HKEY_CURRENT_USER 或 HKEY_LOCAL_MACHINE 配置单元：</span><span class="sxs-lookup"><span data-stu-id="fe5fe-118">For a Click-to-Run version of Office, your provider installer should choose one of the following locations in the HKEY_CURRENT_USER or HKEY_LOCAL_MACHINE hive:</span></span>
  
- `HKEY_CURRENT_USER\Software\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Microsoft\Office\Outlook\SocialConnector\SocialProviders`
    
- `HKEY_LOCAL_MACHINE\Software\Microsoft\Office\ClickToRun\REGISTRY\MACHINE\Software\Microsoft\Outlook\SocialConnector\SocialProviders`
    
## <a name="see-also"></a><span data-ttu-id="fe5fe-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe5fe-119">See also</span></span>

- [<span data-ttu-id="fe5fe-120">安装清单</span><span class="sxs-lookup"><span data-stu-id="fe5fe-120">Installation Checklist</span></span>](installation-checklist.md)
- [<span data-ttu-id="fe5fe-121">快速学习开发提供程序的步骤</span><span class="sxs-lookup"><span data-stu-id="fe5fe-121">Quick Steps for Learning to Develop a Provider</span></span>](quick-steps-for-learning-to-develop-a-provider.md)
- [<span data-ttu-id="fe5fe-122">部署提供程序</span><span class="sxs-lookup"><span data-stu-id="fe5fe-122">Deploying a Provider</span></span>](deploying-a-provider.md)

