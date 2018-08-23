---
title: 关于示例脱机状态加载项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: a6bdf408-114a-2203-189f-101251a65a8c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: dcb5d63e2f8b7b1371fbcf2d74f52c6bba84e6dc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569013"
---
# <a name="about-the-sample-offline-state-add-in"></a><span data-ttu-id="13191-103">关于示例脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="13191-103">About the Sample Offline State Add-in</span></span>

  
  
<span data-ttu-id="13191-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="13191-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="13191-105">脱机状态 API 支持指示在 Outlook 中的用户的连接状态的变化的回调 — 例如，从要在 Outlook 中联机到脱机。</span><span class="sxs-lookup"><span data-stu-id="13191-105">The Offline State API supports callbacks indicating changes in a user's connection state in Outlook—for example, from being online in Outlook to being offline.</span></span> <span data-ttu-id="13191-106">示例脱机状态加载项是 COM 加载项以演示如何接收的连接状态更改通知以及如何修改使用脱机状态 API 的当前状态的 c + + 编写。</span><span class="sxs-lookup"><span data-stu-id="13191-106">The Sample Offline State Add-in is a COM add-in written in C++ that demonstrates how to receive notifications of connection state changes and how to modify the current state using the Offline State API.</span></span> <span data-ttu-id="13191-107">有关脱机状态 API 的详细信息，请参阅[有关脱机状态 API](about-the-offline-state-api.md)。</span><span class="sxs-lookup"><span data-stu-id="13191-107">For more information about the Offline State API, see [About the Offline State API](about-the-offline-state-api.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="13191-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="13191-108">In this section</span></span>

- [<span data-ttu-id="13191-109">安装示例脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="13191-109">Installing the Sample Offline State Add-in</span></span>](installing-the-sample-offline-state-add-in.md)
    
- <span data-ttu-id="13191-110">介绍如何下载并安装示例脱机状态加载项。</span><span class="sxs-lookup"><span data-stu-id="13191-110">Explains how to download and install the Sample Offline State Add-in.</span></span>
    
- [<span data-ttu-id="13191-111">设置脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="13191-111">Setting Up an Offline State Add-in</span></span>](setting-up-an-offline-state-add-in.md)
    
- <span data-ttu-id="13191-112">介绍如何才能使用脱机状态加载项实现连接、 初始化和设置功能。</span><span class="sxs-lookup"><span data-stu-id="13191-112">Describes how to implement connection, initialization, and setup functions in order to use an offline state add-in.</span></span>
    
- [<span data-ttu-id="13191-113">使用脱机状态加载项监视连接状态更改</span><span class="sxs-lookup"><span data-stu-id="13191-113">Monitoring Connection State Changes Using an Offline State Add-in</span></span>](monitoring-connection-state-changes-using-an-offline-state-add-in.md)
    
- <span data-ttu-id="13191-114">介绍如何使用**[HrOpenOfflineObj](hropenofflineobj.md)** 函数可获取脱机对象，以监控并更改连接状态。</span><span class="sxs-lookup"><span data-stu-id="13191-114">Describes how to use the **[HrOpenOfflineObj](hropenofflineobj.md)** function to obtain an offline object to monitor and change the connection state.</span></span> 
    
- [<span data-ttu-id="13191-115">断开脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="13191-115">Disconnecting an Offline State Add-in</span></span>](disconnecting-an-offline-state-add-in.md)
    
- <span data-ttu-id="13191-116">介绍如何正确终止并清理脱机状态外接程序时加载项已断开连接。</span><span class="sxs-lookup"><span data-stu-id="13191-116">Describes how to properly terminate and clean up an offline state add-in when the add-in is disconnected.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="13191-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13191-117">See also</span></span>



[<span data-ttu-id="13191-118">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="13191-118">About the Offline State API</span></span>](about-the-offline-state-api.md)

