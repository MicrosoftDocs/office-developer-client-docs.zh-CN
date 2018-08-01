---
title: MAPI 服务提供程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e7cbc79f-3d60-4f21-a378-7b0088ee8ad3
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: 15a53a0bb16db3683e4c1320ac2e54648c8c697b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776327"
---
# <a name="mapi-service-provider-overview"></a><span data-ttu-id="440f3-103">MAPI 服务提供程序概述</span><span class="sxs-lookup"><span data-stu-id="440f3-103">MAPI Service Provider Overview</span></span>

  
  
<span data-ttu-id="440f3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="440f3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="440f3-105">MAPI 子系统和消息的系统之间的各种服务提供商。</span><span class="sxs-lookup"><span data-stu-id="440f3-105">Between the MAPI subsystem and the messaging systems are the various service providers.</span></span> <span data-ttu-id="440f3-106">服务提供商就像连接到基础消息系统的 MAPI 客户端应用程序的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="440f3-106">Service providers are like drivers that connect MAPI client applications to an underlying messaging system.</span></span> <span data-ttu-id="440f3-107">有三种类型的提供程序： 消息存储提供程序、 通讯簿或目录提供商和邮件传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="440f3-107">There are three types of providers: message store providers, address book or directory providers, and message transport providers.</span></span> <span data-ttu-id="440f3-108">MAPI 支持每种服务独立，使供应商，以提供一个或多个自定义服务提供商。</span><span class="sxs-lookup"><span data-stu-id="440f3-108">MAPI supports each type of service independently, enabling a vendor to offer one or more custom service providers.</span></span> <span data-ttu-id="440f3-109">例如，供应商可能希望在创建使用员工的公司电话簿目录通讯簿提供程序或创建一个使用现有数据库的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="440f3-109">For example, a vendor might want to create an address book provider that uses a corporate telephone book directory of employees or to create a message store provider that uses an existing database.</span></span>
  
<span data-ttu-id="440f3-110">服务提供商的软件开发人员有专门的知识或体验的通常编写特定的邮件系统的特定的系统。</span><span class="sxs-lookup"><span data-stu-id="440f3-110">Service providers are typically written for specific messaging systems by software developers who have specialized knowledge or experience with a particular system.</span></span> <span data-ttu-id="440f3-111">例如，Microsoft Outlook 2013 和 Microsoft Outlook 2010 Mobile 服务使用通讯簿提供程序公开在 Outlook 中的手机通讯簿。</span><span class="sxs-lookup"><span data-stu-id="440f3-111">For example, the Microsoft Outlook 2013 and Microsoft Outlook 2010 Mobile Services use an address book provider to expose a mobile address book in Outlook.</span></span> 
  
<span data-ttu-id="440f3-112">MAPI 提供统一的地址簿和传输提供程序信息的视图的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="440f3-112">MAPI presents client applications with a unified view of address book and transport provider information.</span></span> <span data-ttu-id="440f3-113">此集成的方法防止客户端应用程序无需将数据映射到相应的提供程序。</span><span class="sxs-lookup"><span data-stu-id="440f3-113">This integrated approach prevents the client application from having to map data to the appropriate provider.</span></span> <span data-ttu-id="440f3-114">它还可以阻止用户无需协商之间多个通讯簿和传输提供程序寻址方案。</span><span class="sxs-lookup"><span data-stu-id="440f3-114">It also prevents the user from having to negotiate among multiple address book and transport provider addressing schemes.</span></span> <span data-ttu-id="440f3-115">消息存储提供程序的信息，但是，不统一的并且负责处理它们分别使用多个消息存储提供程序的客户端。</span><span class="sxs-lookup"><span data-stu-id="440f3-115">Message store provider information, however, is not unified, and clients that use multiple message store providers are responsible for handling them individually.</span></span>
  
<span data-ttu-id="440f3-116">服务提供商使用 MAPI 创建和发送消息，采用以下方式： 通过使用适用于特定类型的类，邮件的窗体创建消息。</span><span class="sxs-lookup"><span data-stu-id="440f3-116">The service providers work with MAPI to create and send messages in the following way: messages are created by using a form that is appropriate for the specific type, or class, of message.</span></span> <span data-ttu-id="440f3-117">许多消息进行与标准注释表单附带的 MAPI 子系统，可由用户的客户端应用程序或以编程方式无需用户交互。</span><span class="sxs-lookup"><span data-stu-id="440f3-117">Many messages are made with the standard note form that comes with the MAPI subsystem, either by the user of a client application or programmatically without user interaction.</span></span> <span data-ttu-id="440f3-118">已完成的消息将发送到一个或多个收件人 — 用户组的指定其接收邮件。</span><span class="sxs-lookup"><span data-stu-id="440f3-118">The completed message is addressed to one or more recipients — a user or group of users designated to receive the message.</span></span> <span data-ttu-id="440f3-119">收件人可能或可能不具有的目录中安装的通讯簿提供程序之一拥有一个条目。</span><span class="sxs-lookup"><span data-stu-id="440f3-119">A recipient might or might not have an entry in a directory that one of the installed address book providers owns.</span></span> <span data-ttu-id="440f3-120">未与安装的通讯簿提供程序关联的收件人被称为自定义收件人或一次性地址。</span><span class="sxs-lookup"><span data-stu-id="440f3-120">Recipients that are not associated with an installed address book provider are called custom recipients or one-off addresses.</span></span> <span data-ttu-id="440f3-121">一次性地址可以是临时，持续仅之前该邮件提交。</span><span class="sxs-lookup"><span data-stu-id="440f3-121">A one-off address can be temporary, lasting only until the message is submitted.</span></span> 
  
<span data-ttu-id="440f3-122">当客户端应用程序发送邮件时，消息存储提供程序将检查每个收件人具有唯一的并且有效地址以及邮件是否具有所有传输所需的信息。</span><span class="sxs-lookup"><span data-stu-id="440f3-122">When the client application sends the message, the message store provider checks that each recipient has a unique and valid address and that the message has all of the information necessary for transmission.</span></span> <span data-ttu-id="440f3-123">如果没有疑问 （例如，具有相同名称的多个收件人时） 的收件人，通讯簿提供程序负责解决歧义。</span><span class="sxs-lookup"><span data-stu-id="440f3-123">If there is a question about a recipient (for example, when there are multiple recipients with the same name), an address book provider takes care of resolving the ambiguity.</span></span> <span data-ttu-id="440f3-124">邮件然后放在出站队列。</span><span class="sxs-lookup"><span data-stu-id="440f3-124">The message is then placed in the outbound queue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="440f3-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="440f3-125">See also</span></span>



[<span data-ttu-id="440f3-126">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="440f3-126">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

