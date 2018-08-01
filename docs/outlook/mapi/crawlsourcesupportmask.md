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
ms.openlocfilehash: a1754a7c82d7164617c97df97b762efb1555ccda
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774719"
---
# <a name="crawlsourcesupportmask"></a><span data-ttu-id="5f50b-103">CrawlSourceSupportMask</span><span class="sxs-lookup"><span data-stu-id="5f50b-103">CrawlSourceSupportMask</span></span>

  
  
<span data-ttu-id="5f50b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5f50b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5f50b-105">指定 Microsoft Office Outlook 是否应扫描存储区，包括联系人、 日历和任务文件夹，请在启动填充导航窗格中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="5f50b-105">Specifies whether Microsoft Office Outlook should scan folders in a store, including Contacts, Calendar, and Tasks folders, on startup to populate the Navigation Pane.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="5f50b-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="5f50b-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5f50b-107">公开上：</span><span class="sxs-lookup"><span data-stu-id="5f50b-107">Exposed on:</span></span>  <br/> |<span data-ttu-id="5f50b-108">[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象</span><span class="sxs-lookup"><span data-stu-id="5f50b-108">[IMsgStore : IMAPIProp](imsgstoreimapiprop.md) object</span></span>  <br/> |
|<span data-ttu-id="5f50b-109">通过创建：</span><span class="sxs-lookup"><span data-stu-id="5f50b-109">Created by:</span></span>  <br/> |<span data-ttu-id="5f50b-110">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="5f50b-110">Store provider</span></span>  <br/> |
|<span data-ttu-id="5f50b-111">通过来访问：</span><span class="sxs-lookup"><span data-stu-id="5f50b-111">Accessed by:</span></span>  <br/> |<span data-ttu-id="5f50b-112">Outlook 和其他客户端</span><span class="sxs-lookup"><span data-stu-id="5f50b-112">Outlook and other clients</span></span>  <br/> |
|<span data-ttu-id="5f50b-113">属性类型</span><span class="sxs-lookup"><span data-stu-id="5f50b-113">Property type:</span></span>  <br/> |<span data-ttu-id="5f50b-114">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="5f50b-114">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="5f50b-115">访问类型：</span><span class="sxs-lookup"><span data-stu-id="5f50b-115">Access type:</span></span>  <br/> |<span data-ttu-id="5f50b-116">只读或读/写，具体取决于存储提供程序</span><span class="sxs-lookup"><span data-stu-id="5f50b-116">Read-only or read/write depending on the store provider</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5f50b-117">说明</span><span class="sxs-lookup"><span data-stu-id="5f50b-117">Remarks</span></span>

<span data-ttu-id="5f50b-118">若要提供的任何存储功能，存储提供程序必须实现[IMAPIProp: IUnknown](imapipropiunknown.md)并返回任何传递给[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)调用这些属性的有效属性标记。</span><span class="sxs-lookup"><span data-stu-id="5f50b-118">To provide any of the store functionality, the store provider must implement [IMAPIProp : IUnknown](imapipropiunknown.md) and return a valid property tag for any of these properties passed to an [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) call.</span></span> <span data-ttu-id="5f50b-119">当属性标记为任何这些属性传递给[IMAPIProp::GetProps](imapiprop-getprops.md)时，存储提供程序必须也会返回正确的属性值。</span><span class="sxs-lookup"><span data-stu-id="5f50b-119">When the property tag for any of these properties is passed to [IMAPIProp::GetProps](imapiprop-getprops.md), the store provider must also return the correct property value.</span></span> <span data-ttu-id="5f50b-120">[HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)用于获取或设置这些属性，可以调用存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="5f50b-120">Store providers can call [HrGetOneProp](hrgetoneprop.md) and [HrSetOneProp](hrsetoneprop.md) to get or set these properties.</span></span> 
  
