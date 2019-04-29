---
title: MAPI 对象包含层次结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 33747835-6eeb-4e07-8f92-3cfa81eecd0f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f5faf3a3d4971b01509d0ff0cfa59451015ba205
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426924"
---
# <a name="mapi-object-containment-hierarchy"></a><span data-ttu-id="825db-103">MAPI 对象包含层次结构</span><span class="sxs-lookup"><span data-stu-id="825db-103">MAPI object containment hierarchy</span></span>
  
<span data-ttu-id="825db-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="825db-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="825db-105">对象之间的包容关系指定一些对象对其他对象进行访问的依赖项。</span><span class="sxs-lookup"><span data-stu-id="825db-105">The containment relationship between objects specifies the dependencies that some objects have on other objects for access.</span></span> <span data-ttu-id="825db-106">对于客户端应用程序, 对特定对象的访问允许对其他对象的访问。</span><span class="sxs-lookup"><span data-stu-id="825db-106">For a client application, access to particular objects enables access to others.</span></span> <span data-ttu-id="825db-107">在某些情况下, 服务提供程序实现的对象之间的包含关系遵循逻辑层次结构。</span><span class="sxs-lookup"><span data-stu-id="825db-107">In some cases, the containment relationship between objects implemented by a service provider follows a logical hierarchy.</span></span> <span data-ttu-id="825db-108">在其他情况下, 它是任意的。</span><span class="sxs-lookup"><span data-stu-id="825db-108">In other cases, it is arbitrary.</span></span> 
  
<span data-ttu-id="825db-109">客户端必须先获取 MAPI 会话对象的访问权限, 然后才能使用其他许多对象 (例如, 服务提供商和 MAPI 通讯簿)。</span><span class="sxs-lookup"><span data-stu-id="825db-109">A client must obtain access to a MAPI session object before it can use many other objects (for example, service providers and the MAPI address book).</span></span>
  
<span data-ttu-id="825db-110">邮件存储区包容基于邮件存储区中的对象之间的层次结构关系: 邮件存储对象本身、文件夹、邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="825db-110">Message store containment is based on the hierarchical relationship between objects in the message store: the message store object itself, folders, messages, and attachments.</span></span> <span data-ttu-id="825db-111">从逻辑上讲, 附件包含在邮件中、文件夹中的邮件和邮件存储中的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="825db-111">Logically, attachments are contained in messages, messages in folders, and folders in the message store.</span></span> <span data-ttu-id="825db-112">包含关系与此逻辑层次结构匹配。</span><span class="sxs-lookup"><span data-stu-id="825db-112">The containment relationship matches this logical hierarchy.</span></span> <span data-ttu-id="825db-113">若要获取对邮件的访问权限, 例如, 客户端必须先访问包含该邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="825db-113">To gain access to a message, for example, a client must first access the folder in which the message is contained.</span></span> <span data-ttu-id="825db-114">"配置文件" 和 "状态" 对象是更多的包含关系的示例。</span><span class="sxs-lookup"><span data-stu-id="825db-114">Profiles and status objects are examples of a more arbitrary containment relationship.</span></span> <span data-ttu-id="825db-115">这两个对象都可通过会话使用。</span><span class="sxs-lookup"><span data-stu-id="825db-115">Both of these objects are available through the session.</span></span> 
  
<span data-ttu-id="825db-116">对于某些对象, 容器仅提供访问权限。</span><span class="sxs-lookup"><span data-stu-id="825db-116">With some objects, containers provide the only access.</span></span> <span data-ttu-id="825db-117">附件和收件人是完全依赖其容器的对象的示例。</span><span class="sxs-lookup"><span data-stu-id="825db-117">Attachments and recipients are examples of objects that are totally dependent on their containers.</span></span> <span data-ttu-id="825db-118">对附件或收件人的唯一访问权限是通过其所属的邮件。</span><span class="sxs-lookup"><span data-stu-id="825db-118">The only access to an attachment or a recipient is through the message to which it belongs.</span></span> <span data-ttu-id="825db-119">其他对象具有备用访问路径。</span><span class="sxs-lookup"><span data-stu-id="825db-119">Other objects have alternate access paths.</span></span> <span data-ttu-id="825db-120">这些对象由创建它们的服务提供程序为它们分配二进制标识符 (称为 "条目标识符")。</span><span class="sxs-lookup"><span data-stu-id="825db-120">These objects are assigned binary identifiers, known as entry identifiers, by the service providers that create them.</span></span> <span data-ttu-id="825db-121">条目标识符可用于直接访问其对象, 使客户端能够绕过包含树。</span><span class="sxs-lookup"><span data-stu-id="825db-121">Entry identifiers can be used to access their objects directly, enabling clients to bypass the containment tree.</span></span> 
  
<span data-ttu-id="825db-122">下图显示了 MAPI 包含的层次结构。</span><span class="sxs-lookup"><span data-stu-id="825db-122">The following illustration shows the MAPI containment hierarchy.</span></span> <span data-ttu-id="825db-123">会话位于树的顶部, 因为它是通过客户端获得对所有其他对象的访问权限的会话完成的。</span><span class="sxs-lookup"><span data-stu-id="825db-123">The session is at the top of the tree because it is through the session that a client gains access to all other objects.</span></span> <span data-ttu-id="825db-124">下一个级别包括邮件存储表、一个表对象, 其中列出了当前会话中所有邮件存储提供程序的属性, 以及用于提供对所有通讯簿提供程序的访问权限的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="825db-124">The next level includes the message store table, a table object that lists properties for all of the message store providers in the current session, and the address book to supply access to all of the address book providers.</span></span> <span data-ttu-id="825db-125">邮件存储表和通讯簿用于访问由特定服务提供程序实现的对象, 如下所示, 以包含顺序。</span><span class="sxs-lookup"><span data-stu-id="825db-125">The message store table and address book are used to access the objects implemented by particular service providers, shown next, in containment order.</span></span>
  
<span data-ttu-id="825db-126">**MAPI 包容层次结构**</span><span class="sxs-lookup"><span data-stu-id="825db-126">**MAPI containment hierarchy**</span></span>
  
<span data-ttu-id="825db-127">![MAPI 包含层次结构](media/amapi_41.gif "MAPI 包含层次结构")</span><span class="sxs-lookup"><span data-stu-id="825db-127">![MAPI containment hierarchy](media/amapi_41.gif "MAPI containment hierarchy")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="825db-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="825db-128">See also</span></span>

- [<span data-ttu-id="825db-129">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="825db-129">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

