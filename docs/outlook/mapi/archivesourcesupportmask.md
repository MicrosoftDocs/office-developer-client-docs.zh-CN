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
ms.openlocfilehash: 1e0c099783b4d44b1aaf746b07c77981c135ca9a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19774556"
---
# <a name="archivesourcesupportmask"></a><span data-ttu-id="5be1b-103">ArchiveSourceSupportMask</span><span class="sxs-lookup"><span data-stu-id="5be1b-103">ArchiveSourceSupportMask</span></span>

  
  
<span data-ttu-id="5be1b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5be1b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5be1b-105">指定 Microsoft Office Outlook 是否应扫描存储区中的文件夹并将它们自动存档。</span><span class="sxs-lookup"><span data-stu-id="5be1b-105">Specifies whether Microsoft Office Outlook should scan folders in a store and archive them automatically.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="5be1b-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="5be1b-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5be1b-107">公开上：</span><span class="sxs-lookup"><span data-stu-id="5be1b-107">Exposed on:</span></span>  <br/> |<span data-ttu-id="5be1b-108">[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象</span><span class="sxs-lookup"><span data-stu-id="5be1b-108">[IMsgStore : IMAPIProp](imsgstoreimapiprop.md) object</span></span>  <br/> |
|<span data-ttu-id="5be1b-109">通过创建：</span><span class="sxs-lookup"><span data-stu-id="5be1b-109">Created by:</span></span>  <br/> |<span data-ttu-id="5be1b-110">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="5be1b-110">Store provider</span></span>  <br/> |
|<span data-ttu-id="5be1b-111">通过来访问：</span><span class="sxs-lookup"><span data-stu-id="5be1b-111">Accessed by:</span></span>  <br/> |<span data-ttu-id="5be1b-112">Outlook 和其他客户端</span><span class="sxs-lookup"><span data-stu-id="5be1b-112">Outlook and other clients</span></span>  <br/> |
|<span data-ttu-id="5be1b-113">属性类型</span><span class="sxs-lookup"><span data-stu-id="5be1b-113">Property type:</span></span>  <br/> |<span data-ttu-id="5be1b-114">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="5be1b-114">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="5be1b-115">访问类型：</span><span class="sxs-lookup"><span data-stu-id="5be1b-115">Access type:</span></span>  <br/> |<span data-ttu-id="5be1b-116">只读或读/写，具体取决于存储提供程序</span><span class="sxs-lookup"><span data-stu-id="5be1b-116">Read-only or read/write depending on the store provider</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5be1b-117">说明</span><span class="sxs-lookup"><span data-stu-id="5be1b-117">Remarks</span></span>

<span data-ttu-id="5be1b-118">若要提供的任何存储功能，存储提供程序必须实现[IMAPIProp: IUnknown](imapipropiunknown.md)并返回任何传递给[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)调用这些属性的有效属性标记。</span><span class="sxs-lookup"><span data-stu-id="5be1b-118">To provide any of the store functionality, the store provider must implement [IMAPIProp : IUnknown](imapipropiunknown.md) and return a valid property tag for any of these properties passed to an [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) call.</span></span> <span data-ttu-id="5be1b-119">当属性标记为任何这些属性传递给[IMAPIProp::GetProps](imapiprop-getprops.md)时，存储提供程序必须也会返回正确的属性值。</span><span class="sxs-lookup"><span data-stu-id="5be1b-119">When the property tag for any of these properties is passed to [IMAPIProp::GetProps](imapiprop-getprops.md), the store provider must also return the correct property value.</span></span> <span data-ttu-id="5be1b-120">[HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)用于获取或设置这些属性，可以调用存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="5be1b-120">Store providers can call [HrGetOneProp](hrgetoneprop.md) and [HrSetOneProp](hrsetoneprop.md) to get or set these properties.</span></span> 
  
