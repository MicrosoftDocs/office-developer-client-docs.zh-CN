---
title: MAPI 通讯簿提供程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ead51434-ae19-4c34-aa7a-bdeeccca5bd9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ee628f4b11cb174c05a16ca60c9ec830a0e9abbe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426539"
---
# <a name="mapi-address-book-provider-overview"></a><span data-ttu-id="38459-103">MAPI 通讯簿提供程序概述</span><span class="sxs-lookup"><span data-stu-id="38459-103">MAPI address book provider overview</span></span>
  
<span data-ttu-id="38459-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38459-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38459-105">通讯簿提供程序处理对目录信息的访问。</span><span class="sxs-lookup"><span data-stu-id="38459-105">Address book providers handle access to directory information.</span></span> <span data-ttu-id="38459-106">目录信息包含两种类型的邮件收件人的数据：单个邮件用户和通讯组列表中通常一起寻址的邮件用户组。</span><span class="sxs-lookup"><span data-stu-id="38459-106">Directory information consists of data for two types of message recipients: individual messaging users and groups of messaging users who are commonly addressed together in distribution lists.</span></span> <span data-ttu-id="38459-107">根据收件人和通讯簿提供程序的类型，可以提供各种信息。</span><span class="sxs-lookup"><span data-stu-id="38459-107">Depending on the type of recipient and the address book provider, there is a wide range of information that can be made available.</span></span> <span data-ttu-id="38459-108">例如，所有通讯簿提供程序都存储收件人的姓名、地址和地址类型。</span><span class="sxs-lookup"><span data-stu-id="38459-108">For example, all address book providers store a recipient's name, address, and address type.</span></span>
  
<span data-ttu-id="38459-109">每个通讯簿提供程序都使用一个或多个容器来组织此数据。</span><span class="sxs-lookup"><span data-stu-id="38459-109">Each address book provider organizes this data by using one or more containers.</span></span> <span data-ttu-id="38459-110">容器的数量和结构取决于通讯簿提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="38459-110">The number and structure of the containers depends on the address book provider's implementation.</span></span> <span data-ttu-id="38459-111">例如，一个通讯簿提供程序可能使用一个容器来保存所有信息，另一个地址簿提供程序可能使用一个包含子容器的顶级容器，第三个可能使用几个顶级容器，每个容器存放子容器。</span><span class="sxs-lookup"><span data-stu-id="38459-111">For example, one address book provider might use a single container to hold all of the information, another might use one top-level container that holds subcontainers, and a third might use several top-level containers, each holding subcontainers.</span></span> <span data-ttu-id="38459-112">通讯簿容器层次结构可能很深;对可以使用的子包含者的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="38459-112">An address book container hierarchy can be quite deep; there is no limit to the number of subcontainers that can be used.</span></span>
  
<span data-ttu-id="38459-113">下图显示了典型的 MAPI 通讯簿组织。</span><span class="sxs-lookup"><span data-stu-id="38459-113">The following illustration shows a typical MAPI address book organization.</span></span>
  
<span data-ttu-id="38459-114">**通讯簿组织**</span><span class="sxs-lookup"><span data-stu-id="38459-114">**Address book organization**</span></span>
  
<span data-ttu-id="38459-115">![通讯簿组织](media/amapi_04.gif "通讯簿组织")</span><span class="sxs-lookup"><span data-stu-id="38459-115">![Address book organization](media/amapi_04.gif "Address book organization")</span></span>
  
<span data-ttu-id="38459-116">MAPI 将已安装通讯簿提供程序提供的所有信息集成到一个通讯簿中，为客户端应用程序提供统一视图。</span><span class="sxs-lookup"><span data-stu-id="38459-116">MAPI integrates all the information supplied by the installed address book providers into a single address book, presenting a unified view to the client application.</span></span> <span data-ttu-id="38459-117">集成列表显示由每个已安装的通讯簿提供程序显示的顶级容器。</span><span class="sxs-lookup"><span data-stu-id="38459-117">The integrated list shows the top-level containers displayed by each of the installed address book providers.</span></span> <span data-ttu-id="38459-118">大多数通讯簿提供程序仅公开几个容器 (一到三) 顶级容器，以包含在 MAPI 集成通讯簿的顶层中。</span><span class="sxs-lookup"><span data-stu-id="38459-118">Most address book providers expose only a few containers (typically one to three) at the top level for inclusion in the top level of the MAPI integrated address book.</span></span> <span data-ttu-id="38459-119">例如，通讯簿提供程序可能将"所有用户"和"本地用户"作为顶级的两个容器提供。</span><span class="sxs-lookup"><span data-stu-id="38459-119">For example, an address book provider might make available "All Users" and "Local Users" as two containers at the top level.</span></span>
  
<span data-ttu-id="38459-120">客户端应用程序的用户可以查看通讯簿容器的内容，在某些情况下还可以修改内容。</span><span class="sxs-lookup"><span data-stu-id="38459-120">The users of client applications can view the contents of address book containers and, in some cases, modify the contents.</span></span> <span data-ttu-id="38459-121">可以使用不同的访问级别创建通讯簿容器，具体取决于通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="38459-121">Address book containers can be created with different access levels, depending on the address book provider.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="38459-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38459-122">See also</span></span>

- [<span data-ttu-id="38459-123">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="38459-123">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

