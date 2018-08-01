---
title: MAPI 配置文件概述 （英文)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d6c57be6-2397-4ab1-a912-028454dffc44
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 573709c4374786bb1bd3d763c8ba91de59f7fb1e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776274"
---
# <a name="mapi-profile-overview"></a><span data-ttu-id="b9dd3-103">MAPI 配置文件概述 （英文)</span><span class="sxs-lookup"><span data-stu-id="b9dd3-103">MAPI Profile Overview</span></span>

  
  
<span data-ttu-id="b9dd3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b9dd3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b9dd3-105">一个配置文件信息的消息服务和客户端应用程序的用户希望可在特定的 MAPI 会话过程中的服务提供商的集合。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-105">A profile is a collection of information about the message services and service providers that a user of a client application wants to be available during a particular MAPI session.</span></span> <span data-ttu-id="b9dd3-106">每个用户都至少一个配置文件;许多用户仍使用原来多个。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-106">Every user has at least one profile; many users keep several.</span></span> <span data-ttu-id="b9dd3-107">例如，用户可能具有一个配置文件以使用基于服务器的消息存储服务和另一个配置文件以在本地计算机上处理的消息存储服务。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-107">For example, a user might have one profile to work with a server-based message store service and another profile to work with a message store service on the local computer.</span></span> <span data-ttu-id="b9dd3-108">用户可能需要访问一组消息系统使用某一天和另一天中的 rest 设置的一部分的合适的传输服务。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-108">A user might want to access one set of messaging systems by using the appropriate transport services for part of the day and another set for the rest of the day.</span></span> <span data-ttu-id="b9dd3-109">配置文件提供灵活的方式选择的消息系统服务的组合。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-109">Profiles provide a flexible way to select combinations of messaging system services.</span></span> 
  
<span data-ttu-id="b9dd3-110">配置文件可以在长度具有最 64 字母数字字符的名称。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-110">Profiles can have names up to 64 alphanumeric characters in length.</span></span> <span data-ttu-id="b9dd3-111">名称可以包括重音字符、 下划线和嵌入的空格，并且不能包含前导或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-111">The names can include accent characters, the underscore, and embedded spaces, and cannot include leading or trailing spaces.</span></span> 
  
<span data-ttu-id="b9dd3-112">配置文件的分层组织和分为部分，为每个消息服务的一部分与服务中的每个服务提供商的一节。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-112">Profiles are organized hierarchically and divided into sections, with one section for each message service and one section for each service provider in a service.</span></span> <span data-ttu-id="b9dd3-113">链接的相关的章节，从而方便信息中导航。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-113">The related sections are linked, making it easier to navigate through the information.</span></span> <span data-ttu-id="b9dd3-114">每个部分包含一系列配置使用 MAPI 或客户端应用程序的条目。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-114">Each section contains a series of entries that MAPI or a client application uses for configuration.</span></span>
  
<span data-ttu-id="b9dd3-115">配置文件中包含的项因消息服务的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-115">The entries included in a profile vary from message service to message service.</span></span> <span data-ttu-id="b9dd3-116">以下一些常见的条目：</span><span class="sxs-lookup"><span data-stu-id="b9dd3-116">Some of the common entries include the following:</span></span>
  
- <span data-ttu-id="b9dd3-117">每个邮件服务或服务提供商的名称。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-117">The name of each message service or service provider.</span></span>
    
- <span data-ttu-id="b9dd3-118">包含服务提供商和消息服务的 Dll 名称。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-118">The name of the DLLs that contain service providers and message services.</span></span>
    
- <span data-ttu-id="b9dd3-119">每个消息服务的入口点函数的名称。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-119">The name of each message service's entry point function.</span></span>
    
- <span data-ttu-id="b9dd3-120">组成每个邮件服务服务提供商的列表。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-120">A list of the service providers that make up each message service.</span></span>
    
<span data-ttu-id="b9dd3-121">在安装时，当 MAPI 或消息服务加载到计算机上，或任何更高版本时，可以创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-121">Profiles can be created at installation time, when MAPI or a message service is loaded onto a computer, or at any later time.</span></span> <span data-ttu-id="b9dd3-122">MAPI 提供配置文件管理配置文件向导。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-122">MAPI provides the Profile Wizard for profile administration.</span></span> 
  
<span data-ttu-id="b9dd3-123">配置文件向导是工作的应用程序创建新配置文件具有最少。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-123">The Profile Wizard is an application that creates new profiles with a minimum amount of work.</span></span> <span data-ttu-id="b9dd3-124">向导将使用默认值的设置，尽可能保存用户时间和精力。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-124">The wizard uses default values for settings wherever possible, saving users time and effort.</span></span> <span data-ttu-id="b9dd3-125">用户输入值仅在绝对需要时。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-125">Users enter values only when absolutely necessary.</span></span> <span data-ttu-id="b9dd3-126">有关详细信息，请参阅[创建使用配置文件向导配置文件](creating-a-profile-by-using-the-profile-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-126">For more information, see [Creating a Profile by Using the Profile Wizard](creating-a-profile-by-using-the-profile-wizard.md).</span></span> <span data-ttu-id="b9dd3-127">您可以使用 Office 自定义工具以创建新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-127">You can also use the Office Customization Tool to create a new profile.</span></span> <span data-ttu-id="b9dd3-128">有关详细信息，请参阅[Office Customization Tool](http://go.microsoft.com/fwlink/?LinkId=123000)。</span><span class="sxs-lookup"><span data-stu-id="b9dd3-128">For more information, see [Office Customization Tool](http://go.microsoft.com/fwlink/?LinkId=123000).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b9dd3-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9dd3-129">See also</span></span>



[<span data-ttu-id="b9dd3-130">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="b9dd3-130">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

