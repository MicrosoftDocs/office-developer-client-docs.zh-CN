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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a2da3f6851e45a70dcd4604396a85430c539a830
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428576"
---
# <a name="imapisecuremessagegetbasemessage"></a><span data-ttu-id="925dc-103">IMAPISecureMessage::GetBaseMessage</span><span class="sxs-lookup"><span data-stu-id="925dc-103">IMAPISecureMessage::GetBaseMessage</span></span>

  
  
<span data-ttu-id="925dc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="925dc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="925dc-105">检索此[IMAPISecureMessage ： IUnknown](imapisecuremessageiunknown.md)正在封装的基础[IMessage ： IMAPIProp。](imessageimapiprop.md)</span><span class="sxs-lookup"><span data-stu-id="925dc-105">Retrieves the underlying [IMessage : IMAPIProp](imessageimapiprop.md) that this [IMAPISecureMessage : IUnknown](imapisecuremessageiunknown.md) is encapsulating.</span></span> 
  
```cpp
HRESULT GetBaseMessage(
  LPMMESSAGE FAR * ppmsg
);
```

## <a name="parameters"></a><span data-ttu-id="925dc-106">参数</span><span class="sxs-lookup"><span data-stu-id="925dc-106">Parameters</span></span>

 <span data-ttu-id="925dc-107">_ppmsg_</span><span class="sxs-lookup"><span data-stu-id="925dc-107">_ppmsg_</span></span>
  
> <span data-ttu-id="925dc-108">[out]安全邮件对象。</span><span class="sxs-lookup"><span data-stu-id="925dc-108">[out] A secure message object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="925dc-109">返回值</span><span class="sxs-lookup"><span data-stu-id="925dc-109">Return value</span></span>

<span data-ttu-id="925dc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="925dc-110">S_OK</span></span>
  
> <span data-ttu-id="925dc-111">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="925dc-111">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="925dc-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="925dc-112">See also</span></span>



[<span data-ttu-id="925dc-113">IMAPISecureMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="925dc-113">IMAPISecureMessage : IUnknown</span></span>](imapisecuremessageiunknown.md)
  
[<span data-ttu-id="925dc-114">IMessage : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="925dc-114">IMessage : IMAPIProp</span></span>](imessageimapiprop.md)

