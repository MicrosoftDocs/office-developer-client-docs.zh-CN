---
title: ArchiveSourceSupportMask
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ArchiveSourceSupportMask
api_type:
- COM
ms.assetid: e35216e0-c23f-70f2-0d5f-1ac5dc00fd8c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6fc5e8eb74d79d0a30ae6a423772ce741dee4562
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418090"
---
# <a name="archivesourcesupportmask"></a><span data-ttu-id="6bd0d-103">ArchiveSourceSupportMask</span><span class="sxs-lookup"><span data-stu-id="6bd0d-103">ArchiveSourceSupportMask</span></span>

  
  
<span data-ttu-id="6bd0d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6bd0d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6bd0d-105">指定用户Microsoft Office Outlook扫描存储区中的文件夹并自动存档它们。</span><span class="sxs-lookup"><span data-stu-id="6bd0d-105">Specifies whether Microsoft Office Outlook should scan folders in a store and archive them automatically.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="6bd0d-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="6bd0d-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6bd0d-107">在：</span><span class="sxs-lookup"><span data-stu-id="6bd0d-107">Exposed on:</span></span>  <br/> |<span data-ttu-id="6bd0d-108">[IMsgStore ： IMAPIProp](imsgstoreimapiprop.md) 对象</span><span class="sxs-lookup"><span data-stu-id="6bd0d-108">[IMsgStore : IMAPIProp](imsgstoreimapiprop.md) object</span></span>  <br/> |
|<span data-ttu-id="6bd0d-109">创建者：</span><span class="sxs-lookup"><span data-stu-id="6bd0d-109">Created by:</span></span>  <br/> |<span data-ttu-id="6bd0d-110">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="6bd0d-110">Store provider</span></span>  <br/> |
|<span data-ttu-id="6bd0d-111">访问者：</span><span class="sxs-lookup"><span data-stu-id="6bd0d-111">Accessed by:</span></span>  <br/> |<span data-ttu-id="6bd0d-112">Outlook客户端和其他客户端</span><span class="sxs-lookup"><span data-stu-id="6bd0d-112">Outlook and other clients</span></span>  <br/> |
|<span data-ttu-id="6bd0d-113">属性类型</span><span class="sxs-lookup"><span data-stu-id="6bd0d-113">Property type:</span></span>  <br/> |<span data-ttu-id="6bd0d-114">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="6bd0d-114">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="6bd0d-115">访问类型：</span><span class="sxs-lookup"><span data-stu-id="6bd0d-115">Access type:</span></span>  <br/> |<span data-ttu-id="6bd0d-116">只读或可读/写，具体取决于存储提供程序</span><span class="sxs-lookup"><span data-stu-id="6bd0d-116">Read-only or read/write depending on the store provider</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6bd0d-117">备注</span><span class="sxs-lookup"><span data-stu-id="6bd0d-117">Remarks</span></span>

<span data-ttu-id="6bd0d-118">若要提供任何存储功能，存储提供程序必须实现 [IMAPIProp ： IUnknown](imapipropiunknown.md) 并返回传递给 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 调用的任何属性的有效属性标记。</span><span class="sxs-lookup"><span data-stu-id="6bd0d-118">To provide any of the store functionality, the store provider must implement [IMAPIProp : IUnknown](imapipropiunknown.md) and return a valid property tag for any of these properties passed to an [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) call.</span></span> <span data-ttu-id="6bd0d-119">当其中任何属性的属性标记传递到 [IMAPIProp：：GetProps](imapiprop-getprops.md)时，存储提供程序还必须返回正确的属性值。</span><span class="sxs-lookup"><span data-stu-id="6bd0d-119">When the property tag for any of these properties is passed to [IMAPIProp::GetProps](imapiprop-getprops.md), the store provider must also return the correct property value.</span></span> <span data-ttu-id="6bd0d-120">存储提供程序可以调用 [HrGetOneProp](hrgetoneprop.md) 和 [HrSetOneProp](hrsetoneprop.md) 获取或设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="6bd0d-120">Store providers can call [HrGetOneProp](hrgetoneprop.md) and [HrSetOneProp](hrsetoneprop.md) to get or set these properties.</span></span> 
  
