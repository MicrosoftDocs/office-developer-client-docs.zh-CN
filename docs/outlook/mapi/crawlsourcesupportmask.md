---
title: CrawlSourceSupportMask
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- CrawlSourceSupportMask
api_type:
- COM
ms.assetid: d0a2f7ea-df6a-89e8-18c2-ac92e0a20edc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cc3fcedb73b4acbd85529615d857403b4c268f3d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32333045"
---
# <a name="crawlsourcesupportmask"></a><span data-ttu-id="2ebb5-103">CrawlSourceSupportMask</span><span class="sxs-lookup"><span data-stu-id="2ebb5-103">CrawlSourceSupportMask</span></span>

  
  
<span data-ttu-id="2ebb5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2ebb5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2ebb5-105">指定 Microsoft Office Outlook 是否应扫描存储区中的文件夹, 包括 "联系人"、"日历" 和 "任务" 文件夹, 以便在启动时填充导航窗格。</span><span class="sxs-lookup"><span data-stu-id="2ebb5-105">Specifies whether Microsoft Office Outlook should scan folders in a store, including Contacts, Calendar, and Tasks folders, on startup to populate the Navigation Pane.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="2ebb5-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="2ebb5-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="2ebb5-107">公开于:</span><span class="sxs-lookup"><span data-stu-id="2ebb5-107">Exposed on:</span></span>  <br/> |<span data-ttu-id="2ebb5-108">[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象</span><span class="sxs-lookup"><span data-stu-id="2ebb5-108">[IMsgStore : IMAPIProp](imsgstoreimapiprop.md) object</span></span>  <br/> |
|<span data-ttu-id="2ebb5-109">创建者:</span><span class="sxs-lookup"><span data-stu-id="2ebb5-109">Created by:</span></span>  <br/> |<span data-ttu-id="2ebb5-110">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="2ebb5-110">Store provider</span></span>  <br/> |
|<span data-ttu-id="2ebb5-111">访问者:</span><span class="sxs-lookup"><span data-stu-id="2ebb5-111">Accessed by:</span></span>  <br/> |<span data-ttu-id="2ebb5-112">Outlook 和其他客户端</span><span class="sxs-lookup"><span data-stu-id="2ebb5-112">Outlook and other clients</span></span>  <br/> |
|<span data-ttu-id="2ebb5-113">属性类型</span><span class="sxs-lookup"><span data-stu-id="2ebb5-113">Property type:</span></span>  <br/> |<span data-ttu-id="2ebb5-114">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="2ebb5-114">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="2ebb5-115">访问类型:</span><span class="sxs-lookup"><span data-stu-id="2ebb5-115">Access type:</span></span>  <br/> |<span data-ttu-id="2ebb5-116">只读或读/写, 具体取决于存储提供程序</span><span class="sxs-lookup"><span data-stu-id="2ebb5-116">Read-only or read/write depending on the store provider</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2ebb5-117">注解</span><span class="sxs-lookup"><span data-stu-id="2ebb5-117">Remarks</span></span>

<span data-ttu-id="2ebb5-118">若要提供任何存储功能, 存储提供程序必须实现[IMAPIProp: IUnknown](imapipropiunknown.md) , 并返回传递给[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)调用的任何这些属性的有效属性标记。</span><span class="sxs-lookup"><span data-stu-id="2ebb5-118">To provide any of the store functionality, the store provider must implement [IMAPIProp : IUnknown](imapipropiunknown.md) and return a valid property tag for any of these properties passed to an [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) call.</span></span> <span data-ttu-id="2ebb5-119">当这些属性中任一属性的属性标记传递给[IMAPIProp:: GetProps](imapiprop-getprops.md)时, 存储提供程序还必须返回正确的属性值。</span><span class="sxs-lookup"><span data-stu-id="2ebb5-119">When the property tag for any of these properties is passed to [IMAPIProp::GetProps](imapiprop-getprops.md), the store provider must also return the correct property value.</span></span> <span data-ttu-id="2ebb5-120">存储提供程序可以调用[HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)以获取或设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="2ebb5-120">Store providers can call [HrGetOneProp](hrgetoneprop.md) and [HrSetOneProp](hrsetoneprop.md) to get or set these properties.</span></span> 
  
<span data-ttu-id="2ebb5-121">若要检索此属性的值, 客户端应首先使用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)获取属性标记, 然后在[IMAPIProp:: GetProps](imapiprop-getprops.md)中指定此属性标记以获取值。</span><span class="sxs-lookup"><span data-stu-id="2ebb5-121">To retrieve the value of this property, the client should first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="2ebb5-122">调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)时, 请为输入参数_lppPropNames_所指向的[MAPINAMEID](mapinameid.md)结构指定以下值:</span><span class="sxs-lookup"><span data-stu-id="2ebb5-122">When calling [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), specify the following values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2ebb5-123">lpGuid:</span><span class="sxs-lookup"><span data-stu-id="2ebb5-123">lpGuid:</span></span>  <br/> |<span data-ttu-id="2ebb5-124">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="2ebb5-124">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="2ebb5-125">ulKind:</span><span class="sxs-lookup"><span data-stu-id="2ebb5-125">ulKind:</span></span>  <br/> |<span data-ttu-id="2ebb5-126">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="2ebb5-126">MNID_STRING</span></span>  <br/> |
|<span data-ttu-id="2ebb5-127">类型 lpwstrName:</span><span class="sxs-lookup"><span data-stu-id="2ebb5-127">Kind.lpwstrName:</span></span>  <br/> |<span data-ttu-id="2ebb5-128">L "CrawlSourceSupportMask"</span><span class="sxs-lookup"><span data-stu-id="2ebb5-128">L"CrawlSourceSupportMask"</span></span>  <br/> |
   
