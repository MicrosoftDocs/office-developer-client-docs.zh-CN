---
title: 关于示例脱机状态加载项
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: a6bdf408-114a-2203-189f-101251a65a8c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bf8e647af4aba53dfc24880e6ff491985b50a613
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431181"
---
# <a name="about-the-sample-offline-state-add-in"></a><span data-ttu-id="092a7-103">关于示例脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="092a7-103">About the Sample Offline State Add-in</span></span>

  
  
<span data-ttu-id="092a7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="092a7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="092a7-105">脱机状态 API 支持指示用户连接状态在 Outlook 中的更改的回调，例如，从处于联机状态Outlook脱机。</span><span class="sxs-lookup"><span data-stu-id="092a7-105">The Offline State API supports callbacks indicating changes in a user's connection state in Outlook—for example, from being online in Outlook to being offline.</span></span> <span data-ttu-id="092a7-106">示例脱机状态外接程序是使用 C++ 编写的 COM 加载项，它演示如何接收连接状态更改的通知，以及如何使用脱机状态 API 修改当前状态。</span><span class="sxs-lookup"><span data-stu-id="092a7-106">The Sample Offline State Add-in is a COM add-in written in C++ that demonstrates how to receive notifications of connection state changes and how to modify the current state using the Offline State API.</span></span> <span data-ttu-id="092a7-107">有关脱机状态 API 的详细信息，请参阅[关于脱机状态 API](about-the-offline-state-api.md)。</span><span class="sxs-lookup"><span data-stu-id="092a7-107">For more information about the Offline State API, see [About the Offline State API](about-the-offline-state-api.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="092a7-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="092a7-108">In this section</span></span>

- [<span data-ttu-id="092a7-109">安装示例脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="092a7-109">Installing the Sample Offline State Add-in</span></span>](installing-the-sample-offline-state-add-in.md)
    
- <span data-ttu-id="092a7-110">介绍如何下载和安装示例脱机状态外接程序。</span><span class="sxs-lookup"><span data-stu-id="092a7-110">Explains how to download and install the Sample Offline State Add-in.</span></span>
    
- [<span data-ttu-id="092a7-111">设置脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="092a7-111">Setting Up an Offline State Add-in</span></span>](setting-up-an-offline-state-add-in.md)
    
- <span data-ttu-id="092a7-112">介绍如何实现连接、初始化和设置功能，以便使用脱机状态加载项。</span><span class="sxs-lookup"><span data-stu-id="092a7-112">Describes how to implement connection, initialization, and setup functions in order to use an offline state add-in.</span></span>
    
- [<span data-ttu-id="092a7-113">使用脱机状态加载项监视连接状态更改</span><span class="sxs-lookup"><span data-stu-id="092a7-113">Monitoring Connection State Changes Using an Offline State Add-in</span></span>](monitoring-connection-state-changes-using-an-offline-state-add-in.md)
    
- <span data-ttu-id="092a7-114">介绍如何使用 **[HrOpenOfflineObj](hropenofflineobj.md)** 函数获取脱机对象来监视和更改连接状态。</span><span class="sxs-lookup"><span data-stu-id="092a7-114">Describes how to use the **[HrOpenOfflineObj](hropenofflineobj.md)** function to obtain an offline object to monitor and change the connection state.</span></span> 
    
- [<span data-ttu-id="092a7-115">断开脱机状态加载项</span><span class="sxs-lookup"><span data-stu-id="092a7-115">Disconnecting an Offline State Add-in</span></span>](disconnecting-an-offline-state-add-in.md)
    
- <span data-ttu-id="092a7-116">介绍如何在断开加载项的连接时正确终止和清理脱机状态加载项。</span><span class="sxs-lookup"><span data-stu-id="092a7-116">Describes how to properly terminate and clean up an offline state add-in when the add-in is disconnected.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="092a7-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="092a7-117">See also</span></span>



[<span data-ttu-id="092a7-118">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="092a7-118">About the Offline State API</span></span>](about-the-offline-state-api.md)

