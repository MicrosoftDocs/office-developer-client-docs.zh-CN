---
title: ISocialProviderSocialNetworkIcon
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8b51675f-77b7-4df0-8496-b1e8958c6544
description: 返回表示图标的社交网络的字节数组。
ms.openlocfilehash: b86a2d1c14c444ba79db495a3795dc61b1fe3660
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779351"
---
# <a name="isocialprovidersocialnetworkicon"></a><span data-ttu-id="48e74-103">ISocialProvider::SocialNetworkIcon</span><span class="sxs-lookup"><span data-stu-id="48e74-103">ISocialProvider::SocialNetworkIcon</span></span>

<span data-ttu-id="48e74-104">返回表示图标的社交网络的字节数组。</span><span class="sxs-lookup"><span data-stu-id="48e74-104">Returns an array of bytes that represents the icon for the social network.</span></span> 
  
```cpp
[propget] HRESULT _stdcall SocialNetworkIcon([out, retval] SAFEARRAY(unsigned char)* networkIcon);
```

## <a name="property-value"></a><span data-ttu-id="48e74-105">属性值</span><span class="sxs-lookup"><span data-stu-id="48e74-105">Property value</span></span>

<span data-ttu-id="48e74-106">一个指向指定包含图标的社交网络的字节数组的结构。</span><span class="sxs-lookup"><span data-stu-id="48e74-106">A pointer to a structure that specifies an array of bytes that contains the icon for the social network.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="48e74-107">说明</span><span class="sxs-lookup"><span data-stu-id="48e74-107">Remarks</span></span>

<span data-ttu-id="48e74-108">支持的图片资源是.bmp、.jpeg 和.png 格式。</span><span class="sxs-lookup"><span data-stu-id="48e74-108">The supported picture resources are .bmp, .jpeg, and .png formats.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="48e74-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48e74-109">See also</span></span>

- [<span data-ttu-id="48e74-110">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="48e74-110">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

