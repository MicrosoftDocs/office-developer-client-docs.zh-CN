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
ms.openlocfilehash: ce7f7e2db341be62912935b7a55d69eaf5db8ab5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774697"
---
# <a name="copying-address-book-entries"></a><span data-ttu-id="708f1-103">复制通讯簿条目</span><span class="sxs-lookup"><span data-stu-id="708f1-103">Copying Address Book Entries</span></span>

  
  
<span data-ttu-id="708f1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="708f1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="708f1-105">时调用容器的[IABContainer::CopyEntries](iabcontainer-copyentries.md)方法从相同的一个或多个收件人或另一个容器的复制到此容器。</span><span class="sxs-lookup"><span data-stu-id="708f1-105">Your container's [IABContainer::CopyEntries](iabcontainer-copyentries.md) method is called when one or more recipients from the same or another container are to be copied into this container.</span></span> <span data-ttu-id="708f1-106">**CopyEntries**具有四个输入的参数： 表示要复制的收件人的项标识符、 窗口句柄进度指示器、 进度对象指针，和一个标志值的数组。</span><span class="sxs-lookup"><span data-stu-id="708f1-106">**CopyEntries** has four input parameters: an array of entry identifiers representing the recipients to be copied, a window handle for the progress indicator, a progress object pointer, and a flags value.</span></span> <span data-ttu-id="708f1-107">如果 AB_NO_DIALOG 标志未设置和使用_lpProgress_参数中的进度对象，如果不为 NULL，则您的提供商应显示进度。</span><span class="sxs-lookup"><span data-stu-id="708f1-107">Your provider should display progress if the AB_NO_DIALOG flag is not set and use the progress object from the  _lpProgress_ parameter if it is not NULL.</span></span> <span data-ttu-id="708f1-108">如果_lpProgress_为 NULL，则调用[IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)使用 MAPI 进度对象。</span><span class="sxs-lookup"><span data-stu-id="708f1-108">If  _lpProgress_ is NULL, call [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) to use the MAPI progress object.</span></span> <span data-ttu-id="708f1-109">有关显示进度的详细信息，请参阅[显示进度指示器](mapi-progress-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="708f1-109">For more information about displaying progress, see [Displaying a Progress Indicator](mapi-progress-indicators.md).</span></span>
  
<span data-ttu-id="708f1-110">除了 AB_NO_DIALOG 禁止进度指示器，两个其他标志之一可以设置为请求的重复项检查类型： CREATE_CHECK_DUP_LOOSE 或 CREATE_CHECK_DUP_STRICT。</span><span class="sxs-lookup"><span data-stu-id="708f1-110">In addition to AB_NO_DIALOG to suppress a progress indicator, one of two other flags can be set to request a type of duplicate entry checking: CREATE_CHECK_DUP_LOOSE or CREATE_CHECK_DUP_STRICT.</span></span> <span data-ttu-id="708f1-111">CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志是仅来对您的提供程序如何确定重复项的建议，可以忽略。</span><span class="sxs-lookup"><span data-stu-id="708f1-111">The CREATE_CHECK_DUP_LOOSE and CREATE_CHECK_DUP_STRICT flags are only suggestions as to how your provider determines duplicate entries and can be ignored.</span></span> <span data-ttu-id="708f1-112">MAPI 建议，您的提供商实现这些标志的支持，如下所示。</span><span class="sxs-lookup"><span data-stu-id="708f1-112">MAPI suggests that your provider implement support for these flags as follows.</span></span>
  
|<span data-ttu-id="708f1-113">**重复项标志**</span><span class="sxs-lookup"><span data-stu-id="708f1-113">**Duplicate entry flag**</span></span>|<span data-ttu-id="708f1-114">**建议的实现**</span><span class="sxs-lookup"><span data-stu-id="708f1-114">**Suggested implementation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="708f1-115">CREATE_CHECK_DUP_LOOSE</span><span class="sxs-lookup"><span data-stu-id="708f1-115">CREATE_CHECK_DUP_LOOSE</span></span>  <br/> |<span data-ttu-id="708f1-116">检查是否要创建的项的显示名称匹配项已在容器的显示名称。</span><span class="sxs-lookup"><span data-stu-id="708f1-116">Check if the display name in the entry to be created matches the display name of an entry already in the container.</span></span>  <br/> |
|<span data-ttu-id="708f1-117">CREATE_CHECK_DUP_STRICT</span><span class="sxs-lookup"><span data-stu-id="708f1-117">CREATE_CHECK_DUP_STRICT</span></span>  <br/> |<span data-ttu-id="708f1-118">检查的显示名称和要创建的项中的搜索键匹配容器条目的显示名称和搜索键。</span><span class="sxs-lookup"><span data-stu-id="708f1-118">Check if both the display name and the search key in the entry to be created match the display name and search key of a container entry.</span></span>  <br/> |
   
