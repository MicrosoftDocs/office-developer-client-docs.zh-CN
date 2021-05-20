---
title: MAPI 服务提供程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e7cbc79f-3d60-4f21-a378-7b0088ee8ad3
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: bc25158daa9579b5cd6cebe1eee878bf087762a5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431426"
---
# <a name="mapi-service-provider-overview"></a><span data-ttu-id="f6761-103">MAPI 服务提供程序概述</span><span class="sxs-lookup"><span data-stu-id="f6761-103">MAPI Service Provider Overview</span></span>

  
  
<span data-ttu-id="f6761-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f6761-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f6761-105">MAPI 子系统和邮件系统之间是各种服务提供商。</span><span class="sxs-lookup"><span data-stu-id="f6761-105">Between the MAPI subsystem and the messaging systems are the various service providers.</span></span> <span data-ttu-id="f6761-106">服务提供程序与将 MAPI 客户端应用程序连接到基础邮件系统的驱动程序类似。</span><span class="sxs-lookup"><span data-stu-id="f6761-106">Service providers are like drivers that connect MAPI client applications to an underlying messaging system.</span></span> <span data-ttu-id="f6761-107">有三种类型的提供程序：邮件存储提供程序、通讯簿或目录提供程序以及邮件传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="f6761-107">There are three types of providers: message store providers, address book or directory providers, and message transport providers.</span></span> <span data-ttu-id="f6761-108">MAPI 独立支持每种类型的服务，使供应商能够提供一个或多个自定义服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="f6761-108">MAPI supports each type of service independently, enabling a vendor to offer one or more custom service providers.</span></span> <span data-ttu-id="f6761-109">例如，供应商可能希望创建使用员工的公司电话簿目录的通讯簿提供程序，或者创建使用现有数据库的邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="f6761-109">For example, a vendor might want to create an address book provider that uses a corporate telephone book directory of employees or to create a message store provider that uses an existing database.</span></span>
  
<span data-ttu-id="f6761-110">服务提供商通常由具有特定系统的专门知识或经验的软件开发人员为特定邮件系统编写。</span><span class="sxs-lookup"><span data-stu-id="f6761-110">Service providers are typically written for specific messaging systems by software developers who have specialized knowledge or experience with a particular system.</span></span> <span data-ttu-id="f6761-111">例如，Microsoft Outlook 2013和Microsoft Outlook 2010 移动服务使用通讯簿提供程序在通讯簿中公开Outlook。</span><span class="sxs-lookup"><span data-stu-id="f6761-111">For example, the Microsoft Outlook 2013 and Microsoft Outlook 2010 Mobile Services use an address book provider to expose a mobile address book in Outlook.</span></span> 
  
<span data-ttu-id="f6761-112">MAPI 为客户端应用程序提供通讯簿和传输提供程序信息的统一视图。</span><span class="sxs-lookup"><span data-stu-id="f6761-112">MAPI presents client applications with a unified view of address book and transport provider information.</span></span> <span data-ttu-id="f6761-113">此集成方法使客户端应用程序不必将数据映射到相应的提供程序。</span><span class="sxs-lookup"><span data-stu-id="f6761-113">This integrated approach prevents the client application from having to map data to the appropriate provider.</span></span> <span data-ttu-id="f6761-114">它还防止用户不得不在多个通讯簿和传输提供程序寻址方案之间协商。</span><span class="sxs-lookup"><span data-stu-id="f6761-114">It also prevents the user from having to negotiate among multiple address book and transport provider addressing schemes.</span></span> <span data-ttu-id="f6761-115">但是，邮件存储提供程序信息并不统一，并且使用多个邮件存储提供程序的客户端负责单独处理它们。</span><span class="sxs-lookup"><span data-stu-id="f6761-115">Message store provider information, however, is not unified, and clients that use multiple message store providers are responsible for handling them individually.</span></span>
  
<span data-ttu-id="f6761-116">服务提供商通过 MAPI 以下列方式创建和发送邮件：邮件使用适用于特定类型或类别的邮件表单创建。</span><span class="sxs-lookup"><span data-stu-id="f6761-116">The service providers work with MAPI to create and send messages in the following way: messages are created by using a form that is appropriate for the specific type, or class, of message.</span></span> <span data-ttu-id="f6761-117">许多消息都是使用 MAPI 子系统随附的标准笔记窗体发送的，可以是客户端应用程序的用户发送的，也可以以编程方式发送，无需用户交互。</span><span class="sxs-lookup"><span data-stu-id="f6761-117">Many messages are made with the standard note form that comes with the MAPI subsystem, either by the user of a client application or programmatically without user interaction.</span></span> <span data-ttu-id="f6761-118">完成的邮件将发送给一个或多个收件人 — 指定接收邮件的用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="f6761-118">The completed message is addressed to one or more recipients — a user or group of users designated to receive the message.</span></span> <span data-ttu-id="f6761-119">收件人可能（也可能没有）其中一个已安装的通讯簿提供商拥有目录中的条目。</span><span class="sxs-lookup"><span data-stu-id="f6761-119">A recipient might or might not have an entry in a directory that one of the installed address book providers owns.</span></span> <span data-ttu-id="f6761-120">未与已安装通讯簿提供程序关联的收件人称为自定义收件人或一次地址。</span><span class="sxs-lookup"><span data-stu-id="f6761-120">Recipients that are not associated with an installed address book provider are called custom recipients or one-off addresses.</span></span> <span data-ttu-id="f6761-121">一次发送地址可以是临时的，仅在提交邮件之前持续。</span><span class="sxs-lookup"><span data-stu-id="f6761-121">A one-off address can be temporary, lasting only until the message is submitted.</span></span> 
  
<span data-ttu-id="f6761-122">客户端应用程序发送邮件时，邮件存储提供程序会检查每个收件人是否具有唯一且有效的地址，以及邮件是否具有传输所必需的全部信息。</span><span class="sxs-lookup"><span data-stu-id="f6761-122">When the client application sends the message, the message store provider checks that each recipient has a unique and valid address and that the message has all of the information necessary for transmission.</span></span> <span data-ttu-id="f6761-123">例如，如果存在有关收件人 (的问题，当有多个收件人同名) ，通讯簿提供商会负责解决歧义问题。</span><span class="sxs-lookup"><span data-stu-id="f6761-123">If there is a question about a recipient (for example, when there are multiple recipients with the same name), an address book provider takes care of resolving the ambiguity.</span></span> <span data-ttu-id="f6761-124">然后，将邮件置于出站队列中。</span><span class="sxs-lookup"><span data-stu-id="f6761-124">The message is then placed in the outbound queue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f6761-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6761-125">See also</span></span>



[<span data-ttu-id="f6761-126">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="f6761-126">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

