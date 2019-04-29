---
title: MAPI 通讯簿
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6703ba3f-54a5-4059-b10a-1d42a9e81be1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 14f9bff8dbf55456c37e70e1ae7a0c236471b6c0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410600"
---
# <a name="mapi-address-book"></a><span data-ttu-id="88b14-103">MAPI 通讯簿</span><span class="sxs-lookup"><span data-stu-id="88b14-103">MAPI Address Book</span></span>

  
  
<span data-ttu-id="88b14-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88b14-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="88b14-105">集成通讯簿是 MAPI 实现的对象, 用于提供对来自配置文件中所有通讯簿提供程序的寻址信息的集成集合的访问。</span><span class="sxs-lookup"><span data-stu-id="88b14-105">The integrated address book is an object that MAPI implements to provide access to an integrated collection of addressing information from all of the address book providers in the profile.</span></span> <span data-ttu-id="88b14-106">通过通讯簿, 客户端应用程序和服务提供商不必区分邮件系统的唯一寻址方案。</span><span class="sxs-lookup"><span data-stu-id="88b14-106">With the address book, client applications and service providers do not have to differentiate between the unique addressing schemes of messaging systems.</span></span> <span data-ttu-id="88b14-107">相反, 他们可以在任何邮件系统中查找任何收件人的地址, 只要安装了邮件系统的通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="88b14-107">Instead, they can look up the addresses of any recipients in any messaging system, as long as the address book provider for the messaging system is installed.</span></span>
  
<span data-ttu-id="88b14-108">可以通过编程方式访问通讯簿, 无需用户干预, 也可以交互方式通过使用通用对话框。</span><span class="sxs-lookup"><span data-stu-id="88b14-108">The address book can be accessed programmatically, without user intervention, or interactively through the use of common dialog boxes.</span></span> <span data-ttu-id="88b14-109">MAPI 包括用于显示通讯簿中条目的摘要列表的对话框、有关特定收件人的详细信息, 当用户创建无法映射到唯一地址的收件人时发出警告, 以及用于创建新的模板表单的一组模板表单。发送.</span><span class="sxs-lookup"><span data-stu-id="88b14-109">MAPI includes dialog boxes to display a summary list of the entries in the address book, detailed information about a particular recipient, a warning when a user creates a recipient that cannot be mapped to a unique address, and a set of template forms for creating new recipients.</span></span>
  
<span data-ttu-id="88b14-110">MAPI 通讯簿在结构中类似于邮件存储区, 因为它是按层次组织的。</span><span class="sxs-lookup"><span data-stu-id="88b14-110">The MAPI address book is similar in structure to a message store in that it is organized hierarchically.</span></span> <span data-ttu-id="88b14-111">通讯簿提供了对由通讯簿提供程序实现的三种类型的对象的访问权限:</span><span class="sxs-lookup"><span data-stu-id="88b14-111">The address book provides access to three types of objects implemented by an address book provider:</span></span>
  
- <span data-ttu-id="88b14-112">通讯簿容器对象。</span><span class="sxs-lookup"><span data-stu-id="88b14-112">An address book container object.</span></span>
    
- <span data-ttu-id="88b14-113">通讯组列表对象。</span><span class="sxs-lookup"><span data-stu-id="88b14-113">A distribution list object.</span></span>
    
- <span data-ttu-id="88b14-114">消息传递用户对象。</span><span class="sxs-lookup"><span data-stu-id="88b14-114">A messaging user object.</span></span>
    
<span data-ttu-id="88b14-115">通过其通讯簿提供程序分配的唯一条目标识符访问每种类型的对象。</span><span class="sxs-lookup"><span data-stu-id="88b14-115">Each of these types of objects is accessed through its unique entry identifier that is assigned by its address book provider.</span></span> 
  
<span data-ttu-id="88b14-116">通讯簿容器类似于文件夹, 因为它们保留不同类型的对象。</span><span class="sxs-lookup"><span data-stu-id="88b14-116">Address book containers are similar to folders in that they hold objects of different types.</span></span> <span data-ttu-id="88b14-117">通讯簿容器可以保留其他通讯簿容器以及邮件用户和通讯组列表对象。</span><span class="sxs-lookup"><span data-stu-id="88b14-117">An address book container can hold other address book containers as well as messaging user and distribution list objects.</span></span> <span data-ttu-id="88b14-118">通讯簿容器用于组织和存储通讯簿对象。</span><span class="sxs-lookup"><span data-stu-id="88b14-118">Address book containers are used to organize and store address book objects.</span></span>
  
