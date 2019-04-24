---
title: 复制通讯簿条目
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 285abeb4-45c8-4e82-9a16-b935b4651afe
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 190c4bf12c8f5aaaf8143f59239bb53fb68046f5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32333066"
---
# <a name="copying-address-book-entries"></a><span data-ttu-id="bfc47-103">复制通讯簿条目</span><span class="sxs-lookup"><span data-stu-id="bfc47-103">Copying Address Book Entries</span></span>

  
  
<span data-ttu-id="bfc47-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bfc47-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bfc47-105">当同一个或另一个容器中的一个或多个收件人要复制到此容器中时, 将调用您的容器的[IABContainer:: CopyEntries](iabcontainer-copyentries.md)方法。</span><span class="sxs-lookup"><span data-stu-id="bfc47-105">Your container's [IABContainer::CopyEntries](iabcontainer-copyentries.md) method is called when one or more recipients from the same or another container are to be copied into this container.</span></span> <span data-ttu-id="bfc47-106">**CopyEntries**有四个输入参数: 条目标识符的数组, 用于表示要复制的收件人、进度指示器的窗口句柄、进度对象指针和标志值。</span><span class="sxs-lookup"><span data-stu-id="bfc47-106">**CopyEntries** has four input parameters: an array of entry identifiers representing the recipients to be copied, a window handle for the progress indicator, a progress object pointer, and a flags value.</span></span> <span data-ttu-id="bfc47-107">如果未设置 AB_NO_DIALOG 标志, 则提供程序应显示进度, 如果不是 NULL, 则使用_lpProgress_参数中的进度对象。</span><span class="sxs-lookup"><span data-stu-id="bfc47-107">Your provider should display progress if the AB_NO_DIALOG flag is not set and use the progress object from the  _lpProgress_ parameter if it is not NULL.</span></span> <span data-ttu-id="bfc47-108">如果_lpProgress_为 NULL, 则调用[IMAPISupport::D oprogressdialog](imapisupport-doprogressdialog.md)以使用 MAPI 进度对象。</span><span class="sxs-lookup"><span data-stu-id="bfc47-108">If  _lpProgress_ is NULL, call [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) to use the MAPI progress object.</span></span> <span data-ttu-id="bfc47-109">有关显示进度的详细信息, 请参阅[显示进度指示器](mapi-progress-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="bfc47-109">For more information about displaying progress, see [Displaying a Progress Indicator](mapi-progress-indicators.md).</span></span>
  
<span data-ttu-id="bfc47-110">除了 AB_NO_DIALOG 以取消进度指示器之外, 还可以设置两个其他标志之一, 以请求重复项检查的类型: CREATE_CHECK_DUP_LOOSE 或 CREATE_CHECK_DUP_STRICT。</span><span class="sxs-lookup"><span data-stu-id="bfc47-110">In addition to AB_NO_DIALOG to suppress a progress indicator, one of two other flags can be set to request a type of duplicate entry checking: CREATE_CHECK_DUP_LOOSE or CREATE_CHECK_DUP_STRICT.</span></span> <span data-ttu-id="bfc47-111">CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志仅提供了有关提供程序如何确定重复条目并可被忽略的建议。</span><span class="sxs-lookup"><span data-stu-id="bfc47-111">The CREATE_CHECK_DUP_LOOSE and CREATE_CHECK_DUP_STRICT flags are only suggestions as to how your provider determines duplicate entries and can be ignored.</span></span> <span data-ttu-id="bfc47-112">MAPI 建议提供程序实现对这些标志的支持, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="bfc47-112">MAPI suggests that your provider implement support for these flags as follows.</span></span>
  
|<span data-ttu-id="bfc47-113">**重复条目标志**</span><span class="sxs-lookup"><span data-stu-id="bfc47-113">**Duplicate entry flag**</span></span>|<span data-ttu-id="bfc47-114">**建议的实现**</span><span class="sxs-lookup"><span data-stu-id="bfc47-114">**Suggested implementation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bfc47-115">CREATE_CHECK_DUP_LOOSE</span><span class="sxs-lookup"><span data-stu-id="bfc47-115">CREATE_CHECK_DUP_LOOSE</span></span>  <br/> |<span data-ttu-id="bfc47-116">检查要创建的条目中的显示名称是否与容器中已有条目的显示名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="bfc47-116">Check if the display name in the entry to be created matches the display name of an entry already in the container.</span></span>  <br/> |
|<span data-ttu-id="bfc47-117">CREATE_CHECK_DUP_STRICT</span><span class="sxs-lookup"><span data-stu-id="bfc47-117">CREATE_CHECK_DUP_STRICT</span></span>  <br/> |<span data-ttu-id="bfc47-118">检查要创建的项中的显示名称和搜索关键字是否与容器项的显示名称和搜索关键字相匹配。</span><span class="sxs-lookup"><span data-stu-id="bfc47-118">Check if both the display name and the search key in the entry to be created match the display name and search key of a container entry.</span></span>  <br/> |
   
