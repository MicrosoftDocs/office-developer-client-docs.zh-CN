---
title: 添加邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1e626714-52dc-4141-9741-4d801f32d294
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a7735be5cfb8ff0716b6bd6eba4951563bb938ab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774495"
---
# <a name="adding-a-message-service"></a><span data-ttu-id="4db50-103">添加邮件服务</span><span class="sxs-lookup"><span data-stu-id="4db50-103">Adding a Message Service</span></span>

  
  
<span data-ttu-id="4db50-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4db50-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="4db50-105">**配置文件中添加一个新的消息服务和访问新邮件服务**</span><span class="sxs-lookup"><span data-stu-id="4db50-105">**To add a new message service to a profile and access the new message service**</span></span>
  
<span data-ttu-id="4db50-106">调用[IMsgServiceAdmin2::CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md)。</span><span class="sxs-lookup"><span data-stu-id="4db50-106">Call [IMsgServiceAdmin2::CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md).</span></span> <span data-ttu-id="4db50-107">**CreateMsgServiceEx**执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="4db50-107">**CreateMsgServiceEx** performs the following tasks:</span></span> 
  
1. <span data-ttu-id="4db50-108">复制所有邮件服务正在 MAPISVC 的相关信息。INF 文件中，创建每个提供程序部分的配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="4db50-108">Copies all of the relevant information for the message service that is in the MAPISVC.INF file, creating a profile section for every provider section.</span></span>
    
2. <span data-ttu-id="4db50-109">调用带有_ulContext_参数设置为 MSG_SERVICE_CREATE 消息服务的入口点函数， **MSGSERVICEENTRY**。</span><span class="sxs-lookup"><span data-stu-id="4db50-109">Calls the message service's entry point function, **MSGSERVICEENTRY**, with the  _ulContext_ parameter set to MSG_SERVICE_CREATE.</span></span> 
    
3. <span data-ttu-id="4db50-110">设置和检索邮件服务**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="4db50-110">Sets and retrieves the message service's **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) property.</span></span>
    
 <span data-ttu-id="4db50-111">**若要访问任何新添加的消息服务**</span><span class="sxs-lookup"><span data-stu-id="4db50-111">**To access any newly added message service**</span></span>
  
1. <span data-ttu-id="4db50-112">调用[IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)检索邮件服务表。</span><span class="sxs-lookup"><span data-stu-id="4db50-112">Call [IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) to retrieve the message service table.</span></span> 
    
2. <span data-ttu-id="4db50-113">调用邮件服务表[IMAPITable::Advise](imapitable-advise.md)方法，以注册表通知。</span><span class="sxs-lookup"><span data-stu-id="4db50-113">Call the message service table's [IMAPITable::Advise](imapitable-advise.md) method to register for table notifications.</span></span> 
    
3. <span data-ttu-id="4db50-114">MAPI 时发送 TABLE_ROW_ADDED 通知，包括在[TABLE_NOTIFICATION](table_notification.md)结构[SRow](srow.md)结构中找到的新添加的消息服务的项标识符。</span><span class="sxs-lookup"><span data-stu-id="4db50-114">When MAPI sends a TABLE_ROW_ADDED notification, locate the entry identifier of the newly added message service in the [SRow](srow.md) structure included in the [TABLE_NOTIFICATION](table_notification.md) structure.</span></span> 
    

