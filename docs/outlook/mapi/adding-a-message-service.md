---
title: 添加邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1e626714-52dc-4141-9741-4d801f32d294
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 30cbe49eae7b4a232efb544c7a508a36b326c6b5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407233"
---
# <a name="adding-a-message-service"></a><span data-ttu-id="0d147-103">添加邮件服务</span><span class="sxs-lookup"><span data-stu-id="0d147-103">Adding a Message Service</span></span>

  
  
<span data-ttu-id="0d147-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0d147-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="0d147-105">**将新的邮件服务添加到配置文件并访问新的邮件服务**</span><span class="sxs-lookup"><span data-stu-id="0d147-105">**To add a new message service to a profile and access the new message service**</span></span>
  
<span data-ttu-id="0d147-106">调用[IMsgServiceAdmin2:: CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md)。</span><span class="sxs-lookup"><span data-stu-id="0d147-106">Call [IMsgServiceAdmin2::CreateMsgServiceEx](imsgserviceadmin2-createmsgserviceex.md).</span></span> <span data-ttu-id="0d147-107">**CreateMsgServiceEx**执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="0d147-107">**CreateMsgServiceEx** performs the following tasks:</span></span> 
  
1. <span data-ttu-id="0d147-108">复制 mapisvc.inf 中的邮件服务的所有相关信息。INF 文件, 为每个提供程序部分创建一个配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="0d147-108">Copies all of the relevant information for the message service that is in the MAPISVC.INF file, creating a profile section for every provider section.</span></span>
    
2. <span data-ttu-id="0d147-109">调用邮件服务的入口点函数**MSGSERVICEENTRY**, 并将_ulContext_参数设置为 MSG_SERVICE_CREATE。</span><span class="sxs-lookup"><span data-stu-id="0d147-109">Calls the message service's entry point function, **MSGSERVICEENTRY**, with the  _ulContext_ parameter set to MSG_SERVICE_CREATE.</span></span> 
    
3. <span data-ttu-id="0d147-110">设置和检索邮件服务的**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0d147-110">Sets and retrieves the message service's **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) property.</span></span>
    
 <span data-ttu-id="0d147-111">**访问任何新添加的邮件服务**</span><span class="sxs-lookup"><span data-stu-id="0d147-111">**To access any newly added message service**</span></span>
  
1. <span data-ttu-id="0d147-112">调用[IMsgServiceAdmin:: GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)以检索邮件服务表。</span><span class="sxs-lookup"><span data-stu-id="0d147-112">Call [IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) to retrieve the message service table.</span></span> 
    
2. <span data-ttu-id="0d147-113">调用邮件服务表的[IMAPITable:: Advise](imapitable-advise.md)方法以注册表通知。</span><span class="sxs-lookup"><span data-stu-id="0d147-113">Call the message service table's [IMAPITable::Advise](imapitable-advise.md) method to register for table notifications.</span></span> 
    
3. <span data-ttu-id="0d147-114">当 MAPI 发送 TABLE_ROW_ADDED 通知时, 请在[TABLE_NOTIFICATION](table_notification.md)结构中包含的[SRow](srow.md)结构中查找新添加的邮件服务的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="0d147-114">When MAPI sends a TABLE_ROW_ADDED notification, locate the entry identifier of the newly added message service in the [SRow](srow.md) structure included in the [TABLE_NOTIFICATION](table_notification.md) structure.</span></span> 
    

