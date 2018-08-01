---
title: 短期条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 948e007a-ad68-4abd-9720-204c6584beb5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f601971e61eb6430bef9d50b093642ee04b14044
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778780"
---
# <a name="short-term-entry-identifiers"></a><span data-ttu-id="a3f6a-103">短期条目标识符</span><span class="sxs-lookup"><span data-stu-id="a3f6a-103">Short-term entry identifiers</span></span>

<span data-ttu-id="a3f6a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a3f6a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a3f6a-105">时的标识符必须快速构建和不需要时间或距离上次通过服务提供程序为对象分配的短期的项标识符。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-105">A short-term entry identifier is assigned by a service provider to an object when the identifier must be constructed quickly and does not need to last over time or distance.</span></span> <span data-ttu-id="a3f6a-106">只能通过当前工作站上当前会话的生存期保证短期的项标识符的唯一性。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-106">The uniqueness of a short-term entry identifier is guaranteed only over the life of the current session on the current workstation.</span></span> <span data-ttu-id="a3f6a-107">通常，短期的项标识符是有效的仅直到松开它所表示的对象。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-107">Typically, a short-term entry identifier is valid only until the object that it represents is released.</span></span> 
  
<span data-ttu-id="a3f6a-108">短期条目标识符将分配到表中的行和对话框，其中所需提供数据快速浏览中的条目。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-108">Short-term entry identifiers are assigned to rows in tables and to entries in dialog boxes, where it is necessary to provide data quickly for browsing.</span></span> <span data-ttu-id="a3f6a-109">例如，消息存储提供程序将短期条目标识符分配给内容表中的邮件的行和收件人表中的收件人。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-109">For example, message store providers assign short-term entry identifiers to rows of messages in a contents table and to recipients in a recipients table.</span></span> 

<span data-ttu-id="a3f6a-110">客户端可以使用这些短期条目标识符打开由的表格行的对象。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-110">Clients can use these short-term entry identifiers to open the objects represented by the table rows.</span></span> <span data-ttu-id="a3f6a-111">但是，与可用于任何**OpenEntry**方法的长期条目标识符，应与容器的**OpenEntry**方法使用短期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-111">However, unlike long-term entry identifiers that can be used with any of the **OpenEntry** methods, short-term entry identifiers should be used with the container's **OpenEntry** method.</span></span> 
  
## <a name="implementing-short-term-entry-identifiers"></a><span data-ttu-id="a3f6a-112">实现短期条目标识符</span><span class="sxs-lookup"><span data-stu-id="a3f6a-112">Implementing short-term entry identifiers</span></span>

<span data-ttu-id="a3f6a-113">实现短期条目标识符的最常见方式如下：</span><span class="sxs-lookup"><span data-stu-id="a3f6a-113">The most common ways to implement short-term entry identifiers include the following:</span></span>
  
- <span data-ttu-id="a3f6a-114">发出的短期的项标识符的长期的标识符，保留所有标记取消设置相同。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-114">Making the short-term entry identifiers the same as the long-term identifiers, leaving all of the flags unset.</span></span> 
    
- <span data-ttu-id="a3f6a-115">发出的短期条目标识符不同设置的所有标志的长期标识符。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-115">Making the short-term entry identifiers different from the long-term identifiers, setting all of the flags.</span></span> 
    
<span data-ttu-id="a3f6a-116">客户端可以确定第二种类型的短期条目标识符，通过检查其**abFlags**成员，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a3f6a-116">Clients can identify a short-term entry identifier of the second type by examining its **abFlags** member as follows:</span></span> 
  
```cpp
abFlags[0] = 0xFF;
 
```

<span data-ttu-id="a3f6a-117">某些服务提供商清除创建短期条目标识符具有更高版本的有效性的一个或多个标志。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-117">Some service providers clear one or more flags to create short-term entry identifiers that have greater validity.</span></span> <span data-ttu-id="a3f6a-118">例如，以下**abFlags**成员表示可为多个日期或多个会话的短期条目标识符：</span><span class="sxs-lookup"><span data-stu-id="a3f6a-118">For example, the following **abFlags** members represent short-term entry identifiers that can be used for multiple days or for multiple sessions:</span></span> 
  
```cpp
abFlags[0] = 0xFF & ~MAPI_NOW;
abFlags[0] = 0xFF & ~MAPI_THISSESSION;
 
```

<span data-ttu-id="a3f6a-119">客户端快速获取、 使用和放弃短期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-119">Clients quickly acquire, use, and discard short-term entry identifiers.</span></span> <span data-ttu-id="a3f6a-120">大多数情况下，它们可以采用相同的方式长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-120">For the most part, they can be used in the same manner as long-term entry identifiers.</span></span> <span data-ttu-id="a3f6a-121">他们可以从表格、 传递给**OpenEntry**方法，并与**CompareEntryIDs**方法比较检索。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-121">They can be retrieved from a table, passed to the **OpenEntry** method, and compared with the **CompareEntryIDs** method.</span></span> <span data-ttu-id="a3f6a-122">一个例外，也会永远不会返回从[IMAPIProp::GetProps](imapiprop-getprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-122">The one exception is that they are never returned from the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> <span data-ttu-id="a3f6a-123">返回从**GetProps**属性始终是长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a3f6a-123">The properties returned from **GetProps** are always long-term entry identifiers.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a3f6a-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3f6a-124">See also</span></span>

- [<span data-ttu-id="a3f6a-125">MAPI 条目标识符</span><span class="sxs-lookup"><span data-stu-id="a3f6a-125">MAPI Entry Identifiers</span></span>](mapi-entry-identifiers.md)

