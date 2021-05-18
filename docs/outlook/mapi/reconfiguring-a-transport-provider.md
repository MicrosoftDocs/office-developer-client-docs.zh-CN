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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408408"
---
# <a name="reconfiguring-a-transport-provider"></a><span data-ttu-id="d006a-103">重新配置传输提供程序</span><span class="sxs-lookup"><span data-stu-id="d006a-103">Reconfiguring a Transport Provider</span></span>

  
  
<span data-ttu-id="d006a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d006a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d006a-105">可以使用传输提供程序的状态对象更改提供程序的一些属性。</span><span class="sxs-lookup"><span data-stu-id="d006a-105">You can use a transport provider's status object to change some of the properties of the provider.</span></span> <span data-ttu-id="d006a-106">可更改的属性范围取决于提供程序的提供程序属性中包含的属性属性表定义这些属性的方式。</span><span class="sxs-lookup"><span data-stu-id="d006a-106">The range of properties that can be changed depends on the properties that are included with the provider's property sheet and how those properties are defined.</span></span> 
  
 <span data-ttu-id="d006a-107">**重新配置活动传输提供程序**</span><span class="sxs-lookup"><span data-stu-id="d006a-107">**To reconfigure an active transport provider**</span></span>
  
1. <span data-ttu-id="d006a-108">调用 [IMAPISession：：GetStatusTable](imapisession-getstatustable.md) 以访问状态表。</span><span class="sxs-lookup"><span data-stu-id="d006a-108">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the status table.</span></span> 
    
2. <span data-ttu-id="d006a-109">通过创建与 PR_DISPLAY_NAME ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 与目标提供程序名称相匹配的属性限制，找到要重新配置的传输提供程序的行。</span><span class="sxs-lookup"><span data-stu-id="d006a-109">Locate the row for the transport provider to be reconfigured by creating a property restriction that matches **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) with the name of the target provider.</span></span> 
    
3. <span data-ttu-id="d006a-110">调用 [IMAPITable：：FindRow](imapitable-findrow.md) 以检索相应的行。</span><span class="sxs-lookup"><span data-stu-id="d006a-110">Call [IMAPITable::FindRow](imapitable-findrow.md) to retrieve the appropriate row.</span></span> 
    
4. <span data-ttu-id="d006a-111">检查目标STATUS_SETTINGS_DIALOG [PidTagResourceMethods](pidtagresourcemethods-canonical-property.md) STATUS_VALIDATE_STATE 属性中是否设置了PR_RESOURCE_METHODS (和) 标志。</span><span class="sxs-lookup"><span data-stu-id="d006a-111">Check that the STATUS_SETTINGS_DIALOG and STATUS_VALIDATE_STATE flags are set in the target transport provider's **PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) property.</span></span> <span data-ttu-id="d006a-112">如果未STATUS_SETTINGS_DIALOG，则传输提供程序不会显示配置属性表。</span><span class="sxs-lookup"><span data-stu-id="d006a-112">If STATUS_SETTINGS_DIALOG is not set, the transport provider does not display a configuration property sheet.</span></span> <span data-ttu-id="d006a-113">如果未STATUS_VALIDATE_STATE，则不能执行动态重新配置。</span><span class="sxs-lookup"><span data-stu-id="d006a-113">If STATUS_VALIDATE_STATE is not set, you cannot perform dynamic reconfiguration.</span></span>
    
5. <span data-ttu-id="d006a-114">如果STATUS_SETTINGS_DIALOG，请调用 [IMAPIStatus：：SettingsDialog](imapistatus-settingsdialog.md) 以显示传输提供程序属性表并允许用户进行更改。</span><span class="sxs-lookup"><span data-stu-id="d006a-114">If STATUS_SETTINGS_DIALOG is set, call [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) to display the transport provider's property sheet and allow the user to make changes.</span></span> 
    
6. <span data-ttu-id="d006a-115">在用户完成重新配置后，如果已设置STATUS_VALIDATE_STATE，则调用[IMAPIStatus：：ValidateState，CONFIG_CHANGED。](imapistatus-validatestate.md)</span><span class="sxs-lookup"><span data-stu-id="d006a-115">After the user has finished with the reconfiguration, call [IMAPIStatus::ValidateState](imapistatus-validatestate.md) if STATUS_VALIDATE_STATE is set, passing CONFIG_CHANGED.</span></span> 
    

