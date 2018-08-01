---
title: MAPI 对象包容层次结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 33747835-6eeb-4e07-8f92-3cfa81eecd0f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 94fea23f71e6bc29b038db38f6f06cda0f85d635
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776284"
---
# <a name="mapi-object-containment-hierarchy"></a><span data-ttu-id="7928b-103">MAPI 对象包容层次结构</span><span class="sxs-lookup"><span data-stu-id="7928b-103">MAPI object containment hierarchy</span></span>
  
<span data-ttu-id="7928b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7928b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7928b-105">对象之间的内嵌关系指定具有访问的其他对象的某些对象的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="7928b-105">The containment relationship between objects specifies the dependencies that some objects have on other objects for access.</span></span> <span data-ttu-id="7928b-106">客户端应用程序特定的对象的访问启用向其他人的访问。</span><span class="sxs-lookup"><span data-stu-id="7928b-106">For a client application, access to particular objects enables access to others.</span></span> <span data-ttu-id="7928b-107">在某些情况下，由服务提供商实现的对象的内嵌关系遵循逻辑层次结构。</span><span class="sxs-lookup"><span data-stu-id="7928b-107">In some cases, the containment relationship between objects implemented by a service provider follows a logical hierarchy.</span></span> <span data-ttu-id="7928b-108">在其他情况下，它是任意的。</span><span class="sxs-lookup"><span data-stu-id="7928b-108">In other cases, it is arbitrary.</span></span> 
  
<span data-ttu-id="7928b-109">可以使用多个其他对象 （例如，服务提供商和 MAPI 通讯簿） 之前，客户端必须获取 MAPI 会话对象的访问权。</span><span class="sxs-lookup"><span data-stu-id="7928b-109">A client must obtain access to a MAPI session object before it can use many other objects (for example, service providers and the MAPI address book).</span></span>
  
<span data-ttu-id="7928b-110">消息存储包容基于消息存储区中的对象之间的分层关系： 消息存储对象本身、 文件夹、 邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="7928b-110">Message store containment is based on the hierarchical relationship between objects in the message store: the message store object itself, folders, messages, and attachments.</span></span> <span data-ttu-id="7928b-111">逻辑上，在文件夹和邮件存储区中的文件夹中的邮件的邮件包含附件。</span><span class="sxs-lookup"><span data-stu-id="7928b-111">Logically, attachments are contained in messages, messages in folders, and folders in the message store.</span></span> <span data-ttu-id="7928b-112">内嵌关系匹配此逻辑层次结构。</span><span class="sxs-lookup"><span data-stu-id="7928b-112">The containment relationship matches this logical hierarchy.</span></span> <span data-ttu-id="7928b-113">若要访问一条消息，例如，客户端必须首先访问在其中包含邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="7928b-113">To gain access to a message, for example, a client must first access the folder in which the message is contained.</span></span> <span data-ttu-id="7928b-114">配置文件和状态对象是更任意包容关系的示例。</span><span class="sxs-lookup"><span data-stu-id="7928b-114">Profiles and status objects are examples of a more arbitrary containment relationship.</span></span> <span data-ttu-id="7928b-115">两个对象可通过会话。</span><span class="sxs-lookup"><span data-stu-id="7928b-115">Both of these objects are available through the session.</span></span> 
  
<span data-ttu-id="7928b-116">与某些对象，容器提供唯一的访问。</span><span class="sxs-lookup"><span data-stu-id="7928b-116">With some objects, containers provide the only access.</span></span> <span data-ttu-id="7928b-117">附件和收件人是完全取决于其容器的对象的示例。</span><span class="sxs-lookup"><span data-stu-id="7928b-117">Attachments and recipients are examples of objects that are totally dependent on their containers.</span></span> <span data-ttu-id="7928b-118">仅访问附件或收件人是通过其所属的消息。</span><span class="sxs-lookup"><span data-stu-id="7928b-118">The only access to an attachment or a recipient is through the message to which it belongs.</span></span> <span data-ttu-id="7928b-119">其他对象具有备用访问路径。</span><span class="sxs-lookup"><span data-stu-id="7928b-119">Other objects have alternate access paths.</span></span> <span data-ttu-id="7928b-120">这些对象分配二进制标识符，称为由服务提供程序创建它们的项标识符。</span><span class="sxs-lookup"><span data-stu-id="7928b-120">These objects are assigned binary identifiers, known as entry identifiers, by the service providers that create them.</span></span> <span data-ttu-id="7928b-121">条目标识符可直接访问其对象启用绕过包容树的客户端。</span><span class="sxs-lookup"><span data-stu-id="7928b-121">Entry identifiers can be used to access their objects directly, enabling clients to bypass the containment tree.</span></span> 
  
<span data-ttu-id="7928b-122">下图显示了 MAPI 包容层次结构。</span><span class="sxs-lookup"><span data-stu-id="7928b-122">The following illustration shows the MAPI containment hierarchy.</span></span> <span data-ttu-id="7928b-123">会话已树的顶部，因为它是通过会话客户端获得访问所有其他对象。</span><span class="sxs-lookup"><span data-stu-id="7928b-123">The session is at the top of the tree because it is through the session that a client gains access to all other objects.</span></span> <span data-ttu-id="7928b-124">下一步级别包括消息存储表，table 对象，在当前会话和通讯簿提供访问通讯簿提供程序的所有消息存储提供程序的所有列出的属性。</span><span class="sxs-lookup"><span data-stu-id="7928b-124">The next level includes the message store table, a table object that lists properties for all of the message store providers in the current session, and the address book to supply access to all of the address book providers.</span></span> <span data-ttu-id="7928b-125">消息存储表和地址簿用于访问显示下一步，包容顺序的特定服务提供程序实现的对象。</span><span class="sxs-lookup"><span data-stu-id="7928b-125">The message store table and address book are used to access the objects implemented by particular service providers, shown next, in containment order.</span></span>
  
<span data-ttu-id="7928b-126">**MAPI 包容层次结构**</span><span class="sxs-lookup"><span data-stu-id="7928b-126">**MAPI containment hierarchy**</span></span>
  
<span data-ttu-id="7928b-127">![MAPI 包容层次结构](media/amapi_41.gif "MAPI 包容层次结构")</span><span class="sxs-lookup"><span data-stu-id="7928b-127">![MAPI containment hierarchy](media/amapi_41.gif "MAPI containment hierarchy")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7928b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7928b-128">See also</span></span>

- [<span data-ttu-id="7928b-129">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="7928b-129">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

