---
title: 未初始化状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e071b50f-2e75-4537-ac7b-4a2f5ebea83d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: be35c9d3f8fc7badf83086e63e4c94e0efa4d5bf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425559"
---
# <a name="uninitialized-state"></a><span data-ttu-id="12a0d-103">未初始化状态</span><span class="sxs-lookup"><span data-stu-id="12a0d-103">Uninitialized State</span></span>

  
  
<span data-ttu-id="12a0d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="12a0d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="12a0d-105">"未初始化"状态是首次创建对象时它们应位于的初始状态表单对象。</span><span class="sxs-lookup"><span data-stu-id="12a0d-105">The Uninitialized state is the initial state form objects should be in when they are first created.</span></span> <span data-ttu-id="12a0d-106">当客户端应用程序对表单对象调用 [IPersistMessage：：InitNew](ipersistmessage-initnew.md) 或 [IPersistMessage：：Load](ipersistmessage-load.md) 方法时，Form 对象会使用邮件数据进行初始化。</span><span class="sxs-lookup"><span data-stu-id="12a0d-106">Form objects become initialized with message data when a client application calls the [IPersistMessage::InitNew](ipersistmessage-initnew.md) or [IPersistMessage::Load](ipersistmessage-load.md) method on the form object.</span></span> <span data-ttu-id="12a0d-107">下表介绍了允许从单一化状态转换。</span><span class="sxs-lookup"><span data-stu-id="12a0d-107">The following table describes allowed transitions from the Unitialized state.</span></span> 
  
|<span data-ttu-id="12a0d-108">**IPersistMessage 方法**</span><span class="sxs-lookup"><span data-stu-id="12a0d-108">**IPersistMessage method**</span></span>|<span data-ttu-id="12a0d-109">**Action**</span><span class="sxs-lookup"><span data-stu-id="12a0d-109">**Action**</span></span>|<span data-ttu-id="12a0d-110">**新状态**</span><span class="sxs-lookup"><span data-stu-id="12a0d-110">**New state**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="12a0d-111">IPersistMessage::InitNew</span><span class="sxs-lookup"><span data-stu-id="12a0d-111">IPersistMessage::InitNew</span></span>](ipersistmessage-initnew.md) <br/> |<span data-ttu-id="12a0d-112">使用默认数据加载表单对象。</span><span class="sxs-lookup"><span data-stu-id="12a0d-112">Load the form object with default data.</span></span>  <br/> |[<span data-ttu-id="12a0d-113">Normal</span><span class="sxs-lookup"><span data-stu-id="12a0d-113">Normal</span></span>](normal-state.md) <br/> |
|[<span data-ttu-id="12a0d-114">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="12a0d-114">IPersistMessage::Load</span></span>](ipersistmessage-load.md) <br/> |<span data-ttu-id="12a0d-115">使用来自目标邮件的数据加载表单对象。</span><span class="sxs-lookup"><span data-stu-id="12a0d-115">Load the form object with data from the target message.</span></span>  <br/> |<span data-ttu-id="12a0d-116">一般</span><span class="sxs-lookup"><span data-stu-id="12a0d-116">Normal</span></span>  <br/> |
|[<span data-ttu-id="12a0d-117">IPersistMessage::GetClassID</span><span class="sxs-lookup"><span data-stu-id="12a0d-117">IPersistMessage::GetClassID</span></span>](ipersistmessage-getclassid.md) <br/> |<span data-ttu-id="12a0d-118">返回成功，或将最后一个错误设置为 并返回E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="12a0d-118">Return success, or set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="12a0d-119">未初始化</span><span class="sxs-lookup"><span data-stu-id="12a0d-119">Uninitialized</span></span>  <br/> |
|[<span data-ttu-id="12a0d-120">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="12a0d-120">IPersistMessage::GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="12a0d-121">返回最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="12a0d-121">Return the last error.</span></span>  <br/> |<span data-ttu-id="12a0d-122">未初始化</span><span class="sxs-lookup"><span data-stu-id="12a0d-122">Uninitialized</span></span>  <br/> |
|<span data-ttu-id="12a0d-123">其他 [IPersistMessage ：来自其他接口的 IUnknown](ipersistmessageiunknown.md) 方法</span><span class="sxs-lookup"><span data-stu-id="12a0d-123">Other [IPersistMessage : IUnknown](ipersistmessageiunknown.md) methods or methods from other interfaces</span></span>  <br/> |<span data-ttu-id="12a0d-124">将最后一个错误设置为 并返回E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="12a0d-124">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="12a0d-125">未初始化</span><span class="sxs-lookup"><span data-stu-id="12a0d-125">Uninitialized</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="12a0d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12a0d-126">See also</span></span>



[<span data-ttu-id="12a0d-127">正常状态</span><span class="sxs-lookup"><span data-stu-id="12a0d-127">Normal State</span></span>](normal-state.md)
  
[<span data-ttu-id="12a0d-128">表单状态</span><span class="sxs-lookup"><span data-stu-id="12a0d-128">Form States</span></span>](form-states.md)

