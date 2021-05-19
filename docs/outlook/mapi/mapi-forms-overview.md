---
title: MAPI 表单概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1b3afeaa-4ede-41eb-a3c1-b8947a46ef97
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4e7d48f6f6a47ce28aa0e1291ccef209b998c18e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432518"
---
# <a name="mapi-forms-overview"></a><span data-ttu-id="bfe6a-103">MAPI 表单概述</span><span class="sxs-lookup"><span data-stu-id="bfe6a-103">MAPI forms overview</span></span>
  
<span data-ttu-id="bfe6a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bfe6a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bfe6a-105">MAPI 窗体是邮件的查看器。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-105">A MAPI form is a viewer for a message.</span></span> <span data-ttu-id="bfe6a-106">每封邮件都有一个消息类，用于指示用作其查看器的特定窗体。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-106">Every message has a message class that dictates the particular form that is used as its viewer.</span></span> <span data-ttu-id="bfe6a-107">MAPI 定义多个邮件类，并且已实现用于查看这些类的消息的表单。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-107">MAPI defines several message classes and has implemented the forms for viewing messages of these classes.</span></span> <span data-ttu-id="bfe6a-108">客户端软件开发人员可以创建新的邮件类和自定义窗体，以便查看使用新类创建的消息。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-108">Client software developers can create new message classes and custom forms for viewing messages created by using the new classes.</span></span>
  
<span data-ttu-id="bfe6a-109">每个自定义窗体都实现一组标准菜单命令，如 **"** 打开"、**创建**、删除和答复，以及一组特定于特定窗体的命令。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-109">Every custom form implements a set of standard menu commands, such as **Open**, **Create**, **Delete**, and **Reply**, and a set of commands that are specific to the particular form.</span></span> <span data-ttu-id="bfe6a-110">当表单处于活动状态时，某些表单命令会与客户端应用程序的用户界面集成;其他表单命令完全替换客户端命令。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-110">Some of the form commands are integrated with the user interface of the client application when the form is active; other form commands completely replace the client commands.</span></span> 
  
<span data-ttu-id="bfe6a-111">下图显示了使用表单所涉及的 MAPI 组件之间的关系。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-111">The following illustration shows the relationship between the MAPI components involved in using forms.</span></span> 
  
<span data-ttu-id="bfe6a-112">**MAPI 表单体系结构**</span><span class="sxs-lookup"><span data-stu-id="bfe6a-112">**MAPI form architecture**</span></span>
  
<span data-ttu-id="bfe6a-113">![MAPI 表单体系结构](media/forms01.gif "MAPI 表单体系结构")</span><span class="sxs-lookup"><span data-stu-id="bfe6a-113">![MAPI form architecture](media/forms01.gif "MAPI form architecture")</span></span>
  
<span data-ttu-id="bfe6a-114">在图中，请注意，表单管理器扮演的角色与其他 MAPI 服务提供程序相似，尽管它本身不是服务提供商。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-114">In the diagram, notice that the form manager plays a role that is similar to other MAPI service providers, although it is not a service provider itself.</span></span> <span data-ttu-id="bfe6a-115">表单管理器是一个可替换的 DLL，它实现了一些 MAPI 接口。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-115">The form manager is a replaceable DLL that implements some of the MAPI interfaces.</span></span> <span data-ttu-id="bfe6a-116">尽管开发人员可以实施自己的表单管理器，但由于表单管理器的复杂性，大多数环境都将使用 Microsoft 提供的表单管理器。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-116">Although developers can implement their own form manager, most environments will use the form manager provided by Microsoft due to the form manager's complexity.</span></span>
  
<span data-ttu-id="bfe6a-117">以下列表描述了图表中的组件及其与其他组件的关系：</span><span class="sxs-lookup"><span data-stu-id="bfe6a-117">The following list describes the components in the diagram and their relationship to other components:</span></span>
  
- <span data-ttu-id="bfe6a-118">邮件客户端：可以使用表单对象的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-118">Messaging client: An application that can use form objects.</span></span> <span data-ttu-id="bfe6a-119">邮件客户端使用 MAPI 表单接口与表单管理器进行通信，以将邮件加载到表单对象中。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-119">The messaging client uses the MAPI form interfaces to communicate with the form manager to load messages into form objects.</span></span>
    
- <span data-ttu-id="bfe6a-120">MAPI 表单接口：MAPI 组件之间与表单相关的通信的定义标准。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-120">MAPI form interfaces: A defined standard for communication between MAPI components that are related to forms.</span></span>
    
- <span data-ttu-id="bfe6a-121">表单管理器：邮件客户端用于处理表单库中表单的安装、表单服务器的加载以及邮件客户端和表单服务器之间的初始通信的 DLL。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-121">Form manager: The DLL that messaging clients use to handle installation of forms in form libraries, loading of form servers, and initial communication between messaging clients and form servers.</span></span>
    
- <span data-ttu-id="bfe6a-122">表单库：与表单服务器关联的可执行文件的永久存储。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-122">Form libraries: Permanent storage for the executable files associated with form servers.</span></span>
    
- <span data-ttu-id="bfe6a-123">表单服务器：实现表单的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-123">Form servers: Executable files that implement a form.</span></span> <span data-ttu-id="bfe6a-124">表单服务器创建表单对象和用户界面来处理特定消息。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-124">Form servers create form objects and user interfaces to deal with specific messages.</span></span> <span data-ttu-id="bfe6a-125">此可执行文件也是 OLE 服务器，并且遵循常用的 OLE 约定。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-125">This executable is also an OLE server and adheres to the usual OLE conventions.</span></span>
    
- <span data-ttu-id="bfe6a-126">Form 对象：由与特定邮件对应的表单服务器创建的运行时对象。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-126">Form objects: Run-time objects created by form servers that correspond to specific messages.</span></span> <span data-ttu-id="bfe6a-127">Form 对象与表单服务器在同一进程上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-127">Form objects run in the same process context as their form server.</span></span>
    
<span data-ttu-id="bfe6a-128">有关 MAPI 表单组件详细信息，请参阅 [MAPI Forms](mapi-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe6a-128">For more information about MAPI form components, see [MAPI Forms](mapi-forms.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bfe6a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bfe6a-129">See also</span></span>

- [<span data-ttu-id="bfe6a-130">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="bfe6a-130">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

