---
title: 支持邮件服务安装
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 822e07bc-0bca-4485-8938-2264315161e2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 328884e8758e679eb1c9d968547cba02c01d4d47
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404699"
---
# <a name="supporting-message-service-installation"></a><span data-ttu-id="4bfa3-103">支持邮件服务安装</span><span class="sxs-lookup"><span data-stu-id="4bfa3-103">Supporting Message Service Installation</span></span>

  
  
<span data-ttu-id="4bfa3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4bfa3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4bfa3-105">用于安装邮件服务的安装程序应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4bfa3-105">The setup program for installing your message service should do the following:</span></span>
  
1. <span data-ttu-id="4bfa3-106">将邮件服务文件（如邮件服务和服务提供程序 DLL）从 CD 或磁盘复制到工作站上的本地驱动器。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-106">Copy message service files, such as the message service and service provider DLLs, from a CD or disk, to a local drive on the workstation.</span></span> <span data-ttu-id="4bfa3-107">需要复制的文件取决于您的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-107">The files that need to be copied depend on your message service.</span></span> <span data-ttu-id="4bfa3-108">通常，你将复制至少一个 DLL。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-108">Typically you will copy at least one DLL.</span></span>
    
2. <span data-ttu-id="4bfa3-109">将条目添加到 Mapisvc.inf 配置文件。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-109">Add entries to the Mapisvc.inf configuration file.</span></span> <span data-ttu-id="4bfa3-110">若要详细了解如何修改此文件以支持邮件服务中的服务提供程序，请参阅 File Format of [MapiSvc.inf](file-format-of-mapisvc-inf.md)。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-110">For more information about how to modify this file to support the service providers in your message service, see [File Format of MapiSvc.inf](file-format-of-mapisvc-inf.md).</span></span>
    
3. <span data-ttu-id="4bfa3-111">根据需要将条目添加到邮件服务的系统注册表中。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-111">Add entries, as appropriate, to the system registry for message services.</span></span> <span data-ttu-id="4bfa3-112">有关条目在系统注册表中的显示方式详细信息，请参阅 [安装 MAPI 子系统](installing-the-mapi-subsystem.md)。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-112">For more information about how the entries should appear in the system registry, see [Installing the MAPI Subsystem](installing-the-mapi-subsystem.md).</span></span>
    
4. <span data-ttu-id="4bfa3-113">如果尚不存在默认配置文件，则使用下列项目之一创建一个：</span><span class="sxs-lookup"><span data-stu-id="4bfa3-113">Create a default profile if one does not yet exist by using one of the following items:</span></span>
    
  - <span data-ttu-id="4bfa3-114">通过一系列对话框使用用户交互创建配置文件的配置文件向导。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-114">The Profile Wizard to create a profile by using user interaction through a series of dialog boxes.</span></span> <span data-ttu-id="4bfa3-115">有关使用配置文件向导的信息，请参阅使用配置文件向导 [创建配置文件](creating-a-profile-by-using-the-profile-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-115">For more information about using the Profile Wizard, see [Creating a Profile by Using the Profile Wizard](creating-a-profile-by-using-the-profile-wizard.md).</span></span>
    
  - <span data-ttu-id="4bfa3-116">使用用户交互创建配置文件的控制面板。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-116">The Control Panel to create a profile by using user interaction.</span></span> <span data-ttu-id="4bfa3-117">与配置文件向导一样，控制面板为用户配置邮件服务和设置配置文件属性提供了更大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-117">The Control Panel offers the user more flexibility than the Profile Wizard for configuring the message services and setting profile properties.</span></span> 
    
<span data-ttu-id="4bfa3-118">将安装程序放在指定的公用目录中。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-118">Place the setup program in a designated public directory.</span></span> <span data-ttu-id="4bfa3-119">这一点很重要，因为大多数配置客户端（如控制面板）都要求用户输入目录的名称。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-119">This is important because most configuration clients, such as the Control Panel, require that users enter the name of the directory.</span></span> <span data-ttu-id="4bfa3-120">当用户单击"添加"按钮时，控制面板将调用安装程序，调用"拥有磁盘"对话框，并指定程序的路径。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-120">The Control Panel invokes a setup program when a user clicks the **Add** button, invokes the **Have Disk** dialog box, and specifies the path to the program.</span></span> <span data-ttu-id="4bfa3-121">控制面板运行程序并调用邮件服务的入口点函数  _，ulContext_ 参数设置为 MSG_SERVICE_INSTALL。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-121">The Control Panel runs the program and calls your message service's entry point function with the  _ulContext_ parameter set to MSG_SERVICE_INSTALL.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="4bfa3-122">由于配置文件是 MAPI 体系结构的一部分，因此请确保你的安装程序不会在默认配置文件中存储任何难以重新创建的信息。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-122">Because profiles are an expendable part of the MAPI architecture, be sure that your installation program does not store anything in the default profile that would be difficult to recreate.</span></span> <span data-ttu-id="4bfa3-123">没有用于配置文件恢复、将配置文件从一台计算机移动到另一台计算机、进行外线备份或者从备份副本中执行单个或全局还原的实用工具。</span><span class="sxs-lookup"><span data-stu-id="4bfa3-123">There are no utilities for profile recovery, for moving profiles from one computer to another, for off-line backup, or for individual or global restoration from backup copies.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4bfa3-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4bfa3-124">See also</span></span>



[<span data-ttu-id="4bfa3-125">邮件服务实现</span><span class="sxs-lookup"><span data-stu-id="4bfa3-125">Message Service Implementation</span></span>](message-service-implementation.md)

