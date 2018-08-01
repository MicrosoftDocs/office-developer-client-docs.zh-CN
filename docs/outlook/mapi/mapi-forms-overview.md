---
title: MAPI 表单概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1b3afeaa-4ede-41eb-a3c1-b8947a46ef97
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 91bc0641723a92d8dc86bf3d1037d8e9936930ce
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776247"
---
# <a name="mapi-forms-overview"></a><span data-ttu-id="4ee01-103">MAPI 表单概述</span><span class="sxs-lookup"><span data-stu-id="4ee01-103">MAPI forms overview</span></span>
  
<span data-ttu-id="4ee01-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4ee01-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4ee01-105">MAPI 表单是邮件查看器。</span><span class="sxs-lookup"><span data-stu-id="4ee01-105">A MAPI form is a viewer for a message.</span></span> <span data-ttu-id="4ee01-106">每个邮件有规定用作其查看器的特定窗体的邮件类。</span><span class="sxs-lookup"><span data-stu-id="4ee01-106">Every message has a message class that dictates the particular form that is used as its viewer.</span></span> <span data-ttu-id="4ee01-107">MAPI 定义多个邮件类，并已实现查看这些类的邮件的表单。</span><span class="sxs-lookup"><span data-stu-id="4ee01-107">MAPI defines several message classes and has implemented the forms for viewing messages of these classes.</span></span> <span data-ttu-id="4ee01-108">客户端软件开发人员可以创建新的邮件类和查看邮件使用的新类创建的自定义表单。</span><span class="sxs-lookup"><span data-stu-id="4ee01-108">Client software developers can create new message classes and custom forms for viewing messages created by using the new classes.</span></span>
  
<span data-ttu-id="4ee01-109">每个自定义窗体实现一组标准菜单命令，如**打开**、**创建**、**删除**和**答复**和一组特定于特定的窗体的命令。</span><span class="sxs-lookup"><span data-stu-id="4ee01-109">Every custom form implements a set of standard menu commands, such as **Open**, **Create**, **Delete**, and **Reply**, and a set of commands that are specific to the particular form.</span></span> <span data-ttu-id="4ee01-110">窗体命令的一些集成在一起的客户端应用程序的用户界面窗体处于活动状态; 时其他窗体命令完全替换客户端命令。</span><span class="sxs-lookup"><span data-stu-id="4ee01-110">Some of the form commands are integrated with the user interface of the client application when the form is active; other form commands completely replace the client commands.</span></span> 
  
<span data-ttu-id="4ee01-111">下图显示了使用窗体所涉及的 MAPI 组件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="4ee01-111">The following illustration shows the relationship between the MAPI components involved in using forms.</span></span> 
  
<span data-ttu-id="4ee01-112">**MAPI 表单体系结构**</span><span class="sxs-lookup"><span data-stu-id="4ee01-112">**MAPI form architecture**</span></span>
  
<span data-ttu-id="4ee01-113">![MAPI 表单体系结构](media/forms01.gif "MAPI 表单体系结构")</span><span class="sxs-lookup"><span data-stu-id="4ee01-113">![MAPI form architecture](media/forms01.gif "MAPI form architecture")</span></span>
  
<span data-ttu-id="4ee01-114">在图表中，请注意窗体管理器播放尽管这不是本身的服务提供商类似于其他 MAPI 服务提供商的角色。</span><span class="sxs-lookup"><span data-stu-id="4ee01-114">In the diagram, notice that the form manager plays a role that is similar to other MAPI service providers, although it is not a service provider itself.</span></span> <span data-ttu-id="4ee01-115">窗体管理器是实现一些 MAPI 接口可替换 DLL。</span><span class="sxs-lookup"><span data-stu-id="4ee01-115">The form manager is a replaceable DLL that implements some of the MAPI interfaces.</span></span> <span data-ttu-id="4ee01-116">开发人员可以实现自己的窗体管理器，尽管大多数环境中将使用由 Microsoft 提供的由于窗体管理器的复杂性的窗体管理器。</span><span class="sxs-lookup"><span data-stu-id="4ee01-116">Although developers can implement their own form manager, most environments will use the form manager provided by Microsoft due to the form manager's complexity.</span></span>
  
<span data-ttu-id="4ee01-117">以下列表描述中图表及其关系，以及其他组件的组件：</span><span class="sxs-lookup"><span data-stu-id="4ee01-117">The following list describes the components in the diagram and their relationship to other components:</span></span>
  
- <span data-ttu-id="4ee01-118">消息客户端： 的应用程序可以使用窗体对象。</span><span class="sxs-lookup"><span data-stu-id="4ee01-118">Messaging client: An application that can use form objects.</span></span> <span data-ttu-id="4ee01-119">消息客户端使用的 MAPI 表单接口与窗体管理器加载到表单对象的消息进行通信。</span><span class="sxs-lookup"><span data-stu-id="4ee01-119">The messaging client uses the MAPI form interfaces to communicate with the form manager to load messages into form objects.</span></span>
    
- <span data-ttu-id="4ee01-120">MAPI 表单接口： 与窗体相关的 MAPI 组件之间的通信已定义的标准。</span><span class="sxs-lookup"><span data-stu-id="4ee01-120">MAPI form interfaces: A defined standard for communication between MAPI components that are related to forms.</span></span>
    
- <span data-ttu-id="4ee01-121">窗体管理器： 用于处理安装的表单库中的窗体、 窗体服务器和消息客户端与窗体服务器之间的初始通信的加载消息客户端的 DLL。</span><span class="sxs-lookup"><span data-stu-id="4ee01-121">Form manager: The DLL that messaging clients use to handle installation of forms in form libraries, loading of form servers, and initial communication between messaging clients and form servers.</span></span>
    
- <span data-ttu-id="4ee01-122">表单库： 永久存储与窗体服务器关联的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="4ee01-122">Form libraries: Permanent storage for the executable files associated with form servers.</span></span>
    
- <span data-ttu-id="4ee01-123">表单服务器： 实现的窗体的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="4ee01-123">Form servers: Executable files that implement a form.</span></span> <span data-ttu-id="4ee01-124">窗体服务器创建窗体对象和处理特定邮件的用户界面。</span><span class="sxs-lookup"><span data-stu-id="4ee01-124">Form servers create form objects and user interfaces to deal with specific messages.</span></span> <span data-ttu-id="4ee01-125">此可执行文件也是 OLE 服务器，并且符合您的常用 OLE 约定。</span><span class="sxs-lookup"><span data-stu-id="4ee01-125">This executable is also an OLE server and adheres to the usual OLE conventions.</span></span>
    
- <span data-ttu-id="4ee01-126">窗体对象： 创建窗体服务器对应于特定邮件的运行时对象。</span><span class="sxs-lookup"><span data-stu-id="4ee01-126">Form objects: Run-time objects created by form servers that correspond to specific messages.</span></span> <span data-ttu-id="4ee01-127">作为其窗体服务器的相同过程上下文中运行窗体对象。</span><span class="sxs-lookup"><span data-stu-id="4ee01-127">Form objects run in the same process context as their form server.</span></span>
    
<span data-ttu-id="4ee01-128">有关 MAPI 表单组件的详细信息，请参阅[MAPI Forms](mapi-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="4ee01-128">For more information about MAPI form components, see [MAPI Forms](mapi-forms.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4ee01-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ee01-129">See also</span></span>

- [<span data-ttu-id="4ee01-130">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="4ee01-130">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

