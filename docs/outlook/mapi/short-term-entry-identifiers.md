---
title: 短期条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 948e007a-ad68-4abd-9720-204c6584beb5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1b361e025b631418eb63c5c74da264beadec2974
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439560"
---
# <a name="short-term-entry-identifiers"></a><span data-ttu-id="ab8c1-103">短期条目标识符</span><span class="sxs-lookup"><span data-stu-id="ab8c1-103">Short-term entry identifiers</span></span>

<span data-ttu-id="ab8c1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ab8c1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ab8c1-105">一个短期条目标识符由服务提供商分配给一个对象, 当该标识符必须能够快速构造且不需要在时间或距离上持续。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-105">A short-term entry identifier is assigned by a service provider to an object when the identifier must be constructed quickly and does not need to last over time or distance.</span></span> <span data-ttu-id="ab8c1-106">短期条目标识符的唯一性只能在当前工作站上的当前会话的生命周期内得到保证。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-106">The uniqueness of a short-term entry identifier is guaranteed only over the life of the current session on the current workstation.</span></span> <span data-ttu-id="ab8c1-107">通常, 短期条目标识符仅在释放它所代表的对象时才有效。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-107">Typically, a short-term entry identifier is valid only until the object that it represents is released.</span></span> 
  
<span data-ttu-id="ab8c1-108">短期条目标识符分配给表中的行和对话框中的条目, 在这种情况下, 需要快速提供数据以供浏览。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-108">Short-term entry identifiers are assigned to rows in tables and to entries in dialog boxes, where it is necessary to provide data quickly for browsing.</span></span> <span data-ttu-id="ab8c1-109">例如, 邮件存储提供程序将短期条目标识符分配给内容表中的邮件行和收件人表中的收件人。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-109">For example, message store providers assign short-term entry identifiers to rows of messages in a contents table and to recipients in a recipients table.</span></span> 

<span data-ttu-id="ab8c1-110">客户端可以使用这些短期条目标识符打开表格行所代表的对象。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-110">Clients can use these short-term entry identifiers to open the objects represented by the table rows.</span></span> <span data-ttu-id="ab8c1-111">但是, 与可用于任何**OpenEntry**方法的长期条目标识符不同的是, 短期条目标识符应与容器的**OpenEntry**方法一起使用。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-111">However, unlike long-term entry identifiers that can be used with any of the **OpenEntry** methods, short-term entry identifiers should be used with the container's **OpenEntry** method.</span></span> 
  
## <a name="implementing-short-term-entry-identifiers"></a><span data-ttu-id="ab8c1-112">实现短期条目标识符</span><span class="sxs-lookup"><span data-stu-id="ab8c1-112">Implementing short-term entry identifiers</span></span>

<span data-ttu-id="ab8c1-113">实现短期输入标识符的最常见方法包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="ab8c1-113">The most common ways to implement short-term entry identifiers include the following:</span></span>
  
- <span data-ttu-id="ab8c1-114">使短期条目标识符与长期标识符相同, 并将所有标志保留为未设置。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-114">Making the short-term entry identifiers the same as the long-term identifiers, leaving all of the flags unset.</span></span> 
    
- <span data-ttu-id="ab8c1-115">将短期输入标识符与长期标识符进行不同, 设置所有标志。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-115">Making the short-term entry identifiers different from the long-term identifiers, setting all of the flags.</span></span> 
    
<span data-ttu-id="ab8c1-116">客户端可以通过检查其**abFlags**成员来标识第二种类型的短期条目标识符, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="ab8c1-116">Clients can identify a short-term entry identifier of the second type by examining its **abFlags** member as follows:</span></span> 
  
```cpp
abFlags[0] = 0xFF;
 
```

<span data-ttu-id="ab8c1-117">一些服务提供商清除了一个或多个标志, 以创建具有更高有效性的短期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-117">Some service providers clear one or more flags to create short-term entry identifiers that have greater validity.</span></span> <span data-ttu-id="ab8c1-118">例如, 以下**abFlags**成员表示可用于多天或多个会话的短期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-118">For example, the following **abFlags** members represent short-term entry identifiers that can be used for multiple days or for multiple sessions:</span></span> 
  
```cpp
abFlags[0] = 0xFF & ~MAPI_NOW;
abFlags[0] = 0xFF & ~MAPI_THISSESSION;
 
```

<span data-ttu-id="ab8c1-119">客户端可快速获取、使用和丢弃短期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-119">Clients quickly acquire, use, and discard short-term entry identifiers.</span></span> <span data-ttu-id="ab8c1-120">在大多数情况下, 可以按照与长期条目标识符相同的方式使用它们。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-120">For the most part, they can be used in the same manner as long-term entry identifiers.</span></span> <span data-ttu-id="ab8c1-121">可以从表中检索它们, 并将其传递给**OpenEntry**方法, 并与**CompareEntryIDs**方法进行比较。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-121">They can be retrieved from a table, passed to the **OpenEntry** method, and compared with the **CompareEntryIDs** method.</span></span> <span data-ttu-id="ab8c1-122">一个例外是从不从[IMAPIProp:: GetProps](imapiprop-getprops.md)方法返回。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-122">The one exception is that they are never returned from the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> <span data-ttu-id="ab8c1-123">从**GetProps**返回的属性始终为长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="ab8c1-123">The properties returned from **GetProps** are always long-term entry identifiers.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ab8c1-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab8c1-124">See also</span></span>

- [<span data-ttu-id="ab8c1-125">MAPI 条目标识符</span><span class="sxs-lookup"><span data-stu-id="ab8c1-125">MAPI Entry Identifiers</span></span>](mapi-entry-identifiers.md)