<span data-ttu-id="5be1b-121">若要检索此属性的值，客户应首先使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取该属性标记，然后[IMAPIProp::GetProps](imapiprop-getprops.md)获取值中指定此属性标记。</span><span class="sxs-lookup"><span data-stu-id="5be1b-121">To retrieve the value of this property, the client should first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="5be1b-122">调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)时, 指定的输入的参数_lppPropNames_指向[MAPINAMEID](mapinameid.md)结构的以下值：</span><span class="sxs-lookup"><span data-stu-id="5be1b-122">When calling [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), specify the following values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5be1b-123">lpGuid:</span><span class="sxs-lookup"><span data-stu-id="5be1b-123">lpGuid:</span></span>  <br/> |<span data-ttu-id="5be1b-124">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="5be1b-124">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="5be1b-125">ulKind:</span><span class="sxs-lookup"><span data-stu-id="5be1b-125">ulKind:</span></span>  <br/> |<span data-ttu-id="5be1b-126">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="5be1b-126">MNID_STRING</span></span>  <br/> |
|<span data-ttu-id="5be1b-127">Kind.lpwstrName:</span><span class="sxs-lookup"><span data-stu-id="5be1b-127">Kind.lpwstrName:</span></span>  <br/> |<span data-ttu-id="5be1b-128">L"ArchiveSourceSupportMask"</span><span class="sxs-lookup"><span data-stu-id="5be1b-128">L"ArchiveSourceSupportMask"</span></span>  <br/> |
   
<span data-ttu-id="5be1b-129">此属性允许存储提供程序，以指定 Outlook 是否应扫描存储区中的文件夹并将它们自动存档。</span><span class="sxs-lookup"><span data-stu-id="5be1b-129">This property allows store providers to specify whether Outlook should scan folders in a store and archive them automatically.</span></span>
  
<span data-ttu-id="5be1b-130">默认情况下，对存储，这意味着 Outlook 可以扫描存储区上的文件夹不公开此属性。</span><span class="sxs-lookup"><span data-stu-id="5be1b-130">By default, this property is not exposed on a store, which means Outlook can scan folders on the store.</span></span> <span data-ttu-id="5be1b-131">如果公开此属性，以下是可能的值：</span><span class="sxs-lookup"><span data-stu-id="5be1b-131">If the property is exposed, the following are the possible values:</span></span>
  
```cpp
enum { 
 ASM_DEFAULT              = 0, 
 ASM_DO_NOT_ARCHIVE         = 1 << 0x0, 
 ASM_CLIENT_DO_NOT_CHANGE = 1 << 0xF 
};
```

<span data-ttu-id="5be1b-132">ASM_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="5be1b-132">ASM_DEFAULT</span></span>
  
- <span data-ttu-id="5be1b-133">Outlook 可以扫描存储区上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="5be1b-133">Outlook can scan folders on the store.</span></span>
    
<span data-ttu-id="5be1b-134">ASM_DO_NOT_ARCHIVE</span><span class="sxs-lookup"><span data-stu-id="5be1b-134">ASM_DO_NOT_ARCHIVE</span></span>
  
- <span data-ttu-id="5be1b-135">Outlook 不应扫描存储区上的文件夹。</span><span class="sxs-lookup"><span data-stu-id="5be1b-135">Outlook should not scan folders on the store.</span></span>
    
<span data-ttu-id="5be1b-136">ASM_CLIENT_DO_NOT_CHANGE</span><span class="sxs-lookup"><span data-stu-id="5be1b-136">ASM_CLIENT_DO_NOT_CHANGE</span></span>
  
- <span data-ttu-id="5be1b-137">不允许客户端来更改此属性存储。</span><span class="sxs-lookup"><span data-stu-id="5be1b-137">Do not allow clients to change this property on the store.</span></span> <span data-ttu-id="5be1b-138">请注意，常量**ASM_CLIENT_DO_NOT_CHANGE**以供将来参考是当前未实现。</span><span class="sxs-lookup"><span data-stu-id="5be1b-138">Note that the constant **ASM_CLIENT_DO_NOT_CHANGE** is for future reference and is not currently implemented.</span></span> <span data-ttu-id="5be1b-139">现在，存储可以阻止客户端硬存储此属性返回的值更改此标志。</span><span class="sxs-lookup"><span data-stu-id="5be1b-139">For now, a store can prevent clients from changing this flag by hardcoding the value that the store returns for this property.</span></span> 
    

