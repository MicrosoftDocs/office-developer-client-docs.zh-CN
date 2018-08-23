---
title: 支持邮件服务安装
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 822e07bc-0bca-4485-8938-2264315161e2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1f82741e3c44c589a18a1428fd68cebe6a501d5c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581991"
---
# <a name="supporting-message-service-installation"></a><span data-ttu-id="1aa27-103">支持邮件服务安装</span><span class="sxs-lookup"><span data-stu-id="1aa27-103">Supporting Message Service Installation</span></span>

  
  
<span data-ttu-id="1aa27-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1aa27-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1aa27-105">安装您的消息服务的安装程序应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1aa27-105">The setup program for installing your message service should do the following:</span></span>
  
1. <span data-ttu-id="1aa27-106">将邮件服务文件，如消息服务和服务提供商 Dll，从 CD 或磁盘，复制到本地驱动器工作站上。</span><span class="sxs-lookup"><span data-stu-id="1aa27-106">Copy message service files, such as the message service and service provider DLLs, from a CD or disk, to a local drive on the workstation.</span></span> <span data-ttu-id="1aa27-107">需要将复制的文件取决于您的消息服务。</span><span class="sxs-lookup"><span data-stu-id="1aa27-107">The files that need to be copied depend on your message service.</span></span> <span data-ttu-id="1aa27-108">通常将复制至少一个 DLL。</span><span class="sxs-lookup"><span data-stu-id="1aa27-108">Typically you will copy at least one DLL.</span></span>
    
2. <span data-ttu-id="1aa27-109">将项添加到 Mapisvc.inf 配置文件。</span><span class="sxs-lookup"><span data-stu-id="1aa27-109">Add entries to the Mapisvc.inf configuration file.</span></span> <span data-ttu-id="1aa27-110">有关如何修改此文件以在邮件服务中支持的服务提供程序的详细信息，请参阅[的 MapiSvc.inf 文件格式](file-format-of-mapisvc-inf.md)。</span><span class="sxs-lookup"><span data-stu-id="1aa27-110">For more information about how to modify this file to support the service providers in your message service, see [File Format of MapiSvc.inf](file-format-of-mapisvc-inf.md).</span></span>
    
3. <span data-ttu-id="1aa27-111">根据需要对系统注册表对邮件服务添加条目。</span><span class="sxs-lookup"><span data-stu-id="1aa27-111">Add entries, as appropriate, to the system registry for message services.</span></span> <span data-ttu-id="1aa27-112">有关条目应在系统注册表中的显示方式的详细信息，请参阅[安装 MAPI 子系统](installing-the-mapi-subsystem.md)。</span><span class="sxs-lookup"><span data-stu-id="1aa27-112">For more information about how the entries should appear in the system registry, see [Installing the MAPI Subsystem](installing-the-mapi-subsystem.md).</span></span>
    
4. <span data-ttu-id="1aa27-113">创建默认配置文件，如果一个尚不存在使用以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="1aa27-113">Create a default profile if one does not yet exist by using one of the following items:</span></span>
    
  - <span data-ttu-id="1aa27-114">要使用的对话框一系列用户交互创建一个配置文件的配置文件向导。</span><span class="sxs-lookup"><span data-stu-id="1aa27-114">The Profile Wizard to create a profile by using user interaction through a series of dialog boxes.</span></span> <span data-ttu-id="1aa27-115">有关使用配置文件向导的详细信息，请参阅[创建一个配置文件使用配置文件向导](creating-a-profile-by-using-the-profile-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="1aa27-115">For more information about using the Profile Wizard, see [Creating a Profile by Using the Profile Wizard](creating-a-profile-by-using-the-profile-wizard.md).</span></span>
    
  - <span data-ttu-id="1aa27-116">创建配置文件使用用户交互 Control Panel。</span><span class="sxs-lookup"><span data-stu-id="1aa27-116">The Control Panel to create a profile by using user interaction.</span></span> <span data-ttu-id="1aa27-117">控制面板中，向用户提供用于配置消息服务和设置配置文件属性配置文件向导比更大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="1aa27-117">The Control Panel offers the user more flexibility than the Profile Wizard for configuring the message services and setting profile properties.</span></span> 
    
<span data-ttu-id="1aa27-118">将指定的公共目录中安装程序。</span><span class="sxs-lookup"><span data-stu-id="1aa27-118">Place the setup program in a designated public directory.</span></span> <span data-ttu-id="1aa27-119">这是目录的重要，因为大多数配置客户端，如控制面板中，要求用户输入的名称。</span><span class="sxs-lookup"><span data-stu-id="1aa27-119">This is important because most configuration clients, such as the Control Panel, require that users enter the name of the directory.</span></span> <span data-ttu-id="1aa27-120">当用户单击**添加**按钮，调用**从磁盘**对话框中，并指定该程序的路径，则控制面板调用安装程序。</span><span class="sxs-lookup"><span data-stu-id="1aa27-120">The Control Panel invokes a setup program when a user clicks the **Add** button, invokes the **Have Disk** dialog box, and specifies the path to the program.</span></span> <span data-ttu-id="1aa27-121">控制面板运行程序，并调用_ulContext_参数设置为 MSG_SERVICE_INSTALL 消息服务的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="1aa27-121">The Control Panel runs the program and calls your message service's entry point function with the  _ulContext_ parameter set to MSG_SERVICE_INSTALL.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="1aa27-122">由于配置文件的 MAPI 体系结构可丢弃组成部分，确保您的安装程序不存储任何很难重新创建默认配置文件中。</span><span class="sxs-lookup"><span data-stu-id="1aa27-122">Because profiles are an expendable part of the MAPI architecture, be sure that your installation program does not store anything in the default profile that would be difficult to recreate.</span></span> <span data-ttu-id="1aa27-123">有配置文件恢复的、 用于将配置文件从一台计算机移到另一个、 脱机备份或个人或全局备份副本还原为未实用程序。</span><span class="sxs-lookup"><span data-stu-id="1aa27-123">There are no utilities for profile recovery, for moving profiles from one computer to another, for off-line backup, or for individual or global restoration from backup copies.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1aa27-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1aa27-124">See also</span></span>



[<span data-ttu-id="1aa27-125">邮件服务实现</span><span class="sxs-lookup"><span data-stu-id="1aa27-125">Message Service Implementation</span></span>](message-service-implementation.md)

