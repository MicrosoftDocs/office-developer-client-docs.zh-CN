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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357342"
---
# <a name="mapi-transport-provider-overview"></a><span data-ttu-id="67fff-103">MAPI 传输提供程序概述</span><span class="sxs-lookup"><span data-stu-id="67fff-103">MAPI Transport Provider Overview</span></span>

  
  
<span data-ttu-id="67fff-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="67fff-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="67fff-105">传输提供程序处理邮件传输和接收并实现安全性 (如有必要)。</span><span class="sxs-lookup"><span data-stu-id="67fff-105">Transport providers handle message transmission and reception and implement security, if necessary.</span></span> <span data-ttu-id="67fff-106">他们还负责处理任何必要的预处理和后处理任务。</span><span class="sxs-lookup"><span data-stu-id="67fff-106">They also take care of any necessary preprocessing and postprocessing tasks.</span></span> <span data-ttu-id="67fff-107">通常每个活动邮件系统都有一个传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="67fff-107">There is typically one transport provider for every active messaging system.</span></span>
  
<span data-ttu-id="67fff-108">客户端应用程序通过邮件存储提供程序与传输提供程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="67fff-108">Client applications communicate with the transport provider through a message store provider.</span></span> 
  
<span data-ttu-id="67fff-109">传输提供程序注册 MAPI 以处理一个或多个特定类型的收件人条目。</span><span class="sxs-lookup"><span data-stu-id="67fff-109">Transport providers register with MAPI to handle one or more particular types of recipient entries.</span></span> <span data-ttu-id="67fff-110">当邮件准备好发送时, MAPI 必须确定哪种传输提供程序应处理传输。</span><span class="sxs-lookup"><span data-stu-id="67fff-110">When a message is ready to be sent, MAPI must determine which transport provider should handle the transmission.</span></span> <span data-ttu-id="67fff-111">根据收件人的类型, MAPI 甚至可以在多个传输提供程序上进行调用。</span><span class="sxs-lookup"><span data-stu-id="67fff-111">Depending on the type of recipient, MAPI can even call upon more than one transport provider.</span></span> <span data-ttu-id="67fff-112">如果无法使用的传输提供程序是唯一可以处理收件人的传输提供程序, 则将延迟邮件传输, 直到可以重新建立与该提供程序的连接。</span><span class="sxs-lookup"><span data-stu-id="67fff-112">If an unavailable transport provider is the only one that can handle the recipient, the message transmission will be postponed until a connection with that provider can be reestablished.</span></span>
  
<span data-ttu-id="67fff-113">某些邮件系统是安全系统;在允许访问之前, 所有潜在用户都需要输入一组有效的凭据。</span><span class="sxs-lookup"><span data-stu-id="67fff-113">Some messaging systems are secure systems; all potential users are required to enter a set of valid credentials before access is permitted.</span></span> <span data-ttu-id="67fff-114">MAPI 通过让传输提供程序在登录时验证凭据来阻止对此类安全邮件系统的未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="67fff-114">MAPI prevents unauthorized access to such secure messaging systems by having the transport provider validate credentials at logon time.</span></span> 
  

