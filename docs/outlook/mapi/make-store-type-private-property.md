---
title: 使应用商店类型成为专用属性
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
ms.openlocfilehash: da55afcabb1354959a71d6f10472c05540427b19
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428541"
---
# <a name="make-store-type-private-property"></a><span data-ttu-id="6c3bb-103">使应用商店类型成为专用属性</span><span class="sxs-lookup"><span data-stu-id="6c3bb-103">Make Store Type Private Property</span></span>

  
  
<span data-ttu-id="6c3bb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6c3bb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6c3bb-105">将辅助存储视为专用存储。</span><span class="sxs-lookup"><span data-stu-id="6c3bb-105">Treats a secondary store as private.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="6c3bb-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="6c3bb-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6c3bb-107">在：</span><span class="sxs-lookup"><span data-stu-id="6c3bb-107">Exposed on:</span></span>  <br/> |<span data-ttu-id="6c3bb-108">[IMsgStore ： IMAPIProp](imsgstoreimapiprop.md) 对象</span><span class="sxs-lookup"><span data-stu-id="6c3bb-108">[IMsgStore : IMAPIProp](imsgstoreimapiprop.md) object</span></span>  <br/> |
|<span data-ttu-id="6c3bb-109">创建者：</span><span class="sxs-lookup"><span data-stu-id="6c3bb-109">Created by:</span></span>  <br/> |<span data-ttu-id="6c3bb-110">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="6c3bb-110">Store provider</span></span>  <br/> |
|<span data-ttu-id="6c3bb-111">访问者：</span><span class="sxs-lookup"><span data-stu-id="6c3bb-111">Accessed by:</span></span>  <br/> |<span data-ttu-id="6c3bb-112">Outlook客户端和其他客户端</span><span class="sxs-lookup"><span data-stu-id="6c3bb-112">Outlook and other clients</span></span>  <br/> |
|<span data-ttu-id="6c3bb-113">属性类型</span><span class="sxs-lookup"><span data-stu-id="6c3bb-113">Property type:</span></span>  <br/> |<span data-ttu-id="6c3bb-114">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="6c3bb-114">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="6c3bb-115">访问类型：</span><span class="sxs-lookup"><span data-stu-id="6c3bb-115">Access type:</span></span>  <br/> |<span data-ttu-id="6c3bb-116">读/写</span><span class="sxs-lookup"><span data-stu-id="6c3bb-116">Read/write</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6c3bb-117">备注</span><span class="sxs-lookup"><span data-stu-id="6c3bb-117">Remarks</span></span>

<span data-ttu-id="6c3bb-118">若要提供任何存储功能，存储提供程序必须实现 [IMsgStore ： IMAPIProp](imsgstoreimapiprop.md) 并返回传递给 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 调用的任何属性的有效属性标记。</span><span class="sxs-lookup"><span data-stu-id="6c3bb-118">To provide any of the store functionality, the store provider must implement [IMsgStore : IMAPIProp](imsgstoreimapiprop.md) and return a valid property tag for any of these properties passed to an [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) call.</span></span> <span data-ttu-id="6c3bb-119">当其中任何属性的属性标记传递到 [IMAPIProp：：GetProps](imapiprop-getprops.md)时，存储提供程序还必须返回正确的属性值。</span><span class="sxs-lookup"><span data-stu-id="6c3bb-119">When the property tag for any of these properties is passed to [IMAPIProp::GetProps](imapiprop-getprops.md), the store provider must also return the correct property value.</span></span> <span data-ttu-id="6c3bb-120">存储提供程序可以调用 [HrGetOneProp](hrgetoneprop.md) 和 [HrSetOneProp](hrsetoneprop.md) 获取或设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="6c3bb-120">Store providers can call [HrGetOneProp](hrgetoneprop.md) and [HrSetOneProp](hrsetoneprop.md) to get or set these properties.</span></span> 
  
<span data-ttu-id="6c3bb-121">若要检索此属性的值，客户端应首先使用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 获取属性标记，然后在 [IMAPIProp：：GetProps](imapiprop-getprops.md) 中指定此属性标记以获取值。</span><span class="sxs-lookup"><span data-stu-id="6c3bb-121">To retrieve the value of this property, the client should first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="6c3bb-122">调用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md)时，为输入参数 _lppPropNames_ 指向的 [MAPINAMEID](mapinameid.md)结构指定以下值：</span><span class="sxs-lookup"><span data-stu-id="6c3bb-122">When calling [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), specify the following values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6c3bb-123">lpGuid：</span><span class="sxs-lookup"><span data-stu-id="6c3bb-123">lpGuid:</span></span>  <br/> |<span data-ttu-id="6c3bb-124">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="6c3bb-124">PS_PUBLIC_STRINGS</span></span>  <br/> |
|<span data-ttu-id="6c3bb-125">ulKind：</span><span class="sxs-lookup"><span data-stu-id="6c3bb-125">ulKind:</span></span>  <br/> |<span data-ttu-id="6c3bb-126">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="6c3bb-126">MNID_STRING</span></span>  <br/> |
|<span data-ttu-id="6c3bb-127">Kind.lpwstrName：</span><span class="sxs-lookup"><span data-stu-id="6c3bb-127">Kind.lpwstrName:</span></span>  <br/> |<span data-ttu-id="6c3bb-128">L"urn：schemas-microsoft-com：office：outlook#storetypeprivate"</span><span class="sxs-lookup"><span data-stu-id="6c3bb-128">L"urn:schemas-microsoft-com:office:outlook#storetypeprivate"</span></span>  <br/> |
   
<span data-ttu-id="6c3bb-129">当存储提供程序是用户的辅助Outlook时，可以使用此属性将此属性视为专用存储。</span><span class="sxs-lookup"><span data-stu-id="6c3bb-129">A store provider can use this property to have Outlook treat it as private when it is a secondary store for a user.</span></span> 
  
<span data-ttu-id="6c3bb-130">默认情况下，Outlook存储处理辅助存储的方式与代理存储相同，并且辅助存储中的项目仅在用户专门将其标记为专用时是私有的。</span><span class="sxs-lookup"><span data-stu-id="6c3bb-130">By default, Outlook treats a secondary store the same way as a delegate store, and items in the secondary store are private only if the user marks them specifically as private.</span></span> <span data-ttu-id="6c3bb-131">当此属性为 **true** 时，从辅助存储中删除的项目将移动到主存储中的"已删除 **邮件** "文件夹。</span><span class="sxs-lookup"><span data-stu-id="6c3bb-131">When this property is **true**, items deleted from a secondary store are moved to the **Deleted Items** folder in the primary store.</span></span> <span data-ttu-id="6c3bb-132">标记为私有的项目不显示。</span><span class="sxs-lookup"><span data-stu-id="6c3bb-132">Items marked private are not displayed.</span></span> <span data-ttu-id="6c3bb-133">草稿存储在主存储的"草稿"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6c3bb-133">Drafts are stored in the Drafts folder in the primary store.</span></span> 
  
<span data-ttu-id="6c3bb-134">如果服务包的版本早于 Outlook 2003 Service Pack 1 Microsoft Office Outlook或其值为 **false，** 则忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="6c3bb-134">This property is ignored if the version of Outlook is earlier than Microsoft Office Outlook 2003 Service Pack 1, or if its value is **false**.</span></span>
  

