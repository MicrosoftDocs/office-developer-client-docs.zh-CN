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
ms.openlocfilehash: fc5f5a42e2b1e57374ff80a9333b927cc8dba120
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436805"
---
# <a name="nofolderscan"></a><span data-ttu-id="beb16-103">NoFolderScan</span><span class="sxs-lookup"><span data-stu-id="beb16-103">NoFolderScan</span></span>

  
  
<span data-ttu-id="beb16-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="beb16-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="beb16-105">指定 Microsoft Office Outlook 是否应扫描存储区上的联系人文件夹。</span><span class="sxs-lookup"><span data-stu-id="beb16-105">Specifies whether Microsoft Office Outlook should scan Contacts folders on a store.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="beb16-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="beb16-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="beb16-107">公开于:</span><span class="sxs-lookup"><span data-stu-id="beb16-107">Exposed on:</span></span>  <br/> |<span data-ttu-id="beb16-108">[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象</span><span class="sxs-lookup"><span data-stu-id="beb16-108">[IMsgStore : IMAPIProp](imsgstoreimapiprop.md) object</span></span>  <br/> |
|<span data-ttu-id="beb16-109">创建者:</span><span class="sxs-lookup"><span data-stu-id="beb16-109">Created by:</span></span>  <br/> |<span data-ttu-id="beb16-110">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="beb16-110">Store provider</span></span>  <br/> |
|<span data-ttu-id="beb16-111">访问者:</span><span class="sxs-lookup"><span data-stu-id="beb16-111">Accessed by:</span></span>  <br/> |<span data-ttu-id="beb16-112">Outlook 和其他客户端</span><span class="sxs-lookup"><span data-stu-id="beb16-112">Outlook and other clients</span></span>  <br/> |
|<span data-ttu-id="beb16-113">属性类型</span><span class="sxs-lookup"><span data-stu-id="beb16-113">Property type:</span></span>  <br/> |<span data-ttu-id="beb16-114">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="beb16-114">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="beb16-115">访问类型:</span><span class="sxs-lookup"><span data-stu-id="beb16-115">Access type:</span></span>  <br/> |<span data-ttu-id="beb16-116">只读或读/写, 具体取决于存储提供程序</span><span class="sxs-lookup"><span data-stu-id="beb16-116">Read-only or read/write depending on the store provider</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="beb16-117">说明</span><span class="sxs-lookup"><span data-stu-id="beb16-117">Remarks</span></span>

<span data-ttu-id="beb16-118">若要提供任何存储功能, 存储提供程序必须实现[IMAPIProp: IUnknown](imapipropiunknown.md) , 并返回传递给[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)调用的任何这些属性的有效属性标记。</span><span class="sxs-lookup"><span data-stu-id="beb16-118">To provide any of the store functionality, the store provider must implement [IMAPIProp : IUnknown](imapipropiunknown.md) and return a valid property tag for any of these properties passed to an [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) call.</span></span> <span data-ttu-id="beb16-119">当这些属性中任一属性的属性标记传递给[IMAPIProp:: GetProps](imapiprop-getprops.md)时, 存储提供程序还必须返回正确的属性值。</span><span class="sxs-lookup"><span data-stu-id="beb16-119">When the property tag for any of these properties is passed to [IMAPIProp::GetProps](imapiprop-getprops.md), the store provider must also return the correct property value.</span></span> <span data-ttu-id="beb16-120">存储提供程序可以调用[HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)以获取或设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="beb16-120">Store providers can call [HrGetOneProp](hrgetoneprop.md) and [HrSetOneProp](hrsetoneprop.md) to get or set these properties.</span></span> 
  
<span data-ttu-id="beb16-121">若要检索此属性的值, 客户端应首先使用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)获取属性标记, 然后在[IMAPIProp:: GetProps](imapiprop-getprops.md)中指定此属性标记以获取值。</span><span class="sxs-lookup"><span data-stu-id="beb16-121">To retrieve the value of this property, the client should first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="beb16-122">调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)时, 请为输入参数_lppPropNames_所指向的[MAPINAMEID](mapinameid.md)结构指定以下值:</span><span class="sxs-lookup"><span data-stu-id="beb16-122">When calling [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), specify the following values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="beb16-123">lpGuid:</span><span class="sxs-lookup"><span data-stu-id="beb16-123">lpGuid:</span></span>  <br/> |<span data-ttu-id="beb16-124">PSETID_Common</span><span class="sxs-lookup"><span data-stu-id="beb16-124">PSETID_Common</span></span>  <br/> |
|<span data-ttu-id="beb16-125">ulKind:</span><span class="sxs-lookup"><span data-stu-id="beb16-125">ulKind:</span></span>  <br/> |<span data-ttu-id="beb16-126">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="beb16-126">MNID_STRING</span></span>  <br/> |
|<span data-ttu-id="beb16-127">类型 lpwstrName:</span><span class="sxs-lookup"><span data-stu-id="beb16-127">Kind.lpwstrName:</span></span>  <br/> |<span data-ttu-id="beb16-128">L "NoFolderScan"</span><span class="sxs-lookup"><span data-stu-id="beb16-128">L"NoFolderScan"</span></span>  <br/> |
   
<span data-ttu-id="beb16-129">此属性提供一种方法来存储提供程序, 以指定 Outlook 不扫描存储区中的联系人文件夹以避免性能下降。</span><span class="sxs-lookup"><span data-stu-id="beb16-129">This property provides a way for store providers to specify to Outlook not to scan Contacts folders in the store to avoid performance degradation.</span></span> <span data-ttu-id="beb16-130">它在邮件合并操作中使用, 在此过程中, Outlook 会在启动扫描之前在此属性的状态和值中进行检查。</span><span class="sxs-lookup"><span data-stu-id="beb16-130">It is used in mail merge operations during which Outlook checks for the presence and value of this property before initiating the scan.</span></span>
  
<span data-ttu-id="beb16-131">默认情况下, 不会在存储区上公开此属性, 这意味着 Outlook 可以扫描存储上的 "联系人" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="beb16-131">By default, this property is not exposed on a store, which means Outlook can scan the Contacts folder on the store.</span></span> <span data-ttu-id="beb16-132">如果公开了属性, 以下是可能的值:</span><span class="sxs-lookup"><span data-stu-id="beb16-132">If the property is exposed, the following are the possible values:</span></span>
  
- <span data-ttu-id="beb16-133">零 (0): Outlook 可以执行扫描。</span><span class="sxs-lookup"><span data-stu-id="beb16-133">Zero (0): Outlook can carry out the scan.</span></span>
    
- <span data-ttu-id="beb16-134">非零值: Outlook 不应扫描存储区中的联系人文件夹。</span><span class="sxs-lookup"><span data-stu-id="beb16-134">Non-zero value: Outlook should not scan Contacts folders on the store.</span></span>
    