<span data-ttu-id="88b14-119">为了实现通讯簿的集成外观, 通讯簿提供程序向 MAPI 公开了零个、一个或多个顶级容器, 并将其合并并在一个顶级容器下显示结果。</span><span class="sxs-lookup"><span data-stu-id="88b14-119">To achieve the address book's integrated appearance, address book providers expose zero, one, or more of their top-level containers to MAPI which merges them and displays the results under a single top-level container.</span></span> <span data-ttu-id="88b14-120">通讯簿提供程序可以选择为一种类型的邮件会话和另一个会话的不同集公开一组容器。</span><span class="sxs-lookup"><span data-stu-id="88b14-120">Address book providers can choose to expose one set of containers for one type of messaging session and a different set for another session.</span></span> <span data-ttu-id="88b14-121">通讯簿提供程序也可能没有顶级容器, 只公开可用于创建收件人的模板列表。</span><span class="sxs-lookup"><span data-stu-id="88b14-121">It is also possible for address book providers to have no top-level containers and expose only a list of templates that can be used to create recipients.</span></span>
  
<span data-ttu-id="88b14-122">邮件收件人是通过邮件用户和通讯组列表对象实现的。</span><span class="sxs-lookup"><span data-stu-id="88b14-122">Message recipients are implemented with messaging user and distribution list objects.</span></span> <span data-ttu-id="88b14-123">邮件传递用户是单个收件人;通讯组列表是组收件人。</span><span class="sxs-lookup"><span data-stu-id="88b14-123">Messaging users are individual recipients; distribution lists are group recipients.</span></span> <span data-ttu-id="88b14-124">每个邮件用户都有一个特定类型的唯一地址, 该地址由特定的邮件系统处理。</span><span class="sxs-lookup"><span data-stu-id="88b14-124">Each messaging user has a unique address of a particular type handled by a particular messaging system.</span></span> <span data-ttu-id="88b14-125">通讯组列表是一个已命名的收件人集合。</span><span class="sxs-lookup"><span data-stu-id="88b14-125">A distribution list is a named collection of recipients.</span></span> <span data-ttu-id="88b14-126">通讯组列表可以包含邮件传递用户对象和其他通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="88b14-126">Distribution lists can contain messaging user objects and other distribution lists.</span></span> <span data-ttu-id="88b14-127">当客户端应用程序的用户将邮件发送到通讯组列表时, 该邮件将被发送到列表的每个邮件用户成员。</span><span class="sxs-lookup"><span data-stu-id="88b14-127">When a user of a client application sends a message to a distribution list, the message is being sent to each of the list's messaging user members.</span></span> 
  
<span data-ttu-id="88b14-128">邮件用户和通讯组列表具有一组称为基本地址属性的五个属性。</span><span class="sxs-lookup"><span data-stu-id="88b14-128">Messaging users and distribution lists have a set of five properties that are known as the base address properties.</span></span> <span data-ttu-id="88b14-129">这些属性是必需的属性, 如下所示进行简要说明。</span><span class="sxs-lookup"><span data-stu-id="88b14-129">These are required properties and are briefly described as follows.</span></span>
  
|<span data-ttu-id="88b14-130">**基址属性**</span><span class="sxs-lookup"><span data-stu-id="88b14-130">**Base address property**</span></span>|<span data-ttu-id="88b14-131">**说明**</span><span class="sxs-lookup"><span data-stu-id="88b14-131">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="88b14-132">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="88b14-132">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="88b14-133">收件人的地址类型。</span><span class="sxs-lookup"><span data-stu-id="88b14-133">Type of address for the recipient.</span></span> <span data-ttu-id="88b14-134">每种地址类型遵循一种特定的格式, 并与特定的邮件系统一起使用。</span><span class="sxs-lookup"><span data-stu-id="88b14-134">Each address type follows a particular format and is used with a particular messaging system.</span></span>  <br/> |
|<span data-ttu-id="88b14-135">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="88b14-135">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="88b14-136">收件人的可显示名称。</span><span class="sxs-lookup"><span data-stu-id="88b14-136">Displayable name for the recipient.</span></span>  <br/> |
|<span data-ttu-id="88b14-137">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="88b14-137">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="88b14-138">收件人的地址。</span><span class="sxs-lookup"><span data-stu-id="88b14-138">Address of the recipient.</span></span>  <br/> |
|<span data-ttu-id="88b14-139">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="88b14-139">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="88b14-140">用于访问收件人的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="88b14-140">Entry identifier used to access the recipient.</span></span>  <br/> |
|<span data-ttu-id="88b14-141">**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="88b14-141">**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="88b14-142">用于标识收件人的二进制可比较密钥。</span><span class="sxs-lookup"><span data-stu-id="88b14-142">Binary comparable key used to identify the recipient.</span></span>  <br/> |
   
<span data-ttu-id="88b14-143">MAPI 定义了许多属性组, 它们是基址属性的变体。</span><span class="sxs-lookup"><span data-stu-id="88b14-143">MAPI defines many groups of properties that are variations of the base address properties.</span></span> <span data-ttu-id="88b14-144">这些其他组描述了不同情况下的邮件用户和通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="88b14-144">These other groups describe messaging users and distribution lists in different situations.</span></span> <span data-ttu-id="88b14-145">例如, 一组属性描述了邮件的代理发件人和代理收件人的另一个组。</span><span class="sxs-lookup"><span data-stu-id="88b14-145">For example, one group of properties describes the delegate sender of a message and another group the delegate recipient.</span></span>
  

