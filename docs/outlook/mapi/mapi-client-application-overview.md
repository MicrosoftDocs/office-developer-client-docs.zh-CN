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
# <a name="mapi-client-application-overview"></a><span data-ttu-id="331fa-103">MAPI 客户端应用程序概述</span><span class="sxs-lookup"><span data-stu-id="331fa-103">MAPI Client Application Overview</span></span>

  
  
<span data-ttu-id="331fa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="331fa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="331fa-105">MAPI 客户端应用程序是任何使用 MAPI 编程接口的应用程序。</span><span class="sxs-lookup"><span data-stu-id="331fa-105">A MAPI client application is any application that uses the MAPI programming interface.</span></span> <span data-ttu-id="331fa-106">客户端应用程序将消息传递任务作为主要或次要焦点来实现。</span><span class="sxs-lookup"><span data-stu-id="331fa-106">Client applications implement messaging tasks as either their primary or secondary focus.</span></span> <span data-ttu-id="331fa-107">邮件客户端应用程序（如发送和接收电子邮件的应用程序）将消息传递作为主要重点实现。</span><span class="sxs-lookup"><span data-stu-id="331fa-107">Messaging client applications, such as applications that send and receive email, implement messaging as their primary focus.</span></span> <span data-ttu-id="331fa-108">对于非邮件客户端应用程序（如清单或配置应用程序）来说，消息传递是一项辅助功能。</span><span class="sxs-lookup"><span data-stu-id="331fa-108">For non-messaging client applications, such as inventory or configuration applications, messaging is a secondary feature.</span></span>
  
<span data-ttu-id="331fa-109">例如，邮件活动可能包括一个字处理应用程序，该应用程序在其"文件"菜单上具有"发送"命令以允许发送文档、Microsoft Office Outlook电子邮件、工作流程自动化程序和公告板服务。</span><span class="sxs-lookup"><span data-stu-id="331fa-109">Messaging activities can include, for example, a word processing application that has a **Send** command on its **File** menu to enable documents to be sent, Microsoft Office Outlook email, work flow automation programs, and bulletin board services.</span></span> 
  
<span data-ttu-id="331fa-110">客户端应用程序可以包括用户来创建交互式环境，也可以无需用户在自动化环境中运行。</span><span class="sxs-lookup"><span data-stu-id="331fa-110">Client applications can either include the user to create an interactive environment or operate without a user in an automated environment.</span></span> <span data-ttu-id="331fa-111">虽然 MAPI 提供了一组具有其标准用户界面的常见对话框，但客户端应用程序不需要显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="331fa-111">Although MAPI supplies a set of common dialog boxes with its standard user interface, client applications are not required to present a user interface.</span></span> <span data-ttu-id="331fa-112">事实上，如果需要，可在应用程序中处理所有处理。</span><span class="sxs-lookup"><span data-stu-id="331fa-112">In fact, all processing can be handled in the application, if you want.</span></span> <span data-ttu-id="331fa-113">自动化客户端应用程序的一个示例是一个清单管理应用程序，它经过编程，可定期将特定类型的项目路由到标准收件人。</span><span class="sxs-lookup"><span data-stu-id="331fa-113">An example of an automated client application would be an inventory management application that is programmed to route items of a particular type to standard recipients on a regular basis.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="331fa-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="331fa-114">See also</span></span>



[<span data-ttu-id="331fa-115">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="331fa-115">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

