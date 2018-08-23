---
title: MAPI 传输提供程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b193e819-749e-4642-8afc-dbc47b17b617
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 244dae4d3413587b7a37e93328998b153fb8ece3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585330"
---
# <a name="mapi-transport-provider-overview"></a><span data-ttu-id="447c7-103">MAPI 传输提供程序概述</span><span class="sxs-lookup"><span data-stu-id="447c7-103">MAPI Transport Provider Overview</span></span>

  
  
<span data-ttu-id="447c7-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="447c7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="447c7-105">传输提供程序处理邮件传输和接收和必要实现安全性。</span><span class="sxs-lookup"><span data-stu-id="447c7-105">Transport providers handle message transmission and reception and implement security, if necessary.</span></span> <span data-ttu-id="447c7-106">他们还负责任何必要预处理和后处理任务。</span><span class="sxs-lookup"><span data-stu-id="447c7-106">They also take care of any necessary preprocessing and postprocessing tasks.</span></span> <span data-ttu-id="447c7-107">没有为每个活动的邮件系统通常一个传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="447c7-107">There is typically one transport provider for every active messaging system.</span></span>
  
<span data-ttu-id="447c7-108">与传输提供程序通过消息存储提供程序通信客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="447c7-108">Client applications communicate with the transport provider through a message store provider.</span></span> 
  
<span data-ttu-id="447c7-109">传输提供程序注册到 MAPI 处理一个或多个特定类型的收件人的条目。</span><span class="sxs-lookup"><span data-stu-id="447c7-109">Transport providers register with MAPI to handle one or more particular types of recipient entries.</span></span> <span data-ttu-id="447c7-110">准备发送一条消息时，MAPI 必须确定哪些传输提供程序应处理传输。</span><span class="sxs-lookup"><span data-stu-id="447c7-110">When a message is ready to be sent, MAPI must determine which transport provider should handle the transmission.</span></span> <span data-ttu-id="447c7-111">根据收件人的类型，MAPI 甚至可以呼叫在多个传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="447c7-111">Depending on the type of recipient, MAPI can even call upon more than one transport provider.</span></span> <span data-ttu-id="447c7-112">如果不可用的传输提供程序是唯一可以处理收件人，将会推迟消息传输，直到可重新建立与该提供商的连接。</span><span class="sxs-lookup"><span data-stu-id="447c7-112">If an unavailable transport provider is the only one that can handle the recipient, the message transmission will be postponed until a connection with that provider can be reestablished.</span></span>
  
<span data-ttu-id="447c7-113">某些消息系统是安全的系统;所有潜在用户需要允许访问之前输入的一组有效的凭据。</span><span class="sxs-lookup"><span data-stu-id="447c7-113">Some messaging systems are secure systems; all potential users are required to enter a set of valid credentials before access is permitted.</span></span> <span data-ttu-id="447c7-114">MAPI 防止未授权的访问此类安全的消息系统通过传输提供程序在登录时验证凭据。</span><span class="sxs-lookup"><span data-stu-id="447c7-114">MAPI prevents unauthorized access to such secure messaging systems by having the transport provider validate credentials at logon time.</span></span> 
  

