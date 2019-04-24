---
title: 传输提供程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a51547e6-8f0e-45f4-a341-3cfa735112c2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 53bdba624ba759debba25bae78fb45b0f9d5247e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356635"
---
# <a name="transport-provider-overview"></a><span data-ttu-id="c7a2f-103">传输提供程序概述</span><span class="sxs-lookup"><span data-stu-id="c7a2f-103">Transport Provider Overview</span></span>

  
  
<span data-ttu-id="c7a2f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c7a2f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c7a2f-105">传输提供程序是一个动态链接库 (DLL), 它充当 MAPI 子系统和一个或多个基础邮件系统之间的媒介。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-105">A transport provider is a dynamic-link library (DLL) which acts as an intermediary between the MAPI subsystem and one or more underlying messaging systems.</span></span> <span data-ttu-id="c7a2f-106">邮件系统是发送和接收邮件的一些特定机制。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-106">A messaging system is some specific mechanism by which messages are sent and received.</span></span> <span data-ttu-id="c7a2f-107">邮件系统的一些示例包括:</span><span class="sxs-lookup"><span data-stu-id="c7a2f-107">Some examples of messaging systems are:</span></span>
  
- <span data-ttu-id="c7a2f-108">传输提供程序直接向其写入邮件的共享网络文件系统。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-108">A shared network file system that the transport provider writes messages to directly.</span></span>
    
- <span data-ttu-id="c7a2f-109">传输提供程序用于连接到邮件服务器的 tcp/ip 网络接口。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-109">A TCP/IP network interface that the transport provider uses to connect to a messaging server.</span></span>
    
- <span data-ttu-id="c7a2f-110">用户连接到的联机服务。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-110">An online service that users connect to.</span></span>
    
- <span data-ttu-id="c7a2f-111">基于主机的消息传送或 office 自动化系统。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-111">A host-based messaging or office automation system.</span></span>
    
- <span data-ttu-id="c7a2f-112">对邮件传递服务器的一组远程过程调用。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-112">A set of remote procedure calls to a messaging server.</span></span>
    
- <span data-ttu-id="c7a2f-113">可用于将数据从一台计算机传输到另一台计算机的任何内容。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-113">Anything that can be used to transfer data from one computer to another.</span></span>
    
<span data-ttu-id="c7a2f-114">传输提供程序 DLL 必须符合 MAPI 指定的接口。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-114">A transport provider DLL must conform to the interface specified by MAPI.</span></span> <span data-ttu-id="c7a2f-115">作为传输提供程序开发人员, 你将根据邮件系统中提供的功能来实现此接口。</span><span class="sxs-lookup"><span data-stu-id="c7a2f-115">As a transport provider developer, you will implement this interface in terms of the functionality present in the messaging system.</span></span>
  