<span data-ttu-id="bfc47-119">最后一个标志 CREATE_REPLACE, 指示如果您的提供程序已确定要创建的项与容器中已有的条目重复, 则新条目应替换现有的条目。</span><span class="sxs-lookup"><span data-stu-id="bfc47-119">The last flag, CREATE_REPLACE, indicates that the new entry should replace the existing one if your provider has determined that an entry to be created is a duplicate of an entry already in your container.</span></span> 
  
<span data-ttu-id="bfc47-120">如果您的提供商是个人通讯簿, 请在每个复制操作中包括**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="bfc47-120">If your provider is a personal address book, include the **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property in every copy operation.</span></span> <span data-ttu-id="bfc47-121">包括复制的收件人的详细信息显示表使您的容器能够显示收件人的详细信息, 而无需调用原始容器来创建显示。</span><span class="sxs-lookup"><span data-stu-id="bfc47-121">Including the details display table of a copied recipient enables your container to display the details of the recipient rather than having to call the original container to create the display.</span></span>
  
 <span data-ttu-id="bfc47-122">**实现 IABContainer:: CopyEntries**</span><span class="sxs-lookup"><span data-stu-id="bfc47-122">**To implement IABContainer::CopyEntries**</span></span>
  
1. <span data-ttu-id="bfc47-123">确定_lpEntries_参数中的每个条目标识符是否采用提供程序处理的格式, 如果不是, 则会失败并返回 MAPI_E_INVALID_ENTRYID。</span><span class="sxs-lookup"><span data-stu-id="bfc47-123">Determine if each entry identifier in the  _lpEntries_ parameter is in a format that your provider handles and if it is not, fail and return MAPI_E_INVALID_ENTRYID.</span></span> 
    
2. <span data-ttu-id="bfc47-124">如果条目标识符表示提供程序处理的邮件用户、通讯组列表或容器:</span><span class="sxs-lookup"><span data-stu-id="bfc47-124">If an entry identifier represents a messaging user, distribution list, or container that your provider handles:</span></span>
    
1. <span data-ttu-id="bfc47-125">调用[IMAPISupport:: OpenEntry](imapisupport-openentry.md)方法打开相应的收件人。</span><span class="sxs-lookup"><span data-stu-id="bfc47-125">Call your [IMAPISupport::OpenEntry](imapisupport-openentry.md) method to open the corresponding recipient.</span></span> 
    
2. <span data-ttu-id="bfc47-126">将收件人复制到容器。</span><span class="sxs-lookup"><span data-stu-id="bfc47-126">Copy the recipient to your container.</span></span> 
    
3. <span data-ttu-id="bfc47-127">如果条目标识符代表一个外部收件人:</span><span class="sxs-lookup"><span data-stu-id="bfc47-127">If the entry identifier represents a foreign recipient:</span></span>
    
1. <span data-ttu-id="bfc47-128">调用容器的[IABContainer:: CreateEntry](iabcontainer-createentry.md)方法以创建新的收件人。</span><span class="sxs-lookup"><span data-stu-id="bfc47-128">Call your container's [IABContainer::CreateEntry](iabcontainer-createentry.md) method to create a new recipient.</span></span> 
    
2. <span data-ttu-id="bfc47-129">设置新收件人的初始属性。</span><span class="sxs-lookup"><span data-stu-id="bfc47-129">Set initial properties on the new recipient.</span></span>
    
4. <span data-ttu-id="bfc47-130">调用新对象的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以保存它。</span><span class="sxs-lookup"><span data-stu-id="bfc47-130">Call the new object's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to save it.</span></span> 
    
5. <span data-ttu-id="bfc47-131">更新容器的内容表以反映新的收件人。</span><span class="sxs-lookup"><span data-stu-id="bfc47-131">Update the container's contents table to reflect the new recipient.</span></span> 
    
6. <span data-ttu-id="bfc47-132">调用[IMAPISupport:: Notify](imapisupport-notify.md)向已注册的客户端发送表通知。</span><span class="sxs-lookup"><span data-stu-id="bfc47-132">Call [IMAPISupport::Notify](imapisupport-notify.md) to send a table notification to registered clients.</span></span> 
    

