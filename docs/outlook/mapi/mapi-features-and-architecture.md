---
title: MAPI 功能和体系结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 34bae703-a979-437c-9d86-8b91e9822a54
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8156cb53fc81f4861e4a66da4960df0458ec6c91
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418279"
---
# <a name="mapi-features-and-architecture"></a><span data-ttu-id="80848-103">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="80848-103">MAPI Features and Architecture</span></span>

  
  
<span data-ttu-id="80848-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="80848-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="80848-105">消息传递 API (MAPI) 由一组常用的应用程序编程接口和一个动态链接库 (DLL) 组件组成。</span><span class="sxs-lookup"><span data-stu-id="80848-105">Messaging API (MAPI) is composed of a set of common application programming interfaces and a dynamic-link library (DLL) component.</span></span> <span data-ttu-id="80848-106">这些接口用于创建和访问各种邮件应用程序和邮件系统, 为开发和使用提供统一的环境, 并为两者提供真正的独立性。</span><span class="sxs-lookup"><span data-stu-id="80848-106">The interfaces are used to create and access diverse messaging applications and messaging systems, offering a uniform environment for development and use, and providing true independence for both.</span></span> <span data-ttu-id="80848-107">DLL 包含 MAPI 子系统, 它管理前端邮件应用程序和后端邮件系统之间的交互, 并为频繁的任务提供通用用户界面。</span><span class="sxs-lookup"><span data-stu-id="80848-107">The DLL contains the MAPI subsystem, which manages the interaction between front-end messaging applications and back-end messaging systems and provides a common user interface for frequent tasks.</span></span> <span data-ttu-id="80848-108">MAPI 子系统充当中央交换所, 以统一不同的邮件系统, 并使客户端之间的差异不受保护。</span><span class="sxs-lookup"><span data-stu-id="80848-108">The MAPI subsystem acts as a central clearinghouse to unify the various messaging systems and shield clients from their differences.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="80848-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80848-109">See also</span></span>



[<span data-ttu-id="80848-110">MAPI 概念</span><span class="sxs-lookup"><span data-stu-id="80848-110">MAPI Concepts</span></span>](mapi-concepts.md)