<span data-ttu-id="708f1-119">最后一个标志，CREATE_REPLACE，指示新条目应替换现有的场，是否您的提供商已确定要创建一个条目已在您的容器的条目的副本。</span><span class="sxs-lookup"><span data-stu-id="708f1-119">The last flag, CREATE_REPLACE, indicates that the new entry should replace the existing one if your provider has determined that an entry to be created is a duplicate of an entry already in your container.</span></span> 
  
<span data-ttu-id="708f1-120">如果您的提供商，个人通讯簿中每个复制操作包括**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="708f1-120">If your provider is a personal address book, include the **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property in every copy operation.</span></span> <span data-ttu-id="708f1-121">包括详细信息显示表复制收件人的允许您将显示收件人而无需调用原始容器创建显示详细的容器。</span><span class="sxs-lookup"><span data-stu-id="708f1-121">Including the details display table of a copied recipient enables your container to display the details of the recipient rather than having to call the original container to create the display.</span></span>
  
 <span data-ttu-id="708f1-122">**若要实现 IABContainer::CopyEntries**</span><span class="sxs-lookup"><span data-stu-id="708f1-122">**To implement IABContainer::CopyEntries**</span></span>
  
1. <span data-ttu-id="708f1-123">确定_lpEntries_参数中的每个条目标识符是您的提供商处理并不是，如果失败并返回 MAPI_E_INVALID_ENTRYID 的格式。</span><span class="sxs-lookup"><span data-stu-id="708f1-123">Determine if each entry identifier in the  _lpEntries_ parameter is in a format that your provider handles and if it is not, fail and return MAPI_E_INVALID_ENTRYID.</span></span> 
    
2. <span data-ttu-id="708f1-124">如果条目标识符表示消息的用户、 通讯组列表或提供程序处理的容器：</span><span class="sxs-lookup"><span data-stu-id="708f1-124">If an entry identifier represents a messaging user, distribution list, or container that your provider handles:</span></span>
    
1. <span data-ttu-id="708f1-125">调用您[IMAPISupport::OpenEntry](imapisupport-openentry.md)方法以打开对应的收件人。</span><span class="sxs-lookup"><span data-stu-id="708f1-125">Call your [IMAPISupport::OpenEntry](imapisupport-openentry.md) method to open the corresponding recipient.</span></span> 
    
2. <span data-ttu-id="708f1-126">将收件人复制到您的容器。</span><span class="sxs-lookup"><span data-stu-id="708f1-126">Copy the recipient to your container.</span></span> 
    
3. <span data-ttu-id="708f1-127">如果条目标识符代表外的收件人：</span><span class="sxs-lookup"><span data-stu-id="708f1-127">If the entry identifier represents a foreign recipient:</span></span>
    
1. <span data-ttu-id="708f1-128">调用容器的[IABContainer::CreateEntry](iabcontainer-createentry.md)方法创建一个新收件人。</span><span class="sxs-lookup"><span data-stu-id="708f1-128">Call your container's [IABContainer::CreateEntry](iabcontainer-createentry.md) method to create a new recipient.</span></span> 
    
2. <span data-ttu-id="708f1-129">设置新收件人初始属性。</span><span class="sxs-lookup"><span data-stu-id="708f1-129">Set initial properties on the new recipient.</span></span>
    
4. <span data-ttu-id="708f1-130">调用新对象的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法以将其保存。</span><span class="sxs-lookup"><span data-stu-id="708f1-130">Call the new object's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to save it.</span></span> 
    
5. <span data-ttu-id="708f1-131">更新的容器内容表，以反映新收件人。</span><span class="sxs-lookup"><span data-stu-id="708f1-131">Update the container's contents table to reflect the new recipient.</span></span> 
    
6. <span data-ttu-id="708f1-132">调用[IMAPISupport::Notify](imapisupport-notify.md)将表通知发送到注册的客户端。</span><span class="sxs-lookup"><span data-stu-id="708f1-132">Call [IMAPISupport::Notify](imapisupport-notify.md) to send a table notification to registered clients.</span></span> 
    

