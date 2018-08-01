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
ms.openlocfilehash: fd87d169cd5131c6e1c8ca45a35dded96a295c57
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774664"
---
# <a name="configuring-a-message-service"></a><span data-ttu-id="42821-103">配置邮件服务</span><span class="sxs-lookup"><span data-stu-id="42821-103">Configuring a Message Service</span></span>

  
  
<span data-ttu-id="42821-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="42821-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="42821-105">**配置邮件服务中的所有服务提供商**</span><span class="sxs-lookup"><span data-stu-id="42821-105">**To configure all the service providers in a message service**</span></span>
  
- <span data-ttu-id="42821-106">调用[IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md)。</span><span class="sxs-lookup"><span data-stu-id="42821-106">Call [IMsgServiceAdmin::ConfigureMsgService](imsgserviceadmin-configuremsgservice.md).</span></span> <span data-ttu-id="42821-107">如果所有所需的配置数据以编程方式为可用，则可以选择显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="42821-107">If all of the data necessary for configuration is available programmatically, you can choose whether or not to display a user interface.</span></span> <span data-ttu-id="42821-108">但是，如果一个或多个提供程序的信息的一些不可用，请确保您设置 SERVICE_UI_ALLOWED 或 SERVICE_UI_ALWAYS 标志。</span><span class="sxs-lookup"><span data-stu-id="42821-108">However, if some of the information for one or more providers is not available, make sure that you set the SERVICE_UI_ALLOWED or SERVICE_UI_ALWAYS flag.</span></span> <span data-ttu-id="42821-109">不可用导致的未配置的邮件服务所需的配置数据时，禁止显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="42821-109">Suppressing a user interface when required configuration data is unavailable results in an unconfigured message service.</span></span>
    
 <span data-ttu-id="42821-110">**若要配置单个服务提供程序中的消息服务**</span><span class="sxs-lookup"><span data-stu-id="42821-110">**To configure a single service provider in a message service**</span></span>
  
1. <span data-ttu-id="42821-111">调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问服务提供商的状态对象。</span><span class="sxs-lookup"><span data-stu-id="42821-111">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the service provider's status object.</span></span> 
    
2. <span data-ttu-id="42821-112">调用[IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md)以显示服务提供商的属性表。</span><span class="sxs-lookup"><span data-stu-id="42821-112">Call [IMAPIStatus::SettingsDialog](imapistatus-settingsdialog.md) to display the service provider's property sheet.</span></span> 
    
<span data-ttu-id="42821-113">有关使用状态对象的详细信息，请参阅[状态表和状态对象](status-table-and-status-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="42821-113">For more information about using status objects, see [Status Table and Status Objects](status-table-and-status-objects.md).</span></span>
  

