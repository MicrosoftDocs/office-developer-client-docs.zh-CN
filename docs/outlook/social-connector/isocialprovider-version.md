---
title: ISocialProviderVersion
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: dfc92878-ab8b-4721-aee8-997c56a8e45b
description: 返回一个 string 类型的值, 该值代表此社交网络提供程序的版本号。
ms.openlocfilehash: 0749b8fb83a11328233442b79e1f9de50076effe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438272"
---
# <a name="isocialproviderversion"></a><span data-ttu-id="786f0-103">ISocialProvider::Version</span><span class="sxs-lookup"><span data-stu-id="786f0-103">ISocialProvider::Version</span></span>

<span data-ttu-id="786f0-104">返回一个 string 类型的值, 该值代表此社交网络提供程序的版本号。</span><span class="sxs-lookup"><span data-stu-id="786f0-104">Returns a string that represents the version number of the provider for this social network.</span></span> 
  
```cpp
[propget] HRESULT _stdcall Version([out, retval] BSTR* Version);
```

## <a name="property-value"></a><span data-ttu-id="786f0-105">属性值</span><span class="sxs-lookup"><span data-stu-id="786f0-105">Property value</span></span>

<span data-ttu-id="786f0-106">一个包含提供程序版本号的字符串。</span><span class="sxs-lookup"><span data-stu-id="786f0-106">A string that contains the version number of the provider.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="786f0-107">说明</span><span class="sxs-lookup"><span data-stu-id="786f0-107">Remarks</span></span>

<span data-ttu-id="786f0-108">版本字符串应使用_MajorVersion_。</span><span class="sxs-lookup"><span data-stu-id="786f0-108">The version string should use the  _MajorVersion_.</span></span> <span data-ttu-id="786f0-109">_MinorVersion_格式 (例如, 1.4730)。</span><span class="sxs-lookup"><span data-stu-id="786f0-109">_MinorVersion_ format (for example, 1.4730).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="786f0-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="786f0-110">See also</span></span>

- [<span data-ttu-id="786f0-111">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="786f0-111">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

