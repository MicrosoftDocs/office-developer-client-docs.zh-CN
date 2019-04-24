---
title: MapiSvc.inf 文件格式
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
api_type:
- COM
ms.assetid: b48eda17-83a8-4dc4-85c8-4ca827d13d25
description: 上次修改时间：2011 年 7 月 23 日
localization_priority: Priority
ms.openlocfilehash: 934bb491c0521b1d76d5400aac4728fbd34ba625
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334867"
---
# <a name="file-format-of-mapisvcinf"></a><span data-ttu-id="5bb59-103">MapiSvc.inf 文件格式</span><span class="sxs-lookup"><span data-stu-id="5bb59-103">File format of MapiSvc.inf</span></span>

<span data-ttu-id="5bb59-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5bb59-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5bb59-105">MapiSvc.inf 文件相当于 MAPI 邮件服务配置信息的中央数据库。</span><span class="sxs-lookup"><span data-stu-id="5bb59-105">The MapiSvc.inf file acts as the central database for MAPI message service configuration information.</span></span> <span data-ttu-id="5bb59-106">MapiSvc.inf 中包含有关工作站上安装的邮件服务信息、有关属于每个邮件服务的服务提供程序信息以及有关 MAPI 子系统的信息。</span><span class="sxs-lookup"><span data-stu-id="5bb59-106">MapiSvc.inf contains information about each of the message services installed on the workstation, information about the service providers that belong to each message service, and information about the MAPI subsystem.</span></span> <span data-ttu-id="5bb59-107">MapiSvc.inf 是配置文件的主要信息来源。</span><span class="sxs-lookup"><span data-stu-id="5bb59-107">MapiSvc.inf is the primary source of information for profiles.</span></span> <span data-ttu-id="5bb59-108">也就是说，构建新的配置文件或者修改现有配置文件时，将从 MapiSvc.inf 复制每个邮件服务或服务提供程序的相关信息。</span><span class="sxs-lookup"><span data-stu-id="5bb59-108">That is, when a new profile is being built or an existing one modified, relevant information for each message service or service provider is copied from MapiSvc.inf.</span></span> 
  
<span data-ttu-id="5bb59-109">MapiSvc.inf 分为链接分层分区：</span><span class="sxs-lookup"><span data-stu-id="5bb59-109">MapiSvc.inf is divided into linked hierarchical sections:</span></span>
  
1. <span data-ttu-id="5bb59-110">包含适用于所有配置文件的信息的分区。</span><span class="sxs-lookup"><span data-stu-id="5bb59-110">Section containing information that applies to all profiles.</span></span> <span data-ttu-id="5bb59-111">此分区具有三个部分：</span><span class="sxs-lookup"><span data-stu-id="5bb59-111">This section has three parts:</span></span>
    
   - <span data-ttu-id="5bb59-112">**[服务]** 分区，用于提供至每个后续邮件服务分区的链接。</span><span class="sxs-lookup"><span data-stu-id="5bb59-112">**[Services]** section, providing links to each of the subsequent message service sections.</span></span> 
    
   - <span data-ttu-id="5bb59-113">**[帮助文件映射]** 分区，其中包含有关邮件服务提供的 .HLP 文件的信息。</span><span class="sxs-lookup"><span data-stu-id="5bb59-113">**[Help File Mappings]** section, containing information about .HLP files provided by message services.</span></span> 
    
   - <span data-ttu-id="5bb59-114">**[默认服务]** 分区，用于列出组成默认安装的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="5bb59-114">**[Default Services]** section, listing message services that make up a default installation.</span></span> 
    
2. <span data-ttu-id="5bb59-115">包含适用于单个邮件服务的信息的分区。</span><span class="sxs-lookup"><span data-stu-id="5bb59-115">Section containing information that applies to individual message services.</span></span> <span data-ttu-id="5bb59-116">这些分区中的条目提供了至后续服务提供程序分区的链接。</span><span class="sxs-lookup"><span data-stu-id="5bb59-116">Entries in these sections provide links to subsequent service provider sections.</span></span>
    
3. <span data-ttu-id="5bb59-117">包含适用于邮件服务中的单个服务提供商的信息的分区。</span><span class="sxs-lookup"><span data-stu-id="5bb59-117">Section containing information that applies to individual service providers in a message service.</span></span>
    
<span data-ttu-id="5bb59-118">下图所示为典型 MapiSvc.inf 文件的组织形式。</span><span class="sxs-lookup"><span data-stu-id="5bb59-118">The following illustration shows the organization of a typical MapiSvc.inf file.</span></span> <span data-ttu-id="5bb59-119">三种邮件服务包括：AB、MsgService 和 MS。</span><span class="sxs-lookup"><span data-stu-id="5bb59-119">There are three message services: AB, MsgService, and MS.</span></span> <span data-ttu-id="5bb59-120">在每个邮件服务中，等号右边的名称为服务的显示名称。</span><span class="sxs-lookup"><span data-stu-id="5bb59-120">The name on the right hand side of the equal sign for each message service is the service's display name.</span></span> <span data-ttu-id="5bb59-121">每个邮件服务自己的分区位于链接至一个或多个服务提供程序分区的文件中的其他位置。</span><span class="sxs-lookup"><span data-stu-id="5bb59-121">Each message service has its own section elsewhere in the file that is linked to one or more service provider sections.</span></span> <span data-ttu-id="5bb59-122">属于邮件服务的每个服务提供程序均有一个服务提供程序分区。</span><span class="sxs-lookup"><span data-stu-id="5bb59-122">There is one service provider section for every service provider that belongs to the message service.</span></span> <span data-ttu-id="5bb59-123">AB 和 MS 邮件服务为单一提供程序服务，其中，三个服务提供程序均属于 MsgService 服务。</span><span class="sxs-lookup"><span data-stu-id="5bb59-123">The AB and MS message services are single provider services whereas three service providers belong to the MsgService service.</span></span>
  
