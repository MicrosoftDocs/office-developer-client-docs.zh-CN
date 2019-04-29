---
title: MAPI 邮件服务概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 58f36a6b-bcc5-4ebb-9761-6f420a718d97
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8973cdcee2b10346d0ba07033357b50f7e9a6a27
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406253"
---
# <a name="mapi-message-service-overview"></a><span data-ttu-id="784bc-103">MAPI 邮件服务概述</span><span class="sxs-lookup"><span data-stu-id="784bc-103">MAPI message service overview</span></span>
  
<span data-ttu-id="784bc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="784bc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="784bc-105">邮件服务定义一组相关的服务提供程序, 通常是使用同一个邮件系统的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="784bc-105">A message service defines a group of related service providers, typically service providers that work with the same messaging system.</span></span> <span data-ttu-id="784bc-106">服务提供商执行在邮件系统和 MAPI 子系统之间进行通信的工作, 邮件服务执行在与公用邮件系统配合使用的用户和服务提供程序之间进行通信的工作。</span><span class="sxs-lookup"><span data-stu-id="784bc-106">Whereas service providers perform the work of communicating between messaging systems and the MAPI subsystem, message services perform the work of interfacing between the user and service providers that work with a common messaging system.</span></span>  
  
<span data-ttu-id="784bc-107">存在的邮件服务可使用户更容易地安装和配置服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="784bc-107">Message services exist to make the installation and configuration of service providers easier for users.</span></span> <span data-ttu-id="784bc-108">用户永远不直接安装或配置服务提供商;邮件服务完全处理属于该服务的每个服务提供程序的安装和配置。</span><span class="sxs-lookup"><span data-stu-id="784bc-108">Users never directly install or configure a service provider; the message service completely handles the installation and configuration of each of the service providers that belong to the service.</span></span> <span data-ttu-id="784bc-109">由于此功能, 用户无需熟悉特定的服务提供程序配置要求。</span><span class="sxs-lookup"><span data-stu-id="784bc-109">Because of this feature, users do not need to be familiar with specific service provider configuration requirements.</span></span> 
  
<span data-ttu-id="784bc-110">下图显示了基于邮件的客户端应用程序和两个邮件服务之间的关系。</span><span class="sxs-lookup"><span data-stu-id="784bc-110">The following figure shows the relationship between a messaging-based client application and two message services.</span></span>
  
<span data-ttu-id="784bc-111">**消息服务安装和配置**</span><span class="sxs-lookup"><span data-stu-id="784bc-111">**Message service installation and configuration**</span></span>
  
<span data-ttu-id="784bc-112">![邮件服务的安装和配置](media/amapi_44.gif "邮件服务的安装和配置")</span><span class="sxs-lookup"><span data-stu-id="784bc-112">![Message service installation and configuration](media/amapi_44.gif "Message service installation and configuration")</span></span>
  
<span data-ttu-id="784bc-113">用户调用每个邮件服务的安装代码, 将该服务及其服务提供程序添加到配置文件中。</span><span class="sxs-lookup"><span data-stu-id="784bc-113">The user invokes the installation code of each message service to add the service and its service providers to a profile.</span></span> <span data-ttu-id="784bc-114">在图所示的某个邮件服务中, 有三个服务提供商;在其他邮件服务中, 有两个服务提供商。</span><span class="sxs-lookup"><span data-stu-id="784bc-114">In one of the message services shown in the figure, there are three service providers; in the other message service, there are two service providers.</span></span> <span data-ttu-id="784bc-115">在安装完成后的一些后续时间, 通常在登录时配置每个邮件服务中的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="784bc-115">At some later time after installation is complete, typically at logon time, the service providers in each message service are configured.</span></span> <span data-ttu-id="784bc-116">每个邮件服务中的配置代码处理服务中的提供程序的配置。</span><span class="sxs-lookup"><span data-stu-id="784bc-116">The configuration code in each message service handles the configuration of the providers in the service.</span></span>
  
<span data-ttu-id="784bc-117">安装邮件服务时, 其安装程序会将所需的文件从安装源复制到用户的本地磁盘, 并更新配置文件 mapisvc.inf。</span><span class="sxs-lookup"><span data-stu-id="784bc-117">When a message service is installed, its installation program copies necessary files from the installation source to the user's local disk and updates a configuration file, Mapisvc.inf.</span></span> <span data-ttu-id="784bc-118">mapisvc.inf 文件包含可在计算机上安装的所有邮件服务和服务提供程序的配置设置。</span><span class="sxs-lookup"><span data-stu-id="784bc-118">The Mapisvc.inf file contains configuration settings for all of the message services and service providers that can be installed on the computer.</span></span> <span data-ttu-id="784bc-119">它在分层部分中进行组织, 其中每个级别的各节之间都有链接。</span><span class="sxs-lookup"><span data-stu-id="784bc-119">It is organized in hierarchical sections, with links between each section at each level.</span></span> <span data-ttu-id="784bc-120">顶层的部分包含与 MAPI 子系统相关的信息, 如所有可用邮件服务的列表和联机帮助安装。</span><span class="sxs-lookup"><span data-stu-id="784bc-120">The section at the top level contains information that is relevant for the MAPI subsystem, such as a list of all available message services, and for the online Help installation.</span></span> <span data-ttu-id="784bc-121">下一级别包含每个邮件服务的各个部分, 其中包含邮件服务的 DLL 文件名和其配置入口点函数的名称等信息。</span><span class="sxs-lookup"><span data-stu-id="784bc-121">The next level has sections for each message service, with information such as the DLL file name of the message service and the name of its configuration entry point function.</span></span> <span data-ttu-id="784bc-122">第三个级别包含邮件服务中每个服务提供程序的配置数据的节。</span><span class="sxs-lookup"><span data-stu-id="784bc-122">The third level has sections with configuration data for each service provider in the message service.</span></span> 
  
<span data-ttu-id="784bc-123">若要处理配置, 邮件服务将实现符合 MAPI 定义的原型的入口点函数, 以及称为属性表的选项卡式对话框。</span><span class="sxs-lookup"><span data-stu-id="784bc-123">To handle configuration, a message service implements an entry point function that complies with a prototype defined by MAPI, and a tabbed dialog box known as a property sheet.</span></span> <span data-ttu-id="784bc-124">MAPI 调用入口点函数, 以服务于与配置文件管理和邮件服务中的服务提供程序管理相关的客户端请求。</span><span class="sxs-lookup"><span data-stu-id="784bc-124">MAPI calls the entry point function to service client requests that relate to profile management and the management of service providers in the message service.</span></span> <span data-ttu-id="784bc-125">属性表用于查看和更改邮件服务和服务提供程序配置属性。</span><span class="sxs-lookup"><span data-stu-id="784bc-125">Property sheets are used for viewing and changing message service and service provider configuration properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="784bc-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="784bc-126">See also</span></span>

- [<span data-ttu-id="784bc-127">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="784bc-127">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

