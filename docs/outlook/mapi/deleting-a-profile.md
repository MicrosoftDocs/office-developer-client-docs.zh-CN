---
title: 删除配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d01ab2e-40fd-409d-a69d-163b7d5462ca
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1cd87b92a9d289f06e466f4e44ce757c93074336
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316826"
---
# <a name="deleting-a-profile"></a><span data-ttu-id="165d3-103">删除配置文件</span><span class="sxs-lookup"><span data-stu-id="165d3-103">Deleting a Profile</span></span>

  
  
<span data-ttu-id="165d3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="165d3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="165d3-105">**删除配置文件**</span><span class="sxs-lookup"><span data-stu-id="165d3-105">**To delete a profile**</span></span>
  
- <span data-ttu-id="165d3-106">调用[IProfAdmin::D eleteprofile](iprofadmin-deleteprofile.md)。</span><span class="sxs-lookup"><span data-stu-id="165d3-106">Call [IProfAdmin::DeleteProfile](iprofadmin-deleteprofile.md).</span></span>
    
 <span data-ttu-id="165d3-107">如果要删除的配置文件当前正在使用, 则**DeleteProfile**会将其标记为删除, 等待它不再处于活动状态以将其删除。</span><span class="sxs-lookup"><span data-stu-id="165d3-107">**DeleteProfile** marks the profile for deletion if it is currently being used, waiting until it is no longer active to remove it.</span></span> <span data-ttu-id="165d3-108">只有在具有活动会话的每个客户端断开连接后, 配置文件才会实际消失。</span><span class="sxs-lookup"><span data-stu-id="165d3-108">The profile does not actually disappear until every client with an active session has disconnected.</span></span> 
  
 <span data-ttu-id="165d3-109">**DeleteProfile**调用配置文件中的每个邮件服务的入口点函数, 并将_ulContext_参数设置为 MSG_SERVICE_DELETE。</span><span class="sxs-lookup"><span data-stu-id="165d3-109">**DeleteProfile** calls the entry point function of every message service in the profile with the  _ulContext_ parameter set to MSG_SERVICE_DELETE.</span></span> <span data-ttu-id="165d3-110">对入口点函数的调用在从配置文件中实际删除服务之前发生。</span><span class="sxs-lookup"><span data-stu-id="165d3-110">The calls to the entry point functions occur before the services are physically removed from the profile.</span></span> 
  

