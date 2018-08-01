---
title: ISocialProviderVersion
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: dfc92878-ab8b-4721-aee8-997c56a8e45b
description: 返回一个字符串，表示为此社交网络提供程序的版本号。
ms.openlocfilehash: 5c82df2dc4c052b1a06bcecb16defbb4dee38b18
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779226"
---
# <a name="isocialproviderversion"></a><span data-ttu-id="70a88-103">ISocialProvider::Version</span><span class="sxs-lookup"><span data-stu-id="70a88-103">ISocialProvider::Version</span></span>

<span data-ttu-id="70a88-104">返回一个字符串，表示为此社交网络提供程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="70a88-104">Returns a string that represents the version number of the provider for this social network.</span></span> 
  
```cpp
[propget] HRESULT _stdcall Version([out, retval] BSTR* Version);
```

## <a name="property-value"></a><span data-ttu-id="70a88-105">属性值</span><span class="sxs-lookup"><span data-stu-id="70a88-105">Property value</span></span>

<span data-ttu-id="70a88-106">一个字符串，包含提供程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="70a88-106">A string that contains the version number of the provider.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="70a88-107">说明</span><span class="sxs-lookup"><span data-stu-id="70a88-107">Remarks</span></span>

<span data-ttu-id="70a88-108">版本字符串应使用_MajorVersion_。</span><span class="sxs-lookup"><span data-stu-id="70a88-108">The version string should use the  _MajorVersion_.</span></span> <span data-ttu-id="70a88-109">_MinorVersion_格式 (例如，1.4730)。</span><span class="sxs-lookup"><span data-stu-id="70a88-109">_MinorVersion_ format (for example, 1.4730).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="70a88-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70a88-110">See also</span></span>

- [<span data-ttu-id="70a88-111">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="70a88-111">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

