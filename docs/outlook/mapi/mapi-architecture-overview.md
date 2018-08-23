---
title: MAPI 体系结构概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 00d2993c-d66a-4a00-9fb2-98696d29a007
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a0f2efc17ca8790502f11d677498013cbe10205d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579352"
---
# <a name="mapi-architecture-overview"></a><span data-ttu-id="4a6fa-103">MAPI 体系结构概述</span><span class="sxs-lookup"><span data-stu-id="4a6fa-103">MAPI architecture overview</span></span>
 
<span data-ttu-id="4a6fa-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4a6fa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4a6fa-105">MAPI 定义的模块化体系结构，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="4a6fa-105">MAPI defines a modular architecture, as shown in the following illustration.</span></span>  
  
<span data-ttu-id="4a6fa-106">![Outlook 2010 体系结构](media/amapi_43.gif "Outlook 2010 体系结构")</span><span class="sxs-lookup"><span data-stu-id="4a6fa-106">![Outlook 2010 architecture](media/amapi_43.gif "Outlook 2010 architecture")</span></span>
  
<span data-ttu-id="4a6fa-107">MAPI 应用程序被称为客户端应用程序，因为它是 MAPI 子系统的客户端。</span><span class="sxs-lookup"><span data-stu-id="4a6fa-107">The MAPI application is known as a client application because it is a client of the MAPI subsystem.</span></span> <span data-ttu-id="4a6fa-108">基于消息的应用程序采用消息为其处理的核心部分，并提供大量的消息功能，如的各种格式和功能中保存和组织的信息本地的各种类型的信息交换。</span><span class="sxs-lookup"><span data-stu-id="4a6fa-108">Messaging-based applications employ messaging as a central part of their processing and offer extensive messaging features, such as the exchange of information of various types in various formats and the ability to save and organize the information locally.</span></span> <span data-ttu-id="4a6fa-109">电子邮件、 日程安排和工作流应用程序基于消息的应用程序的示例。</span><span class="sxs-lookup"><span data-stu-id="4a6fa-109">Email, scheduling, and work flow applications are examples of messaging-based applications.</span></span>
  
<span data-ttu-id="4a6fa-110">MAPI 子系统通用的用户界面和编程接口组成。</span><span class="sxs-lookup"><span data-stu-id="4a6fa-110">The MAPI subsystem is made up of a common user interface and the programming interfaces.</span></span> <span data-ttu-id="4a6fa-111">常见用户界面是一致的外观和用户为客户端应用程序提供了一套对话框以一致方式工作。</span><span class="sxs-lookup"><span data-stu-id="4a6fa-111">The common user interface is a set of dialog boxes that gives client applications a consistent look and users a consistent way to work.</span></span>
  
<span data-ttu-id="4a6fa-112">MAPI 具有编程通过 MAPI 子系统、 客户端软件开发人员，以及服务提供程序开发人员使用的接口。</span><span class="sxs-lookup"><span data-stu-id="4a6fa-112">MAPI has programming interfaces that are used by the MAPI subsystem, by client software developers, and by service provider developers.</span></span> <span data-ttu-id="4a6fa-113">MAPI 编程接口是主要基于对象的编程接口。</span><span class="sxs-lookup"><span data-stu-id="4a6fa-113">The MAPI programming interface is the main object-based programming interface.</span></span> <span data-ttu-id="4a6fa-114">MAPI 编程接口类似于 OLE 组件对象模型和 MAPI 子系统和基于消息的客户端应用程序编写 C 或 c + + 中使用。</span><span class="sxs-lookup"><span data-stu-id="4a6fa-114">The MAPI programming interface is similar to the OLE Component Object Model and is used by the MAPI subsystem and messaging-based client applications written in C or C++.</span></span> 
  
<span data-ttu-id="4a6fa-115">作为客户端软件开发人员，您可以直接通过 MAPI 编程界面发起 MAPI 呼叫。</span><span class="sxs-lookup"><span data-stu-id="4a6fa-115">As a client software developer, you make MAPI calls directly through the MAPI programming interface.</span></span> <span data-ttu-id="4a6fa-116">您可以实现消息的单个 MAPI 客户端界面或接口的组合。</span><span class="sxs-lookup"><span data-stu-id="4a6fa-116">You can implement messaging with a single MAPI client interface or a combination of interfaces.</span></span> <span data-ttu-id="4a6fa-117">单个应用程序可以发起呼叫到方法或属于任何接口的函数。</span><span class="sxs-lookup"><span data-stu-id="4a6fa-117">A single application can make calls to methods or functions belonging to any of the interfaces.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4a6fa-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a6fa-118">See also</span></span>

<span data-ttu-id="4a6fa-119">-[MAPI 功能和体系结构](mapi-features-and-architecture.md)</span><span class="sxs-lookup"><span data-stu-id="4a6fa-119">-[MAPI features and architecture](mapi-features-and-architecture.md)</span></span>

