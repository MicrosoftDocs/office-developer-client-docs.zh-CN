---
title: IMAPIViewAdviseSinkOnShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewAdviseSink.OnShutdown
api_type:
- COM
ms.assetid: c9c3aecf-5e4b-407a-8ea1-6211b4c6e0a5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f49ea23ed7fef91bcb360483611af2ee60429934
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592967"
---
# <a name="imapiviewadvisesinkonshutdown"></a><span data-ttu-id="bf26c-103">IMAPIViewAdviseSink::OnShutdown</span><span class="sxs-lookup"><span data-stu-id="bf26c-103">IMAPIViewAdviseSink::OnShutdown</span></span>

  
  
<span data-ttu-id="bf26c-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bf26c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bf26c-105">通知表单查看器正在关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="bf26c-105">Notifies the form viewer that a form is being closed.</span></span>
  
```cpp
HRESULT OnShutdown( void );
```

## <a name="parameters"></a><span data-ttu-id="bf26c-106">参数</span><span class="sxs-lookup"><span data-stu-id="bf26c-106">Parameters</span></span>

<span data-ttu-id="bf26c-107">无</span><span class="sxs-lookup"><span data-stu-id="bf26c-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="bf26c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="bf26c-108">Return value</span></span>

<span data-ttu-id="bf26c-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="bf26c-109">S_OK</span></span> 
  
> <span data-ttu-id="bf26c-110">通知已成功。</span><span class="sxs-lookup"><span data-stu-id="bf26c-110">The notification succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bf26c-111">注解</span><span class="sxs-lookup"><span data-stu-id="bf26c-111">Remarks</span></span>

<span data-ttu-id="bf26c-112">有关窗体通知的详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="bf26c-112">For more information about form notifications, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bf26c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf26c-113">See also</span></span>



[<span data-ttu-id="bf26c-114">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bf26c-114">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)
