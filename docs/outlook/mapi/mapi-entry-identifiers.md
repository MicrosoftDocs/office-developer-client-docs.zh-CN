---
title: MAPI 条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 84c37696-da7a-42e0-b8c0-29658a6c9a48
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4c414b9f8a1d70fd5eea94da326674a749ccefe2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414961"
---
# <a name="mapi-entry-identifiers"></a><span data-ttu-id="050d2-103">MAPI 条目标识符</span><span class="sxs-lookup"><span data-stu-id="050d2-103">MAPI Entry Identifiers</span></span>

  
  
<span data-ttu-id="050d2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="050d2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="050d2-105">条目标识符是存储在[ENTRYID](entryid.md)结构中的一段二进制数据, 用于唯一标识和打开 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="050d2-105">Entry identifiers are pieces of binary data stored in an [ENTRYID](entryid.md) structure that are used to uniquely identify and open a MAPI object.</span></span> <span data-ttu-id="050d2-106">大多数 MAPI 对象都有条目标识符。</span><span class="sxs-lookup"><span data-stu-id="050d2-106">Most MAPI objects have entry identifiers.</span></span> <span data-ttu-id="050d2-107">对象的条目标识符类似于文件的文件名。</span><span class="sxs-lookup"><span data-stu-id="050d2-107">Entry identifiers for objects are analogous to file names for files.</span></span> <span data-ttu-id="050d2-108">但是, 它们不是传输, 不能在其起源的系统之外的系统上使用。</span><span class="sxs-lookup"><span data-stu-id="050d2-108">However, they are not transmittable and cannot be used on systems other than the system they originated on.</span></span> 
  
## <a name="entry-identifiers"></a><span data-ttu-id="050d2-109">条目标识符</span><span class="sxs-lookup"><span data-stu-id="050d2-109">Entry Identifiers</span></span>

<span data-ttu-id="050d2-110">邮件存储提供程序为邮件存储、文件夹和邮件分配条目标识符;通讯簿提供程序将其分配给通讯簿容器、通讯组列表和邮件用户。</span><span class="sxs-lookup"><span data-stu-id="050d2-110">Message store providers assign entry identifiers to message stores, folders, and messages; address book providers assign them to address book containers, distribution lists, and messaging users.</span></span> <span data-ttu-id="050d2-111">条目标识符还用于打开由表中的行表示的对象, 例如状态表中的 status 对象。</span><span class="sxs-lookup"><span data-stu-id="050d2-111">Entry identifiers are also used to open an object represented by a row in a table, such as a status object in the status table.</span></span> <span data-ttu-id="050d2-112">对象在其**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性中存储其条目标识符。</span><span class="sxs-lookup"><span data-stu-id="050d2-112">Objects store their entry identifiers in their **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span> 
  
<span data-ttu-id="050d2-113">虽然服务提供程序创建、分配和检查条目标识符, 但客户端应用程序仅将其用作打开对象的工具。</span><span class="sxs-lookup"><span data-stu-id="050d2-113">Whereas service providers create, assign, and examine entry identifiers, client applications use them only as tools for opening objects.</span></span> <span data-ttu-id="050d2-114">对于客户端, 条目标识符是不透明的二进制数据块, 与基础邮件系统无关。</span><span class="sxs-lookup"><span data-stu-id="050d2-114">To clients, entry identifiers are opaque pieces of binary data and have nothing to do with the underlying messaging system.</span></span> 
  
<span data-ttu-id="050d2-115">客户端调用对象的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索其**PR_ENTRYID**属性或表的[IMAPITable:: QueryColumns](imapitable-querycolumns.md)方法以检索包含**PR_ENTRYID**属性的列。</span><span class="sxs-lookup"><span data-stu-id="050d2-115">Clients call an object's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_ENTRYID** property or a table's [IMAPITable::QueryColumns](imapitable-querycolumns.md) method to retrieve the column that holds the **PR_ENTRYID** property.</span></span> 
  
