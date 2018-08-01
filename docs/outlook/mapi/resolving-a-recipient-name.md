---
title: 解析收件人姓名
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2baed391-85bd-4e88-8800-c19bc2d2d54a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 256412f6ccbe66da067411bf9f66ad0478cf5ca2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778630"
---
# <a name="resolving-a-recipient-name"></a><span data-ttu-id="de3ed-103">解析收件人姓名</span><span class="sxs-lookup"><span data-stu-id="de3ed-103">Resolving a Recipient Name</span></span>

  
  
<span data-ttu-id="de3ed-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="de3ed-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="de3ed-105">时，从而解决了一条消息，收件人列表是构建具有与每个收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="de3ed-105">When a message is addressed, a recipient list is built with properties relating to each recipient.</span></span> <span data-ttu-id="de3ed-106">发送邮件时，这些属性之一必须是收件人的长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="de3ed-106">By the time the message is sent, one of those properties must be the recipient's long-term entry identifier.</span></span> <span data-ttu-id="de3ed-107">若要确保每个收件人，包括**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性，传递[ADRLIST](adrlist.md)结构描述您收件人列表中，将调用[IAddrBook _lpAdrList_参数的内容：ResolveName](iaddrbook-resolvename.md)。</span><span class="sxs-lookup"><span data-stu-id="de3ed-107">To ensure that each recipient includes the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property, pass the [ADRLIST](adrlist.md) structure describing your recipient list in the contents of the  _lpAdrList_ parameter in a call to [IAddrBook::ResolveName](iaddrbook-resolvename.md).</span></span>
  
 <span data-ttu-id="de3ed-108">**ResolveName**开始处理通过忽略已解决， **ADRLIST**结构中的条目，由相应[ADRENTRY](adrentry.md)结构**SPropValue**中的项标识符的状态数组。</span><span class="sxs-lookup"><span data-stu-id="de3ed-108">**ResolveName** begins processing by ignoring the entries in the **ADRLIST** structure that have already been resolved, as indicated by the presence of an entry identifier in the corresponding [ADRENTRY](adrentry.md) structure's **SPropValue** array.</span></span> <span data-ttu-id="de3ed-109">接下来， **ResolveName**自动将一次性条目标识符分配给两种类型的收件人：</span><span class="sxs-lookup"><span data-stu-id="de3ed-109">Next, **ResolveName** automatically assigns one-off entry identifiers to two types of recipients:</span></span> 
  
- <span data-ttu-id="de3ed-110">收件人地址的格式设置为 Internet 地址</span><span class="sxs-lookup"><span data-stu-id="de3ed-110">Recipients with an address formatted as an Internet address</span></span>
    
- <span data-ttu-id="de3ed-111">收件人地址的格式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="de3ed-111">Recipients with an address formatted as follows:</span></span>
    
     `displayname[address type:email address]`
    
<span data-ttu-id="de3ed-112">对于所有剩余的项， **ResolveName**完全匹配上的显示名称搜索通讯簿。</span><span class="sxs-lookup"><span data-stu-id="de3ed-112">For all remaining entries, **ResolveName** searches the address book for an exact match on the display name.</span></span> <span data-ttu-id="de3ed-113">**ResolveName**使用**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性来确定一组的搜索和搜索顺序的容器。</span><span class="sxs-lookup"><span data-stu-id="de3ed-113">**ResolveName** uses the **PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) property to determine the set of containers to search and the search order.</span></span> <span data-ttu-id="de3ed-114">MAPI 调用每个容器试图解析所有名称的[IABContainer::ResolveNames](iabcontainer-resolvenames.md)方法。</span><span class="sxs-lookup"><span data-stu-id="de3ed-114">MAPI calls the [IABContainer::ResolveNames](iabcontainer-resolvenames.md) method of every container to attempt to resolve all of the names.</span></span> <span data-ttu-id="de3ed-115">因为一些容器不支持**ResolveNames**，如果容器返回 MAPI_E_NO_SUPPORT，MAPI 应用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制对照其内容表。</span><span class="sxs-lookup"><span data-stu-id="de3ed-115">Because some containers do not support **ResolveNames**, if the container returns MAPI_E_NO_SUPPORT, MAPI applies a **PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) property restriction against its contents table.</span></span> <span data-ttu-id="de3ed-116">所有通讯簿容器都需要支持名称解析此限制。</span><span class="sxs-lookup"><span data-stu-id="de3ed-116">All address book containers are required to support name resolution with this restriction.</span></span> <span data-ttu-id="de3ed-117">一旦所有名称都均已解析，不再进行容器呼叫。</span><span class="sxs-lookup"><span data-stu-id="de3ed-117">Once all the names are resolved, no further container calls are made.</span></span> <span data-ttu-id="de3ed-118">如果所有容器都已被都调用，但不明确或无法解析名称保持，MAPI 显示尽可能对话框提示用户将其余的名称解析。</span><span class="sxs-lookup"><span data-stu-id="de3ed-118">If all the containers have been called, but ambiguous or unresolved names remain, MAPI displays a dialog box if possible to prompt the user to resolve the remaining names.</span></span>
  
<span data-ttu-id="de3ed-119">**PR_ANR**限制匹配**ADRLIST**结构中的显示名称对**PR_ANR**属性的值。</span><span class="sxs-lookup"><span data-stu-id="de3ed-119">The **PR_ANR** restriction matches the value of the **PR_ANR** property against the display name in the **ADRLIST** structure.</span></span> <span data-ttu-id="de3ed-120">限制带**PR_ANR**属性限制的容器内容表的视图可使通讯簿提供程序执行搜索，针对合理性提供程序的属性匹配"最佳猜测"类型。</span><span class="sxs-lookup"><span data-stu-id="de3ed-120">Limiting the view of a container's contents table with the **PR_ANR** property restriction causes the address book provider to perform a "best guess" type of search, matching against the property that makes sense for the provider.</span></span> <span data-ttu-id="de3ed-121">例如，一个通讯簿提供程序可能总是匹配针对**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的收件人列表中的名称，而另一个可能允许管理员选择的属性。</span><span class="sxs-lookup"><span data-stu-id="de3ed-121">For example, one address book provider might always match names in the recipient list against **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) while another might allow an administrator to select the property.</span></span>
  
 <span data-ttu-id="de3ed-122">**对通讯簿容器内容表设置 PR_ANR 属性限制**</span><span class="sxs-lookup"><span data-stu-id="de3ed-122">**To set a PR_ANR property restriction on an address book container's contents table**</span></span>
  
1. <span data-ttu-id="de3ed-123">创建[SRestriction](srestriction.md)结构，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="de3ed-123">Create an [SRestriction](srestriction.md) structure as shown in the following code:</span></span> 
    
  ```cpp
  SRestriction SRestrict;
  SRestrict.rt = RES_PROPERTY;
  SRestrict.res.resProperty.relop = RELOP_EQ;
  SRestrict.res.resProperty.ulPropTag = PR_ANR;
  SRestrict.res.resProperty.lpProp->ulPropTag = PR_ANR;
  SRestrict.res.resProperty.lpProp->Value.LPSZ = lpszName;
   
  ```

2. <span data-ttu-id="de3ed-124">调用内容表的[IMAPITable::Restrict](imapitable-restrict.md)方法，并作为_lpRestriction_参数传递的**SRestriction**结构。</span><span class="sxs-lookup"><span data-stu-id="de3ed-124">Call the contents table's [IMAPITable::Restrict](imapitable-restrict.md) method, passing the **SRestriction** structure as the  _lpRestriction_ parameter.</span></span> 
    

