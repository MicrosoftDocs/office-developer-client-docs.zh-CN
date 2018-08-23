---
title: MAPI 地址簿提供程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ead51434-ae19-4c34-aa7a-bdeeccca5bd9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 855b145bcca8007601eb8e841665306d4c58982f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576559"
---
# <a name="mapi-address-book-provider-overview"></a><span data-ttu-id="33a3a-103">MAPI 地址簿提供程序概述</span><span class="sxs-lookup"><span data-stu-id="33a3a-103">MAPI address book provider overview</span></span>
  
<span data-ttu-id="33a3a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="33a3a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="33a3a-105">通讯簿提供程序的句柄访问目录信息。</span><span class="sxs-lookup"><span data-stu-id="33a3a-105">Address book providers handle access to directory information.</span></span> <span data-ttu-id="33a3a-106">目录信息包括两种类型的邮件的收件人数据： 单个消息的用户和组的邮件用户通常在通讯组列表一起讨论。</span><span class="sxs-lookup"><span data-stu-id="33a3a-106">Directory information consists of data for two types of message recipients: individual messaging users and groups of messaging users who are commonly addressed together in distribution lists.</span></span> <span data-ttu-id="33a3a-107">根据收件人和通讯簿提供程序的类型，没有各种各样的可提供的信息。</span><span class="sxs-lookup"><span data-stu-id="33a3a-107">Depending on the type of recipient and the address book provider, there is a wide range of information that can be made available.</span></span> <span data-ttu-id="33a3a-108">例如，所有通讯簿提供程序都存储收件人的姓名、 地址和地址类型。</span><span class="sxs-lookup"><span data-stu-id="33a3a-108">For example, all address book providers store a recipient's name, address, and address type.</span></span>
  
<span data-ttu-id="33a3a-109">每个通讯簿提供程序将此数据组织使用一个或多个容器。</span><span class="sxs-lookup"><span data-stu-id="33a3a-109">Each address book provider organizes this data by using one or more containers.</span></span> <span data-ttu-id="33a3a-110">数量和结构的容器取决于通讯簿提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="33a3a-110">The number and structure of the containers depends on the address book provider's implementation.</span></span> <span data-ttu-id="33a3a-111">例如，一个通讯簿提供程序可能使用单个容器保留的所有信息，另一个可能都使用一个包含子容器的顶级容器和第三个可以都使用多个顶级容器，每个保持子容器。</span><span class="sxs-lookup"><span data-stu-id="33a3a-111">For example, one address book provider might use a single container to hold all of the information, another might use one top-level container that holds subcontainers, and a third might use several top-level containers, each holding subcontainers.</span></span> <span data-ttu-id="33a3a-112">通讯簿容器层次结构可以很深;可用的子容器的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="33a3a-112">An address book container hierarchy can be quite deep; there is no limit to the number of subcontainers that can be used.</span></span>
  
<span data-ttu-id="33a3a-113">下图显示了典型的 MAPI 通讯簿组织。</span><span class="sxs-lookup"><span data-stu-id="33a3a-113">The following illustration shows a typical MAPI address book organization.</span></span>
  
<span data-ttu-id="33a3a-114">**通讯簿组织**</span><span class="sxs-lookup"><span data-stu-id="33a3a-114">**Address book organization**</span></span>
  
<span data-ttu-id="33a3a-115">![通讯簿组织](media/amapi_04.gif "通讯簿组织")</span><span class="sxs-lookup"><span data-stu-id="33a3a-115">![Address book organization](media/amapi_04.gif "Address book organization")</span></span>
  
<span data-ttu-id="33a3a-116">MAPI 集成到一个通讯簿，由安装的通讯簿提供程序提供的所有信息演示统一客户端应用程序的视图。</span><span class="sxs-lookup"><span data-stu-id="33a3a-116">MAPI integrates all the information supplied by the installed address book providers into a single address book, presenting a unified view to the client application.</span></span> <span data-ttu-id="33a3a-117">集成的列表显示了显示每个安装的通讯簿提供程序的顶级容器。</span><span class="sxs-lookup"><span data-stu-id="33a3a-117">The integrated list shows the top-level containers displayed by each of the installed address book providers.</span></span> <span data-ttu-id="33a3a-118">大多数通讯簿提供程序在 MAPI 集成的通讯簿的最高级别中包含的顶级公开仅少数容器 （通常一到三个）。</span><span class="sxs-lookup"><span data-stu-id="33a3a-118">Most address book providers expose only a few containers (typically one to three) at the top level for inclusion in the top level of the MAPI integrated address book.</span></span> <span data-ttu-id="33a3a-119">例如，通讯簿提供程序可能会使可用"所有用户"和"本地用户"作为最高级别的两个容器。</span><span class="sxs-lookup"><span data-stu-id="33a3a-119">For example, an address book provider might make available "All Users" and "Local Users" as two containers at the top level.</span></span>
  
<span data-ttu-id="33a3a-120">客户端应用程序的用户都可以查看的通讯簿容器内容，并在某些情况下，修改的内容。</span><span class="sxs-lookup"><span data-stu-id="33a3a-120">The users of client applications can view the contents of address book containers and, in some cases, modify the contents.</span></span> <span data-ttu-id="33a3a-121">可以使用不同的访问级别，具体取决于通讯簿提供程序创建地址簿容器。</span><span class="sxs-lookup"><span data-stu-id="33a3a-121">Address book containers can be created with different access levels, depending on the address book provider.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="33a3a-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33a3a-122">See also</span></span>

- [<span data-ttu-id="33a3a-123">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="33a3a-123">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

