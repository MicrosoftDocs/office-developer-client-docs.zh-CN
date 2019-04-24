---
title: 使用配置文件向导创建配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4b611818-f99f-43a2-9f6b-1aa5b9564d1d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a93cfb05d8abfffc9f55a7ea48efc3c3451dddbb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332933"
---
# <a name="creating-a-profile-by-using-the-profile-wizard"></a><span data-ttu-id="3003a-103">使用配置文件向导创建配置文件</span><span class="sxs-lookup"><span data-stu-id="3003a-103">Creating a Profile by Using the Profile Wizard</span></span>

  
  
<span data-ttu-id="3003a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3003a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3003a-105">配置文件向导是一项 MAPI 功能, 它使用户能够以尽可能最简单的方式创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="3003a-105">The Profile Wizard is a MAPI feature that enables a user to create a profile in the easiest possible way.</span></span> <span data-ttu-id="3003a-106">配置文件向导显示一系列对话框, 提示用户选择邮件服务并为几个最基本的配置属性输入值。</span><span class="sxs-lookup"><span data-stu-id="3003a-106">The Profile Wizard displays a series of dialog boxes which prompt the user to select message services and enter values for a few of the most essential configuration properties.</span></span> <span data-ttu-id="3003a-107">对于大多数其他必需的属性, 配置文件向导使用提供的默认值。</span><span class="sxs-lookup"><span data-stu-id="3003a-107">For most of the other required properties, the Profile Wizard uses default values provided.</span></span> <span data-ttu-id="3003a-108">若要调用配置文件向导, 请调用**LaunchWizard**, 它是基于[LAUNCHWIZARDENTRY](launchwizardentry.md)原型的函数。</span><span class="sxs-lookup"><span data-stu-id="3003a-108">To invoke the Profile Wizard, call **LaunchWizard**, a function based on the [LAUNCHWIZARDENTRY](launchwizardentry.md) prototype.</span></span> 
  
<span data-ttu-id="3003a-109">用户只能将这些邮件服务和服务提供程序添加到支持配置文件向导的新配置文件。</span><span class="sxs-lookup"><span data-stu-id="3003a-109">The user can add only those message services and service providers to the new profile that support the Profile Wizard.</span></span> <span data-ttu-id="3003a-110">由于每个邮件服务可能需要比配置文件向导可以处理的属性数目更多的属性, 请注意, 如果使用此方法, 则一个或多个选定的服务或提供程序可能未完全配置。</span><span class="sxs-lookup"><span data-stu-id="3003a-110">Because each message service might require more properties to be set than the Profile Wizard can handle, be aware that if you use this approach, it is possible for one or more of the selected services or providers to be incompletely configured.</span></span>
  