<span data-ttu-id="5bb59-124">**MapiSvc.inf 文件组织**</span><span class="sxs-lookup"><span data-stu-id="5bb59-124">**MapiSvc.inf file organization**</span></span>
  
<span data-ttu-id="5bb59-125">![MapiSvc.inf 文件组织](media/amapi_30.gif "MapiSvc.inf 文件组织")</span><span class="sxs-lookup"><span data-stu-id="5bb59-125">![MapiSvc.inf file organization](media/amapi_30.gif "MapiSvc.inf file organization")</span></span>
  
<span data-ttu-id="5bb59-126">MAPI 提供了 MapiSvc.inf 文件的框架式版本，其中包含 MAPI 子系统的条目。</span><span class="sxs-lookup"><span data-stu-id="5bb59-126">MAPI provides a skeletal version of the MapiSvc.inf file that contains the entries for the MAPI subsystem.</span></span> <span data-ttu-id="5bb59-127">每个邮件服务实施程序将添加适合于其服务以及属于其服务的服务提供程序的条目。</span><span class="sxs-lookup"><span data-stu-id="5bb59-127">Each message service implementer adds entries that are appropriate both for their service and the service providers that belong to their service.</span></span> <span data-ttu-id="5bb59-128">某些条目为必须项，其余的则是可选项。</span><span class="sxs-lookup"><span data-stu-id="5bb59-128">Some of the entries are required while others are optional.</span></span> <span data-ttu-id="5bb59-129">例如，MAPI 要求你指定邮件服务中的每个服务提供程序的名称和路径。</span><span class="sxs-lookup"><span data-stu-id="5bb59-129">For example, MAPI requires that you specify the name and path of each of the service providers in your message service.</span></span> <span data-ttu-id="5bb59-130">如果没有这些信息，则无法加载它们。</span><span class="sxs-lookup"><span data-stu-id="5bb59-130">Without this information, they cannot be loaded.</span></span>
  
<span data-ttu-id="5bb59-131">你可以在邮件服务分区和/或服务提供程序分区添加必须和可选信息。</span><span class="sxs-lookup"><span data-stu-id="5bb59-131">You can add required and optional information in either the section for your message service and/or to the service provider sections.</span></span> <span data-ttu-id="5bb59-132">添加用于描述邮件服务的信息的位置，取决于服务中的服务提供程序数量。</span><span class="sxs-lookup"><span data-stu-id="5bb59-132">Where you put the information describing your message service depends on the number of service providers in the service.</span></span> <span data-ttu-id="5bb59-133">由于此信息适用于服务中的每个服务提供程序，因此，必须使所有提供程序能够访问它。</span><span class="sxs-lookup"><span data-stu-id="5bb59-133">Because this information applies to each service provider in the service, you must make it accessible to all providers.</span></span> <span data-ttu-id="5bb59-134">将此信息存储到邮件服务分区、首选选项或所有服务提供程序分区中。</span><span class="sxs-lookup"><span data-stu-id="5bb59-134">Store it either in the message service section, the preferred option, or in all of the service provider sections.</span></span> <span data-ttu-id="5bb59-135">存储信息一次以免不必要的复制和同步多个副本。</span><span class="sxs-lookup"><span data-stu-id="5bb59-135">Store information once to avoid unnecessary replication and the need to keep multiple copies synchronized.</span></span>
  
<span data-ttu-id="5bb59-136">如果邮件服务为单一提供程序服务，请将所有邮件服务信息存储到服务提供程序分区，而不是服务分区。</span><span class="sxs-lookup"><span data-stu-id="5bb59-136">If your message service is a single provider service, store all of the message service information in the section for the service provider rather than in the section for the service.</span></span> <span data-ttu-id="5bb59-137">与访问邮件服务分区相比，访问服务提供程序分区速度更快且更直接。</span><span class="sxs-lookup"><span data-stu-id="5bb59-137">Accessing the service provider section is faster and more direct than accessing the message service section.</span></span> 
  
<span data-ttu-id="5bb59-138">仅将公用配置数据存储到 MapiSvc.inf 文件中。</span><span class="sxs-lookup"><span data-stu-id="5bb59-138">Store only public configuration data in the MapiSvc.inf file.</span></span> <span data-ttu-id="5bb59-139">专用信息或者需要额外保护的信息（如密码或其他凭据）应包括在此文件中。</span><span class="sxs-lookup"><span data-stu-id="5bb59-139">Information that is private or requires extra protection, such as passwords or other credentials, should not be included in this file.</span></span> <span data-ttu-id="5bb59-140">相反，选择完全不存储此类信息，或者将其作为安全属性存储在配置文件中。</span><span class="sxs-lookup"><span data-stu-id="5bb59-140">Instead, opt either not to store information of this type at all or keep it in the profile as secure properties.</span></span> <span data-ttu-id="5bb59-141">安全属性具有内置的保护功能，如加密。</span><span class="sxs-lookup"><span data-stu-id="5bb59-141">Secure properties have built-in protection features such as encryption.</span></span>
  

