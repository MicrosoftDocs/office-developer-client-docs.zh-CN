---
title: NoFolderScan
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 4949aef9-4c96-82cc-cd13-57981e07cc40
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3416bc50e4628df2be09f9fe1a22d19530bcdff8
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578050"
---
# <a name="nofolderscan"></a><span data-ttu-id="19a26-103">NoFolderScan</span><span class="sxs-lookup"><span data-stu-id="19a26-103">NoFolderScan</span></span>

  
  
<span data-ttu-id="19a26-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="19a26-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="19a26-105">指定 Microsoft Office Outlook 是否应扫描存储区上的联系人文件夹。</span><span class="sxs-lookup"><span data-stu-id="19a26-105">Specifies whether Microsoft Office Outlook should scan Contacts folders on a store.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="19a26-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="19a26-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="19a26-107">公开上：</span><span class="sxs-lookup"><span data-stu-id="19a26-107">Exposed on:</span></span>  <br/> |<span data-ttu-id="19a26-108">[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象</span><span class="sxs-lookup"><span data-stu-id="19a26-108">[IMsgStore : IMAPIProp](imsgstoreimapiprop.md) object</span></span>  <br/> |
|<span data-ttu-id="19a26-109">通过创建：</span><span class="sxs-lookup"><span data-stu-id="19a26-109">Created by:</span></span>  <br/> |<span data-ttu-id="19a26-110">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="19a26-110">Store provider</span></span>  <br/> |
|<span data-ttu-id="19a26-111">通过来访问：</span><span class="sxs-lookup"><span data-stu-id="19a26-111">Accessed by:</span></span>  <br/> |<span data-ttu-id="19a26-112">Outlook 和其他客户端</span><span class="sxs-lookup"><span data-stu-id="19a26-112">Outlook and other clients</span></span>  <br/> |
|<span data-ttu-id="19a26-113">属性类型</span><span class="sxs-lookup"><span data-stu-id="19a26-113">Property type:</span></span>  <br/> |<span data-ttu-id="19a26-114">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="19a26-114">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="19a26-115">访问类型：</span><span class="sxs-lookup"><span data-stu-id="19a26-115">Access type:</span></span>  <br/> |<span data-ttu-id="19a26-116">只读或读/写，具体取决于存储提供程序</span><span class="sxs-lookup"><span data-stu-id="19a26-116">Read-only or read/write depending on the store provider</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="19a26-117">注解</span><span class="sxs-lookup"><span data-stu-id="19a26-117">Remarks</span></span>

<span data-ttu-id="19a26-118">若要提供的任何存储功能，存储提供程序必须实现[IMAPIProp: IUnknown](imapipropiunknown.md)并返回任何传递给[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)调用这些属性的有效属性标记。</span><span class="sxs-lookup"><span data-stu-id="19a26-118">To provide any of the store functionality, the store provider must implement [IMAPIProp : IUnknown](imapipropiunknown.md) and return a valid property tag for any of these properties passed to an [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) call.</span></span> <span data-ttu-id="19a26-119">当属性标记为任何这些属性传递给[IMAPIProp::GetProps](imapiprop-getprops.md)时，存储提供程序必须也会返回正确的属性值。</span><span class="sxs-lookup"><span data-stu-id="19a26-119">When the property tag for any of these properties is passed to [IMAPIProp::GetProps](imapiprop-getprops.md), the store provider must also return the correct property value.</span></span> <span data-ttu-id="19a26-120">[HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)用于获取或设置这些属性，可以调用存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="19a26-120">Store providers can call [HrGetOneProp](hrgetoneprop.md) and [HrSetOneProp](hrsetoneprop.md) to get or set these properties.</span></span> 
  
<span data-ttu-id="19a26-121">若要检索此属性的值，客户应首先使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取该属性标记，然后[IMAPIProp::GetProps](imapiprop-getprops.md)获取值中指定此属性标记。</span><span class="sxs-lookup"><span data-stu-id="19a26-121">To retrieve the value of this property, the client should first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="19a26-122">调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)时, 指定的输入的参数_lppPropNames_指向[MAPINAMEID](mapinameid.md)结构的以下值：</span><span class="sxs-lookup"><span data-stu-id="19a26-122">When calling [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), specify the following values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="19a26-123">lpGuid:</span><span class="sxs-lookup"><span data-stu-id="19a26-123">lpGuid:</span></span>  <br/> |<span data-ttu-id="19a26-124">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="19a26-124">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="19a26-125">ulKind:</span><span class="sxs-lookup"><span data-stu-id="19a26-125">ulKind:</span></span>  <br/> |<span data-ttu-id="19a26-126">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="19a26-126">MNID_STRING</span></span>  <br/> |
|<span data-ttu-id="19a26-127">Kind.lpwstrName:</span><span class="sxs-lookup"><span data-stu-id="19a26-127">Kind.lpwstrName:</span></span>  <br/> |<span data-ttu-id="19a26-128">L"NoFolderScan"</span><span class="sxs-lookup"><span data-stu-id="19a26-128">L"NoFolderScan"</span></span>  <br/> |
   
<span data-ttu-id="19a26-129">此属性提供了一种方法向 Outlook 中指定的存储提供程序不扫描以避免性能下降存储区中的联系人文件夹。</span><span class="sxs-lookup"><span data-stu-id="19a26-129">This property provides a way for store providers to specify to Outlook not to scan Contacts folders in the store to avoid performance degradation.</span></span> <span data-ttu-id="19a26-130">使用 Outlook 检查在此期间的邮件合并操作中的状态和此属性的值在启动扫描之前。</span><span class="sxs-lookup"><span data-stu-id="19a26-130">It is used in mail merge operations during which Outlook checks for the presence and value of this property before initiating the scan.</span></span>
  
<span data-ttu-id="19a26-131">默认情况下，对存储，这意味着 Outlook 可以扫描存储区上的联系人文件夹不公开此属性。</span><span class="sxs-lookup"><span data-stu-id="19a26-131">By default, this property is not exposed on a store, which means Outlook can scan the Contacts folder on the store.</span></span> <span data-ttu-id="19a26-132">如果公开此属性，以下是可能的值：</span><span class="sxs-lookup"><span data-stu-id="19a26-132">If the property is exposed, the following are the possible values:</span></span>
  
- <span data-ttu-id="19a26-133">零 (0): Outlook 可以执行扫描。</span><span class="sxs-lookup"><span data-stu-id="19a26-133">Zero (0): Outlook can carry out the scan.</span></span>
    
- <span data-ttu-id="19a26-134">非零值： Outlook 不应扫描存储区上的联系人文件夹。</span><span class="sxs-lookup"><span data-stu-id="19a26-134">Non-zero value: Outlook should not scan Contacts folders on the store.</span></span>
    

