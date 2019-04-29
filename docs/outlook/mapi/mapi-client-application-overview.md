---
title: MAPI 客户端应用程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ad2e1f2d-57c3-4fb5-9e0f-db51640df84d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 100d1339ade8e5983c89695afbd85592cc2a4e43
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411279"
---
# <a name="mapi-client-application-overview"></a><span data-ttu-id="128d1-103">MAPI 客户端应用程序概述</span><span class="sxs-lookup"><span data-stu-id="128d1-103">MAPI Client Application Overview</span></span>

  
  
<span data-ttu-id="128d1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="128d1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="128d1-105">mapi 客户端应用程序是使用 MAPI 编程接口的任何应用程序。</span><span class="sxs-lookup"><span data-stu-id="128d1-105">A MAPI client application is any application that uses the MAPI programming interface.</span></span> <span data-ttu-id="128d1-106">客户端应用程序将邮件任务作为主焦点或辅助焦点来实现。</span><span class="sxs-lookup"><span data-stu-id="128d1-106">Client applications implement messaging tasks as either their primary or secondary focus.</span></span> <span data-ttu-id="128d1-107">邮件客户端应用程序 (例如发送和接收电子邮件的应用程序) 将消息作为其主焦点实现。</span><span class="sxs-lookup"><span data-stu-id="128d1-107">Messaging client applications, such as applications that send and receive email, implement messaging as their primary focus.</span></span> <span data-ttu-id="128d1-108">对于非邮件客户端应用程序 (如清单或配置应用程序), 消息传递是辅助功能。</span><span class="sxs-lookup"><span data-stu-id="128d1-108">For non-messaging client applications, such as inventory or configuration applications, messaging is a secondary feature.</span></span>
  
<span data-ttu-id="128d1-109">邮件活动可以包括一个字处理应用程序, 该应用程序的 "**文件**" 菜单上有 "**发送**" 命令, 以启用文档发送、Microsoft Office Outlook 电子邮件、工作流自动化程序和公告牌服务。</span><span class="sxs-lookup"><span data-stu-id="128d1-109">Messaging activities can include, for example, a word processing application that has a **Send** command on its **File** menu to enable documents to be sent, Microsoft Office Outlook email, work flow automation programs, and bulletin board services.</span></span> 
  
<span data-ttu-id="128d1-110">客户端应用程序既可以包括用户, 也可以在自动环境中创建交互式环境, 也可以在没有用户的情况下运行。</span><span class="sxs-lookup"><span data-stu-id="128d1-110">Client applications can either include the user to create an interactive environment or operate without a user in an automated environment.</span></span> <span data-ttu-id="128d1-111">虽然 MAPI 提供了一组通用的对话框及其标准用户界面, 但客户端应用程序不需要提供用户界面。</span><span class="sxs-lookup"><span data-stu-id="128d1-111">Although MAPI supplies a set of common dialog boxes with its standard user interface, client applications are not required to present a user interface.</span></span> <span data-ttu-id="128d1-112">事实上, 如果需要, 可以在应用程序中处理所有处理。</span><span class="sxs-lookup"><span data-stu-id="128d1-112">In fact, all processing can be handled in the application, if you want.</span></span> <span data-ttu-id="128d1-113">自动客户端应用程序的一个示例是设计用于定期将特定类型的项目路由到标准收件人的库存管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="128d1-113">An example of an automated client application would be an inventory management application that is programmed to route items of a particular type to standard recipients on a regular basis.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="128d1-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="128d1-114">See also</span></span>



[<span data-ttu-id="128d1-115">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="128d1-115">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

