---
title: 复制邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 01e8ad76-973a-42fa-96aa-f41aabc12b4f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8388d14446a230b032e49ad0d614c85e79b8ece8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573717"
---
# <a name="copying-a-message-service"></a><span data-ttu-id="9637a-103">复制邮件服务</span><span class="sxs-lookup"><span data-stu-id="9637a-103">Copying a Message Service</span></span>

  
  
<span data-ttu-id="9637a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9637a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="9637a-105">**若要将邮件服务复制到一个配置文件**</span><span class="sxs-lookup"><span data-stu-id="9637a-105">**To copy a message service to a profile**</span></span>
  
- <span data-ttu-id="9637a-106">调用[IMsgServiceAdmin::CopyMsgService](imsgserviceadmin-copymsgservice.md)。</span><span class="sxs-lookup"><span data-stu-id="9637a-106">Call [IMsgServiceAdmin::CopyMsgService](imsgserviceadmin-copymsgservice.md).</span></span>
    
<span data-ttu-id="9637a-107">复制的消息服务时中与原始完全相同的方式, 配置该服务的新实例。</span><span class="sxs-lookup"><span data-stu-id="9637a-107">When a message service is copied, the new instance of the service is configured in exactly the same way as the original.</span></span> <span data-ttu-id="9637a-108">有时**CopyMsgService**将返回错误 MAPI_E_ACCESS_DENIED。</span><span class="sxs-lookup"><span data-stu-id="9637a-108">Sometimes **CopyMsgService** returns the error MAPI_E_ACCESS_DENIED.</span></span> <span data-ttu-id="9637a-109">此错误返回的最常见原因是不允许本身要重复的消息服务。</span><span class="sxs-lookup"><span data-stu-id="9637a-109">The most common cause of this error return is a message service that does not allow itself to be duplicated.</span></span> 
  

