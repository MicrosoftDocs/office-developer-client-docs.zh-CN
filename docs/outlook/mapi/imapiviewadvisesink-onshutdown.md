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
ms.openlocfilehash: 2a09731dbd0ba2c5d6c1055a7c5ed11097c5ef27
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775731"
---
# <a name="imapiviewadvisesinkonshutdown"></a><span data-ttu-id="584c3-103">IMAPIViewAdviseSink::OnShutdown</span><span class="sxs-lookup"><span data-stu-id="584c3-103">IMAPIViewAdviseSink::OnShutdown</span></span>

  
  
<span data-ttu-id="584c3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="584c3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="584c3-105">通知表单查看器正在关闭窗体。</span><span class="sxs-lookup"><span data-stu-id="584c3-105">Notifies the form viewer that a form is being closed.</span></span>
  
```cpp
HRESULT OnShutdown( void );
```

## <a name="parameters"></a><span data-ttu-id="584c3-106">参数</span><span class="sxs-lookup"><span data-stu-id="584c3-106">Parameters</span></span>

<span data-ttu-id="584c3-107">无</span><span class="sxs-lookup"><span data-stu-id="584c3-107">None</span></span>
  
## <a name="return-value"></a><span data-ttu-id="584c3-108">返回值</span><span class="sxs-lookup"><span data-stu-id="584c3-108">Return value</span></span>

<span data-ttu-id="584c3-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="584c3-109">S_OK</span></span> 
  
> <span data-ttu-id="584c3-110">通知已成功。</span><span class="sxs-lookup"><span data-stu-id="584c3-110">The notification succeeded.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="584c3-111">说明</span><span class="sxs-lookup"><span data-stu-id="584c3-111">Remarks</span></span>

<span data-ttu-id="584c3-112">有关窗体通知的详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="584c3-112">For more information about form notifications, see [Sending and Receiving Form Notifications](sending-and-receiving-form-notifications.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="584c3-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="584c3-113">See also</span></span>



[<span data-ttu-id="584c3-114">IMAPIViewAdviseSink : IUnknown</span><span class="sxs-lookup"><span data-stu-id="584c3-114">IMAPIViewAdviseSink : IUnknown</span></span>](imapiviewadvisesinkiunknown.md)

