---
title: 重新配置传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3d466bde-b70d-44b6-ba03-6ad8353ec759
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b35ca2bb52439cf2ba1750c6fad2883730c4c3f8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328411"
---
# <a name="reconfiguring-a-transport-provider"></a><span data-ttu-id="e0a60-103">重新配置传输提供程序</span><span class="sxs-lookup"><span data-stu-id="e0a60-103">Reconfiguring a Transport Provider</span></span>

  
  
<span data-ttu-id="e0a60-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e0a60-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e0a60-105">您可以使用传输提供程序的状态对象来更改提供程序的一些属性。</span><span class="sxs-lookup"><span data-stu-id="e0a60-105">You can use a transport provider's status object to change some of the properties of the provider.</span></span> <span data-ttu-id="e0a60-106">可以更改的属性范围取决于提供程序的属性表附带的属性以及如何定义这些属性。</span><span class="sxs-lookup"><span data-stu-id="e0a60-106">The range of properties that can be changed depends on the properties that are included with the provider's property sheet and how those properties are defined.</span></span> 
  
 <span data-ttu-id="e0a60-107">**重新配置活动传输提供程序**</span><span class="sxs-lookup"><span data-stu-id="e0a60-107">**To reconfigure an active transport provider**</span></span>
  
1. <span data-ttu-id="e0a60-108">调用[IMAPISession:: GetStatusTable](imapisession-getstatustable.md)以访问状态表。</span><span class="sxs-lookup"><span data-stu-id="e0a60-108">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the status table.</span></span> 
    
2. <span data-ttu-id="e0a60-109">通过创建与目标提供程序的名称相匹配的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的属性限制, 找到要重新配置的传输提供程序的行。</span><span class="sxs-lookup"><span data-stu-id="e0a60-109">Locate the row for the transport provider to be reconfigured by creating a property restriction that matches **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) with the name of the target provider.</span></span> 
    
3. <span data-ttu-id="e0a60-110">调用[IMAPITable:: FindRow](imapitable-findrow.md)以检索相应的行。</span><span class="sxs-lookup"><span data-stu-id="e0a60-110">Call [IMAPITable::FindRow](imapitable-findrow.md) to retrieve the appropriate row.</span></span> 
    
4. <span data-ttu-id="e0a60-111">检查目标传输提供程序的**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中是否设置了 STATUS_SETTINGS_DIALOG 和 STATUS_VALIDATE_STATE 标志。</span><span class="sxs-lookup"><span data-stu-id="e0a60-111">Check that the STATUS_SETTINGS_DIALOG and STATUS_VALIDATE_STATE flags are set in the target transport provider's **PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) property.</span></span> <span data-ttu-id="e0a60-112">如果未设置 STATUS_SETTINGS_DIALOG, 则传输提供程序不显示配置属性表。</span><span class="sxs-lookup"><span data-stu-id="e0a60-112">If STATUS_SETTINGS_DIALOG is not set, the transport provider does not display a configuration property sheet.</span></span> <span data-ttu-id="e0a60-113">如果未设置 STATUS_VALIDATE_STATE, 则无法执行动态重新配置。</span><span class="sxs-lookup"><span data-stu-id="e0a60-113">If STATUS_VALIDATE_STATE is not set, you cannot perform dynamic reconfiguration.</span></span>
    
5. <span data-ttu-id="e0a60-114">如果设置了 STATUS_SETTINGS_DIALOG, 则调用[IMAPIStatus:: SettingsDialog](imapistatus-settingsdialog.md)以显示传输提供程序的属性表, 并允许用户进行更改。</span><span class="sxs-lookup"><span data-stu-id="e0a60-114">If STATUS_SETTINGS_DIALOG is set, call [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) to display the transport provider's property sheet and allow the user to make changes.</span></span> 
    
6. <span data-ttu-id="e0a60-115">在用户完成重新配置之后, 调用[IMAPIStatus:: ValidateState](imapistatus-validatestate.md)如果设置了 STATUS_VALIDATE_STATE, 则传递 CONFIG_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="e0a60-115">After the user has finished with the reconfiguration, call [IMAPIStatus::ValidateState](imapistatus-validatestate.md) if STATUS_VALIDATE_STATE is set, passing CONFIG_CHANGED.</span></span> 
    

