---
title: ISocialProviderSocialNetworkIcon
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8b51675f-77b7-4df0-8496-b1e8958c6544
description: 返回表示社交网络图标的字节数组。
ms.openlocfilehash: c63d9996d4478c8ce7e46210aae34791bcfe9222
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438685"
---
# <a name="isocialprovidersocialnetworkicon"></a><span data-ttu-id="4ceaa-103">ISocialProvider::SocialNetworkIcon</span><span class="sxs-lookup"><span data-stu-id="4ceaa-103">ISocialProvider::SocialNetworkIcon</span></span>

<span data-ttu-id="4ceaa-104">返回表示社交网络图标的字节数组。</span><span class="sxs-lookup"><span data-stu-id="4ceaa-104">Returns an array of bytes that represents the icon for the social network.</span></span> 
  
```cpp
[propget] HRESULT _stdcall SocialNetworkIcon([out, retval] SAFEARRAY(unsigned char)* networkIcon);
```

## <a name="property-value"></a><span data-ttu-id="4ceaa-105">属性值</span><span class="sxs-lookup"><span data-stu-id="4ceaa-105">Property value</span></span>

<span data-ttu-id="4ceaa-106">指向结构的指针, 该结构指定包含社交网络图标的字节数组。</span><span class="sxs-lookup"><span data-stu-id="4ceaa-106">A pointer to a structure that specifies an array of bytes that contains the icon for the social network.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4ceaa-107">说明</span><span class="sxs-lookup"><span data-stu-id="4ceaa-107">Remarks</span></span>

<span data-ttu-id="4ceaa-108">支持的图片资源为 .bmp、jpeg 和 .png 格式。</span><span class="sxs-lookup"><span data-stu-id="4ceaa-108">The supported picture resources are .bmp, .jpeg, and .png formats.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4ceaa-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ceaa-109">See also</span></span>

- [<span data-ttu-id="4ceaa-110">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4ceaa-110">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

