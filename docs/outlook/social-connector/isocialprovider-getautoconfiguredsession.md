---
title: ISocialProviderGetAutoConfiguredSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d8d41ced-c2bb-482e-b0bc-1b46c82121bd
description: 获取自动配置的 ISocialSession 界面。
ms.openlocfilehash: 7108a7e42e9b54e069d8d420283c1ebad3367830
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779243"
---
# <a name="isocialprovidergetautoconfiguredsession"></a><span data-ttu-id="4e429-103">ISocialProvider::GetAutoConfiguredSession</span><span class="sxs-lookup"><span data-stu-id="4e429-103">ISocialProvider::GetAutoConfiguredSession</span></span>

<span data-ttu-id="4e429-104">获取自动配置的 [ISocialSession](isocialsessioniunknown.md) 界面。</span><span class="sxs-lookup"><span data-stu-id="4e429-104">Gets an automatically configured [ISocialSession](isocialsessioniunknown.md) interface.</span></span> 
  
```cpp
HRESULT _stdcall GetAutoConfiguredSession([out, retval] ISocialSession** session);
```

## <a name="parameters"></a><span data-ttu-id="4e429-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e429-105">Parameters</span></span>

<span data-ttu-id="4e429-106">_Session_</span><span class="sxs-lookup"><span data-stu-id="4e429-106">_Session_</span></span>
  
> <span data-ttu-id="4e429-107">[out] **ISocialSession** 界面。</span><span class="sxs-lookup"><span data-stu-id="4e429-107">[out] An **ISocialSession** interface.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="4e429-108">说明</span><span class="sxs-lookup"><span data-stu-id="4e429-108">Remarks</span></span>

<span data-ttu-id="4e429-109">返回的 **ISocialSession** 界面会根据特定于提供程序的方法自动登录到网络。</span><span class="sxs-lookup"><span data-stu-id="4e429-109">The returned **ISocialSession** interface is automatically logged on to the network, based on a method that is specific to the provider.</span></span> 
  
<span data-ttu-id="4e429-110">如果社交网络不支持自动配置，提供程序应返回 OSC_E_NOT_IMPLEMENTED 错误。</span><span class="sxs-lookup"><span data-stu-id="4e429-110">The provider should return the OSC_E_NOT_IMPLEMENTED error if the social network does not support automatic configuration.</span></span> <span data-ttu-id="4e429-111">有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="4e429-111">For information about error codes, see [Outlook Social Connector Provider Error Codes](outlook-social-connector-provider-error-codes.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4e429-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e429-112">See also</span></span>

- [<span data-ttu-id="4e429-113">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4e429-113">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

