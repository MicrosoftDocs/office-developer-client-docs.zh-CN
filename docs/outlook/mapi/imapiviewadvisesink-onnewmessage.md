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
ms.openlocfilehash: bb373e4b666f44c432ac1b04c0449eb7f0408a19
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592932"
---
# <a name="imapiviewadvisesinkonnewmessage"></a><span data-ttu-id="d883e-103">IMAPIViewAdviseSink::OnNewMessage</span><span class="sxs-lookup"><span data-stu-id="d883e-103">IMAPIViewAdviseSink::OnNewMessage</span></span>

  
  
<span data-ttu-id="d883e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d883e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d883e-105">通知表单查看器的新的或现有邮件已加载的窗体。</span><span class="sxs-lookup"><span data-stu-id="d883e-105">Notifies the form viewer that a new or an existing message has been loaded in a form.</span></span>
  
```cpp
HRESULT OnNewMessage( void );
```

## <a name="parameters"></a><span data-ttu-id="d883e-106">参数</span><span class="sxs-lookup"><span data-stu-id="d883e-106">Parameters</span></span>

<span data-ttu-id="d883e-107">无</span><span class="sxs-lookup"><span data-stu-id="d883e-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="d883e-108">返回值</span><span class="sxs-lookup"><span data-stu-id="d883e-108">Return value</span></span>

<span data-ttu-id="d883e-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="d883e-109">S_OK</span></span> 
  
> <span data-ttu-id="d883e-110">通知已成功。</span><span class="sxs-lookup"><span data-stu-id="d883e-110">The notification succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d883e-111">注解</span><span class="sxs-lookup"><span data-stu-id="d883e-111">Remarks</span></span>

<span data-ttu-id="d883e-112">表单对象调用**IMAPIViewAdviseSink::OnNewMessage**方法时使用的[IPersistMessage::InitNew](ipersistmessage-initnew.md)或[IPersistMessage::Load](ipersistmessage-load.md)方法的窗体加载一条消息。</span><span class="sxs-lookup"><span data-stu-id="d883e-112">Form objects call the **IMAPIViewAdviseSink::OnNewMessage** method whenever a message is loaded in a form using either the [IPersistMessage::InitNew](ipersistmessage-initnew.md) or [IPersistMessage::Load](ipersistmessage-load.md) method.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="d883e-113">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="d883e-113">Notes to implementers</span></span>

<span data-ttu-id="d883e-114">释放您指向活动窗体对象，因为它不再指向以前已查看您查看器的邮件。</span><span class="sxs-lookup"><span data-stu-id="d883e-114">Release your active pointer to the form object because it no longer points to the message your viewer was formerly viewing.</span></span> 
  
<span data-ttu-id="d883e-115">有关窗体通知的详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="d883e-115">For more information about form notifications, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d883e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d883e-116">See also</span></span>



[<span data-ttu-id="d883e-117">IMAPIForm : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d883e-117">IMAPIForm : IUnknown</span></span>](imapiformiunknown.md)
  
[<span data-ttu-id="d883e-118">IPersistMessage::InitNew</span><span class="sxs-lookup"><span data-stu-id="d883e-118">IPersistMessage::InitNew</span></span>](ipersistmessage-initnew.md)
  
[<span data-ttu-id="d883e-119">IPersistMessage::Load</span><span class="sxs-lookup"><span data-stu-id="d883e-119">IPersistMessage::Load</span></span>](ipersistmessage-load.md)
  
[<span data-ttu-id="d883e-120">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d883e-120">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)

