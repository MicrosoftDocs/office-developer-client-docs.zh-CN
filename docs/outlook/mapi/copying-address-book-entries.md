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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418741"
---
# <a name="copying-address-book-entries"></a><span data-ttu-id="0ead8-103">复制通讯簿条目</span><span class="sxs-lookup"><span data-stu-id="0ead8-103">Copying Address Book Entries</span></span>

  
  
<span data-ttu-id="0ead8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0ead8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0ead8-105">将同一容器或另一个容器中的一个或多个收件人复制到此容器中时，将调用容器的 [IABContainer：：CopyEntries](iabcontainer-copyentries.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="0ead8-105">Your container's [IABContainer::CopyEntries](iabcontainer-copyentries.md) method is called when one or more recipients from the same or another container are to be copied into this container.</span></span> <span data-ttu-id="0ead8-106">**CopyEntries** 有四个输入参数：表示要复制的收件人的条目标识符数组、进度指示器的窗口句柄、进度对象指针和标志值。</span><span class="sxs-lookup"><span data-stu-id="0ead8-106">**CopyEntries** has four input parameters: an array of entry identifiers representing the recipients to be copied, a window handle for the progress indicator, a progress object pointer, and a flags value.</span></span> <span data-ttu-id="0ead8-107">如果未设置 AB_NO_DIALOG，则提供程序应显示进度，如果未为 NULL，则使用  _lpProgress_ 参数中的 progress 对象。</span><span class="sxs-lookup"><span data-stu-id="0ead8-107">Your provider should display progress if the AB_NO_DIALOG flag is not set and use the progress object from the  _lpProgress_ parameter if it is not NULL.</span></span> <span data-ttu-id="0ead8-108">如果  _lpProgress_ 为 NULL，则调用 [IMAPISupport：:D oProgressDialog](imapisupport-doprogressdialog.md) 以使用 MAPI 进度对象。</span><span class="sxs-lookup"><span data-stu-id="0ead8-108">If  _lpProgress_ is NULL, call [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) to use the MAPI progress object.</span></span> <span data-ttu-id="0ead8-109">有关显示进度的信息，请参阅 [显示进度指示器](mapi-progress-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="0ead8-109">For more information about displaying progress, see [Displaying a Progress Indicator](mapi-progress-indicators.md).</span></span>
  
<span data-ttu-id="0ead8-110">除了AB_NO_DIALOG进度指示器之外，还可以设置其他两个标志之一以请求重复项检查的类型：CREATE_CHECK_DUP_LOOSE 或 CREATE_CHECK_DUP_STRICT。</span><span class="sxs-lookup"><span data-stu-id="0ead8-110">In addition to AB_NO_DIALOG to suppress a progress indicator, one of two other flags can be set to request a type of duplicate entry checking: CREATE_CHECK_DUP_LOOSE or CREATE_CHECK_DUP_STRICT.</span></span> <span data-ttu-id="0ead8-111">这些CREATE_CHECK_DUP_LOOSE CREATE_CHECK_DUP_STRICT标记只是有关提供程序如何确定重复条目的建议，可以忽略。</span><span class="sxs-lookup"><span data-stu-id="0ead8-111">The CREATE_CHECK_DUP_LOOSE and CREATE_CHECK_DUP_STRICT flags are only suggestions as to how your provider determines duplicate entries and can be ignored.</span></span> <span data-ttu-id="0ead8-112">MAPI 建议提供程序实现对这些标志的支持，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0ead8-112">MAPI suggests that your provider implement support for these flags as follows.</span></span>
  
|<span data-ttu-id="0ead8-113">**重复的条目标志**</span><span class="sxs-lookup"><span data-stu-id="0ead8-113">**Duplicate entry flag**</span></span>|<span data-ttu-id="0ead8-114">**建议的实现**</span><span class="sxs-lookup"><span data-stu-id="0ead8-114">**Suggested implementation**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0ead8-115">CREATE_CHECK_DUP_LOOSE</span><span class="sxs-lookup"><span data-stu-id="0ead8-115">CREATE_CHECK_DUP_LOOSE</span></span>  <br/> |<span data-ttu-id="0ead8-116">检查要显示名称条目中的项是否与显示名称中已有条目的匹配。</span><span class="sxs-lookup"><span data-stu-id="0ead8-116">Check if the display name in the entry to be created matches the display name of an entry already in the container.</span></span>  <br/> |
|<span data-ttu-id="0ead8-117">CREATE_CHECK_DUP_STRICT</span><span class="sxs-lookup"><span data-stu-id="0ead8-117">CREATE_CHECK_DUP_STRICT</span></span>  <br/> |<span data-ttu-id="0ead8-118">检查要创建的显示名称中的搜索键和搜索键是否显示名称项的搜索键匹配。</span><span class="sxs-lookup"><span data-stu-id="0ead8-118">Check if both the display name and the search key in the entry to be created match the display name and search key of a container entry.</span></span>  <br/> |
   
<span data-ttu-id="0ead8-119">最后一个标志 CREATE_REPLACE 指示，如果提供程序已确定要创建的条目是容器中已存在的条目的重复项，则新条目应替换现有的条目。</span><span class="sxs-lookup"><span data-stu-id="0ead8-119">The last flag, CREATE_REPLACE, indicates that the new entry should replace the existing one if your provider has determined that an entry to be created is a duplicate of an entry already in your container.</span></span> 
  
<span data-ttu-id="0ead8-120">如果您的提供程序是个人通讯簿，则每个复制PR_DETAILS_TABLE ( [PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0ead8-120">If your provider is a personal address book, include the **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property in every copy operation.</span></span> <span data-ttu-id="0ead8-121">通过包括已复制收件人的详细信息显示表，您的容器可以显示收件人的详细信息，而不必调用原始容器来创建显示。</span><span class="sxs-lookup"><span data-stu-id="0ead8-121">Including the details display table of a copied recipient enables your container to display the details of the recipient rather than having to call the original container to create the display.</span></span>
  
 <span data-ttu-id="0ead8-122">**实现 IABContainer：：CopyEntries**</span><span class="sxs-lookup"><span data-stu-id="0ead8-122">**To implement IABContainer::CopyEntries**</span></span>
  
1. <span data-ttu-id="0ead8-123">确定  _lpEntries_ 参数中的每个条目标识符是否采用提供程序处理的格式，如果未采用，则失败并返回MAPI_E_INVALID_ENTRYID。</span><span class="sxs-lookup"><span data-stu-id="0ead8-123">Determine if each entry identifier in the  _lpEntries_ parameter is in a format that your provider handles and if it is not, fail and return MAPI_E_INVALID_ENTRYID.</span></span> 
    
2. <span data-ttu-id="0ead8-124">如果条目标识符表示提供程序处理的消息用户、通讯组列表或容器：</span><span class="sxs-lookup"><span data-stu-id="0ead8-124">If an entry identifier represents a messaging user, distribution list, or container that your provider handles:</span></span>
    
1. <span data-ttu-id="0ead8-125">调用 [IMAPISupport：：OpenEntry](imapisupport-openentry.md) 方法以打开相应的收件人。</span><span class="sxs-lookup"><span data-stu-id="0ead8-125">Call your [IMAPISupport::OpenEntry](imapisupport-openentry.md) method to open the corresponding recipient.</span></span> 
    
2. <span data-ttu-id="0ead8-126">将收件人复制到容器。</span><span class="sxs-lookup"><span data-stu-id="0ead8-126">Copy the recipient to your container.</span></span> 
    
3. <span data-ttu-id="0ead8-127">如果条目标识符表示一个外收件人：</span><span class="sxs-lookup"><span data-stu-id="0ead8-127">If the entry identifier represents a foreign recipient:</span></span>
    
1. <span data-ttu-id="0ead8-128">调用容器的 [IABContainer：：CreateEntry](iabcontainer-createentry.md) 方法以创建新收件人。</span><span class="sxs-lookup"><span data-stu-id="0ead8-128">Call your container's [IABContainer::CreateEntry](iabcontainer-createentry.md) method to create a new recipient.</span></span> 
    
2. <span data-ttu-id="0ead8-129">设置新收件人的初始属性。</span><span class="sxs-lookup"><span data-stu-id="0ead8-129">Set initial properties on the new recipient.</span></span>
    
4. <span data-ttu-id="0ead8-130">调用新对象的 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法来保存它。</span><span class="sxs-lookup"><span data-stu-id="0ead8-130">Call the new object's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to save it.</span></span> 
    
5. <span data-ttu-id="0ead8-131">更新容器的内容表以反映新收件人。</span><span class="sxs-lookup"><span data-stu-id="0ead8-131">Update the container's contents table to reflect the new recipient.</span></span> 
    
6. <span data-ttu-id="0ead8-132">调用 [IMAPISupport：：Notify](imapisupport-notify.md) 以向注册的客户端发送表通知。</span><span class="sxs-lookup"><span data-stu-id="0ead8-132">Call [IMAPISupport::Notify](imapisupport-notify.md) to send a table notification to registered clients.</span></span> 
    

