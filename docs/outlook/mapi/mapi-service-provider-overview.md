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
# <a name="mapi-service-provider-overview"></a><span data-ttu-id="6b017-103">MAPI 服务提供程序概述</span><span class="sxs-lookup"><span data-stu-id="6b017-103">MAPI Service Provider Overview</span></span>

  
  
<span data-ttu-id="6b017-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6b017-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6b017-105">在 MAPI 子系统和邮件系统之间是各种服务提供商。</span><span class="sxs-lookup"><span data-stu-id="6b017-105">Between the MAPI subsystem and the messaging systems are the various service providers.</span></span> <span data-ttu-id="6b017-106">服务提供程序与将 MAPI 客户端应用程序连接到基础邮件系统的驱动程序类似。</span><span class="sxs-lookup"><span data-stu-id="6b017-106">Service providers are like drivers that connect MAPI client applications to an underlying messaging system.</span></span> <span data-ttu-id="6b017-107">有三种类型的提供程序: 邮件存储提供程序、通讯簿或目录提供程序以及邮件传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="6b017-107">There are three types of providers: message store providers, address book or directory providers, and message transport providers.</span></span> <span data-ttu-id="6b017-108">MAPI 单独支持每种类型的服务, 使供应商能够提供一个或多个自定义服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="6b017-108">MAPI supports each type of service independently, enabling a vendor to offer one or more custom service providers.</span></span> <span data-ttu-id="6b017-109">例如, 供应商可能想要创建一个通讯簿提供程序, 该提供商使用员工的公司电话簿目录, 或创建使用现有数据库的邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="6b017-109">For example, a vendor might want to create an address book provider that uses a corporate telephone book directory of employees or to create a message store provider that uses an existing database.</span></span>
  
<span data-ttu-id="6b017-110">服务提供商通常是由软件开发人员为特定的邮件系统编写的, 他们具有特定系统的专业知识或经验。</span><span class="sxs-lookup"><span data-stu-id="6b017-110">Service providers are typically written for specific messaging systems by software developers who have specialized knowledge or experience with a particular system.</span></span> <span data-ttu-id="6b017-111">例如, microsoft outlook 2013 和 microsoft outlook 2010 移动服务使用通讯簿提供程序在 Outlook 中公开移动通讯簿。</span><span class="sxs-lookup"><span data-stu-id="6b017-111">For example, the Microsoft Outlook 2013 and Microsoft Outlook 2010 Mobile Services use an address book provider to expose a mobile address book in Outlook.</span></span> 
  
<span data-ttu-id="6b017-112">MAPI 提供了包含通讯簿和传输提供程序信息的统一视图的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="6b017-112">MAPI presents client applications with a unified view of address book and transport provider information.</span></span> <span data-ttu-id="6b017-113">此集成方法可防止客户端应用程序将数据映射到适当的提供程序。</span><span class="sxs-lookup"><span data-stu-id="6b017-113">This integrated approach prevents the client application from having to map data to the appropriate provider.</span></span> <span data-ttu-id="6b017-114">它还可防止用户必须在多个通讯簿和传输提供程序寻址方案之间进行协商。</span><span class="sxs-lookup"><span data-stu-id="6b017-114">It also prevents the user from having to negotiate among multiple address book and transport provider addressing schemes.</span></span> <span data-ttu-id="6b017-115">但是, 邮件存储提供程序信息不是统一的, 使用多个邮件存储提供程序的客户端负责单独处理它们。</span><span class="sxs-lookup"><span data-stu-id="6b017-115">Message store provider information, however, is not unified, and clients that use multiple message store providers are responsible for handling them individually.</span></span>
  
<span data-ttu-id="6b017-116">服务提供商与 MAPI 配合使用, 以下列方式创建和发送邮件: 通过使用适合于特定类型或类的邮件的表单创建邮件。</span><span class="sxs-lookup"><span data-stu-id="6b017-116">The service providers work with MAPI to create and send messages in the following way: messages are created by using a form that is appropriate for the specific type, or class, of message.</span></span> <span data-ttu-id="6b017-117">通过客户端应用程序的用户或以编程方式而无需用户交互, 可以使用 MAPI 子系统附带的标准便笺表单发出多封邮件。</span><span class="sxs-lookup"><span data-stu-id="6b017-117">Many messages are made with the standard note form that comes with the MAPI subsystem, either by the user of a client application or programmatically without user interaction.</span></span> <span data-ttu-id="6b017-118">已完成的邮件将发送给一个或多个收件人, 即指定接收邮件的一个或一组用户。</span><span class="sxs-lookup"><span data-stu-id="6b017-118">The completed message is addressed to one or more recipients — a user or group of users designated to receive the message.</span></span> <span data-ttu-id="6b017-119">收件人在某个已安装的通讯簿提供程序拥有的目录中可能有或可能没有条目。</span><span class="sxs-lookup"><span data-stu-id="6b017-119">A recipient might or might not have an entry in a directory that one of the installed address book providers owns.</span></span> <span data-ttu-id="6b017-120">未与已安装的通讯簿提供程序关联的收件人称为 "自定义收件人" 或 "一次性地址"。</span><span class="sxs-lookup"><span data-stu-id="6b017-120">Recipients that are not associated with an installed address book provider are called custom recipients or one-off addresses.</span></span> <span data-ttu-id="6b017-121">一次性地址可以是临时的, 只有在提交邮件后才会持续。</span><span class="sxs-lookup"><span data-stu-id="6b017-121">A one-off address can be temporary, lasting only until the message is submitted.</span></span> 
  
<span data-ttu-id="6b017-122">当客户端应用程序发送邮件时, 邮件存储提供程序会检查每个收件人是否都有唯一且有效的地址, 以及邮件是否包含传输所需的所有信息。</span><span class="sxs-lookup"><span data-stu-id="6b017-122">When the client application sends the message, the message store provider checks that each recipient has a unique and valid address and that the message has all of the information necessary for transmission.</span></span> <span data-ttu-id="6b017-123">如果有关于收件人的问题 (例如, 当有多个收件人具有相同的名称) 时, 通讯簿提供程序负责解决多义性。</span><span class="sxs-lookup"><span data-stu-id="6b017-123">If there is a question about a recipient (for example, when there are multiple recipients with the same name), an address book provider takes care of resolving the ambiguity.</span></span> <span data-ttu-id="6b017-124">然后, 将邮件放在出站队列中。</span><span class="sxs-lookup"><span data-stu-id="6b017-124">The message is then placed in the outbound queue.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6b017-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b017-125">See also</span></span>



[<span data-ttu-id="6b017-126">MAPI 功能和体系结构</span><span class="sxs-lookup"><span data-stu-id="6b017-126">MAPI Features and Architecture</span></span>](mapi-features-and-architecture.md)

