---
title: Uninitialized 状态
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: e071b50f-2e75-4537-ac7b-4a2f5ebea83d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 95ed80a6d0ea6a6a7c8cc768b32981ac899b69e4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578246"
---
# <a name="uninitialized-state"></a><span data-ttu-id="8e3cf-103">Uninitialized 状态</span><span class="sxs-lookup"><span data-stu-id="8e3cf-103">Uninitialized State</span></span>

  
  
<span data-ttu-id="8e3cf-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8e3cf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8e3cf-105">未初始化的状态是首次创建时，对象应中的初始状态窗体。</span><span class="sxs-lookup"><span data-stu-id="8e3cf-105">The Uninitialized state is the initial state form objects should be in when they are first created.</span></span> <span data-ttu-id="8e3cf-106">客户端应用程序在窗体对象上调用[IPersistMessage::InitNew](ipersistmessage-initnew.md)或[IPersistMessage::Load](ipersistmessage-load.md)方法时，使用消息数据成为初始化表单对象。</span><span class="sxs-lookup"><span data-stu-id="8e3cf-106">Form objects become initialized with message data when a client application calls the [IPersistMessage::InitNew](ipersistmessage-initnew.md) or [IPersistMessage::Load](ipersistmessage-load.md) method on the form object.</span></span> <span data-ttu-id="8e3cf-107">下表介绍允许的 Unitialized 状态转换。</span><span class="sxs-lookup"><span data-stu-id="8e3cf-107">The following table describes allowed transitions from the Unitialized state.</span></span> 
  
|<span data-ttu-id="8e3cf-108">**IPersistMessage 方法**</span><span class="sxs-lookup"><span data-stu-id="8e3cf-108">**IPersistMessage method**</span></span>|<span data-ttu-id="8e3cf-109">**操作**</span><span class="sxs-lookup"><span data-stu-id="8e3cf-109">**Action**</span></span>|<span data-ttu-id="8e3cf-110">**新的状态**</span><span class="sxs-lookup"><span data-stu-id="8e3cf-110">**New state**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="8e3cf-111">IPersistMessage::InitNew</span><span class="sxs-lookup"><span data-stu-id="8e3cf-111">IPersistMessage::InitNew</span></span>](ipersistmessage-initnew.md) <br/> |<span data-ttu-id="8e3cf-112">加载表单对象的默认数据。</span><span class="sxs-lookup"><span data-stu-id="8e3cf-112">Load the form object with default data.</span></span>  <br/> |[<span data-ttu-id="8e3cf-113">Normal</span><span class="sxs-lookup"><span data-stu-id="8e3cf-113">Normal</span></span>](normal-state.md) <br/> |
|[<span data-ttu-id="8e3cf-114">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="8e3cf-114">IPersistMessage::Load</span></span>](ipersistmessage-load.md) <br/> |<span data-ttu-id="8e3cf-115">从目标邮件加载数据的窗体对象。</span><span class="sxs-lookup"><span data-stu-id="8e3cf-115">Load the form object with data from the target message.</span></span>  <br/> |<span data-ttu-id="8e3cf-116">常规</span><span class="sxs-lookup"><span data-stu-id="8e3cf-116">Normal</span></span>  <br/> |
|[<span data-ttu-id="8e3cf-117">IPersistMessage::GetClassID</span><span class="sxs-lookup"><span data-stu-id="8e3cf-117">IPersistMessage::GetClassID</span></span>](ipersistmessage-getclassid.md) <br/> |<span data-ttu-id="8e3cf-118">返回成功，或设置为上一个错误，并返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="8e3cf-118">Return success, or set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="8e3cf-119">未初始化</span><span class="sxs-lookup"><span data-stu-id="8e3cf-119">Uninitialized</span></span>  <br/> |
|[<span data-ttu-id="8e3cf-120">IPersistMessage::GetLastError</span><span class="sxs-lookup"><span data-stu-id="8e3cf-120">IPersistMessage::GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="8e3cf-121">返回的最后一个错误。</span><span class="sxs-lookup"><span data-stu-id="8e3cf-121">Return the last error.</span></span>  <br/> |<span data-ttu-id="8e3cf-122">未初始化</span><span class="sxs-lookup"><span data-stu-id="8e3cf-122">Uninitialized</span></span>  <br/> |
|<span data-ttu-id="8e3cf-123">其他[IPersistMessage: IUnknown](ipersistmessageiunknown.md)方法或来自其他接口方法</span><span class="sxs-lookup"><span data-stu-id="8e3cf-123">Other [IPersistMessage : IUnknown](ipersistmessageiunknown.md) methods or methods from other interfaces</span></span>  <br/> |<span data-ttu-id="8e3cf-124">设置为上一个错误，并返回 E_UNEXPECTED。</span><span class="sxs-lookup"><span data-stu-id="8e3cf-124">Set the last error to and return E_UNEXPECTED.</span></span>  <br/> |<span data-ttu-id="8e3cf-125">未初始化</span><span class="sxs-lookup"><span data-stu-id="8e3cf-125">Uninitialized</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8e3cf-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e3cf-126">See also</span></span>



[<span data-ttu-id="8e3cf-127">Normal 状态</span><span class="sxs-lookup"><span data-stu-id="8e3cf-127">Normal State</span></span>](normal-state.md)
  
[<span data-ttu-id="8e3cf-128">表单状态</span><span class="sxs-lookup"><span data-stu-id="8e3cf-128">Form States</span></span>](form-states.md)

