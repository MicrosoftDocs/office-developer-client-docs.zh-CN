---
title: MAPI 条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 84c37696-da7a-42e0-b8c0-29658a6c9a48
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d8c9fb0b24d8954fae75274bfbedca9d7c62de93
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567858"
---
# <a name="mapi-entry-identifiers"></a><span data-ttu-id="80926-103">MAPI 条目标识符</span><span class="sxs-lookup"><span data-stu-id="80926-103">MAPI Entry Identifiers</span></span>

  
  
<span data-ttu-id="80926-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="80926-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="80926-105">条目标识符是存储在[ENTRYID](entryid.md)结构用于唯一标识，并打开 MAPI 对象的二进制数据的片段。</span><span class="sxs-lookup"><span data-stu-id="80926-105">Entry identifiers are pieces of binary data stored in an [ENTRYID](entryid.md) structure that are used to uniquely identify and open a MAPI object.</span></span> <span data-ttu-id="80926-106">大多数 MAPI 对象具有条目标识符。</span><span class="sxs-lookup"><span data-stu-id="80926-106">Most MAPI objects have entry identifiers.</span></span> <span data-ttu-id="80926-107">对象的项标识符是类似于文件的文件名。</span><span class="sxs-lookup"><span data-stu-id="80926-107">Entry identifiers for objects are analogous to file names for files.</span></span> <span data-ttu-id="80926-108">但是，他们不可传送，并且不能使用它们在产生的系统之外的系统上。</span><span class="sxs-lookup"><span data-stu-id="80926-108">However, they are not transmittable and cannot be used on systems other than the system they originated on.</span></span> 
  
## <a name="entry-identifiers"></a><span data-ttu-id="80926-109">条目标识符</span><span class="sxs-lookup"><span data-stu-id="80926-109">Entry Identifiers</span></span>

<span data-ttu-id="80926-110">消息存储提供程序分配给消息存储库、 文件夹和消息; 条目标识符通讯簿提供程序将其分配给通讯簿容器、 通讯组列表和消息的用户。</span><span class="sxs-lookup"><span data-stu-id="80926-110">Message store providers assign entry identifiers to message stores, folders, and messages; address book providers assign them to address book containers, distribution lists, and messaging users.</span></span> <span data-ttu-id="80926-111">条目标识符还用于打开由表，如状态表中的状态对象中的行对象。</span><span class="sxs-lookup"><span data-stu-id="80926-111">Entry identifiers are also used to open an object represented by a row in a table, such as a status object in the status table.</span></span> <span data-ttu-id="80926-112">对象在其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性中存储其条目标识符。</span><span class="sxs-lookup"><span data-stu-id="80926-112">Objects store their entry identifiers in their **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="80926-113">服务提供商创建，分配，并检查条目标识符，而客户端应用程序将它们仅用作工具打开对象。</span><span class="sxs-lookup"><span data-stu-id="80926-113">Whereas service providers create, assign, and examine entry identifiers, client applications use them only as tools for opening objects.</span></span> <span data-ttu-id="80926-114">向客户端，条目标识符是二进制数据的不透明片段，并且没有执行与基础邮件系统。</span><span class="sxs-lookup"><span data-stu-id="80926-114">To clients, entry identifiers are opaque pieces of binary data and have nothing to do with the underlying messaging system.</span></span> 
  
<span data-ttu-id="80926-115">客户端调用对象的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索其**PR_ENTRYID**属性或表的[IMAPITable::QueryColumns](imapitable-querycolumns.md)方法来检索包含**PR_ENTRYID**属性的列。</span><span class="sxs-lookup"><span data-stu-id="80926-115">Clients call an object's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_ENTRYID** property or a table's [IMAPITable::QueryColumns](imapitable-querycolumns.md) method to retrieve the column that holds the **PR_ENTRYID** property.</span></span> 
  
<span data-ttu-id="80926-116">条目标识符作为参数传递给**OpenEntry**和**CompareEntryIDs**方法。</span><span class="sxs-lookup"><span data-stu-id="80926-116">Entry identifiers are passed as parameters to the **OpenEntry** and **CompareEntryIDs** methods.</span></span> <span data-ttu-id="80926-117">几个 MAPI 对象实现的**OpenEntry**和**CompareEntryIDs**方法。</span><span class="sxs-lookup"><span data-stu-id="80926-117">Several MAPI objects implement the **OpenEntry** and **CompareEntryIDs** methods.</span></span> <span data-ttu-id="80926-118">与**OpenEntry**，客户端可以打开一个对象。</span><span class="sxs-lookup"><span data-stu-id="80926-118">With **OpenEntry**, clients can open an object.</span></span> <span data-ttu-id="80926-119">**CompareEntryIDs**，使用客户端可以比较两个条目标识符来确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="80926-119">With **CompareEntryIDs**, clients can compare two entry identifiers to determine whether they refer to the same object.</span></span> <span data-ttu-id="80926-120">因为条目标识符不一定是二进制比较，客户端必须对它们进行比较**CompareEntryIDs**方法。</span><span class="sxs-lookup"><span data-stu-id="80926-120">Because entry identifiers are not necessarily binary comparable, clients must compare them by the **CompareEntryIDs** method.</span></span> 
  
<span data-ttu-id="80926-121">客户端应该与服务提供商，其呼叫总是传递自然地对齐的条目标识符，因为服务提供商应处理的任意位置对齐的项标识符，尽管这并不总是这种情况。</span><span class="sxs-lookup"><span data-stu-id="80926-121">Clients should always pass naturally aligned entry identifiers in their calls to service providers, because although service providers should handle entry identifiers that are arbitrarily aligned, this is not always the case.</span></span> <span data-ttu-id="80926-122">自然地对齐的内存地址允许访问它支持在该地址不生成对齐错误任何数据类型的计算机。</span><span class="sxs-lookup"><span data-stu-id="80926-122">A naturally aligned memory address enables the computer to access any data type it supports at that address without generating an alignment fault.</span></span> <span data-ttu-id="80926-123">自然对齐系数通常由系统内存分配程序相同的对齐方式系数和通常是 8 字节。</span><span class="sxs-lookup"><span data-stu-id="80926-123">The natural alignment factor is typically the same alignment factor used by the system memory allocator and is usually 8 bytes.</span></span>
  
<span data-ttu-id="80926-124">条目标识符分为两种类型： 短期和长期。</span><span class="sxs-lookup"><span data-stu-id="80926-124">Entry identifiers come in two types: short-term and long-term.</span></span> <span data-ttu-id="80926-125">短期条目标识符更快的构造，但其唯一性保证只能通过当前工作站上当前会话的生命周期。</span><span class="sxs-lookup"><span data-stu-id="80926-125">Short-term entry identifiers are faster to construct, but their uniqueness is guaranteed only over the life of the current session on the current workstation.</span></span> <span data-ttu-id="80926-126">长期条目标识符具有更多长时间的生命周期。</span><span class="sxs-lookup"><span data-stu-id="80926-126">Long-term entry identifiers have a more prolonged lifespan.</span></span> <span data-ttu-id="80926-127">短期条目标识符主要用于表中的行和条目在对话框中，而长期条目标识符可用于多个对象，如信息、 文件夹和通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="80926-127">Short-term entry identifiers are used primarily for rows in tables and entries in dialog boxes, whereas long-term entry identifiers are used for many objects such as messages, folders, and distribution lists.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="80926-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80926-128">See also</span></span>



[<span data-ttu-id="80926-129">MAPI 应用程序开发</span><span class="sxs-lookup"><span data-stu-id="80926-129">MAPI Application Development</span></span>](mapi-application-development.md)

