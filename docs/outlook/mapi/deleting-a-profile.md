---
title: 删除配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4d01ab2e-40fd-409d-a69d-163b7d5462ca
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 29e7806afce885968956d53005a66bd14639ad64
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774761"
---
# <a name="deleting-a-profile"></a><span data-ttu-id="67f36-103">删除配置文件</span><span class="sxs-lookup"><span data-stu-id="67f36-103">Deleting a Profile</span></span>

  
  
<span data-ttu-id="67f36-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="67f36-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="67f36-105">**删除配置文件**</span><span class="sxs-lookup"><span data-stu-id="67f36-105">**To delete a profile**</span></span>
  
- <span data-ttu-id="67f36-106">调用[IProfAdmin::DeleteProfile](iprofadmin-deleteprofile.md)。</span><span class="sxs-lookup"><span data-stu-id="67f36-106">Call [IProfAdmin::DeleteProfile](iprofadmin-deleteprofile.md).</span></span>
    
 <span data-ttu-id="67f36-107">**DeleteProfile**标记为删除的配置文件，如果当前正在使用它，等待它不再处于活动状态，以将其删除。</span><span class="sxs-lookup"><span data-stu-id="67f36-107">**DeleteProfile** marks the profile for deletion if it is currently being used, waiting until it is no longer active to remove it.</span></span> <span data-ttu-id="67f36-108">配置文件没有实际消失之前每个客户端与活动会话已断开。</span><span class="sxs-lookup"><span data-stu-id="67f36-108">The profile does not actually disappear until every client with an active session has disconnected.</span></span> 
  
 <span data-ttu-id="67f36-109">**DeleteProfile** _ulContext_参数设置为 MSG_SERVICE_DELETE 配置文件中调用每种消息服务的入口点函数。</span><span class="sxs-lookup"><span data-stu-id="67f36-109">**DeleteProfile** calls the entry point function of every message service in the profile with the  _ulContext_ parameter set to MSG_SERVICE_DELETE.</span></span> <span data-ttu-id="67f36-110">对入口点函数的调用发生之前从配置文件已从物理上隔离到服务。</span><span class="sxs-lookup"><span data-stu-id="67f36-110">The calls to the entry point functions occur before the services are physically removed from the profile.</span></span> 
  

