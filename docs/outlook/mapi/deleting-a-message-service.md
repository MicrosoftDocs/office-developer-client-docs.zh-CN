---
title: 删除邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 346608d7-f7de-497e-9852-4d4d7696177e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 27c20242417e51886ab184b1cc87d6ebb185e4bf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428121"
---
# <a name="deleting-a-message-service"></a><span data-ttu-id="486e9-103">删除邮件服务</span><span class="sxs-lookup"><span data-stu-id="486e9-103">Deleting a Message Service</span></span>

  
  
<span data-ttu-id="486e9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="486e9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="486e9-105">**从配置文件中删除邮件服务**</span><span class="sxs-lookup"><span data-stu-id="486e9-105">**To delete a message service from a profile**</span></span>
  
1. <span data-ttu-id="486e9-106">调用**IMAPISession:: GetMsgServiceTable**以访问邮件服务表。</span><span class="sxs-lookup"><span data-stu-id="486e9-106">Call **IMAPISession::GetMsgServiceTable** to access the message service table.</span></span> 
    
2. <span data-ttu-id="486e9-107">找到邮件服务的行, 并将_lpuid_参数中的**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列传递给[IMsgServiceAdmin::D eletemsgservice](imsgserviceadmin-deletemsgservice.md)。</span><span class="sxs-lookup"><span data-stu-id="486e9-107">Locate the row for the message service and pass its **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) column in the  _lpuid_ parameter to [IMsgServiceAdmin::DeleteMsgService](imsgserviceadmin-deletemsgservice.md).</span></span> 
    
 <span data-ttu-id="486e9-108">**DeleteMsgService**调用邮件服务的入口点函数, 并将_ulContext_参数设置为 MSG_SERVICE_DELETE。</span><span class="sxs-lookup"><span data-stu-id="486e9-108">**DeleteMsgService** calls the message service's entry point function with the  _ulContext_ parameter set to MSG_SERVICE_DELETE.</span></span> <span data-ttu-id="486e9-109">在从配置文件中删除所有任务之前, 邮件服务将执行任何清除任务。</span><span class="sxs-lookup"><span data-stu-id="486e9-109">Message services perform any clean up tasks at this time before they are removed from the profile.</span></span> 
  

