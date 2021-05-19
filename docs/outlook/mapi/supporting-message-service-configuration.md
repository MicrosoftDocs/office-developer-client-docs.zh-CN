---
title: 支持邮件服务配置
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: bb6ab537-2876-474b-be7a-84734ace2bae
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: aa1a433e90eda24f1199783bc604e047deb03ecd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418993"
---
# <a name="supporting-message-service-configuration"></a><span data-ttu-id="14a96-103">支持邮件服务配置</span><span class="sxs-lookup"><span data-stu-id="14a96-103">Supporting message service configuration</span></span>
  
<span data-ttu-id="14a96-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="14a96-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="14a96-105">若要支持邮件服务配置，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="14a96-105">To support message service configuration, use the following procedure:</span></span>
  
1. <span data-ttu-id="14a96-106">实现符合 [MSGSERVICEENTRY](msgserviceentry.md) 原型的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="14a96-106">Implement an entry point function that conforms to the [MSGSERVICEENTRY](msgserviceentry.md) prototype.</span></span> <span data-ttu-id="14a96-107">邮件服务入口点函数管理对配置数据的访问，在下列情况下调用：</span><span class="sxs-lookup"><span data-stu-id="14a96-107">Message service entry point functions manage access to configuration data and are called in the following circumstances:</span></span> 
    
   - <span data-ttu-id="14a96-108">客户端登录以检索信息以配置邮件服务时。</span><span class="sxs-lookup"><span data-stu-id="14a96-108">When a client logs on to retrieve information to configure your message service.</span></span>
    
   - <span data-ttu-id="14a96-109">客户端想要查看或更改配置属性时。</span><span class="sxs-lookup"><span data-stu-id="14a96-109">When a client wants to view or change a configuration property.</span></span> 
    
   <span data-ttu-id="14a96-110">虽然大多数邮件服务将提供入口点功能，但并非严格要求它们。</span><span class="sxs-lookup"><span data-stu-id="14a96-110">Although most message services will provide entry point functions, as they should, these functions are not strictly required.</span></span> <span data-ttu-id="14a96-111">邮件服务可以通过其他方式提供对配置数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="14a96-111">Message services can provide access to configuration data in other ways.</span></span> <span data-ttu-id="14a96-112">但是，使用入口点函数可以标准化并简化配置过程。</span><span class="sxs-lookup"><span data-stu-id="14a96-112">However, using an entry point function standardizes and simplifies the process of configuration.</span></span>
    
   <span data-ttu-id="14a96-113">MAPI 期望所有邮件服务入口点功能能够存储和检索与其邮件服务关联的配置文件节中的属性。</span><span class="sxs-lookup"><span data-stu-id="14a96-113">MAPI expects all message service entry point functions to be able to store and retrieve properties from the profile sections that are associated with their message service.</span></span> <span data-ttu-id="14a96-114">你可以以交互方式、以编程方式或以交互方式和以编程方式支持此功能。</span><span class="sxs-lookup"><span data-stu-id="14a96-114">You can support this functionality interactively, programmatically, or both interactively and programmatically.</span></span>
    
   <span data-ttu-id="14a96-115">若要支持交互式配置，属性表显示配置邮件服务所涉及的属性。</span><span class="sxs-lookup"><span data-stu-id="14a96-115">To support interactive configuration, provide a property sheet that displays the properties involved in configuring your message service.</span></span> <span data-ttu-id="14a96-116">作为一个选项，您还可以提供每个可配置提供程序的属性表。</span><span class="sxs-lookup"><span data-stu-id="14a96-116">As an option, you can also supply property sheets for each configurable provider.</span></span> <span data-ttu-id="14a96-117">某些邮件服务将用户限制为配置属性的只读视图;其他邮件服务允许用户进行更改。</span><span class="sxs-lookup"><span data-stu-id="14a96-117">Some message services restrict users to a read-only view of configuration properties; other message services allow users to make changes.</span></span>
    
   <span data-ttu-id="14a96-118">若要支持编程配置，邮件服务入口点函数必须能够在用户干预的情况下工作。</span><span class="sxs-lookup"><span data-stu-id="14a96-118">To support programmatic configuration, your message service entry point function must be able to work without user intervention.</span></span> <span data-ttu-id="14a96-119">如果邮件服务可以通过配置文件向导调用，则必须支持编程配置。</span><span class="sxs-lookup"><span data-stu-id="14a96-119">If your message service can be called by the Profile Wizard, you must support programmatic configuration.</span></span> <span data-ttu-id="14a96-120">如果邮件服务不允许使用配置文件向导配置自身，您可以选择是否支持编程配置。</span><span class="sxs-lookup"><span data-stu-id="14a96-120">If your message service does not allow itself to be configured by using the Profile Wizard, you can choose whether or not to support programmatic configuration.</span></span>
    
   <span data-ttu-id="14a96-121">若要详细了解如何支持邮件服务入口点函数中的配置，请参阅[MSGSERVICEENTRY。](msgserviceentry.md)</span><span class="sxs-lookup"><span data-stu-id="14a96-121">For more information about how to support configuration in a message service entry point function, see [MSGSERVICEENTRY](msgserviceentry.md).</span></span>
    
2. <span data-ttu-id="14a96-122">在邮件服务部分包含以下条目，以在 Mapisvc.inf 配置文件中发布邮件服务入口点函数的名称：</span><span class="sxs-lookup"><span data-stu-id="14a96-122">Publish the name of your message service entry point function in the Mapisvc.inf configuration file by including the following entry in the message service section:</span></span>
    
   `PR_SERVICE_ENTRY_NAME=<name of message service>`
    
3. <span data-ttu-id="14a96-123">创建一个或多个属性表用于显示配置数据的对话框。</span><span class="sxs-lookup"><span data-stu-id="14a96-123">Create one or more property sheet dialog boxes for displaying configuration data.</span></span>
    
4. <span data-ttu-id="14a96-124">如果要允许配置文件向导配置邮件服务，请执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="14a96-124">Perform the following tasks if you want to allow the Profile Wizard to configure your message service:</span></span>
    
   - <span data-ttu-id="14a96-125">实现符合 [WIZARDENTRY](wizardentry.md) 原型的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="14a96-125">Implement an entry point function that conforms to the [WIZARDENTRY](wizardentry.md) prototype.</span></span> 
    
   - <span data-ttu-id="14a96-126">实现一个Windows [SERVICEWIZARDDLGPROC](servicewizarddlgproc.md)原型的标准对话框过程。</span><span class="sxs-lookup"><span data-stu-id="14a96-126">Implement a standard Windows dialog box procedure that conforms to the [SERVICEWIZARDDLGPROC](servicewizarddlgproc.md) prototype.</span></span> 
    
   - <span data-ttu-id="14a96-127">增强邮件服务入口点功能以响应其他事件。</span><span class="sxs-lookup"><span data-stu-id="14a96-127">Enhance your message service entry point function to respond to additional events.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="14a96-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14a96-128">See also</span></span>

- [<span data-ttu-id="14a96-129">邮件服务实现</span><span class="sxs-lookup"><span data-stu-id="14a96-129">Message Service Implementation</span></span>](message-service-implementation.md)