<span data-ttu-id="050d2-116">条目标识符作为参数传递给**OpenEntry**和**CompareEntryIDs**方法。</span><span class="sxs-lookup"><span data-stu-id="050d2-116">Entry identifiers are passed as parameters to the **OpenEntry** and **CompareEntryIDs** methods.</span></span> <span data-ttu-id="050d2-117">几个 MAPI 对象实现**OpenEntry**和**CompareEntryIDs**方法。</span><span class="sxs-lookup"><span data-stu-id="050d2-117">Several MAPI objects implement the **OpenEntry** and **CompareEntryIDs** methods.</span></span> <span data-ttu-id="050d2-118">通过**OpenEntry**, 客户端可以打开对象。</span><span class="sxs-lookup"><span data-stu-id="050d2-118">With **OpenEntry**, clients can open an object.</span></span> <span data-ttu-id="050d2-119">通过**CompareEntryIDs**, 客户端可以对两个条目标识符进行比较, 以确定它们是否引用同一个对象。</span><span class="sxs-lookup"><span data-stu-id="050d2-119">With **CompareEntryIDs**, clients can compare two entry identifiers to determine whether they refer to the same object.</span></span> <span data-ttu-id="050d2-120">由于条目标识符不一定是二进制可比较的, 因此客户端必须将其与**CompareEntryIDs**方法进行比较。</span><span class="sxs-lookup"><span data-stu-id="050d2-120">Because entry identifiers are not necessarily binary comparable, clients must compare them by the **CompareEntryIDs** method.</span></span> 
  
<span data-ttu-id="050d2-121">客户端应始终在其对服务提供程序的调用中传递自然对齐的条目标识符, 因为尽管服务提供程序应处理任意对齐的条目标识符, 但这并不总是如此。</span><span class="sxs-lookup"><span data-stu-id="050d2-121">Clients should always pass naturally aligned entry identifiers in their calls to service providers, because although service providers should handle entry identifiers that are arbitrarily aligned, this is not always the case.</span></span> <span data-ttu-id="050d2-122">通过自然对齐的内存地址, 计算机可以访问它在该地址支持的任何数据类型, 而不会生成对齐错误。</span><span class="sxs-lookup"><span data-stu-id="050d2-122">A naturally aligned memory address enables the computer to access any data type it supports at that address without generating an alignment fault.</span></span> <span data-ttu-id="050d2-123">自然对齐因子通常与系统内存分配器使用相同的校准因子, 并且通常为8个字节。</span><span class="sxs-lookup"><span data-stu-id="050d2-123">The natural alignment factor is typically the same alignment factor used by the system memory allocator and is usually 8 bytes.</span></span>
  
<span data-ttu-id="050d2-124">条目标识符分为两种类型: 短期和长期。</span><span class="sxs-lookup"><span data-stu-id="050d2-124">Entry identifiers come in two types: short-term and long-term.</span></span> <span data-ttu-id="050d2-125">短期条目标识符的构建速度更快, 但仅在当前工作站上的当前会话的生命周期内保证它们的唯一性。</span><span class="sxs-lookup"><span data-stu-id="050d2-125">Short-term entry identifiers are faster to construct, but their uniqueness is guaranteed only over the life of the current session on the current workstation.</span></span> <span data-ttu-id="050d2-126">长期条目标识符的生命周期较长。</span><span class="sxs-lookup"><span data-stu-id="050d2-126">Long-term entry identifiers have a more prolonged lifespan.</span></span> <span data-ttu-id="050d2-127">短期条目标识符主要用于表格中的行和对话框中的条目, 而长期条目标识符用于许多对象, 例如邮件、文件夹和通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="050d2-127">Short-term entry identifiers are used primarily for rows in tables and entries in dialog boxes, whereas long-term entry identifiers are used for many objects such as messages, folders, and distribution lists.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="050d2-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="050d2-128">See also</span></span>



[<span data-ttu-id="050d2-129">MAPI 应用程序开发</span><span class="sxs-lookup"><span data-stu-id="050d2-129">MAPI Application Development</span></span>](mapi-application-development.md)

