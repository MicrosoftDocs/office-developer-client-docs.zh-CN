---
title: 配置邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d68892e3-7c87-4b3a-a691-bff92f83ed00
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2b170037bc51a7848154c12acbfe700a0142ef8f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564106"
---
# <a name="configuring-a-message-service"></a><span data-ttu-id="59ab3-103">配置邮件服务</span><span class="sxs-lookup"><span data-stu-id="59ab3-103">Configuring a Message Service</span></span>

  
  
<span data-ttu-id="59ab3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="59ab3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="59ab3-105">**配置邮件服务中的所有服务提供商**</span><span class="sxs-lookup"><span data-stu-id="59ab3-105">**To configure all the service providers in a message service**</span></span>
  
- <span data-ttu-id="59ab3-106">调用[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)。</span><span class="sxs-lookup"><span data-stu-id="59ab3-106">Call [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md).</span></span> <span data-ttu-id="59ab3-107">如果所有所需的配置数据以编程方式为可用，则可以选择显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="59ab3-107">If all of the data necessary for configuration is available programmatically, you can choose whether or not to display a user interface.</span></span> <span data-ttu-id="59ab3-108">但是，如果一个或多个提供程序的信息的一些不可用，请确保您设置 SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 标志。</span><span class="sxs-lookup"><span data-stu-id="59ab3-108">However, if some of the information for one or more providers is not available, make sure that you set the SERVICE_UI_ALLOWED or SERVICE_UI_ALWAYS flag.</span></span> <span data-ttu-id="59ab3-109">不可用导致的未配置的邮件服务所需的配置数据时，禁止显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="59ab3-109">Suppressing a user interface when required configuration data is unavailable results in an unconfigured message service.</span></span>
    
 <span data-ttu-id="59ab3-110">**若要配置单个服务提供程序中的消息服务**</span><span class="sxs-lookup"><span data-stu-id="59ab3-110">**To configure a single service provider in a message service**</span></span>
  
1. <span data-ttu-id="59ab3-111">调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问服务提供商的状态对象。</span><span class="sxs-lookup"><span data-stu-id="59ab3-111">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the service provider's status object.</span></span> 
    
2. <span data-ttu-id="59ab3-112">调用[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)以显示服务提供商的属性表。</span><span class="sxs-lookup"><span data-stu-id="59ab3-112">Call [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) to display the service provider's property sheet.</span></span> 
    
<span data-ttu-id="59ab3-113">有关使用状态对象的详细信息，请参阅[状态表和状态对象](status-table-and-status-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="59ab3-113">For more information about using status objects, see [Status Table and Status Objects](status-table-and-status-objects.md).</span></span>
  

