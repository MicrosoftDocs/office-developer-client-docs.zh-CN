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
# <a name="deleting-a-message-service"></a><span data-ttu-id="386f4-103">删除邮件服务</span><span class="sxs-lookup"><span data-stu-id="386f4-103">Deleting a Message Service</span></span>

  
  
<span data-ttu-id="386f4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="386f4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="386f4-105">**从配置文件中删除邮件服务**</span><span class="sxs-lookup"><span data-stu-id="386f4-105">**To delete a message service from a profile**</span></span>
  
1. <span data-ttu-id="386f4-106">调用 **IMAPISession：：GetMsgServiceTable** 以访问邮件服务表。</span><span class="sxs-lookup"><span data-stu-id="386f4-106">Call **IMAPISession::GetMsgServiceTable** to access the message service table.</span></span> 
    
2. <span data-ttu-id="386f4-107">找到邮件服务的行，将 _lpuid_ 参数中的 PR_SERVICE_UID ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) 列传递到 [IMsgServiceAdmin：:D eleteMsgService](imsgserviceadmin-deletemsgservice.md)。 </span><span class="sxs-lookup"><span data-stu-id="386f4-107">Locate the row for the message service and pass its **PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md)) column in the  _lpuid_ parameter to [IMsgServiceAdmin::DeleteMsgService](imsgserviceadmin-deletemsgservice.md).</span></span> 
    
 <span data-ttu-id="386f4-108">**DeleteMsgService** 调用邮件服务的入口点函数  _，ulContext_ 参数设置为 MSG_SERVICE_DELETE。</span><span class="sxs-lookup"><span data-stu-id="386f4-108">**DeleteMsgService** calls the message service's entry point function with the  _ulContext_ parameter set to MSG_SERVICE_DELETE.</span></span> <span data-ttu-id="386f4-109">邮件服务此时将执行任何清理任务，然后再将其从配置文件中删除。</span><span class="sxs-lookup"><span data-stu-id="386f4-109">Message services perform any clean up tasks at this time before they are removed from the profile.</span></span> 
  

