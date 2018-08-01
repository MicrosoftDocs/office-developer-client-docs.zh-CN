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
ms.openlocfilehash: b328a65f400e424fb2cd177e710fb8bcffa392c2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776174"
---
# <a name="mapi-address-book"></a><span data-ttu-id="b756d-103">MAPI 通讯簿</span><span class="sxs-lookup"><span data-stu-id="b756d-103">MAPI Address Book</span></span>

  
  
<span data-ttu-id="b756d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b756d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b756d-105">集成的通讯簿是 MAPI 实现以提供从配置文件中的地址簿提供程序的所有访问寻址信息集成集合的对象。</span><span class="sxs-lookup"><span data-stu-id="b756d-105">The integrated address book is an object that MAPI implements to provide access to an integrated collection of addressing information from all of the address book providers in the profile.</span></span> <span data-ttu-id="b756d-106">通讯簿中，使用客户端应用程序和服务提供商不必区分消息系统的唯一的寻址方案。</span><span class="sxs-lookup"><span data-stu-id="b756d-106">With the address book, client applications and service providers do not have to differentiate between the unique addressing schemes of messaging systems.</span></span> <span data-ttu-id="b756d-107">相反，它们可查找任何收件人的地址在任何消息系统中，只要安装在邮件系统通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="b756d-107">Instead, they can look up the addresses of any recipients in any messaging system, as long as the address book provider for the messaging system is installed.</span></span>
  
<span data-ttu-id="b756d-108">无需用户干预，或以交互方式使用通用对话框可以以编程方式访问通讯簿。</span><span class="sxs-lookup"><span data-stu-id="b756d-108">The address book can be accessed programmatically, without user intervention, or interactively through the use of common dialog boxes.</span></span> <span data-ttu-id="b756d-109">MAPI 包括在通讯簿，特定收件人，当用户创建的收件人，无法映射到唯一的地址和一套将表单模板创建新的警告的详细信息中显示的项的摘要列表的对话框收件人。</span><span class="sxs-lookup"><span data-stu-id="b756d-109">MAPI includes dialog boxes to display a summary list of the entries in the address book, detailed information about a particular recipient, a warning when a user creates a recipient that cannot be mapped to a unique address, and a set of template forms for creating new recipients.</span></span>
  
<span data-ttu-id="b756d-110">MAPI 通讯簿的消息存储结构类似，在于层次结构组织。</span><span class="sxs-lookup"><span data-stu-id="b756d-110">The MAPI address book is similar in structure to a message store in that it is organized hierarchically.</span></span> <span data-ttu-id="b756d-111">通讯簿提供了三种类型的通讯簿提供程序实现的对象的访问：</span><span class="sxs-lookup"><span data-stu-id="b756d-111">The address book provides access to three types of objects implemented by an address book provider:</span></span>
  
- <span data-ttu-id="b756d-112">通讯簿容器对象。</span><span class="sxs-lookup"><span data-stu-id="b756d-112">An address book container object.</span></span>
    
- <span data-ttu-id="b756d-113">通讯组列表对象。</span><span class="sxs-lookup"><span data-stu-id="b756d-113">A distribution list object.</span></span>
    
- <span data-ttu-id="b756d-114">消息的用户对象。</span><span class="sxs-lookup"><span data-stu-id="b756d-114">A messaging user object.</span></span>
    
<span data-ttu-id="b756d-115">每个这些类型的对象来访问其分配由其地址簿提供程序的唯一项标识符。</span><span class="sxs-lookup"><span data-stu-id="b756d-115">Each of these types of objects is accessed through its unique entry identifier that is assigned by its address book provider.</span></span> 
  
<span data-ttu-id="b756d-116">通讯簿容器是类似于文件夹的这是的它们保存不同类型的对象。</span><span class="sxs-lookup"><span data-stu-id="b756d-116">Address book containers are similar to folders in that they hold objects of different types.</span></span> <span data-ttu-id="b756d-117">通讯簿容器可以保留其他通讯簿容器以及消息用户和通讯组列表对象。</span><span class="sxs-lookup"><span data-stu-id="b756d-117">An address book container can hold other address book containers as well as messaging user and distribution list objects.</span></span> <span data-ttu-id="b756d-118">通讯簿容器用于组织和存储通讯簿对象。</span><span class="sxs-lookup"><span data-stu-id="b756d-118">Address book containers are used to organize and store address book objects.</span></span>
  
<span data-ttu-id="b756d-119">若要获得通讯簿的集成的外观，通讯簿提供程序公开零、 一个或多个为其将它们合并，并显示单个的顶级容器下结果的 MAPI 其顶级容器。</span><span class="sxs-lookup"><span data-stu-id="b756d-119">To achieve the address book's integrated appearance, address book providers expose zero, one, or more of their top-level containers to MAPI which merges them and displays the results under a single top-level container.</span></span> <span data-ttu-id="b756d-120">通讯簿提供程序可以选择要公开的一种类型的另一个会话的邮件会话和一组不同的容器的一组。</span><span class="sxs-lookup"><span data-stu-id="b756d-120">Address book providers can choose to expose one set of containers for one type of messaging session and a different set for another session.</span></span> <span data-ttu-id="b756d-121">还有可能地址簿提供商已没有顶级容器和公开仅可用于创建收件人的模板的列表。</span><span class="sxs-lookup"><span data-stu-id="b756d-121">It is also possible for address book providers to have no top-level containers and expose only a list of templates that can be used to create recipients.</span></span>
  
