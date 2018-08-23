---
title: 重新配置传输提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3d466bde-b70d-44b6-ba03-6ad8353ec759
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5e7c94b387a5fe9f9682854de4097f6f1bbcd786
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565597"
---
# <a name="reconfiguring-a-transport-provider"></a><span data-ttu-id="58af5-103">重新配置传输提供程序</span><span class="sxs-lookup"><span data-stu-id="58af5-103">Reconfiguring a Transport Provider</span></span>

  
  
<span data-ttu-id="58af5-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="58af5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="58af5-105">您可以使用传输提供程序的状态对象更改的一些提供程序的属性。</span><span class="sxs-lookup"><span data-stu-id="58af5-105">You can use a transport provider's status object to change some of the properties of the provider.</span></span> <span data-ttu-id="58af5-106">可以更改属性的范围取决于包含在提供程序的属性表和如何定义这些属性的属性。</span><span class="sxs-lookup"><span data-stu-id="58af5-106">The range of properties that can be changed depends on the properties that are included with the provider's property sheet and how those properties are defined.</span></span> 
  
 <span data-ttu-id="58af5-107">**若要重新配置的活动传输提供程序**</span><span class="sxs-lookup"><span data-stu-id="58af5-107">**To reconfigure an active transport provider**</span></span>
  
1. <span data-ttu-id="58af5-108">调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问状态表。</span><span class="sxs-lookup"><span data-stu-id="58af5-108">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the status table.</span></span> 
    
2. <span data-ttu-id="58af5-109">找到要通过创建匹配**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的属性限制重新配置的传输提供程序的行与目标提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="58af5-109">Locate the row for the transport provider to be reconfigured by creating a property restriction that matches **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) with the name of the target provider.</span></span> 
    
3. <span data-ttu-id="58af5-110">调用[IMAPITable::FindRow](imapitable-findrow.md)检索相应行。</span><span class="sxs-lookup"><span data-stu-id="58af5-110">Call [IMAPITable::FindRow](imapitable-findrow.md) to retrieve the appropriate row.</span></span> 
    
4. <span data-ttu-id="58af5-111">目标传输提供程序的**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中设置了 STATUS_SETTINGS_DIALOG 和 STATUS_VALIDATE_STATE 标志的检查。</span><span class="sxs-lookup"><span data-stu-id="58af5-111">Check that the STATUS_SETTINGS_DIALOG and STATUS_VALIDATE_STATE flags are set in the target transport provider's **PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) property.</span></span> <span data-ttu-id="58af5-112">如果未设置 STATUS_SETTINGS_DIALOG，传输提供程序不显示配置属性表。</span><span class="sxs-lookup"><span data-stu-id="58af5-112">If STATUS_SETTINGS_DIALOG is not set, the transport provider does not display a configuration property sheet.</span></span> <span data-ttu-id="58af5-113">如果未设置 STATUS_VALIDATE_STATE，不能执行动态重新配置。</span><span class="sxs-lookup"><span data-stu-id="58af5-113">If STATUS_VALIDATE_STATE is not set, you cannot perform dynamic reconfiguration.</span></span>
    
5. <span data-ttu-id="58af5-114">如果设置 STATUS_SETTINGS_DIALOG，调用[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)显示传输提供程序的属性表，并允许用户做出更改。</span><span class="sxs-lookup"><span data-stu-id="58af5-114">If STATUS_SETTINGS_DIALOG is set, call [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) to display the transport provider's property sheet and allow the user to make changes.</span></span> 
    
6. <span data-ttu-id="58af5-115">用户已重新配置完成后，调用[IMAPIStatus::ValidateState](imapistatus-validatestate.md) ，如果设置 STATUS_VALIDATE_STATE，传递 CONFIG_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="58af5-115">After the user has finished with the reconfiguration, call [IMAPIStatus::ValidateState](imapistatus-validatestate.md) if STATUS_VALIDATE_STATE is set, passing CONFIG_CHANGED.</span></span> 
    

