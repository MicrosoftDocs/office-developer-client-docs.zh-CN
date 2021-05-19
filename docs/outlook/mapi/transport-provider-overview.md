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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433155"
---
# <a name="transport-provider-overview"></a><span data-ttu-id="8cfbc-103">传输提供程序概述</span><span class="sxs-lookup"><span data-stu-id="8cfbc-103">Transport Provider Overview</span></span>

  
  
<span data-ttu-id="8cfbc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8cfbc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8cfbc-105">传输提供程序是动态链接库， (DLL) 充当 MAPI 子系统与一个或多个基础邮件系统之间的中介。</span><span class="sxs-lookup"><span data-stu-id="8cfbc-105">A transport provider is a dynamic-link library (DLL) which acts as an intermediary between the MAPI subsystem and one or more underlying messaging systems.</span></span> <span data-ttu-id="8cfbc-106">邮件系统是一些特定的机制，通过该机制可以收发邮件。</span><span class="sxs-lookup"><span data-stu-id="8cfbc-106">A messaging system is some specific mechanism by which messages are sent and received.</span></span> <span data-ttu-id="8cfbc-107">邮件系统的一些示例如下：</span><span class="sxs-lookup"><span data-stu-id="8cfbc-107">Some examples of messaging systems are:</span></span>
  
- <span data-ttu-id="8cfbc-108">传输提供程序直接将邮件写入的共享网络文件系统。</span><span class="sxs-lookup"><span data-stu-id="8cfbc-108">A shared network file system that the transport provider writes messages to directly.</span></span>
    
- <span data-ttu-id="8cfbc-109">传输提供程序用于连接到消息服务器的 TCP/IP 网络接口。</span><span class="sxs-lookup"><span data-stu-id="8cfbc-109">A TCP/IP network interface that the transport provider uses to connect to a messaging server.</span></span>
    
- <span data-ttu-id="8cfbc-110">用户连接到的联机服务。</span><span class="sxs-lookup"><span data-stu-id="8cfbc-110">An online service that users connect to.</span></span>
    
- <span data-ttu-id="8cfbc-111">基于主机的消息传送或 Office 自动化系统。</span><span class="sxs-lookup"><span data-stu-id="8cfbc-111">A host-based messaging or office automation system.</span></span>
    
- <span data-ttu-id="8cfbc-112">对消息服务器的一组远程过程调用。</span><span class="sxs-lookup"><span data-stu-id="8cfbc-112">A set of remote procedure calls to a messaging server.</span></span>
    
- <span data-ttu-id="8cfbc-113">可用于将数据从一台计算机转移到另一台计算机的一切内容。</span><span class="sxs-lookup"><span data-stu-id="8cfbc-113">Anything that can be used to transfer data from one computer to another.</span></span>
    
<span data-ttu-id="8cfbc-114">传输提供程序 DLL 必须符合 MAPI 指定的接口。</span><span class="sxs-lookup"><span data-stu-id="8cfbc-114">A transport provider DLL must conform to the interface specified by MAPI.</span></span> <span data-ttu-id="8cfbc-115">作为传输提供程序开发人员，您将根据邮件系统中提供的功能实现此接口。</span><span class="sxs-lookup"><span data-stu-id="8cfbc-115">As a transport provider developer, you will implement this interface in terms of the functionality present in the messaging system.</span></span>
  

