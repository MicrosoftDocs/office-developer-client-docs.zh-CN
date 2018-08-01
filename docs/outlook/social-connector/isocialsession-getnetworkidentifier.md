---
title: ISocialSessionGetNetworkIdentifier
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 534e404f-54c6-4d2b-a8d0-d2ee990a972f
description: 获取一个字符串，表示对于给定的社交网络连接的唯一的社交网络标识符。
ms.openlocfilehash: eb618ba8e8bb37278c1fdb09d984fba141a9d686
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779355"
---
# <a name="isocialsessiongetnetworkidentifier"></a><span data-ttu-id="59013-103">ISocialSession::GetNetworkIdentifier</span><span class="sxs-lookup"><span data-stu-id="59013-103">ISocialSession::GetNetworkIdentifier</span></span>

<span data-ttu-id="59013-104">获取一个字符串，表示对于给定的社交网络连接的唯一的社交网络标识符。</span><span class="sxs-lookup"><span data-stu-id="59013-104">Gets a string that represents a unique social network identifier for a given social network connection.</span></span> 
  
```cpp
HRESULT _stdcall GetNetworkIdentifier([out, retval] BSTR* networkIdentifier);
```

## <a name="parameters"></a><span data-ttu-id="59013-105">参数</span><span class="sxs-lookup"><span data-stu-id="59013-105">Parameters</span></span>

<span data-ttu-id="59013-106">_networkIdentifier_</span><span class="sxs-lookup"><span data-stu-id="59013-106">_networkIdentifier_</span></span>
  
> <span data-ttu-id="59013-107">[输出]一个字符串，包含一个唯一的社交网络的标识符。</span><span class="sxs-lookup"><span data-stu-id="59013-107">[out] A string that contains a unique social network identifier.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="59013-108">说明</span><span class="sxs-lookup"><span data-stu-id="59013-108">Remarks</span></span>

<span data-ttu-id="59013-109">一个唯一的网络标识符是一个字符串，标识 Outlook Social Connector (OSC) 提供程序社交网络。</span><span class="sxs-lookup"><span data-stu-id="59013-109">A unique network identifier is a string that identifies the Outlook Social Connector (OSC) provider social network.</span></span> <span data-ttu-id="59013-110">此方法还可以返回 E_NOTIMPL。</span><span class="sxs-lookup"><span data-stu-id="59013-110">This method can also return E_NOTIMPL.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="59013-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59013-111">See also</span></span>

- [<span data-ttu-id="59013-112">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="59013-112">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

