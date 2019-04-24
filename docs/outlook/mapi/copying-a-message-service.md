---
title: 复制邮件服务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 01e8ad76-973a-42fa-96aa-f41aabc12b4f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a4db4ed1c3098226891edca054621fe145daaa1f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32333052"
---
# <a name="copying-a-message-service"></a><span data-ttu-id="3ca86-103">复制邮件服务</span><span class="sxs-lookup"><span data-stu-id="3ca86-103">Copying a Message Service</span></span>

  
  
<span data-ttu-id="3ca86-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3ca86-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="3ca86-105">**将邮件服务复制到配置文件**</span><span class="sxs-lookup"><span data-stu-id="3ca86-105">**To copy a message service to a profile**</span></span>
  
- <span data-ttu-id="3ca86-106">调用[IMsgServiceAdmin:: CopyMsgService](imsgserviceadmin-copymsgservice.md)。</span><span class="sxs-lookup"><span data-stu-id="3ca86-106">Call [IMsgServiceAdmin::CopyMsgService](imsgserviceadmin-copymsgservice.md).</span></span>
    
<span data-ttu-id="3ca86-107">复制邮件服务时, 该服务的新实例的配置方式与原始的完全相同。</span><span class="sxs-lookup"><span data-stu-id="3ca86-107">When a message service is copied, the new instance of the service is configured in exactly the same way as the original.</span></span> <span data-ttu-id="3ca86-108">有时**CopyMsgService**将返回错误 MAPI_E_ACCESS_DENIED。</span><span class="sxs-lookup"><span data-stu-id="3ca86-108">Sometimes **CopyMsgService** returns the error MAPI_E_ACCESS_DENIED.</span></span> <span data-ttu-id="3ca86-109">此错误返回最常见的原因是不允许自身重复的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="3ca86-109">The most common cause of this error return is a message service that does not allow itself to be duplicated.</span></span> 
  

