---
title: MAPI 配置文件概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d6c57be6-2397-4ab1-a912-028454dffc44
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e196800b717ce2528da4b9871bad7425f3a2c326
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328160"
---
# <a name="mapi-profile-overview"></a><span data-ttu-id="c8f57-103">MAPI 配置文件概述</span><span class="sxs-lookup"><span data-stu-id="c8f57-103">MAPI Profile Overview</span></span>

  
  
<span data-ttu-id="c8f57-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c8f57-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c8f57-105">配置文件是有关特定 MAPI 会话期间客户端应用程序用户希望其可用的邮件服务和服务提供程序的信息集合。</span><span class="sxs-lookup"><span data-stu-id="c8f57-105">A profile is a collection of information about the message services and service providers that a user of a client application wants to be available during a particular MAPI session.</span></span> <span data-ttu-id="c8f57-106">每个用户都至少有一个配置文件;许多用户保留多个。</span><span class="sxs-lookup"><span data-stu-id="c8f57-106">Every user has at least one profile; many users keep several.</span></span> <span data-ttu-id="c8f57-107">例如，用户可能有一个配置文件用于基于服务器的邮件存储服务，另一个配置文件用于本地计算机上的邮件存储服务。</span><span class="sxs-lookup"><span data-stu-id="c8f57-107">For example, a user might have one profile to work with a server-based message store service and another profile to work with a message store service on the local computer.</span></span> <span data-ttu-id="c8f57-108">用户可能想要通过使用一天中的相应传输服务访问一组邮件系统，在一天中的其余时间使用另一组传输服务。</span><span class="sxs-lookup"><span data-stu-id="c8f57-108">A user might want to access one set of messaging systems by using the appropriate transport services for part of the day and another set for the rest of the day.</span></span> <span data-ttu-id="c8f57-109">配置文件提供了选择邮件系统服务组合的灵活方法。</span><span class="sxs-lookup"><span data-stu-id="c8f57-109">Profiles provide a flexible way to select combinations of messaging system services.</span></span> 
  
<span data-ttu-id="c8f57-110">配置文件的名称长度最多为 64 个字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="c8f57-110">Profiles can have names up to 64 alphanumeric characters in length.</span></span> <span data-ttu-id="c8f57-111">名称可以包括重音字符、下划线和嵌入空格，并且不能包含前导空格或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="c8f57-111">The names can include accent characters, the underscore, and embedded spaces, and cannot include leading or trailing spaces.</span></span> 
  
<span data-ttu-id="c8f57-112">配置文件按层次结构组织并分为若干部分，每个邮件服务有一个部分，服务中的每个服务提供商有一个分区。</span><span class="sxs-lookup"><span data-stu-id="c8f57-112">Profiles are organized hierarchically and divided into sections, with one section for each message service and one section for each service provider in a service.</span></span> <span data-ttu-id="c8f57-113">相关部分链接在一起，便于在信息中导航。</span><span class="sxs-lookup"><span data-stu-id="c8f57-113">The related sections are linked, making it easier to navigate through the information.</span></span> <span data-ttu-id="c8f57-114">每个部分都包含 MAPI 或客户端应用程序用于配置的一系列条目。</span><span class="sxs-lookup"><span data-stu-id="c8f57-114">Each section contains a series of entries that MAPI or a client application uses for configuration.</span></span>
  
<span data-ttu-id="c8f57-115">配置文件中包含的条目因邮件服务而异。</span><span class="sxs-lookup"><span data-stu-id="c8f57-115">The entries included in a profile vary from message service to message service.</span></span> <span data-ttu-id="c8f57-116">一些常见条目包括：</span><span class="sxs-lookup"><span data-stu-id="c8f57-116">Some of the common entries include the following:</span></span>
  
- <span data-ttu-id="c8f57-117">每个邮件服务或服务提供商的名称。</span><span class="sxs-lookup"><span data-stu-id="c8f57-117">The name of each message service or service provider.</span></span>
    
- <span data-ttu-id="c8f57-118">包含服务提供程序和消息服务的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="c8f57-118">The name of the DLLs that contain service providers and message services.</span></span>
    
- <span data-ttu-id="c8f57-119">每个邮件服务的入口点函数的名称。</span><span class="sxs-lookup"><span data-stu-id="c8f57-119">The name of each message service's entry point function.</span></span>
    
- <span data-ttu-id="c8f57-120">包含每个邮件服务的服务提供商的列表。</span><span class="sxs-lookup"><span data-stu-id="c8f57-120">A list of the service providers that make up each message service.</span></span>
    
<span data-ttu-id="c8f57-121">可以在安装时、将 MAPI 或邮件服务加载到计算机上时或在以后的任何时间创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="c8f57-121">Profiles can be created at installation time, when MAPI or a message service is loaded onto a computer, or at any later time.</span></span> <span data-ttu-id="c8f57-122">MAPI 提供配置文件向导以用于配置文件管理。</span><span class="sxs-lookup"><span data-stu-id="c8f57-122">MAPI provides the Profile Wizard for profile administration.</span></span> 
  
<span data-ttu-id="c8f57-123">配置文件向导是一个应用程序，它以最少的工作创建新配置文件。</span><span class="sxs-lookup"><span data-stu-id="c8f57-123">The Profile Wizard is an application that creates new profiles with a minimum amount of work.</span></span> <span data-ttu-id="c8f57-124">向导尽可能使用设置的默认值，从而节省用户时间和精力。</span><span class="sxs-lookup"><span data-stu-id="c8f57-124">The wizard uses default values for settings wherever possible, saving users time and effort.</span></span> <span data-ttu-id="c8f57-125">用户仅在绝对必要时输入值。</span><span class="sxs-lookup"><span data-stu-id="c8f57-125">Users enter values only when absolutely necessary.</span></span> <span data-ttu-id="c8f57-126">有关详细信息，请参阅 [使用配置文件向导创建配置文件](creating-a-profile-by-using-the-profile-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="c8f57-126">For more information, see [Creating a Profile by Using the Profile Wizard](creating-a-profile-by-using-the-profile-wizard.md).</span></span> <span data-ttu-id="c8f57-127">您还可以使用自定义Office工具创建新配置文件。</span><span class="sxs-lookup"><span data-stu-id="c8f57-127">You can also use the Office Customization Tool to create a new profile.</span></span> <span data-ttu-id="c8f57-128">有关详细信息，请参阅 [Office 自定义工具](https://go.microsoft.com/fwlink/?LinkId=123000)。</span><span class="sxs-lookup"><span data-stu-id="c8f57-128">For more information, see [Office Customization Tool](https://go.microsoft.com/fwlink/?LinkId=123000).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c8f57-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8f57-129">See also</span></span>



[<span data-ttu-id="c8f57-130">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="c8f57-130">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

