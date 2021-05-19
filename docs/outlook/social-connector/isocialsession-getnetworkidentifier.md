---
title: ISocialSessionGetNetworkIdentifier
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 534e404f-54c6-4d2b-a8d0-d2ee990a972f
description: 获取一个字符串，该字符串代表给定社交网络连接的唯一社交网络标识符。
ms.openlocfilehash: 3051abd6dcccec878e8c53332980731772d543eb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433274"
---
# <a name="isocialsessiongetnetworkidentifier"></a><span data-ttu-id="c95ea-103">ISocialSession::GetNetworkIdentifier</span><span class="sxs-lookup"><span data-stu-id="c95ea-103">ISocialSession::GetNetworkIdentifier</span></span>

<span data-ttu-id="c95ea-104">获取一个字符串，该字符串代表给定社交网络连接的唯一社交网络标识符。</span><span class="sxs-lookup"><span data-stu-id="c95ea-104">Gets a string that represents a unique social network identifier for a given social network connection.</span></span> 
  
```cpp
HRESULT _stdcall GetNetworkIdentifier([out, retval] BSTR* networkIdentifier);
```

## <a name="parameters"></a><span data-ttu-id="c95ea-105">参数</span><span class="sxs-lookup"><span data-stu-id="c95ea-105">Parameters</span></span>

<span data-ttu-id="c95ea-106">_networkIdentifier_</span><span class="sxs-lookup"><span data-stu-id="c95ea-106">_networkIdentifier_</span></span>
  
> <span data-ttu-id="c95ea-107">[out]包含唯一社交网络标识符的字符串。</span><span class="sxs-lookup"><span data-stu-id="c95ea-107">[out] A string that contains a unique social network identifier.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c95ea-108">备注</span><span class="sxs-lookup"><span data-stu-id="c95ea-108">Remarks</span></span>

<span data-ttu-id="c95ea-109">唯一网络标识符是标识 OSC Outlook社交网络 (连接器) 连接器的字符串。</span><span class="sxs-lookup"><span data-stu-id="c95ea-109">A unique network identifier is a string that identifies the Outlook Social Connector (OSC) provider social network.</span></span> <span data-ttu-id="c95ea-110">此方法还可以返回E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="c95ea-110">This method can also return E_NOTIMPL.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c95ea-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c95ea-111">See also</span></span>

- [<span data-ttu-id="c95ea-112">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c95ea-112">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

