---
title: MAPI 体系结构概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 00d2993c-d66a-4a00-9fb2-98696d29a007
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 98a723528a714918ad7e0f10534efb0d38ef139a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297886"
---
# <a name="mapi-architecture-overview"></a><span data-ttu-id="ec901-103">MAPI 体系结构概述</span><span class="sxs-lookup"><span data-stu-id="ec901-103">MAPI architecture overview</span></span>
 
<span data-ttu-id="ec901-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ec901-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ec901-105">MAPI 定义了模块化体系结构, 如下图所示。</span><span class="sxs-lookup"><span data-stu-id="ec901-105">MAPI defines a modular architecture, as shown in the following illustration.</span></span>  
  
<span data-ttu-id="ec901-106">![Outlook 2010 体系结构](media/amapi_43.gif "Outlook 2010 体系结构")</span><span class="sxs-lookup"><span data-stu-id="ec901-106">![Outlook 2010 architecture](media/amapi_43.gif "Outlook 2010 architecture")</span></span>
  
<span data-ttu-id="ec901-107">mapi 应用程序称为客户端应用程序, 因为它是 mapi 子系统的客户端。</span><span class="sxs-lookup"><span data-stu-id="ec901-107">The MAPI application is known as a client application because it is a client of the MAPI subsystem.</span></span> <span data-ttu-id="ec901-108">基于邮件的应用程序将消息传递作为其处理的中心部分, 并提供广泛的邮件功能, 如各种格式的信息交换, 以及在本地保存和组织信息的能力。</span><span class="sxs-lookup"><span data-stu-id="ec901-108">Messaging-based applications employ messaging as a central part of their processing and offer extensive messaging features, such as the exchange of information of various types in various formats and the ability to save and organize the information locally.</span></span> <span data-ttu-id="ec901-109">电子邮件、调度和工作流应用程序是基于邮件的应用程序的示例。</span><span class="sxs-lookup"><span data-stu-id="ec901-109">Email, scheduling, and work flow applications are examples of messaging-based applications.</span></span>
  
<span data-ttu-id="ec901-110">MAPI 子系统由通用用户界面和编程接口组成。</span><span class="sxs-lookup"><span data-stu-id="ec901-110">The MAPI subsystem is made up of a common user interface and the programming interfaces.</span></span> <span data-ttu-id="ec901-111">公共用户界面是一组对话框, 为客户端应用程序提供一致的外观和用户一种一致的工作方式。</span><span class="sxs-lookup"><span data-stu-id="ec901-111">The common user interface is a set of dialog boxes that gives client applications a consistent look and users a consistent way to work.</span></span>
  
<span data-ttu-id="ec901-112">mapi 具有由 MAPI 子系统、客户端软件开发人员和服务提供商开发人员使用的编程接口。</span><span class="sxs-lookup"><span data-stu-id="ec901-112">MAPI has programming interfaces that are used by the MAPI subsystem, by client software developers, and by service provider developers.</span></span> <span data-ttu-id="ec901-113">MAPI 编程接口是基于对象的主要编程接口。</span><span class="sxs-lookup"><span data-stu-id="ec901-113">The MAPI programming interface is the main object-based programming interface.</span></span> <span data-ttu-id="ec901-114">mapi 编程接口类似于 OLE 组件对象模型, 由 mapi 子系统和以 c 或 c + + 编写的基于邮件的客户端应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="ec901-114">The MAPI programming interface is similar to the OLE Component Object Model and is used by the MAPI subsystem and messaging-based client applications written in C or C++.</span></span> 
  
<span data-ttu-id="ec901-115">作为客户端软件开发人员, 您可以直接通过 mapi 编程接口进行 mapi 调用。</span><span class="sxs-lookup"><span data-stu-id="ec901-115">As a client software developer, you make MAPI calls directly through the MAPI programming interface.</span></span> <span data-ttu-id="ec901-116">您可以使用单个 MAPI 客户端接口或接口组合来实现邮件传递。</span><span class="sxs-lookup"><span data-stu-id="ec901-116">You can implement messaging with a single MAPI client interface or a combination of interfaces.</span></span> <span data-ttu-id="ec901-117">单个应用程序可以调用属于任何接口的方法或函数。</span><span class="sxs-lookup"><span data-stu-id="ec901-117">A single application can make calls to methods or functions belonging to any of the interfaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ec901-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec901-118">See also</span></span>

<span data-ttu-id="ec901-119">-[MAPI 功能和体系结构](mapi-features-and-architecture.md)</span><span class="sxs-lookup"><span data-stu-id="ec901-119">-[MAPI features and architecture](mapi-features-and-architecture.md)</span></span>

