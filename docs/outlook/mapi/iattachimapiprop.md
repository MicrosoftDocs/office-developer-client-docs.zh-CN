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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409088"
---
# <a name="iattach--imapiprop"></a><span data-ttu-id="d2765-103">IAttach : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="d2765-103">IAttach : IMAPIProp</span></span>

  
  
<span data-ttu-id="d2765-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d2765-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d2765-105">维护并提供对邮件中附件的属性的访问。</span><span class="sxs-lookup"><span data-stu-id="d2765-105">Maintains and provides access to the properties of attachments in messages.</span></span> <span data-ttu-id="d2765-106">**IAttach**接口没有自己的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="d2765-106">The **IAttach** interface has no unique methods of its own.</span></span> <span data-ttu-id="d2765-107">有关如何使用附件的详细信息, 请参阅[MAPI 附件](mapi-attachments.md)和[附件表](attachment-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="d2765-107">For more information about how to use attachments, see [MAPI Attachments](mapi-attachments.md) and [Attachment Tables](attachment-tables.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d2765-108">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d2765-108">Header file:</span></span>  <br/> |<span data-ttu-id="d2765-109">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d2765-109">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="d2765-110">公开者:</span><span class="sxs-lookup"><span data-stu-id="d2765-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="d2765-111">附件对象</span><span class="sxs-lookup"><span data-stu-id="d2765-111">Attachment objects</span></span>  <br/> |
|<span data-ttu-id="d2765-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="d2765-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="d2765-113">邮件存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="d2765-113">Message store providers</span></span>  <br/> |
|<span data-ttu-id="d2765-114">调用者：</span><span class="sxs-lookup"><span data-stu-id="d2765-114">Called by:</span></span>  <br/> |<span data-ttu-id="d2765-115">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="d2765-115">Client applications</span></span>  <br/> |
|<span data-ttu-id="d2765-116">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="d2765-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="d2765-117">IID_IAttachment</span><span class="sxs-lookup"><span data-stu-id="d2765-117">IID_IAttachment</span></span>  <br/> |
|<span data-ttu-id="d2765-118">指针类型:</span><span class="sxs-lookup"><span data-stu-id="d2765-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="d2765-119">LPATTACH</span><span class="sxs-lookup"><span data-stu-id="d2765-119">LPATTACH</span></span>  <br/> |
|<span data-ttu-id="d2765-120">事务模型:</span><span class="sxs-lookup"><span data-stu-id="d2765-120">Transaction model:</span></span>  <br/> |<span data-ttu-id="d2765-121">事务</span><span class="sxs-lookup"><span data-stu-id="d2765-121">Transacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="d2765-122">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="d2765-122">Vtable order</span></span>

<span data-ttu-id="d2765-123">此接口没有任何唯一的方法。</span><span class="sxs-lookup"><span data-stu-id="d2765-123">This interface does not have any unique methods.</span></span>
  
|<span data-ttu-id="d2765-124">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="d2765-124">**Required properties**</span></span>|<span data-ttu-id="d2765-125">**访问**</span><span class="sxs-lookup"><span data-stu-id="d2765-125">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d2765-126">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d2765-126">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d2765-127">只读</span><span class="sxs-lookup"><span data-stu-id="d2765-127">Read-only</span></span>  <br/> |
|<span data-ttu-id="d2765-128">**PR_ATTACH_METHOD**([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d2765-128">**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d2765-129">读/写</span><span class="sxs-lookup"><span data-stu-id="d2765-129">Read/write</span></span>  <br/> |
|<span data-ttu-id="d2765-130">**PR_RENDERING_POSITION**([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d2765-130">**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d2765-131">读/写</span><span class="sxs-lookup"><span data-stu-id="d2765-131">Read/write</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d2765-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2765-132">See also</span></span>



[<span data-ttu-id="d2765-133">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="d2765-133">MAPI Interfaces</span></span>](mapi-interfaces.md)