<span data-ttu-id="b756d-122">邮件的收件人，实现与邮件用户和通讯组列表对象。</span><span class="sxs-lookup"><span data-stu-id="b756d-122">Message recipients are implemented with messaging user and distribution list objects.</span></span> <span data-ttu-id="b756d-123">消息的用户是单个收件人;通讯组列表是组收件人。</span><span class="sxs-lookup"><span data-stu-id="b756d-123">Messaging users are individual recipients; distribution lists are group recipients.</span></span> <span data-ttu-id="b756d-124">每个邮件用户具有特定的消息系统处理的特定类型的唯一的地址。</span><span class="sxs-lookup"><span data-stu-id="b756d-124">Each messaging user has a unique address of a particular type handled by a particular messaging system.</span></span> <span data-ttu-id="b756d-125">通讯组列表是收件人的命名的集合。</span><span class="sxs-lookup"><span data-stu-id="b756d-125">A distribution list is a named collection of recipients.</span></span> <span data-ttu-id="b756d-126">通讯组列表可以包含消息的用户对象和其他通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b756d-126">Distribution lists can contain messaging user objects and other distribution lists.</span></span> <span data-ttu-id="b756d-127">当客户端应用程序的用户将一条消息发送到通讯组列表时，邮件被发送到每个列表的邮件用户的成员。</span><span class="sxs-lookup"><span data-stu-id="b756d-127">When a user of a client application sends a message to a distribution list, the message is being sent to each of the list's messaging user members.</span></span> 
  
<span data-ttu-id="b756d-128">邮件用户和通讯组列表具有一组称为基址属性的五个属性。</span><span class="sxs-lookup"><span data-stu-id="b756d-128">Messaging users and distribution lists have a set of five properties that are known as the base address properties.</span></span> <span data-ttu-id="b756d-129">这些是必需的属性，并简要描述，如下所示。</span><span class="sxs-lookup"><span data-stu-id="b756d-129">These are required properties and are briefly described as follows.</span></span>
  
|<span data-ttu-id="b756d-130">**基址属性**</span><span class="sxs-lookup"><span data-stu-id="b756d-130">**Base address property**</span></span>|<span data-ttu-id="b756d-131">**说明**</span><span class="sxs-lookup"><span data-stu-id="b756d-131">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b756d-132">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b756d-132">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b756d-133">收件人地址的类型。</span><span class="sxs-lookup"><span data-stu-id="b756d-133">Type of address for the recipient.</span></span> <span data-ttu-id="b756d-134">每个地址类型遵循特定的格式，并使用与特定的邮件系统。</span><span class="sxs-lookup"><span data-stu-id="b756d-134">Each address type follows a particular format and is used with a particular messaging system.</span></span>  <br/> |
|<span data-ttu-id="b756d-135">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b756d-135">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b756d-136">收件人的可显示名称。</span><span class="sxs-lookup"><span data-stu-id="b756d-136">Displayable name for the recipient.</span></span>  <br/> |
|<span data-ttu-id="b756d-137">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b756d-137">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b756d-138">收件人地址。</span><span class="sxs-lookup"><span data-stu-id="b756d-138">Address of the recipient.</span></span>  <br/> |
|<span data-ttu-id="b756d-139">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b756d-139">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b756d-140">用于访问收件人的项标识符。</span><span class="sxs-lookup"><span data-stu-id="b756d-140">Entry identifier used to access the recipient.</span></span>  <br/> |
|<span data-ttu-id="b756d-141">**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="b756d-141">**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b756d-142">用于标识的收件人的二进制相当键。</span><span class="sxs-lookup"><span data-stu-id="b756d-142">Binary comparable key used to identify the recipient.</span></span>  <br/> |
   
<span data-ttu-id="b756d-143">MAPI 定义多组变体的基址属性的属性。</span><span class="sxs-lookup"><span data-stu-id="b756d-143">MAPI defines many groups of properties that are variations of the base address properties.</span></span> <span data-ttu-id="b756d-144">邮件用户和通讯组列表在不同情况下，介绍了这些其他组。</span><span class="sxs-lookup"><span data-stu-id="b756d-144">These other groups describe messaging users and distribution lists in different situations.</span></span> <span data-ttu-id="b756d-145">例如，一组属性描述了一条消息和其他组委托收件人的代理人发件人。</span><span class="sxs-lookup"><span data-stu-id="b756d-145">For example, one group of properties describes the delegate sender of a message and another group the delegate recipient.</span></span>
  

