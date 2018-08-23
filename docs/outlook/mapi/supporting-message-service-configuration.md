---
title: 支持的消息服务配置
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bb6ab537-2876-474b-be7a-84734ace2bae
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6f9ac5d9cef09ce6d4f3006ecc804db6291cae77
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579338"
---
# <a name="supporting-message-service-configuration"></a><span data-ttu-id="8322b-103">支持的消息服务配置</span><span class="sxs-lookup"><span data-stu-id="8322b-103">Supporting message service configuration</span></span>
  
<span data-ttu-id="8322b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8322b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8322b-105">若要支持消息服务配置，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="8322b-105">To support message service configuration, use the following procedure:</span></span>
  
1. <span data-ttu-id="8322b-106">实现符合[MSGSERVICEENTRY](msgserviceentry.md)原型入口点函数。</span><span class="sxs-lookup"><span data-stu-id="8322b-106">Implement an entry point function that conforms to the [MSGSERVICEENTRY](msgserviceentry.md) prototype.</span></span> <span data-ttu-id="8322b-107">消息服务入口点函数管理访问配置数据，并在以下情况下调用：</span><span class="sxs-lookup"><span data-stu-id="8322b-107">Message service entry point functions manage access to configuration data and are called in the following circumstances:</span></span> 
    
   - <span data-ttu-id="8322b-108">当客户端登录时检索配置消息服务的信息。</span><span class="sxs-lookup"><span data-stu-id="8322b-108">When a client logs on to retrieve information to configure your message service.</span></span>
    
   - <span data-ttu-id="8322b-109">当客户端要查看或更改的配置属性。</span><span class="sxs-lookup"><span data-stu-id="8322b-109">When a client wants to view or change a configuration property.</span></span> 
    
   <span data-ttu-id="8322b-110">尽管大多数消息服务将提供入口点函数，如它们应，这些函数不严格需要。</span><span class="sxs-lookup"><span data-stu-id="8322b-110">Although most message services will provide entry point functions, as they should, these functions are not strictly required.</span></span> <span data-ttu-id="8322b-111">消息服务可提供对其他方式配置数据访问。</span><span class="sxs-lookup"><span data-stu-id="8322b-111">Message services can provide access to configuration data in other ways.</span></span> <span data-ttu-id="8322b-112">但是，使用入口点函数标准化和简化的配置过程。</span><span class="sxs-lookup"><span data-stu-id="8322b-112">However, using an entry point function standardizes and simplifies the process of configuration.</span></span>
    
   <span data-ttu-id="8322b-113">MAPI 要求所有邮件服务入口点函数能够从存储和检索属性与其消息服务关联的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="8322b-113">MAPI expects all message service entry point functions to be able to store and retrieve properties from the profile sections that are associated with their message service.</span></span> <span data-ttu-id="8322b-114">您可以支持此功能，以交互方式，以编程方式或两个以交互方式以及通过编程方式。</span><span class="sxs-lookup"><span data-stu-id="8322b-114">You can support this functionality interactively, programmatically, or both interactively and programmatically.</span></span>
    
   <span data-ttu-id="8322b-115">若要支持交互式配置，提供显示配置您的消息服务所涉及的属性的属性表。</span><span class="sxs-lookup"><span data-stu-id="8322b-115">To support interactive configuration, provide a property sheet that displays the properties involved in configuring your message service.</span></span> <span data-ttu-id="8322b-116">作为一个选项，还可以为每个可配置提供程序提供属性表。</span><span class="sxs-lookup"><span data-stu-id="8322b-116">As an option, you can also supply property sheets for each configurable provider.</span></span> <span data-ttu-id="8322b-117">某些消息服务将用户限制为只读的视图的配置属性;其他消息服务允许用户进行更改。</span><span class="sxs-lookup"><span data-stu-id="8322b-117">Some message services restrict users to a read-only view of configuration properties; other message services allow users to make changes.</span></span>
    
   <span data-ttu-id="8322b-118">若要支持编程配置，您消息服务入口点函数必须能够无需用户干预工作。</span><span class="sxs-lookup"><span data-stu-id="8322b-118">To support programmatic configuration, your message service entry point function must be able to work without user intervention.</span></span> <span data-ttu-id="8322b-119">如果您的消息服务可由配置文件向导，您必须支持编程配置。</span><span class="sxs-lookup"><span data-stu-id="8322b-119">If your message service can be called by the Profile Wizard, you must support programmatic configuration.</span></span> <span data-ttu-id="8322b-120">如果您的消息服务不允许自身来使用配置文件向导进行配置，则可以选择支持编程配置。</span><span class="sxs-lookup"><span data-stu-id="8322b-120">If your message service does not allow itself to be configured by using the Profile Wizard, you can choose whether or not to support programmatic configuration.</span></span>
    
   <span data-ttu-id="8322b-121">有关如何在消息服务项中支持配置的详细信息指向函数，请参阅[MSGSERVICEENTRY](msgserviceentry.md)。</span><span class="sxs-lookup"><span data-stu-id="8322b-121">For more information about how to support configuration in a message service entry point function, see [MSGSERVICEENTRY](msgserviceentry.md).</span></span>
    
2. <span data-ttu-id="8322b-122">Mapisvc.inf 配置文件中发布您的消息服务入口点函数的名称，通过在邮件服务部分中包含以下条目：</span><span class="sxs-lookup"><span data-stu-id="8322b-122">Publish the name of your message service entry point function in the Mapisvc.inf configuration file by including the following entry in the message service section:</span></span>
    
   `PR_SERVICE_ENTRY_NAME=<name of message service>`
    
3. <span data-ttu-id="8322b-123">创建一个或多个属性表对话框显示的配置数据。</span><span class="sxs-lookup"><span data-stu-id="8322b-123">Create one or more property sheet dialog boxes for displaying configuration data.</span></span>
    
4. <span data-ttu-id="8322b-124">如果您想要让配置文件向导以配置邮件服务，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="8322b-124">Perform the following tasks if you want to allow the Profile Wizard to configure your message service:</span></span>
    
   - <span data-ttu-id="8322b-125">实现符合[WIZARDENTRY](wizardentry.md)原型入口点函数。</span><span class="sxs-lookup"><span data-stu-id="8322b-125">Implement an entry point function that conforms to the [WIZARDENTRY](wizardentry.md) prototype.</span></span> 
    
   - <span data-ttu-id="8322b-126">实现[SERVICEWIZARDDLGPROC](servicewizarddlgproc.md)原型符合标准的 Windows 对话框框过程。</span><span class="sxs-lookup"><span data-stu-id="8322b-126">Implement a standard Windows dialog box procedure that conforms to the [SERVICEWIZARDDLGPROC](servicewizarddlgproc.md) prototype.</span></span> 
    
   - <span data-ttu-id="8322b-127">增强对其他事件作出响应您消息服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="8322b-127">Enhance your message service entry point function to respond to additional events.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8322b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8322b-128">See also</span></span>

- [<span data-ttu-id="8322b-129">邮件服务实现</span><span class="sxs-lookup"><span data-stu-id="8322b-129">Message Service Implementation</span></span>](message-service-implementation.md)

