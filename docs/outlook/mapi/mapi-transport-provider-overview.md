---
title: MAPI 传输提供程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b193e819-749e-4642-8afc-dbc47b17b617
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 20b03f7c52ec86d1fb554bf69c53947c3dda4f36
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404573"
---
# <a name="mapi-transport-provider-overview"></a><span data-ttu-id="86ee3-103">MAPI 传输提供程序概述</span><span class="sxs-lookup"><span data-stu-id="86ee3-103">MAPI Transport Provider Overview</span></span>

  
  
<span data-ttu-id="86ee3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="86ee3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="86ee3-105">传输提供商负责处理邮件传输和接收，并在必要时实现安全性。</span><span class="sxs-lookup"><span data-stu-id="86ee3-105">Transport providers handle message transmission and reception and implement security, if necessary.</span></span> <span data-ttu-id="86ee3-106">它们还负责任何必要的预处理和后处理任务。</span><span class="sxs-lookup"><span data-stu-id="86ee3-106">They also take care of any necessary preprocessing and postprocessing tasks.</span></span> <span data-ttu-id="86ee3-107">每个活动邮件系统通常有一个传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="86ee3-107">There is typically one transport provider for every active messaging system.</span></span>
  
<span data-ttu-id="86ee3-108">客户端应用程序通过邮件存储提供程序与传输提供程序通信。</span><span class="sxs-lookup"><span data-stu-id="86ee3-108">Client applications communicate with the transport provider through a message store provider.</span></span> 
  
<span data-ttu-id="86ee3-109">传输提供程序在 MAPI 中注册以处理一个或多个特定类型的收件人条目。</span><span class="sxs-lookup"><span data-stu-id="86ee3-109">Transport providers register with MAPI to handle one or more particular types of recipient entries.</span></span> <span data-ttu-id="86ee3-110">当准备好发送邮件时，MAPI 必须确定哪个传输提供程序应处理传输。</span><span class="sxs-lookup"><span data-stu-id="86ee3-110">When a message is ready to be sent, MAPI must determine which transport provider should handle the transmission.</span></span> <span data-ttu-id="86ee3-111">根据收件人的类型，MAPI 甚至可以调用多个传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="86ee3-111">Depending on the type of recipient, MAPI can even call upon more than one transport provider.</span></span> <span data-ttu-id="86ee3-112">如果不可用的传输提供程序是唯一可以处理收件人的传输提供程序，则邮件传输将延迟，直到可以重新建立与该提供商的连接。</span><span class="sxs-lookup"><span data-stu-id="86ee3-112">If an unavailable transport provider is the only one that can handle the recipient, the message transmission will be postponed until a connection with that provider can be reestablished.</span></span>
  
<span data-ttu-id="86ee3-113">某些邮件系统是安全系统;所有潜在用户都需要在允许访问之前输入一组有效凭据。</span><span class="sxs-lookup"><span data-stu-id="86ee3-113">Some messaging systems are secure systems; all potential users are required to enter a set of valid credentials before access is permitted.</span></span> <span data-ttu-id="86ee3-114">MAPI 通过让传输提供程序在登录时验证凭据来防止对此类安全邮件系统的未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="86ee3-114">MAPI prevents unauthorized access to such secure messaging systems by having the transport provider validate credentials at logon time.</span></span> 
  

