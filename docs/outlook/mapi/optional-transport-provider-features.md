---
title: 可选的传输提供程序功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0bec2c17-b41c-4e46-8961-a55bde1f7326
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fd685e5bc67a3cb0785d9102e94c11ea921f07ed
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776562"
---
# <a name="optional-transport-provider-features"></a><span data-ttu-id="e2e9f-103">可选的传输提供程序功能</span><span class="sxs-lookup"><span data-stu-id="e2e9f-103">Optional Transport Provider Features</span></span>

  
  
<span data-ttu-id="e2e9f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e2e9f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e2e9f-105">传输提供程序可以实现的可选功能包括：</span><span class="sxs-lookup"><span data-stu-id="e2e9f-105">Optional features transport providers can implement include:</span></span>
  
- <span data-ttu-id="e2e9f-106">注册消息和特定于传输提供程序的收件人选项。</span><span class="sxs-lookup"><span data-stu-id="e2e9f-106">Registering message and recipient options specific to the transport provider.</span></span>
    
- <span data-ttu-id="e2e9f-107">维护配置文件，如有必要，以存储配置信息和消息系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="e2e9f-107">Maintaining a profile, if necessary, to store configuration information and credentials to the messaging system.</span></span>
    
- <span data-ttu-id="e2e9f-108">执行任何的所需的邮件系统的凭据进行验证。</span><span class="sxs-lookup"><span data-stu-id="e2e9f-108">Performing any verification of credentials required by the messaging system.</span></span>
    
- <span data-ttu-id="e2e9f-109">使用[IMAPISupport::Notify](imapisupport-notify.md)方法支持感客户端应用程序的事件通知。</span><span class="sxs-lookup"><span data-stu-id="e2e9f-109">Supporting event notification for interested client applications with the [IMAPISupport::Notify](imapisupport-notify.md) method.</span></span> 
    
- <span data-ttu-id="e2e9f-110">显示配置属性表和向导的对话框，以便用户能够配置传输提供程序的设置。</span><span class="sxs-lookup"><span data-stu-id="e2e9f-110">Displaying configuration property sheets and wizard dialog boxes to enable users to configure the transport provider's settings.</span></span>
    
- <span data-ttu-id="e2e9f-111">提供客户端应用程序的邮件送达报告。</span><span class="sxs-lookup"><span data-stu-id="e2e9f-111">Providing message delivery reports to client applications.</span></span>
    

