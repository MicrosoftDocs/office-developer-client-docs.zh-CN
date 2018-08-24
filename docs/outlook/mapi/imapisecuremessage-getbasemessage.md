---
title: IMAPISecureMessageGetBaseMessage
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISecureMessage.GetBaseMessage
api_type:
- COM
ms.assetid: 573f40c5-e0d2-4281-8c22-10a1ae1f0dee
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d246fc0cfc60d0a2b9ff12ee70eae2366cf9b53a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594836"
---
# <a name="imapisecuremessagegetbasemessage"></a><span data-ttu-id="69adc-103">IMAPISecureMessage::GetBaseMessage</span><span class="sxs-lookup"><span data-stu-id="69adc-103">IMAPISecureMessage::GetBaseMessage</span></span>

  
  
<span data-ttu-id="69adc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="69adc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="69adc-105">检索基础[IMessage: IMAPIProp](imessageimapiprop.md)这[IMAPISecureMessage: IUnknown](imapisecuremessageiunknown.md)封装。</span><span class="sxs-lookup"><span data-stu-id="69adc-105">Retrieves the underlying [IMessage : IMAPIProp](imessageimapiprop.md) that this [IMAPISecureMessage : IUnknown](imapisecuremessageiunknown.md) is encapsulating.</span></span> 
  
```cpp
HRESULT GetBaseMessage(
  LPMMESSAGE FAR * ppmsg
);
```

## <a name="parameters"></a><span data-ttu-id="69adc-106">参数</span><span class="sxs-lookup"><span data-stu-id="69adc-106">Parameters</span></span>

 <span data-ttu-id="69adc-107">_ppmsg_</span><span class="sxs-lookup"><span data-stu-id="69adc-107">_ppmsg_</span></span>
  
> <span data-ttu-id="69adc-108">[输出]一个安全邮件对象。</span><span class="sxs-lookup"><span data-stu-id="69adc-108">[out] A secure message object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="69adc-109">返回值</span><span class="sxs-lookup"><span data-stu-id="69adc-109">Return value</span></span>

<span data-ttu-id="69adc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="69adc-110">S_OK</span></span>
  
> <span data-ttu-id="69adc-111">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="69adc-111">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="69adc-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69adc-112">See also</span></span>



[<span data-ttu-id="69adc-113">IMAPISecureMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="69adc-113">IMAPISecureMessage : IUnknown</span></span>](imapisecuremessageiunknown.md)
  
[<span data-ttu-id="69adc-114">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="69adc-114">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)