<span data-ttu-id="6bd0d-121">若要检索此属性的值，客户端应首先使用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 获取属性标记，然后在 [IMAPIProp：：GetProps](imapiprop-getprops.md) 中指定此属性标记以获取值。</span><span class="sxs-lookup"><span data-stu-id="6bd0d-121">To retrieve the value of this property, the client should first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="6bd0d-122">调用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md)时，为输入参数 _lppPropNames_ 指向的 [MAPINAMEID](mapinameid.md)结构指定以下值：</span><span class="sxs-lookup"><span data-stu-id="6bd0d-122">When calling [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), specify the following values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6bd0d-123">lpGuid：</span><span class="sxs-lookup"><span data-stu-id="6bd0d-123">lpGuid:</span></span>  <br/> |<span data-ttu-id="6bd0d-124">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="6bd0d-124">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="6bd0d-125">ulKind：</span><span class="sxs-lookup"><span data-stu-id="6bd0d-125">ulKind:</span></span>  <br/> |<span data-ttu-id="6bd0d-126">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="6bd0d-126">MNID_STRING</span></span>  <br/> |
|<span data-ttu-id="6bd0d-127">Kind.lpwstrName：</span><span class="sxs-lookup"><span data-stu-id="6bd0d-127">Kind.lpwstrName:</span></span>  <br/> |<span data-ttu-id="6bd0d-128">L"ArchiveSourceSupportMask"</span><span class="sxs-lookup"><span data-stu-id="6bd0d-128">L"ArchiveSourceSupportMask"</span></span>  <br/> |
   
<span data-ttu-id="6bd0d-129">此属性允许存储提供程序指定Outlook应扫描存储区中的文件夹并自动存档它们。</span><span class="sxs-lookup"><span data-stu-id="6bd0d-129">This property allows store providers to specify whether Outlook should scan folders in a store and archive them automatically.</span></span>
  
<span data-ttu-id="6bd0d-130">默认情况下，此属性不会在存储区上公开，这意味着Outlook扫描存储区上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="6bd0d-130">By default, this property is not exposed on a store, which means Outlook can scan folders on the store.</span></span> <span data-ttu-id="6bd0d-131">如果公开该属性，则可能的值如下：</span><span class="sxs-lookup"><span data-stu-id="6bd0d-131">If the property is exposed, the following are the possible values:</span></span>
  
```cpp
enum { 
 ASM_DEFAULT              = 0, 
 ASM_DO_NOT_ARCHIVE         = 1 << 0x0, 
 ASM_CLIENT_DO_NOT_CHANGE = 1 << 0xF 
};
```

<span data-ttu-id="6bd0d-132">ASM_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="6bd0d-132">ASM_DEFAULT</span></span>
  
- <span data-ttu-id="6bd0d-133">Outlook扫描存储区上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="6bd0d-133">Outlook can scan folders on the store.</span></span>
    
<span data-ttu-id="6bd0d-134">ASM_DO_NOT_ARCHIVE</span><span class="sxs-lookup"><span data-stu-id="6bd0d-134">ASM_DO_NOT_ARCHIVE</span></span>
  
- <span data-ttu-id="6bd0d-135">Outlook不应扫描存储区上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="6bd0d-135">Outlook should not scan folders on the store.</span></span>
    
<span data-ttu-id="6bd0d-136">ASM_CLIENT_DO_NOT_CHANGE</span><span class="sxs-lookup"><span data-stu-id="6bd0d-136">ASM_CLIENT_DO_NOT_CHANGE</span></span>
  
- <span data-ttu-id="6bd0d-137">不允许客户端在存储上更改此属性。</span><span class="sxs-lookup"><span data-stu-id="6bd0d-137">Do not allow clients to change this property on the store.</span></span> <span data-ttu-id="6bd0d-138">请注意，常量 **ASM_CLIENT_DO_NOT_CHANGE** 供将来参考，当前未实现。</span><span class="sxs-lookup"><span data-stu-id="6bd0d-138">Note that the constant **ASM_CLIENT_DO_NOT_CHANGE** is for future reference and is not currently implemented.</span></span> <span data-ttu-id="6bd0d-139">目前，存储区可以通过硬用存储为此属性返回的值硬值来阻止客户端更改此标志。</span><span class="sxs-lookup"><span data-stu-id="6bd0d-139">For now, a store can prevent clients from changing this flag by hardcoding the value that the store returns for this property.</span></span> 
    