<span data-ttu-id="5f50b-121">若要检索此属性的值，客户应首先使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取该属性标记，然后[IMAPIProp::GetProps](imapiprop-getprops.md)获取值中指定此属性标记。</span><span class="sxs-lookup"><span data-stu-id="5f50b-121">To retrieve the value of this property, the client should first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="5f50b-122">调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)时, 指定的输入的参数_lppPropNames_指向[MAPINAMEID](mapinameid.md)结构的以下值：</span><span class="sxs-lookup"><span data-stu-id="5f50b-122">When calling [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), specify the following values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5f50b-123">lpGuid:</span><span class="sxs-lookup"><span data-stu-id="5f50b-123">lpGuid:</span></span>  <br/> |<span data-ttu-id="5f50b-124">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="5f50b-124">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="5f50b-125">ulKind:</span><span class="sxs-lookup"><span data-stu-id="5f50b-125">ulKind:</span></span>  <br/> |<span data-ttu-id="5f50b-126">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="5f50b-126">MNID_STRING</span></span>  <br/> |
|<span data-ttu-id="5f50b-127">Kind.lpwstrName:</span><span class="sxs-lookup"><span data-stu-id="5f50b-127">Kind.lpwstrName:</span></span>  <br/> |<span data-ttu-id="5f50b-128">L"CrawlSourceSupportMask"</span><span class="sxs-lookup"><span data-stu-id="5f50b-128">L"CrawlSourceSupportMask"</span></span>  <br/> |
   
<span data-ttu-id="5f50b-129">此属性提供了一种存储提供程序，以指定 Outlook 是否应扫描各种文件夹存储区中的方法。</span><span class="sxs-lookup"><span data-stu-id="5f50b-129">This property provides a way for store providers to specify whether Outlook should scan various folders in a store.</span></span> <span data-ttu-id="5f50b-130">时使用它在启动 Outlook 扫描填充**导航**窗格中; 每个打开的存储区上的现有文件夹Outlook 将启动扫描之前检查状态和存储区上的此属性的值。</span><span class="sxs-lookup"><span data-stu-id="5f50b-130">It is used on startup when Outlook scans existing folders on each opened store to populate the **Navigation** pane; Outlook checks for the presence and value of this property on a store before initiating the scan.</span></span> 
  
<span data-ttu-id="5f50b-131">默认情况下，对存储，这意味着 Outlook 可以扫描存储区上的文件夹不公开此属性。</span><span class="sxs-lookup"><span data-stu-id="5f50b-131">By default, this property is not exposed on a store, which means Outlook can scan folders on the store.</span></span> <span data-ttu-id="5f50b-132">如果公开此属性，以下是可能的值：</span><span class="sxs-lookup"><span data-stu-id="5f50b-132">If the property is exposed, the following are the possible values:</span></span>
  
```
enum { 
 CSM_DEFAULT              = 0, 
 CSM_DO_NOT_CRAWL         = 1 << 0x0, 
 CSM_CLIENT_DO_NOT_CHANGE = 1 << 0xF 
};
```

<span data-ttu-id="5f50b-133">CSM_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="5f50b-133">CSM_DEFAULT</span></span>
  
- <span data-ttu-id="5f50b-134">Outlook 可以扫描存储区上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="5f50b-134">Outlook can scan folders on the store.</span></span>
    
<span data-ttu-id="5f50b-135">CSM_DO_NOT_CRAWL</span><span class="sxs-lookup"><span data-stu-id="5f50b-135">CSM_DO_NOT_CRAWL</span></span>
  
- <span data-ttu-id="5f50b-136">Outlook 不应扫描存储区上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="5f50b-136">Outlook should not scan folders on the store.</span></span>
    
<span data-ttu-id="5f50b-137">CSM_CLIENT_DO_NOT_CHANGE</span><span class="sxs-lookup"><span data-stu-id="5f50b-137">CSM_CLIENT_DO_NOT_CHANGE</span></span>
  
- <span data-ttu-id="5f50b-138">不允许客户端来更改此属性存储。</span><span class="sxs-lookup"><span data-stu-id="5f50b-138">Do not allow clients to change this property on the store.</span></span> <span data-ttu-id="5f50b-139">请注意，常量**CSM_CLIENT_DO_NOT_CHANGE**以供将来参考是当前未实现。</span><span class="sxs-lookup"><span data-stu-id="5f50b-139">Note that the constant **CSM_CLIENT_DO_NOT_CHANGE** is for future reference and is not currently implemented.</span></span> <span data-ttu-id="5f50b-140">现在，存储可以阻止客户端硬存储此属性返回的值更改此标志。</span><span class="sxs-lookup"><span data-stu-id="5f50b-140">For now, a store can prevent clients from changing this flag by hardcoding the value that the store returns for this property.</span></span> 
    

