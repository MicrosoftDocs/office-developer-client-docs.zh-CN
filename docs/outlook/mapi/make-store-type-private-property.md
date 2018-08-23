---
title: 将存储类型视为专用的属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- Make Store Type Private Property
api_type:
- COM
ms.assetid: 7f489f55-46d4-8a88-6ebe-9db6446e69a5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2d927b00391725d8804e41b66b1ec8c384f98e7c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568831"
---
# <a name="make-store-type-private-property"></a><span data-ttu-id="dd26a-103">将存储类型视为专用的属性</span><span class="sxs-lookup"><span data-stu-id="dd26a-103">Make Store Type Private Property</span></span>

  
  
<span data-ttu-id="dd26a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dd26a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dd26a-105">辅助存储视为私有。</span><span class="sxs-lookup"><span data-stu-id="dd26a-105">Treats a secondary store as private.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="dd26a-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="dd26a-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="dd26a-107">公开上：</span><span class="sxs-lookup"><span data-stu-id="dd26a-107">Exposed on:</span></span>  <br/> |<span data-ttu-id="dd26a-108">[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象</span><span class="sxs-lookup"><span data-stu-id="dd26a-108">[IMsgStore : IMAPIProp](imsgstoreimapiprop.md) object</span></span>  <br/> |
|<span data-ttu-id="dd26a-109">通过创建：</span><span class="sxs-lookup"><span data-stu-id="dd26a-109">Created by:</span></span>  <br/> |<span data-ttu-id="dd26a-110">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="dd26a-110">Store provider</span></span>  <br/> |
|<span data-ttu-id="dd26a-111">通过来访问：</span><span class="sxs-lookup"><span data-stu-id="dd26a-111">Accessed by:</span></span>  <br/> |<span data-ttu-id="dd26a-112">Outlook 和其他客户端</span><span class="sxs-lookup"><span data-stu-id="dd26a-112">Outlook and other clients</span></span>  <br/> |
|<span data-ttu-id="dd26a-113">属性类型</span><span class="sxs-lookup"><span data-stu-id="dd26a-113">Property type:</span></span>  <br/> |<span data-ttu-id="dd26a-114">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="dd26a-114">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="dd26a-115">访问类型：</span><span class="sxs-lookup"><span data-stu-id="dd26a-115">Access type:</span></span>  <br/> |<span data-ttu-id="dd26a-116">读/写</span><span class="sxs-lookup"><span data-stu-id="dd26a-116">Read/write</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dd26a-117">备注</span><span class="sxs-lookup"><span data-stu-id="dd26a-117">Remarks</span></span>

<span data-ttu-id="dd26a-118">若要提供的任何存储功能，存储提供程序必须实现[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)并返回任何传递给[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)调用这些属性的有效属性标记。</span><span class="sxs-lookup"><span data-stu-id="dd26a-118">To provide any of the store functionality, the store provider must implement [IMsgStore : IMAPIProp](imsgstoreimapiprop.md) and return a valid property tag for any of these properties passed to an [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) call.</span></span> <span data-ttu-id="dd26a-119">当属性标记为任何这些属性传递给[IMAPIProp::GetProps](imapiprop-getprops.md)时，存储提供程序必须也会返回正确的属性值。</span><span class="sxs-lookup"><span data-stu-id="dd26a-119">When the property tag for any of these properties is passed to [IMAPIProp::GetProps](imapiprop-getprops.md), the store provider must also return the correct property value.</span></span> <span data-ttu-id="dd26a-120">[HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)用于获取或设置这些属性，可以调用存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="dd26a-120">Store providers can call [HrGetOneProp](hrgetoneprop.md) and [HrSetOneProp](hrsetoneprop.md) to get or set these properties.</span></span> 
  
<span data-ttu-id="dd26a-121">若要检索此属性的值，客户应首先使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取该属性标记，然后[IMAPIProp::GetProps](imapiprop-getprops.md)获取值中指定此属性标记。</span><span class="sxs-lookup"><span data-stu-id="dd26a-121">To retrieve the value of this property, the client should first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="dd26a-122">调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)时, 指定的输入的参数_lppPropNames_指向[MAPINAMEID](mapinameid.md)结构的以下值：</span><span class="sxs-lookup"><span data-stu-id="dd26a-122">When calling [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), specify the following values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dd26a-123">lpGuid:</span><span class="sxs-lookup"><span data-stu-id="dd26a-123">lpGuid:</span></span>  <br/> |<span data-ttu-id="dd26a-124">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="dd26a-124">PS_PUBLIC_STRINGS</span></span>  <br/> |
|<span data-ttu-id="dd26a-125">ulKind:</span><span class="sxs-lookup"><span data-stu-id="dd26a-125">ulKind:</span></span>  <br/> |<span data-ttu-id="dd26a-126">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="dd26a-126">MNID_STRING</span></span>  <br/> |
|<span data-ttu-id="dd26a-127">Kind.lpwstrName:</span><span class="sxs-lookup"><span data-stu-id="dd26a-127">Kind.lpwstrName:</span></span>  <br/> |<span data-ttu-id="dd26a-128">L"urn： 架构-microsoft-com:office:outlook #storetypeprivate"</span><span class="sxs-lookup"><span data-stu-id="dd26a-128">L"urn:schemas-microsoft-com:office:outlook#storetypeprivate"</span></span>  <br/> |
   
<span data-ttu-id="dd26a-129">存储提供程序可以使用此属性使 Outlook 辅助用户存储时，将其视为私有。</span><span class="sxs-lookup"><span data-stu-id="dd26a-129">A store provider can use this property to have Outlook treat it as private when it is a secondary store for a user.</span></span> 
  
<span data-ttu-id="dd26a-130">默认情况下，Outlook 将辅助存储相同的方式视为代理存储区，并辅助存储中的项目是专用仅当用户标记这些专门为私有。</span><span class="sxs-lookup"><span data-stu-id="dd26a-130">By default, Outlook treats a secondary store the same way as a delegate store, and items in the secondary store are private only if the user marks them specifically as private.</span></span> <span data-ttu-id="dd26a-131">当此属性为**true**时，从第二存储区删除的项目被移动到主存储区中的**已删除邮件**文件夹。</span><span class="sxs-lookup"><span data-stu-id="dd26a-131">When this property is **true**, items deleted from a secondary store are moved to the **Deleted Items** folder in the primary store.</span></span> <span data-ttu-id="dd26a-132">不显示标记为私密的项。</span><span class="sxs-lookup"><span data-stu-id="dd26a-132">Items marked private are not displayed.</span></span> <span data-ttu-id="dd26a-133">草稿存储在主存储区中草稿文件夹中。</span><span class="sxs-lookup"><span data-stu-id="dd26a-133">Drafts are stored in the Drafts folder in the primary store.</span></span> 
  
<span data-ttu-id="dd26a-134">如果 Outlook 版本早于 Microsoft Office Outlook 2003 Service Pack 1，或如果其值为**false**，则忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="dd26a-134">This property is ignored if the version of Outlook is earlier than Microsoft Office Outlook 2003 Service Pack 1, or if its value is **false**.</span></span>
  

