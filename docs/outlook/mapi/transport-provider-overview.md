---
title: 传输提供程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a51547e6-8f0e-45f4-a341-3cfa735112c2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: dbc56b7334d3966696641a84f23a64ce3802e3e4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595270"
---
# <a name="transport-provider-overview"></a><span data-ttu-id="f2522-103">传输提供程序概述</span><span class="sxs-lookup"><span data-stu-id="f2522-103">Transport Provider Overview</span></span>

  
  
<span data-ttu-id="f2522-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f2522-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f2522-105">传输提供程序是作为中介的 MAPI 子系统和一个或多个基础的消息系统的动态链接库 (DLL)。</span><span class="sxs-lookup"><span data-stu-id="f2522-105">A transport provider is a dynamic-link library (DLL) which acts as an intermediary between the MAPI subsystem and one or more underlying messaging systems.</span></span> <span data-ttu-id="f2522-106">邮件系统是一些特定机制所发送和接收邮件。</span><span class="sxs-lookup"><span data-stu-id="f2522-106">A messaging system is some specific mechanism by which messages are sent and received.</span></span> <span data-ttu-id="f2522-107">邮件系统的一些示例包括：</span><span class="sxs-lookup"><span data-stu-id="f2522-107">Some examples of messaging systems are:</span></span>
  
- <span data-ttu-id="f2522-108">共享的网络文件系统传输提供程序直接写入到的邮件。</span><span class="sxs-lookup"><span data-stu-id="f2522-108">A shared network file system that the transport provider writes messages to directly.</span></span>
    
- <span data-ttu-id="f2522-109">传输提供程序用来连接到消息服务器 TCP/IP 网络接口。</span><span class="sxs-lookup"><span data-stu-id="f2522-109">A TCP/IP network interface that the transport provider uses to connect to a messaging server.</span></span>
    
- <span data-ttu-id="f2522-110">用户连接到联机服务。</span><span class="sxs-lookup"><span data-stu-id="f2522-110">An online service that users connect to.</span></span>
    
- <span data-ttu-id="f2522-111">基于主机的消息或 office 自动化系统。</span><span class="sxs-lookup"><span data-stu-id="f2522-111">A host-based messaging or office automation system.</span></span>
    
- <span data-ttu-id="f2522-112">远程过程调用的消息的服务器的一组。</span><span class="sxs-lookup"><span data-stu-id="f2522-112">A set of remote procedure calls to a messaging server.</span></span>
    
- <span data-ttu-id="f2522-113">任何可用于将数据从一台计算机传输到另一个。</span><span class="sxs-lookup"><span data-stu-id="f2522-113">Anything that can be used to transfer data from one computer to another.</span></span>
    
<span data-ttu-id="f2522-114">传输提供程序 DLL 必须符合指定 MAPI 的接口。</span><span class="sxs-lookup"><span data-stu-id="f2522-114">A transport provider DLL must conform to the interface specified by MAPI.</span></span> <span data-ttu-id="f2522-115">作为传输提供程序开发人员，您将实现此接口方面存在邮件系统中的功能。</span><span class="sxs-lookup"><span data-stu-id="f2522-115">As a transport provider developer, you will implement this interface in terms of the functionality present in the messaging system.</span></span>
  

