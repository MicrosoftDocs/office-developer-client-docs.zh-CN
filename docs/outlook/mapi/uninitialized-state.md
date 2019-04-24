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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360499"
---
# <a name="uninitialized-state"></a><span data-ttu-id="e7c39-103">未初始化状态</span><span class="sxs-lookup"><span data-stu-id="e7c39-103">Uninitialized State</span></span>

  
  
<span data-ttu-id="e7c39-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e7c39-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e7c39-105">未初始化状态是首次创建窗体对象时, 它们应位于的初始状态。</span><span class="sxs-lookup"><span data-stu-id="e7c39-105">The Uninitialized state is the initial state form objects should be in when they are first created.</span></span> <span data-ttu-id="e7c39-106">当客户端应用程序对 form 对象调用[IPersistMessage:: InitNew](ipersistmessage-initnew.md)或[IPersistMessage:: Load](ipersistmessage-load.md)方法时, 窗体对象将被初始化为邮件数据。</span><span class="sxs-lookup"><span data-stu-id="e7c39-106">Form objects become initialized with message data when a client application calls the [IPersistMessage::InitNew](ipersistmessage-initnew.md) or [IPersistMessage::Load](ipersistmessage-load.md) method on the form object.</span></span> <span data-ttu-id="e7c39-107">下表介绍了允许从 Unitialized 状态进行的转换。</span><span class="sxs-lookup"><span data-stu-id="e7c39-107">The following table describes allowed transitions from the Unitialized state.</span></span> 
  
|<span data-ttu-id="e7c39-108">**IPersistMessage 方法**</span><span class="sxs-lookup"><span data-stu-id="e7c39-108">**IPersistMessage method**</span></span>|<span data-ttu-id="e7c39-109">**Action**</span><span class="sxs-lookup"><span data-stu-id="e7c39-109">**Action**</span></span>|<span data-ttu-id="e7c39-110">**新状态**</span><span class="sxs-lookup"><span data-stu-id="e7c39-110">**New state**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="e7c39-111">IPersistMessage::InitNew</span><span class="sxs-lookup"><span data-stu-id="e7c39-111">IPersistMessage::InitNew</span></span>](ipersistmessage-initnew.md) <br/> |<span data-ttu-id="e7c39-112">使用默认数据加载 form 对象。</span><span class="sxs-lookup"><span data-stu-id="e7c39-112">Load the form object with default data.</span></span>  <br/> |[<span data-ttu-id="e7c39-113">Normal</span><span class="sxs-lookup"><span data-stu-id="e7c39-113">Normal</span></span>](normal-state.md) <br/> |
|[<span data-ttu-id="e7c39-114">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="e7c39-114">IPersistMessage::Load</span></span>](ipersistmessage-load.md) <br/> |<span data-ttu-id="e7c39-115">使用目标邮件中的数据加载 form 对象。</span><span class="sxs-lookup"><span data-stu-id="e7c39-115">Load the form object with data from the target message.</span></span>  <br/> |<span data-ttu-id="e7c39-116">一般</span><span class="sxs-lookup"><span data-stu-id="e7c39-116">Normal</span></span>  <br/> |
|[<span data-ttu-id="e7c39-117">IPersistMessage::GetClassID</span><span class="sxs-lookup"><span data-stu-id="e7c39-117">IPersistMessage::GetClassID</span></span>](ipersistmessage-getclassid.md) <br/> |<span data-ttu-id="e7c39-118">返回 success, 或将上一个错误设置为并返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="e7c39-118">Return success, or set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="e7c39-119">即</span><span class="sxs-lookup"><span data-stu-id="e7c39-119">Uninitialized</span></span>  <br/> |
|[<span data-ttu-id="e7c39-120">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="e7c39-120">IPersistMessage::GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="e7c39-121">返回上一个错误。</span><span class="sxs-lookup"><span data-stu-id="e7c39-121">Return the last error.</span></span>  <br/> |<span data-ttu-id="e7c39-122">即</span><span class="sxs-lookup"><span data-stu-id="e7c39-122">Uninitialized</span></span>  <br/> |
|<span data-ttu-id="e7c39-123">其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口的方法</span><span class="sxs-lookup"><span data-stu-id="e7c39-123">Other [IPersistMessage : IUnknown](ipersistmessageiunknown.md) methods or methods from other interfaces</span></span>  <br/> |<span data-ttu-id="e7c39-124">将上一个错误设置为并返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="e7c39-124">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="e7c39-125">即</span><span class="sxs-lookup"><span data-stu-id="e7c39-125">Uninitialized</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e7c39-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7c39-126">See also</span></span>



[<span data-ttu-id="e7c39-127">正常状态</span><span class="sxs-lookup"><span data-stu-id="e7c39-127">Normal State</span></span>](normal-state.md)
  
[<span data-ttu-id="e7c39-128">表单状态</span><span class="sxs-lookup"><span data-stu-id="e7c39-128">Form States</span></span>](form-states.md)