<span data-ttu-id="2ebb5-129">此属性提供了一种存储提供程序以指定 Outlook 是否应扫描存储中的各个文件夹的方法。</span><span class="sxs-lookup"><span data-stu-id="2ebb5-129">This property provides a way for store providers to specify whether Outlook should scan various folders in a store.</span></span> <span data-ttu-id="2ebb5-130">当 Outlook 扫描每个打开的存储区上的现有文件夹以填充**导航**窗格时, 在启动时使用它。Outlook 在启动扫描前检查是否存在该存储的该属性的状态和值。</span><span class="sxs-lookup"><span data-stu-id="2ebb5-130">It is used on startup when Outlook scans existing folders on each opened store to populate the **Navigation** pane; Outlook checks for the presence and value of this property on a store before initiating the scan.</span></span> 
  
<span data-ttu-id="2ebb5-131">默认情况下, 不会在存储区上公开此属性, 这意味着 Outlook 可以扫描存储区上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="2ebb5-131">By default, this property is not exposed on a store, which means Outlook can scan folders on the store.</span></span> <span data-ttu-id="2ebb5-132">如果公开了属性, 以下是可能的值:</span><span class="sxs-lookup"><span data-stu-id="2ebb5-132">If the property is exposed, the following are the possible values:</span></span>
  
```
enum { 
 CSM_DEFAULT              = 0, 
 CSM_DO_NOT_CRAWL         = 1 << 0x0, 
 CSM_CLIENT_DO_NOT_CHANGE = 1 << 0xF 
};
```

<span data-ttu-id="2ebb5-133">CSM_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2ebb5-133">CSM_DEFAULT</span></span>
  
- <span data-ttu-id="2ebb5-134">Outlook 可以扫描存储区上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="2ebb5-134">Outlook can scan folders on the store.</span></span>
    
<span data-ttu-id="2ebb5-135">CSM_DO_NOT_CRAWL</span><span class="sxs-lookup"><span data-stu-id="2ebb5-135">CSM_DO_NOT_CRAWL</span></span>
  
- <span data-ttu-id="2ebb5-136">Outlook 不应扫描存储区上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="2ebb5-136">Outlook should not scan folders on the store.</span></span>
    
<span data-ttu-id="2ebb5-137">CSM_CLIENT_DO_NOT_CHANGE</span><span class="sxs-lookup"><span data-stu-id="2ebb5-137">CSM_CLIENT_DO_NOT_CHANGE</span></span>
  
- <span data-ttu-id="2ebb5-138">不允许客户端更改存储区上的该属性。</span><span class="sxs-lookup"><span data-stu-id="2ebb5-138">Do not allow clients to change this property on the store.</span></span> <span data-ttu-id="2ebb5-139">请注意, 常量**CSM_CLIENT_DO_NOT_CHANGE**是为了供将来参考, 目前尚未实现。</span><span class="sxs-lookup"><span data-stu-id="2ebb5-139">Note that the constant **CSM_CLIENT_DO_NOT_CHANGE** is for future reference and is not currently implemented.</span></span> <span data-ttu-id="2ebb5-140">现在, 存储可以阻止客户端更改此标志, hardcoding 存储为此属性返回的值。</span><span class="sxs-lookup"><span data-stu-id="2ebb5-140">For now, a store can prevent clients from changing this flag by hardcoding the value that the store returns for this property.</span></span> 
    

