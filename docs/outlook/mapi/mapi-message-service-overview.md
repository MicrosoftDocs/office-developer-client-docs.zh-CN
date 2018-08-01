---
title: MAPI 邮件服务概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 58f36a6b-bcc5-4ebb-9761-6f420a718d97
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fc444725aae20e7321fa287a90cf7d3e13b7ffb4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776256"
---
# <a name="mapi-message-service-overview"></a><span data-ttu-id="3cfc4-103">MAPI 邮件服务概述</span><span class="sxs-lookup"><span data-stu-id="3cfc4-103">MAPI message service overview</span></span>
  
<span data-ttu-id="3cfc4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3cfc4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3cfc4-105">消息服务定义一组相关的服务提供程序，通常使用相同的消息系统的服务提供。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-105">A message service defines a group of related service providers, typically service providers that work with the same messaging system.</span></span> <span data-ttu-id="3cfc4-106">服务提供程序执行的消息系统和 MAPI 子系统之间进行通信工作，而消息服务执行工作的用户和使用常见的邮件系统的服务提供商之间的交互。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-106">Whereas service providers perform the work of communicating between messaging systems and the MAPI subsystem, message services perform the work of interfacing between the user and service providers that work with a common messaging system.</span></span>  
  
<span data-ttu-id="3cfc4-107">消息服务面临着用户更轻松地进行安装和配置服务提供商。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-107">Message services exist to make the installation and configuration of service providers easier for users.</span></span> <span data-ttu-id="3cfc4-108">用户从不直接安装或配置服务提供程序;邮件服务完全处理的安装和配置每个属于该服务的服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-108">Users never directly install or configure a service provider; the message service completely handles the installation and configuration of each of the service providers that belong to the service.</span></span> <span data-ttu-id="3cfc4-109">由于此功能，用户不需要了解与特定服务提供程序配置要求。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-109">Because of this feature, users do not need to be familiar with specific service provider configuration requirements.</span></span> 
  
<span data-ttu-id="3cfc4-110">下图显示了基于消息的客户端应用程序和两个邮件服务之间的关系。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-110">The following figure shows the relationship between a messaging-based client application and two message services.</span></span>
  
<span data-ttu-id="3cfc4-111">**消息服务安装和配置**</span><span class="sxs-lookup"><span data-stu-id="3cfc4-111">**Message service installation and configuration**</span></span>
  
<span data-ttu-id="3cfc4-112">![消息服务安装和配置](media/amapi_44.gif "消息服务安装和配置")</span><span class="sxs-lookup"><span data-stu-id="3cfc4-112">![Message service installation and configuration](media/amapi_44.gif "Message service installation and configuration")</span></span>
  
<span data-ttu-id="3cfc4-113">用户调用每个邮件服务，将服务和其服务提供程序添加到一个配置文件的安装代码。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-113">The user invokes the installation code of each message service to add the service and its service providers to a profile.</span></span> <span data-ttu-id="3cfc4-114">在图中显示的消息服务之一，有三种服务提供商;在其他邮件服务，有两个服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-114">In one of the message services shown in the figure, there are three service providers; in the other message service, there are two service providers.</span></span> <span data-ttu-id="3cfc4-115">以后安装完成后，通常在登录时，每个邮件服务中的服务提供程序配置。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-115">At some later time after installation is complete, typically at logon time, the service providers in each message service are configured.</span></span> <span data-ttu-id="3cfc4-116">每个邮件服务中的配置代码处理服务中的提供程序的配置。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-116">The configuration code in each message service handles the configuration of the providers in the service.</span></span>
  
<span data-ttu-id="3cfc4-117">安装的消息服务后，及其安装程序将将必要的文件从安装源复制到用户的本地磁盘，并更新配置文件，Mapisvc.inf。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-117">When a message service is installed, its installation program copies necessary files from the installation source to the user's local disk and updates a configuration file, Mapisvc.inf.</span></span> <span data-ttu-id="3cfc4-118">Mapisvc.inf 文件包含所有消息服务和可以安装在计算机的服务提供商的配置的设置。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-118">The Mapisvc.inf file contains configuration settings for all of the message services and service providers that can be installed on the computer.</span></span> <span data-ttu-id="3cfc4-119">它被组织在分层节，并在每个级别的每个部分之间的链接。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-119">It is organized in hierarchical sections, with links between each section at each level.</span></span> <span data-ttu-id="3cfc4-120">最高级别部分包含 MAPI 子系统，列表的所有可用的邮件服务，如和联机帮助安装相关的信息。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-120">The section at the top level contains information that is relevant for the MAPI subsystem, such as a list of all available message services, and for the online Help installation.</span></span> <span data-ttu-id="3cfc4-121">下一个级别包括为每个邮件服务，例如 DLL 文件名称的消息服务和其配置入口点函数的名称的信息的部分。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-121">The next level has sections for each message service, with information such as the DLL file name of the message service and the name of its configuration entry point function.</span></span> <span data-ttu-id="3cfc4-122">第三级消息服务中的每个服务提供商有若干节进行配置数据。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-122">The third level has sections with configuration data for each service provider in the message service.</span></span> 
  
<span data-ttu-id="3cfc4-123">若要处理配置，消息服务实现符合由 MAPI 和称为属性表选项卡式的对话框中定义的原型入口点函数。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-123">To handle configuration, a message service implements an entry point function that complies with a prototype defined by MAPI, and a tabbed dialog box known as a property sheet.</span></span> <span data-ttu-id="3cfc4-124">MAPI 调用入口点函数与配置文件管理和管理邮件服务服务提供商的服务客户端请求。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-124">MAPI calls the entry point function to service client requests that relate to profile management and the management of service providers in the message service.</span></span> <span data-ttu-id="3cfc4-125">属性表用于查看和更改消息服务和服务提供程序配置属性。</span><span class="sxs-lookup"><span data-stu-id="3cfc4-125">Property sheets are used for viewing and changing message service and service provider configuration properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3cfc4-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cfc4-126">See also</span></span>

- [<span data-ttu-id="3cfc4-127">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="3cfc4-127">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

