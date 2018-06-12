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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 66e318c3b7b772f2713b5c730590ce4a8ad5965b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775256"
---
# <a name="iattach--imapiprop"></a><span data-ttu-id="c748f-103">IAttach: IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="c748f-103">IAttach : IMAPIProp</span></span>

  
  
<span data-ttu-id="c748f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c748f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c748f-105">维护并提供对属性的邮件中的附件的访问。</span><span class="sxs-lookup"><span data-stu-id="c748f-105">Maintains and provides access to the properties of attachments in messages.</span></span> <span data-ttu-id="c748f-106">**IAttach**接口都有其自己的方法都不唯一。</span><span class="sxs-lookup"><span data-stu-id="c748f-106">The **IAttach** interface has no unique methods of its own.</span></span> <span data-ttu-id="c748f-107">有关如何使用附件的详细信息，请参阅[MAPI 附件](mapi-attachments.md)和[附件表](attachment-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="c748f-107">For more information about how to use attachments, see [MAPI Attachments](mapi-attachments.md) and [Attachment Tables](attachment-tables.md).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c748f-108">头文件：</span><span class="sxs-lookup"><span data-stu-id="c748f-108">Header file:</span></span>  <br/> |<span data-ttu-id="c748f-109">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c748f-109">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="c748f-110">由公开：</span><span class="sxs-lookup"><span data-stu-id="c748f-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="c748f-111">Attachment 对象</span><span class="sxs-lookup"><span data-stu-id="c748f-111">Attachment objects</span></span>  <br/> |
|<span data-ttu-id="c748f-112">通过实现：</span><span class="sxs-lookup"><span data-stu-id="c748f-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="c748f-113">消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="c748f-113">Message store providers</span></span>  <br/> |
|<span data-ttu-id="c748f-114">调用：</span><span class="sxs-lookup"><span data-stu-id="c748f-114">Called by:</span></span>  <br/> |<span data-ttu-id="c748f-115">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="c748f-115">Client applications</span></span>  <br/> |
|<span data-ttu-id="c748f-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="c748f-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="c748f-117">IID_IAttachment</span><span class="sxs-lookup"><span data-stu-id="c748f-117">IID_IAttachment</span></span>  <br/> |
|<span data-ttu-id="c748f-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="c748f-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="c748f-119">LPATTACH</span><span class="sxs-lookup"><span data-stu-id="c748f-119">LPATTACH</span></span>  <br/> |
|<span data-ttu-id="c748f-120">事务模型：</span><span class="sxs-lookup"><span data-stu-id="c748f-120">Transaction model:</span></span>  <br/> |<span data-ttu-id="c748f-121">事务处理</span><span class="sxs-lookup"><span data-stu-id="c748f-121">Transacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="c748f-122">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="c748f-122">Vtable order</span></span>

<span data-ttu-id="c748f-123">此接口不具有任何唯一的方法。</span><span class="sxs-lookup"><span data-stu-id="c748f-123">This interface does not have any unique methods.</span></span>
  
|<span data-ttu-id="c748f-124">**必需的属性**</span><span class="sxs-lookup"><span data-stu-id="c748f-124">**Required properties**</span></span>|<span data-ttu-id="c748f-125">**访问**</span><span class="sxs-lookup"><span data-stu-id="c748f-125">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c748f-126">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="c748f-126">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="c748f-127">只读</span><span class="sxs-lookup"><span data-stu-id="c748f-127">Read-only</span></span>  <br/> |
|<span data-ttu-id="c748f-128">**PR_ATTACH_METHOD**([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="c748f-128">**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="c748f-129">读/写</span><span class="sxs-lookup"><span data-stu-id="c748f-129">Read/write</span></span>  <br/> |
|<span data-ttu-id="c748f-130">**PR_RENDERING_POSITION**([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="c748f-130">**PR_RENDERING_POSITION** ([PidTagRenderingPosition](pidtagrenderingposition-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="c748f-131">读/写</span><span class="sxs-lookup"><span data-stu-id="c748f-131">Read/write</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c748f-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c748f-132">See also</span></span>



[<span data-ttu-id="c748f-133">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="c748f-133">MAPI Interfaces</span></span>](mapi-interfaces.md)

