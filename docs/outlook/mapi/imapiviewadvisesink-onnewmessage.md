---
title: IMAPIViewAdviseSinkOnNewMessage
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewAdviseSink.OnNewMessage
api_type:
- COM
ms.assetid: 0a2fb371-90ea-41dc-b2ab-051cf790e85a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6a6f8f9d675bee362b4a9f1c5b7fc544fa66d7b0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419602"
---
# <a name="imapiviewadvisesinkonnewmessage"></a><span data-ttu-id="24be4-103">IMAPIViewAdviseSink::OnNewMessage</span><span class="sxs-lookup"><span data-stu-id="24be4-103">IMAPIViewAdviseSink::OnNewMessage</span></span>

  
  
<span data-ttu-id="24be4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="24be4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="24be4-105">通知表单查看器已在表单中加载了新邮件或现有邮件。</span><span class="sxs-lookup"><span data-stu-id="24be4-105">Notifies the form viewer that a new or an existing message has been loaded in a form.</span></span>
  
```cpp
HRESULT OnNewMessage( void );
```

## <a name="parameters"></a><span data-ttu-id="24be4-106">参数</span><span class="sxs-lookup"><span data-stu-id="24be4-106">Parameters</span></span>

<span data-ttu-id="24be4-107">无</span><span class="sxs-lookup"><span data-stu-id="24be4-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="24be4-108">返回值</span><span class="sxs-lookup"><span data-stu-id="24be4-108">Return value</span></span>

<span data-ttu-id="24be4-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="24be4-109">S_OK</span></span> 
  
> <span data-ttu-id="24be4-110">通知成功。</span><span class="sxs-lookup"><span data-stu-id="24be4-110">The notification succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="24be4-111">备注</span><span class="sxs-lookup"><span data-stu-id="24be4-111">Remarks</span></span>

<span data-ttu-id="24be4-112">只要使用 [IPersistMessage：：InitNew](ipersistmessage-initnew.md)或 [IPersistMessage：：Load](ipersistmessage-load.md)方法在表单中加载邮件，Form 对象就会调用 **IMAPIViewAdviseSink：：OnNewMessage** 方法。</span><span class="sxs-lookup"><span data-stu-id="24be4-112">Form objects call the **IMAPIViewAdviseSink::OnNewMessage** method whenever a message is loaded in a form using either the [IPersistMessage::InitNew](ipersistmessage-initnew.md) or [IPersistMessage::Load](ipersistmessage-load.md) method.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="24be4-113">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="24be4-113">Notes to implementers</span></span>

<span data-ttu-id="24be4-114">释放窗体对象的活动指针，因为它不再指向查看者以前查看的消息。</span><span class="sxs-lookup"><span data-stu-id="24be4-114">Release your active pointer to the form object because it no longer points to the message your viewer was formerly viewing.</span></span> 
  
<span data-ttu-id="24be4-115">有关表单通知详细信息，请参阅 [发送和接收表单通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="24be4-115">For more information about form notifications, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="24be4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24be4-116">See also</span></span>



[<span data-ttu-id="24be4-117">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="24be4-117">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)
  
[<span data-ttu-id="24be4-118">IPersistMessage::InitNew</span><span class="sxs-lookup"><span data-stu-id="24be4-118">IPersistMessage::InitNew</span></span>](ipersistmessage-initnew.md)
  
[<span data-ttu-id="24be4-119">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="24be4-119">IPersistMessage::Load</span></span>](ipersistmessage-load.md)
  
[<span data-ttu-id="24be4-120">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="24be4-120">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)

