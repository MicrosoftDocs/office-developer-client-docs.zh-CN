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
ms.openlocfilehash: 7d1296ba74bbafcd26a8878dfb1eb2f359ab3e03
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774677"
---
# <a name="copying-a-message-service"></a><span data-ttu-id="13437-103">复制邮件服务</span><span class="sxs-lookup"><span data-stu-id="13437-103">Copying a Message Service</span></span>

  
  
<span data-ttu-id="13437-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="13437-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="13437-105">**若要将邮件服务复制到一个配置文件**</span><span class="sxs-lookup"><span data-stu-id="13437-105">**To copy a message service to a profile**</span></span>
  
- <span data-ttu-id="13437-106">调用[IMsgServiceAdmin::CopyMsgService](imsgserviceadmin-copymsgservice.md)。</span><span class="sxs-lookup"><span data-stu-id="13437-106">Call [IMsgServiceAdmin::CopyMsgService](imsgserviceadmin-copymsgservice.md).</span></span>
    
<span data-ttu-id="13437-107">复制的消息服务时中与原始完全相同的方式, 配置该服务的新实例。</span><span class="sxs-lookup"><span data-stu-id="13437-107">When a message service is copied, the new instance of the service is configured in exactly the same way as the original.</span></span> <span data-ttu-id="13437-108">有时**CopyMsgService**将返回错误 MAPI_E_ACCESS_DENIED。</span><span class="sxs-lookup"><span data-stu-id="13437-108">Sometimes **CopyMsgService** returns the error MAPI_E_ACCESS_DENIED.</span></span> <span data-ttu-id="13437-109">此错误返回的最常见原因是不允许本身要重复的消息服务。</span><span class="sxs-lookup"><span data-stu-id="13437-109">The most common cause of this error return is a message service that does not allow itself to be duplicated.</span></span> 
  

