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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: adf9b28e941e9ead9b83660f58701f13f35cabc7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775743"
---
# <a name="imapiviewadvisesinkonnewmessage"></a><span data-ttu-id="19df6-103">IMAPIViewAdviseSink::OnNewMessage</span><span class="sxs-lookup"><span data-stu-id="19df6-103">IMAPIViewAdviseSink::OnNewMessage</span></span>

  
  
<span data-ttu-id="19df6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="19df6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="19df6-105">通知表单查看器的新的或现有邮件已加载的窗体。</span><span class="sxs-lookup"><span data-stu-id="19df6-105">Notifies the form viewer that a new or an existing message has been loaded in a form.</span></span>
  
```cpp
HRESULT OnNewMessage( void );
```

## <a name="parameters"></a><span data-ttu-id="19df6-106">参数</span><span class="sxs-lookup"><span data-stu-id="19df6-106">Parameters</span></span>

<span data-ttu-id="19df6-107">无</span><span class="sxs-lookup"><span data-stu-id="19df6-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="19df6-108">返回值</span><span class="sxs-lookup"><span data-stu-id="19df6-108">Return value</span></span>

<span data-ttu-id="19df6-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="19df6-109">S_OK</span></span> 
  
> <span data-ttu-id="19df6-110">通知已成功。</span><span class="sxs-lookup"><span data-stu-id="19df6-110">The notification succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="19df6-111">说明</span><span class="sxs-lookup"><span data-stu-id="19df6-111">Remarks</span></span>

<span data-ttu-id="19df6-112">表单对象调用**IMAPIViewAdviseSink::OnNewMessage**方法时使用的[IPersistMessage::InitNew](ipersistmessage-initnew.md)或[IPersistMessage::Load](ipersistmessage-load.md)方法的窗体加载一条消息。</span><span class="sxs-lookup"><span data-stu-id="19df6-112">Form objects call the **IMAPIViewAdviseSink::OnNewMessage** method whenever a message is loaded in a form using either the [IPersistMessage::InitNew](ipersistmessage-initnew.md) or [IPersistMessage::Load](ipersistmessage-load.md) method.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="19df6-113">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="19df6-113">Notes to implementers</span></span>

<span data-ttu-id="19df6-114">释放您指向活动窗体对象，因为它不再指向以前已查看您查看器的邮件。</span><span class="sxs-lookup"><span data-stu-id="19df6-114">Release your active pointer to the form object because it no longer points to the message your viewer was formerly viewing.</span></span> 
  
<span data-ttu-id="19df6-115">有关窗体通知的详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="19df6-115">For more information about form notifications, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="19df6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19df6-116">See also</span></span>



[<span data-ttu-id="19df6-117">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="19df6-117">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)
  
[<span data-ttu-id="19df6-118">IPersistMessage::InitNew</span><span class="sxs-lookup"><span data-stu-id="19df6-118">IPersistMessage::InitNew</span></span>](ipersistmessage-initnew.md)
  
[<span data-ttu-id="19df6-119">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="19df6-119">IPersistMessage::Load</span></span>](ipersistmessage-load.md)
  
[<span data-ttu-id="19df6-120">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="19df6-120">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)

