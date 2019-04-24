---
title: IAttach IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAttach
api_type:
- COM
ms.assetid: f47e20e1-2a30-4c9e-8ca6-e8c5e72f44a1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2ef3bc973e12bd5630cc00b3c512b748d4a16e86
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341620"
---
# <a name="iattach--imapiprop"></a><span data-ttu-id="fbbcd-103">IAttach : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="fbbcd-103">IAttach : IMAPIProp</span></span>

  
  
<span data-ttu-id="fbbcd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fbbcd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fbbcd-105">维护并提供对邮件中附件的属性的访问。</span><span class="sxs-lookup"><span data-stu-id="fbbcd-105">Maintains and provides access to the properties of attachments in messages.</span></span> <span data-ttu-id="fbbcd-106">**IAttach**接口没有自己的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="fbbcd-106">The **IAttach** interface has no unique methods of its own.</span></span> <span data-ttu-id="fbbcd-107">有关如何使用附件的详细信息, 请参阅[MAPI 附件](mapi-attachments.md)和[附件表](attachment-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="fbbcd-107">For more information about how to use attachments, see [MAPI Attachments](mapi-attachments.md) and [Attachment Tables](attachment-tables.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fbbcd-108">标头文件：</span><span class="sxs-lookup"><span data-stu-id="fbbcd-108">Header file:</span></span>  <br/> |<span data-ttu-id="fbbcd-109">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="fbbcd-109">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="fbbcd-110">公开者:</span><span class="sxs-lookup"><span data-stu-id="fbbcd-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="fbbcd-111">附件对象</span><span class="sxs-lookup"><span data-stu-id="fbbcd-111">Attachment objects</span></span>  <br/> |
|<span data-ttu-id="fbbcd-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="fbbcd-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="fbbcd-113">邮件存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="fbbcd-113">Message store providers</span></span>  <br/> |
|<span data-ttu-id="fbbcd-114">调用者：</span><span class="sxs-lookup"><span data-stu-id="fbbcd-114">Called by:</span></span>  <br/> |<span data-ttu-id="fbbcd-115">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="fbbcd-115">Client applications</span></span>  <br/> |
|<span data-ttu-id="fbbcd-116">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="fbbcd-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="fbbcd-117">IID_IAttachment</span><span class="sxs-lookup"><span data-stu-id="fbbcd-117">IID_IAttachment</span></span>  <br/> |
|<span data-ttu-id="fbbcd-118">指针类型:</span><span class="sxs-lookup"><span data-stu-id="fbbcd-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="fbbcd-119">LPATTACH</span><span class="sxs-lookup"><span data-stu-id="fbbcd-119">LPATTACH</span></span>  <br/> |
|<span data-ttu-id="fbbcd-120">事务模型:</span><span class="sxs-lookup"><span data-stu-id="fbbcd-120">Transaction model:</span></span>  <br/> |<span data-ttu-id="fbbcd-121">事务</span><span class="sxs-lookup"><span data-stu-id="fbbcd-121">Transacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="fbbcd-122">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="fbbcd-122">Vtable order</span></span>

<span data-ttu-id="fbbcd-123">此接口没有任何唯一的方法。</span><span class="sxs-lookup"><span data-stu-id="fbbcd-123">This interface does not have any unique methods.</span></span>
  
|<span data-ttu-id="fbbcd-124">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="fbbcd-124">**Required properties**</span></span>|<span data-ttu-id="fbbcd-125">**Access**</span><span class="sxs-lookup"><span data-stu-id="fbbcd-125">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fbbcd-126">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="fbbcd-126">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="fbbcd-127">只读</span><span class="sxs-lookup"><span data-stu-id="fbbcd-127">Read-only</span></span>  <br/> |
|<span data-ttu-id="fbbcd-128">**PR_ATTACH_METHOD**([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="fbbcd-128">**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="fbbcd-129">读/写</span><span class="sxs-lookup"><span data-stu-id="fbbcd-129">Read/write</span></span>  <br/> |
|<span data-ttu-id="fbbcd-130">**PR_RENDERING_POSITION**([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="fbbcd-130">**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="fbbcd-131">读/写</span><span class="sxs-lookup"><span data-stu-id="fbbcd-131">Read/write</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fbbcd-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbbcd-132">See also</span></span>



[<span data-ttu-id="fbbcd-133">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="fbbcd-133">MAPI Interfaces</span></span>](mapi-interfaces.md)

