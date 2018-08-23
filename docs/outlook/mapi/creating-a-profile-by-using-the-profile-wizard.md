---
title: 使用配置文件向导创建配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4b611818-f99f-43a2-9f6b-1aa5b9564d1d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f30dca8323f74bc2817bab375b58fcc1bc15c18b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574256"
---
# <a name="creating-a-profile-by-using-the-profile-wizard"></a><span data-ttu-id="00332-103">使用配置文件向导创建配置文件</span><span class="sxs-lookup"><span data-stu-id="00332-103">Creating a Profile by Using the Profile Wizard</span></span>

  
  
<span data-ttu-id="00332-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="00332-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="00332-105">配置文件向导是 MAPI 功能，使用户能够创建配置文件中的最简单的可能方式。</span><span class="sxs-lookup"><span data-stu-id="00332-105">The Profile Wizard is a MAPI feature that enables a user to create a profile in the easiest possible way.</span></span> <span data-ttu-id="00332-106">配置文件向导显示对话框提示用户选择消息服务和输入的一些最重要的配置属性的值的一系列。</span><span class="sxs-lookup"><span data-stu-id="00332-106">The Profile Wizard displays a series of dialog boxes which prompt the user to select message services and enter values for a few of the most essential configuration properties.</span></span> <span data-ttu-id="00332-107">对于大多数其他必需的属性，该配置文件向导使用提供的默认值。</span><span class="sxs-lookup"><span data-stu-id="00332-107">For most of the other required properties, the Profile Wizard uses default values provided.</span></span> <span data-ttu-id="00332-108">若要调用配置文件向导，请调用**LaunchWizard**，基于[LAUNCHWIZARDENTRY](launchwizardentry.md)原型的函数。</span><span class="sxs-lookup"><span data-stu-id="00332-108">To invoke the Profile Wizard, call **LaunchWizard**, a function based on the [LAUNCHWIZARDENTRY](launchwizardentry.md) prototype.</span></span> 
  
<span data-ttu-id="00332-109">用户可以向支持配置文件向导的新配置文件添加这些消息服务和服务提供商。</span><span class="sxs-lookup"><span data-stu-id="00332-109">The user can add only those message services and service providers to the new profile that support the Profile Wizard.</span></span> <span data-ttu-id="00332-110">因为每个邮件服务可能需要多个属性不是配置文件向导可以处理进行设置，请注意，如果使用此方法，则可能为一个或多个选定的服务或提供商能够配置不完全。</span><span class="sxs-lookup"><span data-stu-id="00332-110">Because each message service might require more properties to be set than the Profile Wizard can handle, be aware that if you use this approach, it is possible for one or more of the selected services or providers to be incompletely configured.</span></span>
  

